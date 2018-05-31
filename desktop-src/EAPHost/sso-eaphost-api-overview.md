---
title: SSO EAPHost API Overview
description: Provides an overview of the EAPHost APIs that support Single-Sign-On (SSO).
ms.assetid: 3c01d10a-9098-4965-8983-c7f65be31884
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# SSO EAPHost API Overview

This topic provides an overview of the EAPHost APIs that support Single-Sign-On (SSO). For specific SSO scenarios, see [SSO EAPHost Scenarios](why-eaphost-sso.md).

## EAPHost Enumerations

The following enumerations support SSO.



| Name                                                                    | Purpose                                                                                      |
|-------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|
| [**EAP\_CONFIG\_INPUT\_FIELD\_TYPE**](/windows/previous-versions/eaptypes/ne-eaptypes-_eap_config_input_field_type?branch=master)  | Defines a set of possible input field types available when querying for user credentials.    |
| [**EAP\_INTERACTIVE\_UI\_DATA\_TYPE**](/windows/previous-versions/eaptypes/ne-eaptypes-_eap_config_input_field_type?branch=master) | Specifies the types of interactive UI context data supplied to certain supplicant API calls. |



 

## EAPHost Structures

The following data structures support SSO.



| Name                                                                     | Purpose                                                                                                                                                                         |
|--------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**EAP\_CONFIG\_INPUT\_FIELD\_DATA**](/windows/previous-versions/eaptypes/ns-eaptypes-_eap_config_input_field_data?branch=master)   | Contains the data associated with a single input field.                                                                                                                         |
| [**EAP\_CONFIG\_INPUT\_FIELD\_ARRAY**](/windows/previous-versions/eaptypes/ns-eaptypes-_eap_config_input_field_array?branch=master) | Contains a set of [**EAP\_CONFIG\_INPUT\_FIELD\_DATA**](/windows/previous-versions/eaptypes/ns-eaptypes-_eap_config_input_field_data?branch=master) structures that collectively contain the user input field data obtained from the user. |
| [**EAP\_INTERACTIVE\_UI\_DATA**](/windows/previous-versions/eaptypes/ns-eaptypes-_eap_interactive_ui_data?branch=master)            | Contains configuration information for interactive UI components raised on an EAP supplicant.                                                                                   |
| [**EAP\_CRED\_REQ**](eap-cred-req.md)                                   | Contains both the old and new EAP credentials for a credential change operations.                                                                                               |
| [**EAP\_CRED\_RESP**](eap-cred-resp.md)                                 | Contains both the old and new EAP credentials for a credential change operations.                                                                                               |
| [**EAP\_CRED\_EXPIRY\_REQ**](/windows/previous-versions/eaptypes/ns-eaptypes-_eap_cred_expiry_req?branch=master)                    | Contains both the old and new EAP credentials for credential expiry operations.                                                                                                 |
| [**EAP\_CRED\_EXPIRY\_RESP**](https://msdn.microsoft.com/library/windows/desktop/bb530539)              | Contains both the old and new EAP credentials for credential expiry operations.                                                                                                 |



 

## EAPHost Peer (Supplicant) APIs

The following supplicant functions support SSO.

The [**EapHostPeerQueryCredentialInputFields**](/windows/previous-versions/eaphostpeerconfigapis/nf-eaphostpeerconfigapis-eaphostpeerquerycredentialinputfields?branch=master) and [**EapHostPeerQueryUserBlobFromCredentialInputFields**](/windows/previous-versions/eaphostpeerconfigapis/nf-eaphostpeerconfigapis-eaphostpeerqueryuserblobfromcredentialinputfields?branch=master) functions are exclusive to SSO.



| Name                                                                                                             | Purpose                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Order Called |
|------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|
| [**EapHostPeerQueryInteractiveUIInputFields**](/windows/previous-versions/eaphostpeerconfigapis/nf-eaphostpeerconfigapis-eaphostpeerqueryinteractiveuiinputfields?branch=master)                     | Obtains the input fields for interactive UI components to be raised on the supplicant.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | 4            |
| [**EapHostPeerQueryCredentialInputFields**](/windows/previous-versions/eaphostpeerconfigapis/nf-eaphostpeerconfigapis-eaphostpeerquerycredentialinputfields?branch=master)                           | Allows the user to determine what kind of credentials are required by the methods to perform authentication in a SSO scenario.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | 1            |
| [**EapHostPeerQueryUIBlobFromInteractiveUIInputFields**](/windows/previous-versions/eaphostpeerconfigapis/nf-eaphostpeerconfigapis-eaphostpeerqueryuiblobfrominteractiveuiinputfields?branch=master) | Converts user information into a user BLOB that can be consumed by EAPHost run-time functions.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    | 5            |
| [**EapHostPeerQueryUserBlobFromCredentialInputFields**](/windows/previous-versions/eaphostpeerconfigapis/nf-eaphostpeerconfigapis-eaphostpeerqueryuserblobfromcredentialinputfields?branch=master)   | Obtains a credential BLOB that can be used to start authentication from user input received by the SSO UI.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | 2            |
| [**EapHostPeerBeginSession**](/windows/previous-versions/eappapis/nf-eappapis-eaphostpeerbeginsession?branch=master)                                                       | The supplicant uses the **EAP\_FLAG\_PRE\_LOGON** flag to indicate that EAPHost should provide SSO. If the [EapHostPeerResponseInvokeUI](/windows/previous-versions/eaphostpeertypes/ne-eaphostpeertypes-tageaphostpeerresponseaction?branch=master) action code is returned, EAPHost calls [**EapPeerQueryInteractiveUIInputFields**](/windows/previous-versions/eapmethodpeerapis/nf-eapmethodpeerapis-eappeerqueryinteractiveuiinputfields?branch=master), and then calls [**EapHostPeerQueryUIBlobFromInteractiveUIInputFields**](/windows/previous-versions/eaphostpeerconfigapis/nf-eaphostpeerconfigapis-eaphostpeerqueryuiblobfrominteractiveuiinputfields?branch=master)<br/> If the [EapHostPeerResponseInvokeUI](/windows/previous-versions/eaphostpeertypes/ne-eaphostpeertypes-tageaphostpeerresponseaction?branch=master) action code is not returned, EAPHost proceeds with the regular, non SSO call sequence. For more information, see [Supplicant API Call Sequence](supplicant-api-call-sequence.md).<br/> | 3            |



 

## EAPHost Peer Method APIs

The following peer functions support SSO.

The [**EapPeerQueryCredentialInputFields**](/windows/previous-versions/eapmethodpeerapis/nf-eapmethodpeerapis-eappeerquerycredentialinputfields?branch=master) and [**EapPeerQueryUserBlobFromCredentialInputFields**](/windows/previous-versions/eapmethodpeerapis/nf-eapmethodpeerapis-eappeerqueryuserblobfromcredentialinputfields?branch=master) functions are exclusive to SSO.



| Name                                                                                                      | Purpose                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Order Called |
|-----------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|
| [**EapPeerQueryInteractiveUIInputFields**](/windows/previous-versions/eapmethodpeerapis/nf-eapmethodpeerapis-eappeerqueryinteractiveuiinputfields?branch=master)                      | Defines the implementation of an EAP method API that provides the input fields for interactive UI components to be raised on the supplicant.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | 4            |
| [**EapPeerQueryCredentialInputFields**](/windows/previous-versions/eapmethodpeerapis/nf-eapmethodpeerapis-eappeerquerycredentialinputfields?branch=master)                            | Defines the implementation of an EAP method-specific function that obtains the EAP SSO credential input fields for that EAP method.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | 1            |
| [**EapPeerQueryUIBlobFromInteractiveUIInputFields**](/windows/previous-versions/eapmethodpeerapis/nf-eapmethodpeerapis-eappeerqueryuiblobfrominteractiveuiinputfields?branch=master)  | Converts user information into a user BLOB that can be consumed by EAPHost run-time functions.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | 5            |
| [**EapPeerQueryUserBlobFromCredentialInputFields**](/windows/previous-versions/eapmethodpeerapis/nf-eapmethodpeerapis-eappeerqueryuserblobfromcredentialinputfields?branch=master) | Defines the implementation of an EAP method function that obtains the user BLOB data provided by the interactive SSO UI raised on the supplicant.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | 2            |
| [**EapPeerBeginSession**](/windows/previous-versions/eapmethodpeerapis/nf-eapmethodpeerapis-eappeerbeginsession?branch=master)                                                        | The **EAP\_FLAG\_PRE\_LOGON** flag indicates that EAPHost should provide SSO. In an SSO scenario if the **EapPeerResponseInvokeUI** action code is returned, EAPHost calls [**EapPeerQueryInteractiveUIInputFields**](/windows/previous-versions/eapmethodpeerapis/nf-eapmethodpeerapis-eappeerqueryinteractiveuiinputfields?branch=master), and then calls [**EapPeerQueryUserBlobFromCredentialInputFields**](/windows/previous-versions/eapmethodpeerapis/nf-eapmethodpeerapis-eappeerqueryuserblobfromcredentialinputfields?branch=master)<br/> If the **EapPeerResponseInvokeUI** action code is not returned, EAPHost proceeds with the regular, non SSO call sequence. For more information, see [Peer Method API Call Sequence](peer-method-api-call-sequence.md).<br/> | 3            |



 

## Related topics

<dl> <dt>

[SSO and PLAP](understanding-sso-and-plap.md)
</dt> <dt>

[SSO EAPHost Scenarios](why-eaphost-sso.md)
</dt> </dl>

 

 




