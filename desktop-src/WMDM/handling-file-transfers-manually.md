---
title: Handling File Transfers Manually
description: Handling File Transfers Manually
ms.assetid: ff94191b-a0f2-4118-996c-d040f214fb9b
keywords:
- Windows Media Device Manager,manual file transfers
- Device Manager,manual file transfers
- programming guide,manual file transfers
- desktop applications,manual file transfers
- creating Windows Media Device Manager applications,manual file transfers
- manual file transfers
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Handling File Transfers Manually

Your application can implement the [**IWMDMOperation**](/windows/win32/mswmdm/nn-mswmdm-iwmdmoperation?branch=master) interface to manage part of the reading or writing process. On a read from device, the implementation enables the application to receive blocks of raw data from a device file. On a write to device, it enables the application to send blocks of raw data to a file on the device.

In both read and write operations, the [**IWMDMOperation::TransferObjectData**](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation-transferobjectdata?branch=master) method passes the data between the computer and the device. To know the direction of the data transfer, your application must set a flag when Windows Media Device Manager calls [**BeginRead**](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation-beginread?branch=master) or [**BeginWrite**](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation-beginwrite?branch=master). When the [**End**](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation-end?branch=master) method is called, the application should reset this flag.

> [!Note]  
> If the service provider and device properly implement [**IMDSPObject2**](/windows/win32/mswmdm/nn-mswmdm-imdspobject2?branch=master), it will first call the application's [IWMDMOperation3::TransferObjectDataOnClearChannel](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation3-transferobjectdataonclearchannel?branch=master) method, if implemented. This method is a more efficient way of transferring data. **TransferObjectDataOnClearChannel** is handled the same way as **TransferObjectData**, except that the data is never encrypted and has no MAC values to verify.

 

The following sections describe both the reading and the writing process, when your application implements **IWMDMOperation**.

**Reading from a device**

When reading a file from a device, Windows Media Device Manager calls the following **IWMDMOperation** methods in order:

-   [**BeginRead**](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation-beginread?branch=master) Called to notify the application that a read from device is beginning.
-   [**TransferObjectData**](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation-transferobjectdata?branch=master) Called one or more times. The processing of data is described in the following steps:
    1.  **TransferObjectData** receives a buffer, *pData*, of size *pdwSize* bytes, filled with data, and a MAC to verify the incoming data.
    2.  The application verifies the incoming parameters with the incoming data MAC.
    3.  The application decrypts and reads as much of the data in *pData* as it can, and modifies the returned value of *pdwSize* to indicate how many bytes were actually read.
    4.  The application decrypts the data, using [**CSecureChannelClient::DecryptParam**](/windows/win32/scclient/nf-scclient-csecurechannelclient-decryptparam?branch=master), and stores it or uses it, as needed.
    5.  **TransferObjectData** returns S\_OK.
    6.  Windows Media Device Manager continues to call **TransferObjectData** until the application has read all the data from the file, or the application returns WMDM\_E\_USER\_CANCELLED to cancel the operation (in which case the read is canceled, and Windows Media Device Manager calls **End**).
-   [**End**](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation-end?branch=master) Called to notify the application that a read from device is ending.

**Writing to a device**

When writing a file to the device, Windows Media Device Manager calls the following **IWMDMOperation** methods in order:

-   [**GetObjectName**](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation-getobjectname?branch=master) Called to allow the application to specify a name for the new storage. This method is only called if the application did not specify a name in the **Insert** method.
-   [**GetObjectAttributes**](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation-getobjectattributes?branch=master) Called to allow the application to specify attributes for the new storage on the device.
-   [**BeginWrite**](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation-beginwrite?branch=master) Called to notify that that a write to device is beginning.
-   [**GetObjectTotalSize**](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation-getobjecttotalsize?branch=master) Called to retrieve the total size of the object being written to the device, to enable optimization of the transfer, and also to give Windows Media Device Manager an opportunity to cancel the transfer if the file is too large for the device.
-   [**TransferObjectData**](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation-transferobjectdata?branch=master) Called one or more times. The processing of data is described in the following steps:
    1.  **TransferObjectData** receives a pointer to a buffer of size *pdwSize* bytes.
    2.  The application gets a block of data to send to the device, usually by reading data from a file, and fills the received buffer with up to *pdwSize* bytes. It should modify *pdwSize* (if necessary) to reflect how many bytes were added to the buffer.
    3.  The application creates a MAC of all the method parameters.
    4.  The application encrypts the data in the buffer, using [**CSecureChannelClient::EncryptParam**](/windows/win32/scclient/nf-scclient-csecurechannelclient-encryptparam?branch=master).
    5.  **TransferObjectData** returns S\_OK to indicate that there is more data, or S\_FALSE to indicate that there is no more data. If the application returns WMDM\_E\_USER\_CANCELLED, the write operation is canceled and Windows Media Device Manager will call **End**.
    6.  Windows Media Device Manager continues to call **TransferObjectData** as long as the application returns S\_OK.
-   [**End**](/windows/win32/mswmdm/nf-mswmdm-iwmdmoperation-end?branch=master) Called to notify that a write to device is ending.

For a code example, see [Encryption and Decryption](encryption-and-decryption.md).

## Related topics

<dl> <dt>

[**Creating a Windows Media Device Manager Application**](creating-a-windows-media-device-manager-application.md)
</dt> </dl>

 

 



