## Overview

JAX uses a special workflow for importing data into OMERO. When you need to have data imported, you will place your data into a specific folder, and the OMERO admins do the import. This is both due to an established minimum requirement for metadata and due to specificities on how we manage storage for the OMERO server.

## Instructions

### Option 1: Use Globus
Use Globus to facilitate data transfers between many of the data storage locations at JAX, including Sumner, the scientific services delivery folders, Box, OneDrive, and the OMERO import folders.

1. Follow the [instructions for using Globus](https://jacksonlaboratory.sharepoint.com/sites/ResearchIT/SitePages/Globus-Data-Transfers.aspx) to set up a data transfer from any other collection to `omero_drop/dropbox` in the `The Jackson Laboratory Scientific Services` collection. Before initating a data transfer, read the **Import data** section below for details on how to structure your import folder.
    ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/globus_omero_import.png?raw=true)


### Option 2: Mount network drive locally
Skip if using Globus

1. Map the path \\jax.org\jax\omero-drop\dropbox on your computer. On Windows, use map network drive from This PC with this path; on Mac, open Finder, then click Go -> Connect to server and use smb://jax.org/jax/omero-drop/dropbox. 
    ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_import_1.png?raw=true)

    ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_import_2.png?raw=true)

    ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_import_3.png?raw=true)

### Import data

1. Create a folder with a name following the convention `shortname_YYYYMMDD` (so, for me on 01/18/2025, that would be `govekk_20250118`). Place your image files directly in this folder, do not use subfolders (unless the images themselves use subfolders, such as VSIs).

2. Fill out [this spreadsheet template](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/raw/main/omero/OMERO_submission_form.xlsx). Add one row in the "Submission Form" sheet per file you are uploading, but otherwise do not edit the format of that sheet.
    - **Metadata**: Each column past `filename, project, dataset` will be uploaded as a key-value pair in OMERO. This is the easiest way for you to bulk annotate your images with experimental metadata, so please add as much metadata as you want. 
    - **Filenames**: File names in the spreadsheet must match filenames in your import folder, *including extensions*.
    - **Username and group**: `OMERO group` must match your OMERO group name exactly (case-sensitive), `OMERO user` must be a JAX username in that group (all lowercase)

    > IMPORTANT: if you are importing data into an OMERO project owned by a different user, you must use their username instead of your own in the import spreadsheet. This means the images will be owned by that user in OMERO. Otherwise you must use a different OMERO project for yourself.

3. Place the completed spreadsheet inside your `shortname_YYYYMMDD` folder

4. If your import is particularly large (>100 Gb), contains a new image file format, or you are otherwise unsure about the process, please email or slack message Kiya Govek or Peter Sobolewski. We will keep an eye out for your import to ensure the images make it into OMERO successfully.

