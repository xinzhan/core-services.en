---
description: If you do not upload using drag-and-drop, you can upload customer attribute data via FTP to the Experience Cloud.
keywords: customer attributes;core services
seo-description: If you do not upload using drag-and-drop, you can upload customer attribute data via FTP to the Experience Cloud.
seo-title: Optional - Upload the data file via FTP
solution: Experience Cloud
title: Optional - Upload the data file via FTP
uuid: 5df565dd-b6f8-420e-981f-4b6fc6f7d0e4
index: y
internal: n
snippet: y
translate: y
---

# Optional - Upload the data file via FTP

If you do not upload using drag-and-drop, you can upload customer attribute data via FTP to the Experience Cloud.

You can upload the data after you create a customer attribute source and an FTP account in the Experience Cloud. You create one FTP account per attribute source. The uploaded files are stored in the root folder of that account. The data must be in [!DNL .csv] format, with a second [!DNL .fin] file to indicate the upload is complete. 

>[!IMPORTANT]
>
>Review [Data file requirements for uploading customer attributes](../attributes/crs_data_file.md#concept_DE908F362DF24172BFEF48E1797DAF19) before uploading the file. 


File uploads to the customer attributes FTP site can be done via FTP or SFTP. 

* You need a client that supports SFTP connections.
* You can connect with SFTP using either username/password or using no password, as described [here](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/?f=ftp_sftp_cert_auth).



<!-- <p>Error states - get with Matt and Dave </p> 
<p>What are the most common reasons for doing this? Retail? Do a use case example, then show an AN example. </p> 
<p>You create one FTP per attribute source. Files go to the root folder in that account. The file type .fin is user-created. (For example, upload a .csv then a .fin of the same name, which signals you have completed the upload. https://wiki.corp.adobe.com/display/marketingcloud/Customer+Record+Services#CustomerRecordServices-FileFormats (leverage for doc). Possibly link from FTP File Reqs page to a help file about naming conventions. Need a new file type page for this. Similar content here: https://marketing.adobe.com/resources/help/en_US/reference/c_general_file_structure.html and here: https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_datasources.html </p> 
<p>Drag-n-drop and zip functionality for uploads - 1/21/2015. S/b less than 100 megs for drag and drop zip file. Fin file not required for drag/drop. </p> 
<p>Preview Data - shows the last upload (?) </p> 
<p>Need a link to the "instructions" on that information icon with the image. </p> 
<p>Workflow: Drag and drop, validate schema, configure subscription, save/activate. </p> -->
**To upload the data file via FTP** 

1. [Create a customer attribute source and upload the data file...](../attributes/t_crs_usecase.md#task_BCC327B2A0EF4A1BBB2934013AB92B78).

   Ensure that you are logged in to your FTP site at [!DNL ftp.adobe.com/<sftpname>]. 

1. Click **[!UICONTROL Actions]** > **[!UICONTROL File Upload]**.

1. Upload a [!DNL .fin] file, so that your file can be retrieved.

   The file type [!DNL .fin] is user-created and signals that the upload is finished. It can be a blank notepad file. For example, if you upload [!DNL crs123.csv], you also upload [!DNL crs123.fin]. 

   If the upload is successful, both files are moved to a folder called **processed**. 


   See [Data file requirements for uploading customer attributes](../attributes/crs_data_file.md#concept_DE908F362DF24172BFEF48E1797DAF19) for important information about file names and structure. 
