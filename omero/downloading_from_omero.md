# Downloading images from OMERO

To download images from OMERO, we recommend you use a command line tool called `omero` which allows you to interact directly with the OMERO server.

## Prerequisites

In order to install the `omero` command line tool, you will need to have `conda` installed on your system.  

You can find step-by-step instructions for downloading and installing the `miniforge` conda distribution on SharePoint:  

[https://jacksonlaboratory.sharepoint.com/sites/ResearchIT/SitePages/conda_installing_miniforge.aspx](https://jacksonlaboratory.sharepoint.com/sites/ResearchIT/SitePages/conda_installing_miniforge.aspx)

## Installing the `omero` command line tool

1. Open a terminal window (Mac/Linux) or miniforge prompt (Windows).
2. Create a new conda environment for the `omero` tool:
   ```bash
   conda create -n omero -c conda-forge omero-py 
   ```
3. Activate the new environment:
   ```bash
   conda activate omero
   ```
4. Verify that the `omero` command is available:
   ```bash
   omero --help
   ```
   This should display the detailed help message for the `omero` command.
5. Install the `omero-cli-transfer` plugin:
   ```bash
   pip install omero-cli-transfer
   ```
6. Verify that the `omero transfer` command is available:
   ```bash
   omero transfer --help
   ```
   This should display the detailed help message for the `omero transfer` command.

## Logging into the OMERO server

In order to download images from the OMERO server, you need to log in first. You can do this using the `omero login` command:

1. Ensure you have the `omero` environment activated:
   ```bash
   conda activate omero
   ```
2. Log in to the OMERO server using your credentials:
   ```bash
   omero login -s omeroweb.jax.org -p 4064 -g <group_in_omero>
   ```
    Replace `<group_in_omero>` with the name of the group you belong to in OMERO.  
    Note: If the group name contains a space, like `Research IT`, then you need to use quotation marks when passing it to the `omero` tool: `"Research IT"`.  
    You will be prompted to enter your username and password: use your JAX shortname and password, just like you do for the web interface. If you have previously logged in, your user name will be pre-filled.

## Downloading individual images

Once you are logged in, you can download individual images using the `omero download` command. You can get more information about this command by running:

```bash
omero download --help
```

To download an image, you need to know its image ID in OMERO. You can find this ID by browsing the OMERO web interface. When you have an image selected, the image ID will be displayed in the right-hand Metadata panel, in the General tab, right under the name of the image, as a number next to the label *Image ID:*.  
For more information on using the web interface, please see the OMERO web documentation in SharePoint:  

[https://jacksonlaboratory.sharepoint.com/sites/ResearchIT/SitePages/Browsing-images-and-metadata-in-OMERO.aspx](https://jacksonlaboratory.sharepoint.com/sites/ResearchIT/SitePages/Browsing-images-and-metadata-in-OMERO.aspx)

Once you have the image ID, you can download the image using the following command:

```bash
omero download Image:<image_id> <output_directory>
```
Replace `<image_id>` with the actual image ID number and `<output_directory>` with the path to the directory where you want to save the downloaded image. Note: if you want to download the image to the current directory, you need to use `.` (the period character) as the output directory. The image file will be downloaded in its original format and will be named according to the image name in OMERO.

## Downloading multiple images, a dataset, or a project

In order to download multiple images, a dataset, or a project, you can use the `omero transfer` command. This command allows you to download all images associated with a dataset or project in one go.

### Downloading multiple images by ID

You can download multiple images by specifying their IDs in a comma-separated list. For example, to download images with IDs 123, 456, and 789, you would run:

```bash
omero transfer pack --simple --zip Image:123,456,789 my_images.zip
``` 
The images, along with their metadata, will be downloaded and packed into a single zip file named `my_images.zip`, which you can then extract to access the individual image files as needed.

### Downloading a dataset

If you have a `dataset` in OMERO (green folder icon), you can download all images in that dataset using its ID. You can find this ID by browsing the OMERO web interface. When you have the dataset selected, the dataset ID will be displayed in the right-hand Metadata panel, in the General tab, right under the name of the dataset, as a number next to the label *Dataset ID:*.

To download an entire dataset to a local zip file, run the following command, replacing `<dataset_id>` with the actual dataset ID:

```bash
omero transfer pack --simple --zip Dataset:<dataset_id> my_dataset.zip
```
The dataset, along with its metadata, will be downloaded and packed into a single zip file named `my_dataset.zip`, which you can then extract to access the dataset folder inside, which will contain all of the images in that dataset.

### Downloading a project

You can also download all images in an OMERO `project` (blue-gray folder icon) using its ID. You can find this ID by browsing the OMERO web interface. When you have the project selected, the project ID will be displayed in the right-hand Metadata panel, in the General tab, right under the name of the project, as a number next to the label *Project ID:*.

To download an entire project to a local zip file, run the following command, replacing `<project_id>` with the actual project ID:

```bash
omero transfer pack --simple --zip Project:<project_id> my_project.zip
```
The project, along with its metadata, will be downloaded and packed into a single zip file named `my_project.zip`, which you can then extract to access the project folder inside--the directory structure will reflect all of the datasets and images contained in the project.
