---
title: How-to - Register an app in Azure AD for customers
description: Learn about how to register an app in the customer tenant.
services: active-directory
author: csmulligan
ms.author: cmulligan
manager: celestedg
ms.service: active-directory
ms.workload: identity
ms.subservice: ciam
ms.topic: how-to
ms.date: 05/09/2023

ms.custom: it-pro

#Customer intent: As a dev, devops, or it admin, I want to learn about how to register an app on the Microsoft Entra admin center.
---
# Register your app in the customer tenant

Azure Active Directory (Azure AD) for customers enables your organization to manage customers’ identities, and securely control access to your public facing applications and APIs. Applications where your customers can buy your products, subscribe to your services, or access their account and data.  Your customers only need to sign in on a device or a web browser once and have access to all your applications you granted them permissions.

To enable your application to sign in with Azure AD for customers, you need to register your app in the Azure AD for customers. The app registration establishes a trust relationship between the app and Azure AD for customers.
During app registration, you specify the redirect URI. The redirect URI is the endpoint to which users are redirected by Azure AD for customers after they authenticate. The app registration process generates an application ID, also known as the client ID, that uniquely identifies your app.

Azure AD for customers supports authentication for various modern application architectures, for example web app or single-page app. The interaction of each application type with the customer tenant is different, therefore, you must specify the type of application you want to register.

In this article, you’ll learn how to register an application in your customer tenant.

## Prerequisites

- An Azure account that has an active subscription. [Create an account for free](https://azure.microsoft.com/free/?WT.mc_id=A261C142F).
- Your Azure AD for customers tenant. If you don't already have one, sign up for a [free trial](https://aka.ms/ciam-free-trial?wt.mc_id=ciamcustomertenantfreetrial_linkclick_content_cnl).

## Choose your app type

# [Single-page app (SPA)](#tab/spa)
## How to register your Single-page app?

The following steps show you how to register your app in the admin center:

1.  Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/).

1. If you have access to multiple tenants, make sure you use the directory that contains your Azure AD for customers tenant:
    
    1. Select the **Directories + subscriptions** icon in the portal toolbar. 
    
    1. On the **Portal settings | Directories + subscriptions** page, find your Azure AD for customers directory in the **Directory name** list, and then select **Switch**. 

1. On the sidebar menu, select **Azure Active Directory**.

1. Select **Applications**, then select **App Registrations**.

1. Select **+ New registration**.

1. In the **Register an application page** that appears, enter your application's registration information:
    
    1. In the **Name** section, enter a meaningful application name that will be displayed to users of the app, for example *ciam-client-app*.
    
    1. Under **Supported account types**, select **Accounts in this organizational directory only**.
	
	1. Under **Redirect URI (optional)**, select **Single-page application (SPA)** and then, in the URL box, enter `http://localhost:3000/`.

1. Select **Register**.

1. The application's **Overview pane** is displayed when registration is complete. Record the **Directory (tenant) ID** and the **Application (client) ID** to be used in your application source code.

[!INCLUDE [add about redirect URI](../customers/includes/register-app/about-redirect-url.md)]  

### Add delegated permissions
This app signs in users. You can add delegated permissions to it, by following the steps below:

[!INCLUDE [grant permision for signing in users](../customers/includes/register-app/grant-api-permission-sign-in.md)] 

### If you want to call an API follow the steps below (optional):
[!INCLUDE [grant permisions for calling an API](../customers/includes/register-app/grant-api-permission-call-api.md)] 

If you'd like to learn how to expose the permissions by adding a link, go to the [Web API](how-to-register-ciam-app.md?tabs=webapi) section.

## Next steps
 
- [Create a sign-up and sign-in user flow](how-to-user-flow-sign-up-sign-in-customers.md)
- [Sign in users in a sample vanilla JavaScript single-page app](how-to-single-page-app-vanillajs-sample-sign-in.md) 

# [Web app](#tab/webapp)
## How to register your Web app?

The following steps show you how to register your app in the admin center:

1.  Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/).

1. If you have access to multiple tenants, make sure you use the directory that contains your Azure AD for customers tenant:
    
    1. Select the **Directories + subscriptions** icon in the portal toolbar. 
    
    1. On the **Portal settings | Directories + subscriptions** page, find your Azure AD for customers directory in the **Directory name** list, and then select **Switch**. 

1. On the sidebar menu, select **Azure Active Directory**.

1. Select **Applications**, then select **App Registrations**.

1. Select **+ New registration**.

1. In the **Register an application page** that appears, enter your application's registration information:
    
    1. In the **Name** section, enter a meaningful application name that will be displayed to users of the app, for example *ciam-client-app*.
    
    1. Under **Supported account types**, select **Accounts in this organizational directory only**.
	
	1. Under **Redirect URI (optional)**, select **Web** and then, in the URL box, enter `http://localhost:3000/`.

1. Select **Register**.

1. The application's **Overview pane** is displayed when registration is complete. Record the **Directory (tenant) ID** and the **Application (client) ID** to be used in your application source code.

[!INCLUDE [add about redirect URI](../customers/includes/register-app/about-redirect-url.md)] 

### Add delegated permissions
This app signs in users. You can add delegated permissions to it, by following the steps below:

[!INCLUDE [grant permission for signing in users](../customers/includes/register-app/grant-api-permission-sign-in.md)] 

### Create a client secret 
[!INCLUDE [add a client secret](../customers/includes/register-app/add-app-client-secret.md)]

### If you want to call an API follow the steps below (optional):
[!INCLUDE [grant permissions for calling an API](../customers/includes/register-app/grant-api-permission-call-api.md)] 

## Next steps
 
- [Create a sign-up and sign-in user flow](how-to-user-flow-sign-up-sign-in-customers.md)
- [Sign in users in a sample Node.js web app](how-to-web-app-node-sample-sign-in.md) 

# [Web API](#tab/webapi)
## How to register your Web API?

[!INCLUDE [register app](../customers/includes/register-app/register-api-app.md)]

### Expose permissions

[!INCLUDE [expose permissions](../customers/includes/register-app/add-api-scopes.md)]

### If you want to add app roles follow the steps below (optional):

[!INCLUDE [configure app roles](../customers/includes/register-app/add-app-role.md)]

## Next steps
 
- [Create a sign-up and sign-in user flow](how-to-user-flow-sign-up-sign-in-customers.md) 

# [Desktop or Mobile app](#tab/desktopmobileapp)
## How to register your Desktop or Mobile app?

The following steps show you how to register your app in the admin center:

1.  Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/).

1. If you have access to multiple tenants, make sure you use the directory that contains your Azure AD for customers tenant:
    
    1. Select the **Directories + subscriptions** icon in the portal toolbar. 
    
    1. On the **Portal settings | Directories + subscriptions** page, find your Azure AD for customers directory in the **Directory name** list, and then select **Switch**. 

1. On the sidebar menu, select **Azure Active Directory**.

1. Select **Applications**, then select **App Registrations**.

1. Select **+ New registration**.

1. In the **Register an application page** that appears, enter your application's registration information:
    
    1. In the **Name** section, enter a meaningful application name that will be displayed to users of the app, for example *ciam-client-app*.
    
    1. Under **Supported account types**, select **Accounts in this organizational directory only**.
	
	1. Under **Redirect URI (optional)**, select the **Mobile and desktop applications** option and then, in the URL box, enter a URI with a unique scheme. For example, Electron desktop app's redirect URI looks something similar to `http://localhost` while that of a .NET Multi-platform App UI (MAUI) looks similar to `msal{ClientId}://auth`. 

1. Select **Register**.

1. The application's **Overview pane** is displayed when registration is complete. Record the **Directory (tenant) ID** and the **Application (client) ID** to be used in your application source code.

### Add delegated permissions
[!INCLUDE [grant permission for signing in users](../customers/includes/register-app/grant-api-permission-sign-in.md)]

### If you want to call an API follow the steps below (optional):
[!INCLUDE [grant permissions for calling an API](../customers/includes/register-app/grant-api-permission-call-api.md)] 

## Next steps
 
- [Create a sign-up and sign-in user flow](how-to-user-flow-sign-up-sign-in-customers.md)
- [Sign in users in a sample Electron desktop app](how-to-desktop-app-electron-sample-sign-in.md) 

# [Daemon app](#tab/daemonapp)
## How to register your Daemon app?

[!INCLUDE [register daemon app](../customers/includes/register-app/register-daemon-app.md)]

### If you want to call an API follow the steps below (optional)
A daemon app signs-in as itself using the [OAuth 2.0 client credentials flow](/azure/active-directory/develop/v2-oauth2-client-creds-grant-flow), you add application permissions, which is required by apps that authenticate as themselves:

[!INCLUDE [register daemon app](../customers/includes/register-app/grant-api-permissions-app-permissions.md)]

## Next steps
 
- Learn more about a [daemon app that calls a web API in the daemon's name](/azure/active-directory/develop/authentication-flows-app-scenarios#daemon-app-that-calls-a-web-api-in-the-daemons-name)
- [Create a sign-up and sign-in user flow](how-to-user-flow-sign-up-sign-in-customers.md)
