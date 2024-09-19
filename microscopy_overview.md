## Why use delivery folders for the Microscopy Service?
Most of the microscopes managed by the Microscopy Service are run by workstations to which Microscopy customers have access. Thus, users have a variety of options by which it is possible to transfer data to their own laboratory workspace/storage. Many of these options carry risks or are otherwise problematic. For example, USB devices such as thumb drives and external hard drives have a high failure rate and can transmit viruses between computers. And moving data directly to laboratory Windows shares can often lead to data duplication and quickly fill storage quotas. Importantly, neither of these options will lead to the primary data being properly archived and protected.

To help keep laboratory microscopy data safe and secure, Research IT has worked with the Microscopy Service to develop the delivery folder system. This system gives users the option to transfer their microscopy data via a standardized, centralized mechanism that is subjected to regular data backup.

The major limitation of the Delivery Folder system is that users have write access to their laboratory’s delivery folders by necessity, so problems can arise if users are not following proper procedures. This document is intended to guide users through the best practices for using the Delivery Folder system.

## Overall structure of the Microscopy Service Delivery Folders.
There are two shares used for data delivery, organized by site. These are:

- Data from Farmington-based Microscopes: ```\\jax.org\jax\ct-microscopy (smb); The Jackson Laboratory Scientific Services:/microscopy_delivery/ct-microscopy (Globus)```
- Data from Bar Harbor-based Microscopes: ```\\jax.org\jax\bh-microscopy (smb); The Jackson Laboratory Scientific Services:/microscopy_delivery/bh-microscopy (Globus)```

From these base directories, the directory structure follows this convention:

        SITE \ INSTRUMENT \ LABORATORY \ PROJECT

For example, the Korstanje lab would use the following directory for their Nanozoomer data:

     bh-microscopy\Hamamatsu_NanoZoomer-20233\korstanje_lab\

A single imaging session would produce a directory like:

     bh-microscopy\Hamamatsu_NanoZoomer-20233\korstanje_lab\abcde_20200320\

Where ```abcde``` is the shortname of the user who owns the data contained within the directory, and ```20200320``` is the date of the imaging session in YYYYMMDD format. Note that the ```abcde_20200320``` directory is usually going to be created and named by the user who is moving their data from an instrument workstation to the delivery folder. This folder##  should be named according to the ```shortname_YYYYMMDD``` convention to facilitate archive retrieval in the future.

Instructions for using the Delivery Folders
*Note: these instructions assume you are using a Bar Harbor instrument. If you are moving data from a Farmington instrument, replace bh-microscopy with ct-microscopy.*

### To move files from the instrument workstation to the delivery folder:
1. If this is the first time your lab is using a delivery folder for this instrument: Ahead of your imaging session, open a helpdesk ticket requesting creation of a delivery folder for your lab at: ```\\jax.org\jax\bh-microscopy\<name_of_microscope>\```. When you log on to the instrument workstation, the server containing your delivery folder will be mounted as the M: drive. Open this drive (e.g., type Win + R, then type M: and hit enter).
2. Navigate to: ```<name_of_microscope>\<yourlab>```
Create a project folder that includes your username and the date in the format YYYYMMDD (e.g., ```\djme_20180337```).
3. After your imaging session is complete, move all imaging files and associated metadata to the new project folder.

### To copy files from the delivery folder to another computer:
#### Globus method (PREFERRED, but you must use Globus! Reach out to Research IT for help)
1. Using your web browser, navigate to globus.org and sign in with The Jackson Laboratory organization.
2. Open the two-panel view (upper right).
3. In the left panel, choose *The Jackson Laboratory Scientific Services* for your Collection, then navigate to the folder containing your data below.
4. In the right panel, choose the Collection appropriate for where you want to deliver the data. For example, this could be *The Jackson Laboratory for Genomic Medicine* if you want to copy data to the HPC cluster, or your own Globus Connect Personal endpoint if you want to transfer data to your laptop (reach out to Research IT if you don't know what this means).
5. Once you have a destination Collection selected in the right panel, choose the folder in which you want to copy the data below.
6. Click the Start button in the *left panel*. This will initiate a transfer, and you can close your browser.

#### smb method (OLD, mount directory to workstation. Please consider using Globus!)
On a Mac:
1. Click on the desktop and type ```cmd + k```.
2. In the Server Address field, type: ```smb://jax.org/jax/bh-microscopy```
3. Click the ```+``` button, then ```Connect```.
4. You should be able to now open the bh-microscopy share and navigate to your project folder. Copy the contents to a new destination (e.g., your lab share).
5. Do not delete files in the delivery folder. They will be automatically archived after 90 days.

On a Windows PC:
1. Type ```Win+R```.
2. Type ```\\jax.org\jax\bh-microscopy and hit enter```.
3. You should be able to now open the bh-microscopy share and navigate to your project folder. Copy the contents to a new destination (e.g., your lab share).
4. Do not delete files in the delivery folder. They will be automatically archived after 90 days.

## IMPORTANT
Delivery folder files may be archived any time after 7 days and deleted any time after 90 days!
- You *must* copy your folder with images to your own personal or laboratory storage within 90 days.
- You should *NEVER* make any changes to a delivery project folder after its initial creation. **Changes made to folders, including addition of files, are not captured after a folder is archived and will thus be lost.**

If you need to recover files after they have been deleted from the delivery folder, you will need to put in a request to retrieve your data from archive [here](https://jax.service-now.com/jax?id=sc_cat_item&sys_id=17cb0f5d1ba710d0832f206cbc4bcb47).