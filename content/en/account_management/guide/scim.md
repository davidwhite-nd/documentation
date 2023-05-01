---
title: User Provisioning with SCIM
kind: guide
---

## Overview

The System for Cross-domain Identity Management, or SCIM, is an open standard that allows for the automation of user provisioning. Using SCIM, your can automatically provision and deprovision users in your Datadog organization in sync with your organization's identity provider (IdP).

### Prerequisites

Datadog strongly recommends that you use a service account application key when configuring SCIM to avoid any disruption in access. For further details, see [Using a service account with SCIM][1].

This documentation assumes your organization manages user identities using an identity provider. 

Datadog supports using SCIM with the Azure Active Directory (Azure AD) IdP.

## Configuring SCIM with Azure Active Directory

### Creating a Datadog application in Azure AD

1. In your Azure portal, go to **Azure Active Directory** -> **Enterprise Applications**
1. Click **New Application** -> **Create your own application**
1. Type “Datadog” in the search box
1. Select the Datadog application from the gallery 
1. Enter a name
1. Click **Create**

**Note:** If you already have Datadog configured with Azure AD for SSO, go to **Enterprise Applications** and select your existing Datadog application.

### Configure provisioning

1. In the app management screen, select **Provisioning** in the left panel
1. In the **Provisioning Mode** menu, select **Automatic**
1. Open **Admin Credentials**
1. Complete the **Admin Credentials** section as follows:
    - **Authentication Method**: Bearer Authentication
    - **Tenant URL**: `https://app.datadoghq.com/api/v2/scim?aadOptscim062020`
    - **Secret Token**: TODO reword and fix - Go to your organization Application Keys page in Datadog and create an application key. It is highly recommended to use a service account for your application key.
1. Click **Test Connection** and wait for the message that confirms that the credentials are authorized to enable provisioning.
1. Click **Save**.

### Attribute mapping

## Using a service account with SCIM

To enable SCIM, you must use an [application key][2] to secure the connection between your identity provider and your Datadog account. A specific user or service account controls each application key.

If you use an application key tied to a user to enable SCIM and that user leaves your organization, their Datadog account becomes deprovisioned. That user-specific application key gets revoked, and you permanently break your SCIM integration, preventing users in your organization from accessing Datadog.

To avoid losing access to your data, Datadog strongly recommends that you create a [service account][3] dedicated to SCIM. Within that service account, create an application key to use in the SCIM integration.

[1]: /account_management/guide/scim/#using-a-service-account-with-scim
[2]: /account_management/api-app-keys
[3]: /account_management/org_settings/service_accounts
