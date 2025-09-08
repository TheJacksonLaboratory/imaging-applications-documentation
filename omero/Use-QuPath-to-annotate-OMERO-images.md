## Install QuPath

If you already have QuPath installed, check your version by opening QuPath and going to `Help > System Info`. If the version is not 0.6.0 or newer, then we recommend downloading the latest QuPath.

If you do not already have QuPath installed, download QuPath from https://qupath.github.io/ and follow the installation instructions to download the correct one for your operating system.

## Installing the QuPath OMERO extension

Once you have QuPath 0.6.0 or newer, you can install the QuPath OMERO extension using the built in Extensions Manager:  

1. To access the Extensions Manager, you can follow the prompt at startup, or use the menu: `Extensions > Manage extensions`
2. In the Extensions Manager you should see "QuPath OMERO extension", labeled with a ⭐️ on the left.
3. To install this extension, click the green (+) symbol.  
4. In the "Install extension" window that pops up, make sure that the box "Install optional dependencies" is checked.  
 **Important:** Ensure you have QuPath OMERO extension **v0.1.2** or newer! For more information, as well as details about updating on *Windows*, please see [our documentation](https://jacksonlaboratory.sharepoint.com/sites/ResearchIT/SitePages/Upgrade-your-QuPath-OMERO-Extension!.aspx).

## Create a project in QuPath (recommended)
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
1. Browse OMERO images using the group and data owner dropdowns above the browser panel Select a project, dataset, or image.

    ![Pop-up window for browsing OMERO datasets](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/qupath-omero-browse.png?raw=true)

    🛑 Note the dropdown next to the label "Pixel API". There are two main ways to access OMERO images:  
    - OMERO.web API 
        - fast access to JPEG-compressed RGB image (same as OMERO web)
        - ✅ best for viewing and annotating images quickly
        - ❌ not recommended for quantitative analysis involving pixel values 
    - OMERO Ice API
        - access to raw pixel values via OMERO.server
        - ✅ necessary for quantitative analysis of pixel values
        - ❌ slower to view images
    
    Choose the option that best suites your needs.
2. Once you have selected an image and chosen the Pixel API, click the button at the bottom of the window to "Import ___ to QuPath".    

3. When opening an image for the first time (double click), QuPath may ask for confirmation of the image type. Apply the correct image type for the optimal viewing experience.

    ![Pop-up window for QuPath setting image type](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/qupath_set_type.png?raw=true)

(Optional) To improve performance, you may consider increasing the tile cache QuPath uses to reduce how often data needs to be reloaded from OMERO. You can do this in the Preferences. Go to the `Edit menu > Preferences` and then click the `General` tab and look for `Percentage memory for tile cache`. The default is 25%, but you can increase this to 50% or even higher, depending how much memory your computer has. You can monitor memory usage and number of cached tiles using the `View menu > Memory monitor`, where you can also clear the tile cache.

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