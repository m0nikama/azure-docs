---
title: SaaS applications publishing guide - Microsoft commercial marketplace
description: Requirements and resources for publishing publishing SaaS application offers to Microsoft AppSource and Azure Marketplace.
services: Marketplace, Compute, Storage, Networking, Blockchain, Security, SaaS
author: dsindona
ms.service: marketplace
ms.subservice: partnercenter-marketplace-publisher
ms.topic: conceptual
ms.date: 04/23/2020
ms.author: dsindona
---

# SaaS applications offer publishing guide

You can publish SaaS applications in the commercial marketplace with three different calls to action: "Contact Me," "Try it now," and "Get it Now." This article explains these three options, including requirements for each. 

## Offer overview  

SaaS applications are available in Microsoft AppSource and Azure Marketplace.  Both storefronts support list, trial, and transact offers.

**List:**  The Listing publishing option consists of a Contact Me offer type and is used when a Trial- or Transaction-level participation is not feasible. The benefit of this approach is that it enables publishers with a solution in-market to immediately begin receiving leads that can be turned into deals to increase your business.  
**Trial/Transaction:**  The customer has the option to directly buy or request a trial for your solution. Providing a Trial experience increases the engagement level offered to customers and enables customers to explore your solution before buying. With a Trial experience, you will have better chances of promotion in the storefronts, and you should expect more and richer leads from customer engagements. Trials must include free support at least for the duration of the trial period.  

| SaaS Apps Offer | Business Requirements | Technical Requirements |  
| --- | --- | --- |  
| **Contact Us** | Yes | No |  
| **Power BI / Dynamics** | Yes | Yes (Azure AD integration) |  
| **SaaS Apps**| Yes | Yes (Azure AD integration) |     

## SaaS List

The call to action for a SaaS listing with no trial and no billing functionality is "Contact Me." 

You do not need to configure Azure Active Directory to list a SaaS application. 

|Requirements  |Details  |
|---------|---------|
|Your app is a SaaS offering  |   Your solution is a SaaS offering and you offer a multitenant SaaS product.      |


## SaaS Trial

You provide a solution or app using a free-to-try, software-as-a-service (SaaS)-based trial. Free trial offers may be presented as a limited-use or limited-duration trial account. 


|Requirements  |Details  |
|---------|---------|
|Your app is a SaaS offering  |   Your solution is a SaaS offering and you offer a multitenant SaaS product.      |
|Your app is AAD enabled     |   The customer will be re-directed to your domain and you will transact with the customer directly       |


## SaaS Trial Technical requirements

The technical requirements for SaaS applications are simple. Publishers are only required to be integrated with Azure Active Directory (Azure AD) to be published. Azure AD integration with applications is well documented and Microsoft provides multiple SDKs and resources to accomplish this.  

To start, we recommend that you have a subscription dedicated for your Azure Marketplace publishing, allowing you to isolate the work from other initiatives. Once this is done you can start deploying your SaaS application in this subscription to start the development work.  

The best Azure Active Directory documentation, samples and guidance are located at the following sites: 

* [Azure Active Directory Developer's Guide](../active-directory/develop/index.yml)

* [Integrating with Azure Active Directory](../active-directory/develop/active-directory-how-to-integrate.md)

* [Azure Roadmap - Security and Identity](https://azure.microsoft.com/roadmap/?category=security-identity)

For video tutorials, review the following:

* [Azure Active Directory Authentication with Vittorio Bertocci](https://channel9.msdn.com/Shows/XamarinShow/Episode-27-Azure-Active-Directory-Authentication-with-Vittorio-Bertocci?term=azure%20active%20directory%20integration)

* [Azure Active Directory Identity Technical Briefing - Part 1 of 2](https://channel9.msdn.com/Blogs/MVP-Enterprise-Mobility/Azure-Active-Directory-Identity-Technical-Briefing-Part-1-of-2?term=azure%20active%20directory%20integration)

* [Azure Active Directory Identity Technical Briefing - Part 2 of 2](https://channel9.msdn.com/Blogs/MVP-Azure/Azure-Active-Directory-Identity-Technical-Briefing-Part-2-of-2?term=azure%20active%20directory%20integration)

* [Building Apps with Microsoft Azure Active Directory](https://channel9.msdn.com/Blogs/Windows-Development-for-the-Enterprise/Building-Apps-with-Microsoft-Azure-Active-Directory?term=azure%20active%20directory%20integration)

* [Microsoft Azure Videos focused on Active Directory](https://azure.microsoft.com/resources/videos/index/?services=active-directory)

Free Azure Active Directory training is available at  
* [Microsoft Azure for IT Pros Content Series: Azure Active Directory](https://mva.microsoft.com/training-courses/microsoft-azure-for-it-pros-content-series-azure-active-directory-16754?l=N0e23wtxC_2106218965)

In addition, Azure Active Directory provides a site to check for Service Updates   
* [Azure AD Service updates](https://azure.microsoft.com/updates/?product=active-directory)

## Using Azure Active Directory to enable trials  

Microsoft authenticates all Marketplace users with Azure AD, so when an authenticated user clicks through your Trial listing in Marketplace and is redirected to your Trial environment, you can provision the user directly into a Trial without requiring an additional sign-in step. The token that your app receives from Azure AD during authentication includes valuable user information that you can use to create a user account in your app, enabling you to automate the provisioning experience and increase the likelihood of conversion. For more information about the token, see [Sample Tokens](../active-directory/develop/active-directory-token-and-claims.md) .

Using Azure AD to enable 1-click authentication to your app or Trial does the following:  
* Streamlines the customer experience from Marketplace to Trial.  
* Maintains the feel of an 'in-product experience' even when the user is redirected from Marketplace to your domain or Trial environment.  
* Decreases the likelihood of abandonment on redirect because there is not an additional sign-in step.  
* Reduces deployment barriers for the large population of Azure AD users.  

## Certifying your Azure AD integration for Marketplace  

Certify your Azure AD integration in a few different ways, depending on whether your application is single-tenant or multi-tenant, and whether you are new to Azure AD federated single sign-on (SSO), or already support it.  

**For multi-tenant applications:**  

If you already support Azure AD, do the following:
1.    Register your application in the Azure portal
2.    Enable the multi-tenancy support feature in Azure AD to get a 'one-click' trial experience. More specific information can be found [here](../active-directory/develop/active-directory-integrating-applications.md).  

If you are new to Azure AD Federated SSO, do the following: 
1.  Register your application in the Azure portal
2.  Develop SSO with Azure AD using [OpenID Connect](../active-directory/develop/active-directory-protocols-openid-connect-code.md) or [OAuth 2.0](../active-directory/develop/active-directory-protocols-oauth-code.md).
3.  Enable multi-tenancy support feature in AAD to get 'one-click' trial experience More specific information can be found [here](../active-directory/develop/active-directory-devhowto-appsource-certified.md).  

**For single-tenant application, use any of the following options:**  
* Add users to your directory as guest users using [Azure B2B](../active-directory/active-directory-b2b-what-is-azure-ad-b2b.md)
* Manually provision trials for customers by using 'Contact Me'
* Develop a per-customer 'Test Drive'
* Build a multi-tenant sample demo app with SSO

## SaaS Subscriptions

Use SaaS app offer type to enable your customer to buy your SaaS-based, technical solution as a subscription. The following requirements must be met for your SaaS app:
- Price and bill the service at a flat (monthly or yearly), or at a per-user rate.
- Provide a method to upgrade or cancel the service at any time.
Microsoft hosts the commerce transaction. Microsoft bills your customer on your behalf. To offer a SaaS App as a subscription, you must integrate with the SaaS fulfillment APIs.  Your service must support provisioning, upgrading, and canceling.

| Requirement | Details |  
|:--- |:--- |  
|Billing and metering | Your offer is priced based on the pricing model you select before publishing (flat rate or per-user).  If using the flat rate model, you can optionally include additional dimensions used to charge customers for usage not included in the flat rate. |  
|Cancellation | Your offer is cancelable by the customer at any time. |  
|Transaction landing page | You host an Azure co-branded transaction landing page where users can create and manage their SaaS service account. |   
| Subscription API | You expose a service that can interact with the SaaS Subscription to create, update, and delete a user account and service plan. Critical API changes must be supported within 24 hours. Non-critical API changes will be released periodically. |  

>[!Note]
>Cloud Solution Providers (CSP) partner channel opt-in is now available.  Please see [Cloud Solution Providers](./cloud-solution-providers.md) for more information on marketing your offer through the Microsoft CSP partner channels.

## Next steps
If you haven't already done so,

* [Learn](https://azuremarketplace.microsoft.com/sell) about the marketplace.

To register in Partner Center, start creating a new offer or working on an existing one:

* [Sign in to Partner Center](https://partner.microsoft.com/dashboard/account/v3/enrollment/introduction/partnership) to create or complete your offer.
* See [create a SaaS application offer](./partner-center-portal/create-new-saas-offer.md) for more information.
