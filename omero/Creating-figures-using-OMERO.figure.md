## Overview
OMERO.figure is a tool for rapid figure creation using the image rendering and metadata capabilities of an OMERO server. Instead of having figure panels be static snapshots of your original image, with OMERO.figure each panel is effectively a multidimensional image viewer, allowing for zooming and panning, adjusting rendering settings and scrolling through Z-slices and time. 

In this article, we teach you how to create new panels, add new images to your figure, adjust their alignment and rendering settings, zoom levels and panning. We also show you how to add scalebars and labels based on OMERO metadata and how to save and export your figures when you are done.

## Open OMERO.figure
Select your image(s) and use the Open with button on the right panel to select OMERO.figure. Or, right click the image name(s) in the left panel and select Open With... > OMERO.figure.
![OMERO front page with Open with > OMERO.figure highlighted](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_figure_1.png?raw=true)

## Create a grid of image panels of different channels and time points
Select the image in OMERO.figure and copy-paste. OMERO.figure will automatically align the copy with the original image. Select the copy, then in the popup in the right go to the Preview tab. Click the green channel name to turn it off. 
![Screenshot of OMERO.figure showing two copies of the image, one showing both red and green channels and one showing only red.](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_figure_2.png?raw=true)

Now select both images and copy-paste two more times. OMERO.figure should automatically create a 3x2 grid of images. If original image is a time series, you can change which time point each column is showing. Select the two images in a column and move the T slider in the Preview tab.
![Screenshot of OMERO.figure where 6 copies of the image are organized by channel and time](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_figure_3.png?raw=true)

## Adjust image zoom and panning
Select all six images and move the Zoom slider in the Preview tab to zoom in all images equally. Click and drag the image in the Preview tab to center all images on the same point.
![Screenshot of OMERO.figure with zoom scroll highlighted](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_figure_4.png?raw=true)

## Add labels based on image metadata
OMERO.figure can retrieve information about images from Channel names, Time, or any Tags or Key-Value pairs (e.g. experiment information). Select the images to add labels to, then in the Labels tab use the Add Labels dropdown to select which information to use. Choose the location and color of the labels (in this case we are adding the Time to the upper left corner of the images in white). You can also choose to show scalebars, which will use the pixel dimensions defined in the image metadata.
![Screenshot of OMERO.figure where channel and time information have been added to images.](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_figure_5.png?raw=true)

## Save figure
Click Save to save your figure. To export your figure as PDF, click the Export PDF button at the top-right of the screen and wait for the PDF to be created on the server and the Download button to appear. Click to download the PDF and import to a PDF editor. You can post-process the PDF in Inkscape or Adobe Illustrator/Photoshop for example.
![Screenshot of OMERO.figure with Save and Export PDF buttons hightlighted](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_figure_6.png?raw=true)