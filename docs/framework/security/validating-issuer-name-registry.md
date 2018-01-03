---
title: "验证颁发者名称注册表"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4644dd1-dead-48ff-abeb-7bffae69a6ac
caps.latest.revision: "4"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d131a032aa2747bda83874e8dd744588dfe07dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="validating-issuer-name-registry"></a><span data-ttu-id="25193-102">验证颁发者名称注册表</span><span class="sxs-lookup"><span data-stu-id="25193-102">Validating Issuer Name Registry</span></span>
<span data-ttu-id="25193-103">Windows Identity Foundation 的验证颁发者名称注册表 (VINR) 可启用多租户应用程序，以确保传入标记已由受信任的租户和标识提供程序颁发。</span><span class="sxs-lookup"><span data-stu-id="25193-103">The Validating Issuer Name Registry (VINR) for Windows Identity Foundation enables multi-tenant applications to ensure that an incoming token has been issued by a trusted tenant and identity provider.</span></span> <span data-ttu-id="25193-104">此功能对于使用 Microsoft Azure Active Directory 的多租户应用程序尤其有用，因为由 Microsoft Azure AD 颁发的所有标记都使用同一证书进行签名。</span><span class="sxs-lookup"><span data-stu-id="25193-104">This functionality is particularly useful for multi-tenant applications that use Windows Azure Active Directory because all tokens issued by Windows Azure AD are signed using the same certificate.</span></span> <span data-ttu-id="25193-105">为了区分来自使用同一证书的多个租户的请求（它们具有相同的指纹），您的应用程序必须保持每个租户的颁发者名称以便执行验证逻辑。</span><span class="sxs-lookup"><span data-stu-id="25193-105">In order to differentiate between requests from multiple tenants that use the same certificate – and consequently have the same thumbprint – your application must persist the issuer name for each tenant to perform validation logic.</span></span> <span data-ttu-id="25193-106">VINR 可提供此功能，除了配置文件之外，还使您能够在位置中添加自定义验证逻辑或存储颁发者注册表数据。</span><span class="sxs-lookup"><span data-stu-id="25193-106">The VINR provides this functionality, and it also enables you to add custom validation logic or to store the issuer registry data in locations other than a configuration file.</span></span> <span data-ttu-id="25193-107">该扩展可添加到应用程序的 WIF 管道中，也可单独进行使用。</span><span class="sxs-lookup"><span data-stu-id="25193-107">The extension can be added to your application’s WIF pipeline or it can be used independently.</span></span>  
  
 <span data-ttu-id="25193-108">VINR 作为 NuGet 程序包提供。</span><span class="sxs-lookup"><span data-stu-id="25193-108">The VINR is available as a NuGet package.</span></span> <span data-ttu-id="25193-109">请参阅[下载验证颁发者名称注册表包](../../../docs/framework/security/downloading-the-validating-issuer-name-registry-package.md)，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="25193-109">See [Downloading the Validating Issuer Name Registry Package](../../../docs/framework/security/downloading-the-validating-issuer-name-registry-package.md) for more information.</span></span>  
  
## <a name="scenarios"></a><span data-ttu-id="25193-110">方案</span><span class="sxs-lookup"><span data-stu-id="25193-110">Scenarios</span></span>  
 <span data-ttu-id="25193-111">VINR 支持以下关键方案：</span><span class="sxs-lookup"><span data-stu-id="25193-111">The VINR enables the following key scenario:</span></span>  
  
-   <span data-ttu-id="25193-112">在多租户应用程序中验证标记：在此方案中，一家名为 Litware 的公司开发了一个使用标识提供者（如 Microsoft Azure AD）的多租户应用程序。</span><span class="sxs-lookup"><span data-stu-id="25193-112">**Validate a Token in a Multi-Tenant Application**: In this scenario, a company named Litware has developed a multi-tenant application that uses an identity provider such as Windows Azure AD.</span></span> <span data-ttu-id="25193-113">此应用程序为两个客户提供服务：Contoso 和 Fabrikam。</span><span class="sxs-lookup"><span data-stu-id="25193-113">This application serves two customers: Contoso and Fabrikam.</span></span> <span data-ttu-id="25193-114">当针对 Litware 的应用程序对来自 Fabrikam 的用户进行身份验证时，将使用其标准证书对 Microsoft Azure AD 的结果标记进行签名并且 Fabrikam 将发出请求。</span><span class="sxs-lookup"><span data-stu-id="25193-114">When a user from Fabrikam authenticates to Litware’s application, the resulting token from Windows Azure AD is signed using its standard certificate and the request is issued by Fabrikam.</span></span> <span data-ttu-id="25193-115">应用程序需要验证颁发者名称和标记是否有效，并且需要区分使用来自 Microsoft Azure AD 的同一证书进行签名的 Contoso 请求。</span><span class="sxs-lookup"><span data-stu-id="25193-115">The application needs to verify that both the issuer name and the token is valid, and needs to differentiate requests from Contoso that are signed using the same certificate from Windows Azure AD.</span></span> <span data-ttu-id="25193-116">VINR 使得 Litware 的应用程序能够轻松区分和验证来自多个租户（例如 Contoso 和 Fabrikam）的请求。</span><span class="sxs-lookup"><span data-stu-id="25193-116">The VINR makes it easy for Litware’s application to differentiate and validate requests from multiple tenants such as Contoso and Fabrikam.</span></span>  
  
## <a name="features"></a><span data-ttu-id="25193-117">功能</span><span class="sxs-lookup"><span data-stu-id="25193-117">Features</span></span>  
 <span data-ttu-id="25193-118">VINR 具有以下功能：</span><span class="sxs-lookup"><span data-stu-id="25193-118">The VINR offers the following features:</span></span>  
  
-   <span data-ttu-id="25193-119">颁发者名称和多租户应用程序的标记验证：通过确认颁发者名称（租户）来验证传入标记，并验证是否已使用来自标识提供者的有效证书对标记进行签名。</span><span class="sxs-lookup"><span data-stu-id="25193-119">**Issuer Name and Token Validation for Multi-Tenant Applications**: Validates the incoming token by verifying the issuer name (tenant) and whether the token was signed using a valid certificate from the identity provider.</span></span>  
  
-   <span data-ttu-id="25193-120">自定义验证逻辑和数据存储的扩展性：除了默认配置文件之外，还提供扩展性以插入自己的验证逻辑并指定数据存储。</span><span class="sxs-lookup"><span data-stu-id="25193-120">**Extensibility for Custom Validation Logic and Data Stores**: Provides extensibility to inject your own validation logic and to specify a data store other than the default configuration file.</span></span>
