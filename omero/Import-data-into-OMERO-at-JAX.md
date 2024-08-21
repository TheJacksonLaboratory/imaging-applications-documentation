## Overview

JAX uses a special workflow for importing data into OMERO. When you need to have data imported, you will place your data into a specific folder, and the OMERO admins do the import. This is both due to an established minimum requirement for metadata and due to specificities on how we manage storage for the OMERO server.

## Instructions

1. Map the path \\jax.org\jax\omero-drop\dropbox on your computer. On Windows, use map network drive from This PC with this path; on Mac, open Finder, then click Go -> Connect to server and use smb://jax.org/jax/omero-drop/dropbox. 
    ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_import_1.png?raw=true)

    ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_import_2.png?raw=true)

    ![](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/blob/main/omero/images/omero_import_3.png?raw=true)

2. Create a folder with a name following the convention shortname_YYYYMMDD (so, for me on 01/18/2021, that would be ratame_20210118). 

3. Place your data inside that folder, together with a copy of [this template](https://github.com/TheJacksonLaboratory/imaging-applications-documentation/raw/main/omero/OMERO_submission_form.xlsx) filled in for your submission. Use one row per file you are uploading; add as much metadata as you want. Note that matches need to be exact; your user, group and file names need to be exactly the same in the spreadsheet as your short username (all lowercase), your OMERO group (case-sensitive) and the filenames of the files in the folder (including extensions). 

    > IMPORTANT: if you are importing data into an OMERO project owned by a different user, you must use their username instead of your own in the import spreadsheet. This means the images will be owned by that user in OMERO. Otherwise you must use a different OMERO project for yourself.

4. (optional) Let us know there is a new batch of files to be imported into OMERO. This can be a simple email or Slack message.

