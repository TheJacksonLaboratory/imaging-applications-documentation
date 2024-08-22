## Connect Fiji to OMERO
1. Start the Fiji app and use the OMERO plugin to browse data in OMERO i.e. *Plugins > OMERO > Connect To OMERO*. If you do not have the plugin, follow these instructions for [Installing the OMERO plugin for Fiji/ImageJ](https://omero-guides.readthedocs.io/en/latest/fiji/docs/installation.html)

2. In the OMERO login dialog, click the wrench icon and then add the server address (ctomero01lp.jax.org – NOTE THIS IS A DIFFERENT ADDRESS!) in the dialog. Click Apply. Now, log in with your JAX shortname and password (same as the webpage).
    ![Screenshot of OMERO insight login and server selection from imageJ](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_fiji_1.png?raw=true)

3. Find and open any image (double-click the thumbnail) to make sure things work!

## Open image in Fiji/ImageJ
Double click the image thumbnail. Click OK on the popup window. Wait for a new image window to pop up - it can take a while.
![Screenshot of OMERO connection through Fiji](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_fiji_2.png?raw=true)

## Example image segmentation workflow in Fiji
Before starting the image segmentation workflow, check that *Process > Binary > Options* has *Black background* checked.

1. Select the image window, then click *Image > Adjust > Threshold*.
    ![Fiji menu selecting Image > Adjust > Threshold](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_fiji_3.png?raw=true)

2. In the first Threshold window, click *Apply*. Set the following parameters:

    ```
    Method: Default, Background: Dark, Calculate threshold for each Image and Black background (of binary masks).
    ```

    Click OK and close the Threshold dialog if you want.
    ![Fiji threshold window](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_fiji_4.png?raw=true)

3.  In the menu, click *Analyze > Analyze Particles*. In the following dialog, select these parameters:
    ```
    Size 50-Infinity, Show: Outlines, Display Results, Clear Results, Summarize, Add to manager
    ```

    Click OK. Click Yes on the confirmation dialog.
    ![Fiji Analyze Particles dialog](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_fiji_5.png?raw=true)

4. Many windows will appear, including ROIs, Results table, and the mask timelapse with outlines:
    ![Fiji many windows results of Analyze Particles](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_fiji_6.png?raw=true)

5. Select the *Results* table and in the menu go to *Results > Distribution*. Click OK in the pop up.

## Save results back to OMERO
1. Select original image (now also showing ROIs in yellow). It might be hidden behind other windows. Select *Plugins > OMERO > Save ROIs to OMERO*. Save both ROIs and Measurements and give the file a name. This will attach the results as a CSV attachment (to open for example in Excel) to the image in OMERO.
    ![Menu showing saving ROI image back to Omero Dialog for saving ImageJ results back to Omero, with both ROI and Measurements checked](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_fiji_7.png?raw=true)

2. Select the image with outlines named “Drawing of...”. *Select File > Save As > Tiff...* and give it a meaningful name (outlines.tiff, for example).
    ![Menu for saving ROI outlines as Tiff](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_fiji_8.png?raw=true)

3. Now save the created images back to OMERO. select *Plugins > OMERO > Save Image(s) to OMERO*. Select in which project and dataset the new images are going to be imported into on the left-hand side. When you are done selecting project and dataset, check Add Images from all image windows. Click Add to Queue then Import.
    ![ImageJ import window for Omero](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_fiji_9.png?raw=true)

## Viewing results in OMERO
You will see the new result images in the OMERO web client, along with an attachment for the ROI measurements:
![Omero webclient showing results imported from imageJ](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_fiji_10.png?raw=true)

The ROIs outline image and other results can also be used in OMERO.figure, just like any other image. For more information on using OMERO.figure, see Creating figures using OMERO.figure (video).
![Omero figure using results from ImageJ](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_fiji_10.png?raw=true)