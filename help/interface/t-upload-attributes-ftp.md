---
description: Learn how to upload Customer Attribute data via FTP to the Experience Cloud.
keywords: Customer Attributes;core services
solution: Experience Cloud
title: Upload the Customer Attribute data file via FTP 
uuid: 5df565dd-b6f8-420e-981f-4b6fc6f7d0e4
feature: Customer Attributes
topic: Administration
role: Administrator
level: Experienced
exl-id: ed9e4a8f-493a-4a0f-a87e-674c7da95b99
---
# Optional - Upload the data file via FTP

If you do not upload using drag-and-drop, you can upload Customer Attribute data via FTP to the Experience Cloud.

You can upload the data after you create a Customer Attribute source and an FTP account in the Experience Cloud. You create one FTP account per attribute source. The uploaded files are stored in the root folder of that account. The data must be in `.csv` format, with a second `.fin` file to indicate that the upload is complete. 

>[!IMPORTANT]
>
>Review [Data file requirements for uploading Customer Attributes](crs-data-file.md#concept_DE908F362DF24172BFEF48E1797DAF19) before uploading the file. 

File uploads to the Customer Attributes FTP site can be done via FTP or SFTP: 

* You need a client that supports SFTP connections.
* You can connect with SFTP using either username/password or using no password, as described [here](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/secure-file-transfer-protocol/ftp-sftp-cert-auth.html?lang=en).

**To upload the data file via FTP** 

1. [Create a Customer Attribute source and upload the data file...](t-crs-usecase.md#task_BCC327B2A0EF4A1BBB2934013AB92B78).

   Ensure that you are logged in to your FTP site at `ftp.adobe.com/<sftpname>`. 

1. Click **[!UICONTROL Actions]** > **[!UICONTROL File Upload]**.

1. Upload a `.fin` file, so that your file can be retrieved.

   The file type `.fin` is user-created and signals that the upload is finished. It can be a blank notepad file. For example, if you upload [!DNL crs123.csv], you also upload [!DNL crs123.fin]. 

   If the upload is successful, both files are moved to a folder called **processed**. 

   See [Data file requirements for uploading Customer Attributes](crs-data-file.md#concept_DE908F362DF24172BFEF48E1797DAF19) for important information about file names and structure.
