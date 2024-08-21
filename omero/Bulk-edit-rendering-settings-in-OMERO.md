## Why might I need to bulk-edit rendering settings in OMERO

When OMERO imports an image, image rendering settings will be automatically set depending on image type. This is not always desirable behavior. For example, OMERO may render images such that the minimum and maximum pixel values are rendered at minimum and maximum levels on your display, when you may want to consider the full range of possible pixel values. This is especially problematic for RGB TIF images, where automatically setting the rendering for each color channel independently can lead to distorted colors and interfere with biological interpretation.

Fortunately, it is easy to correct OMERO's rendering settings using OMERO.web!

## Instructions

1. Navigate to a Dataset containing images with problematic rendering settings, then click on the "Preview" tab on the right panel.

    ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_render_1.png?raw=true)

2. Examine the rendering settings in the Preview Pane to identify the problem.

    ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_render_2.png?raw=true)

    In this example, we need all of the "Max" values to be set to 255 and "Min" values to be set to 0. For that, we can simply select "Full Range".

    ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_render_3.png?raw=true)
 
3. Click on the "Copy" button in the rendering settings panel. This will save your new rendering settings to your clipboard.

    ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_render_4.png?raw=true)

4. Select all of the images to which you want to apply your copied rendering settings, then right click, then click "Rendering Settings..." -> "Paste and Save"

    ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_render_5.png?raw=true)

5. If you are ready to apply the settings, click "OK" on the dialog box that appears

    ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_render_6.png?raw=true)

Now your rendering settings should be applied to all of the new images!
![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_render_7.png?raw=true)
