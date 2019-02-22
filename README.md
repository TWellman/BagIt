
-------------------------------------------------
Using BagIt: hierarchical file packaging format 
-------------------------------------------------


-----------
Contacts:
-----------
Tristan Wellman (twellman@usgs.gov)

Science Analytics and Synthesis (SAS), Core Science Systems.




-----------
Purpose:
-----------
This repository contains basic scripts on how to use Bagit for disk-based storage and network transfer of digital content. BagIt is a hierarchical file packaging format for the creation of standardised digital containers called 'bags,' which are used for storing and transferring digital content.

----------------
Functionality:
----------------
[`BagIt`](https://en.wikipedia.org/wiki/BagIt) is used as a packaging format to support storage of digital content. `BagIt` packages can be used to facilitate data sharing with Federal, State, and Local archive centers - thus ensuring preservation of important datasets.  Bags are ideal for digital content normally kept as a collection of files. They are also well-suited to export, for archival purposes of content normally kept in database structures that receiving parties are unlikely to support. Relying on cross-platform (Windows and Unix) filesystem naming conventions, a bag's payload may include any number of directories and sub-directories (folders and sub-folders). A bag can specify payload content indirectly via a "fetch.txt" file that lists URLs for content that can be fetched over the network to complete the bag; simple parallelization (e.g. running 10 instances of Wget) can exploit this feature to transfer large bags very quickly. 

1) Wide adoption in digital libraries (e.g. the Library of Congress).<br />
2) Easy to implement using ubiquitous and ordinary filesystem tools.<br />
3) Content that originates as files need only be copied to the payload directory.<br />
4) Compared to XML wrapping, content need not be encoded (e.g. Base64) which saves time and storage space.<br />
5) Received content is ready-to-go in a familiar filesystem tree.<br />
6) Easy to implement fast network transfer by running ordinary transfer tools in parallel.




-----------
Audiences:
-----------
Data managers and scientists 


-----------
Development Status:
-------------------
In progress, exploratory python scripts have been created to retrieve datasets, archive repo content, perform validation analysis, and archive compression. These scripts present functional case examples of using BagIt as an archive technology. 


-----------
Source Code:
--------------
  1) File: /source/BagIt-Sciencebase_example.ipnb

     Operations: <br />
     (a) Constructs BagIt data archive for preserving one ScienceBase item (data files, item *.json),<br />
     (b) Selects appropriate files in ScienceBase item to be stored in archive using search criteria,<br /> 
     (c) Employs stream request to download relevant files into archive folder,<br />
     (d) Infuses BagIt archive metadata (task name, processing uuid, provider, contact, etc.),<br /> 
     (e) Validates Bagit archive structure and manifest information,<br />
     (f) Compresses Archive folder in *.tar format for improved transfer capabilities.
     (g) Shows archive structure with archive metadata

  2) File: /source/BagIt_ScienceBase_process_OBIS.ipnb
  
     Operations: <br />
     (a) Constructs BagIt data archives for ScienceBase items in OBIS-USA parent collection (data files, item *.json),<br />
     (b) Selects appropriate files in ScienceBase item to be stored in archive using search criteria,<br /> 
     (c) Employs stream request to download relevant files into archive folder,<br />
     (d) Infuses BagIt archive metadata (task name, processing uuid, provider, contact, etc.),<br /> 
     (e) Validates Bagit archive structure and manifest information,<br />
     (f) Compresses Archive folder in *.tar format for improved transfer capabilities.
     
  2) File: /source/BagIt_archive_metadata.ipnb
  
     examples to retrieve and customize archive metadata
  
     Operations: <br />
     (a) Retrieves default archive metadata,<br />
     (b) Retrieves default search criteria to select data files from ScienceBase items, and<br />
     (c) Customizes defaults via kwargs (optional)

  3) /bags

     Content: <br />
     (a) BagIt example archives of OBIS-USA ScienceBase items
     

Copyright and License:
---------------------
This USGS product is considered to be in the U.S. public domain, and is licensed under
[CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/).

Although this software program has been used by the U.S. Geological Survey (USGS), no warranty, expressed or implied,
is made by the USGS or the U.S. Government as to the accuracy and functioning of the program and related program
material nor shall the fact of distribution constitute any such warranty, and no responsibility is assumed by the
USGS in connection therewith.
