## What is OMERO?
OMERO is a software platform for visualizing, managing, and annotating scientific image data. OMERO lets you import and archive your images, annotate and tag them, record your experimental protocols, and export images in a number of formats. It also allows you to collaborate with colleagues by creating user groups with different permission levels. Finally, it provides a convenient interface for programmatic access to your image data.

OMERO.web is a web-based interface that provides most of the core OMERO functions described above. You can explore the public JAX instance of OMERO.web at [images.jax.org](https://images.jax.org), where we have made some data publicly available. Note that this website is just a viewer for our public data and will not allow you to log in.

### How can I work with image data stored in OMERO?
There are several options for working with image data in OMERO:
1. The web interface available at [omeroweb.jax.org](https://omeroweb.jax.org) can be used to view and annotate images and create figures.
2. The OMERO plugin for Fiji/ImageJ allows you to directly interface your Fiji workflows with OMERO and save results back to the server easily.
3. If you prefer to code your own solutions, OMERO also has interfaces with Python, Java, R, CellProfiler, and other analysis platforms. By using OMERO, you never need to worry about manually downloading data before running your analysis algorithms.

### Is my data private? Can I see other people’s data?
By default, your data will not be seen outside of your group (i.e. lab). Each group owner (e.g., PI) can choose the set of permissions for their group. These range from private (each user only sees their own data, PI can see the whole group’s data) to read-write (everyone can do everything to each other’s data inside the group, including deletion).

## How can I get started?
To be able to store your images in OMERO, you’ll have to request access via the Service Portal. Fill out an [Omero Access request ticket](https://jax.service-now.com/jax?id=sc_cat_item&sys_id=0ff8f9b5db5f9450b2d52eda489619b3), which can also be found by searching for OMERO in the service catalog.
Once you have access to OMERO, you can log in to our internal, research instance at [omeroweb.jax.org](https://omeroweb.jax.org) using your JAX “shortname” and password.

## How do I import my image data into OMERO?
JAX uses a special workflow for importing data into OMERO. Instead of relying on users to upload their own data directly to the server, we only require them to place their data into a specific folder, and the OMERO admins do the import. This is both due to an established minimum requirement for metadata and due to specificities on how we manage storage for the OMERO server. Follow the steps at [OMERO: import data into OMERO](https://jacksonlaboratory.sharepoint.com/sites/ResearchIT/SitePages/Import-data-into-OMERO-at-JAX.aspx) at JAX to import your data.

## How can I learn more?
Follow the links to the right &#8594; to walk through some basic tutorials for using OMERO at JAX.

The [Research IT Imaging Applications](https://jacksonlaboratory.sharepoint.com/sites/ResearchIT/SitePages/Imaging-Applications.aspx) team at JAX runs OMERO workshops each year:
- **"Intro to OMERO"** covers viewing and annotating data in OMERO.web, working with regions of interest in OMERO.iviewer, creating figures for publication using OMERO.figure, and analyzing data from OMERO in ImageJ/Fiji
- **"OMERO for developers"** covers accessing OMERO data from Python. The ["OMERO for developers" workshop materials](https://github.com/TheJacksonLaboratory/omero_for_developers) are available on Github as Jupyter Notebooks. Contact the Research IT Imaging Applications team for login information to our training OMERO server.

For more information about OMERO, please see the [official OMERO user documentation](https://help.openmicroscopy.org/index.html).