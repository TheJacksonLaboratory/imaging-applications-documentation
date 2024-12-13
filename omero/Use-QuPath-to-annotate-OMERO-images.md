This guide is intended for QuPath 0.5.0 and 0.5.1

## Install QuPath

If you already have QuPath installed, check your version by opening QuPath and going to `Help > System Info`. If the version is not 0.5.0 or 0.5.1, this guide has not been tested for your version of QuPath and some information in it may be incorrect. It is possible to install multiple versions of QuPath on the same computer, so you may wish to follow the below instructions to install one of the 0.5 versions.

If you do not already have QuPath installed, download QuPath from https://qupath.github.io/ and follow the installation instructions. If the text below the download button does not say "Release notes v0.5.1", click "all releases" below and scroll down to 0.5.1 to expand the `assets` and download the correct one for your operating system.

## Download OMERO extension for QuPath

Before choosing an extension, it is important to understand how images are accessed from OMERO. There are two main ways OMERO can share images with other viewers or analysis software:
- OMERO.web API 
    - fast access to JPEG-compressed RGB image 
    - ✅ best for viewing and annotating images quickly
    - ❌ not usable for quantitative analysis
- OMERO Ice API
    - access to raw pixel values via OMERO.server
    - ✅ necessary for quantitative analysis of pixel values
    - ❌ slower to view images, may require Java dependencies

Note: the OMERO.web API is also used by omeroweb.jax.org, so the image quality will be identical, meanwhile the OMERO Ice API is used by ezomero in Python.

There are three different OMERO extensions for QuPath, with different methods of accessing images:
- [qupath/qupath-extension-omero](https://github.com/qupath/qupath-extension-omero) (Recommended) ⭐️
    - current QuPath-supported extension
    - supports image access via both OMERO.web API and Ice API, defaulting to web
- [qupath/qupath-extension-omero-web](https://github.com/qupath/qupath-extension-omero-web)
    - Old QuPath-supported extension for accessing images using the OMERO.web API
    - May be deprecated in 2025
    - Some JAX users with certain special characters in their password have experienced issues authenticating using this extension
- [BIOP/qupath-extension-biop-omero](https://github.com/BIOP/qupath-extension-biop-omero)
    - Image access via OMERO Ice API only

These extensions are not interchangeable within a QuPath project - you will need to create a new project in QuPath if you want to switch extensions.

The following steps will use [qupath/qupath-extension-omero](https://github.com/qupath/qupath-extension-omero) using the OMERO.web API. To install the extension, download the `.jar` file from the `Assets` dropdown under [Releases](https://github.com/qupath/qupath-extension-omero/releases). Start QuPath and drag the `.jar` file into the QuPath main window.

## Create a project in QuPath
In order to import multiple images into QuPath or save your work, you will need a locally saved QuPath project. This will not download the OMERO images locally.
1. Click `Create project` in the QuPath window or in `File > Project... > Create project`
2. Create a new folder

## Connect QuPath to OMERO
1. Go to `Extensions > OMERO > Browse server... > New server...`. On a Mac, this will be in the upper toolbar of the screen. On Windows, the menu dropdowns will be part of the QuPath window.
    
    ![QuPath extensions dropdown](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/qupath-addserver-dropdown.png?raw=true)

2. Enter `https://omeroweb.jax.org` as the OMERO server URL.
    
    ![Pop-up window for entering OMERO url into QuPath extension](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/qupath-omero-url.png?raw=true)

3. Log in using your normal JAX username and password.

## Open OMERO image in QuPath
1. Browse OMERO images using the group and data owner dropdowns above the browser panel Select a project, dataset, or image and click the button at the bottom of the window to "Import ___ to QuPath".

    ![Pop-up window for browsing OMERO datasets](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/qupath-omero-browse.png?raw=true)

    🛑 Remember that with the `Pixel API: Web` setting, the image viewed in QuPath is a JPEG-compressed RGB version of the original image. DO NOT use this image for quantitative analysis of pixel values.

2. When opening an image for the first time (double click), QuPath may ask for confirmation of the image type. Apply the correct image type for the optimal viewing experience.

    ![Pop-up window for QuPath setting image type](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/qupath_set_type.png?raw=true)

## Add annotations in QuPath
1. Use the QuPath annotation tools to draw ROIs on the image. Find more information about using each tool in the [QuPath documentation](https://qupath.readthedocs.io/en/0.5/docs/starting/annotating.html).

    ![Annotation toolbar](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/qupath_annotation_tools.png?raw=true)

2. It is possible to create an ROI of a specific size using `Objects > Annotations > Specify annotation`. Toggle "Use μm" to switch between pixel and μm.

    ![Dropdown to open window to specify annotations](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/qupath_specify_anno_dropdown.png?raw=true)

    ![Pop-up window to specify annotations with use microns selected](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/qupath_specify_anno.png?raw=true)

3. With the Move icon ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/qupath_move.png?raw=true) selected in the menu, double click on an existing annotation to select it. Once annotation is highlighted in yellow with boxes, move it to desired location.

    ![QuPath window with annotation selected in yellow](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/qupath_anno_select.png?raw=true)

## Save annotations back to OMERO as ROIs
1. With the image open in QuPath, go to `Extensions > Send to OMERO > Send annotations`.

    ![QuPath dropdown for Send to OMERO](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/qupath_send_dropdown.png?raw=true)

2. In the pop-up window, unselect "Delete existing annotations" and "Delete existing measurements" to preserve previously created or imported ROIs in OMERO. Choose whether to send all annotations or only those selected in yellow using the dropdown. Click OK to create ROIs in OMERO for these annotations.

    ![QuPath pop-up window for sending annotations to OMERO](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/qupath_send_anno.png?raw=true)

The QuPath annotations will be created as ROIs in OMERO, which can be viewed in OMERO.iviewer. Minimal shape measurements for the annotations are added to the images in OMERO as CSV attachments if the measurements checkboxes are selected in the "Data to send" pop-up window.