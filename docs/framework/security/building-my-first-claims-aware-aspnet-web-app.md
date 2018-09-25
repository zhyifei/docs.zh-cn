---
title: 生成我的第一个声明感知 ASP.NET Web 应用程序
ms.date: 03/30/2017
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
author: BrucePerlerMS
ms.openlocfilehash: 76b02a0e6869b0d4de181b59296a0858aa80948c
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47108788"
---
# <a name="building-my-first-claims-aware-aspnet-web-application"></a><span data-ttu-id="99df5-102">生成我的第一个声明感知 ASP.NET Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="99df5-102">Building My First Claims-Aware ASP.NET Web Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="99df5-103">适用于</span><span class="sxs-lookup"><span data-stu-id="99df5-103">Applies To</span></span>  
  
-   <span data-ttu-id="99df5-104">Windows Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="99df5-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="99df5-105">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="99df5-105">ASP.NET</span></span>  
  
 <span data-ttu-id="99df5-106">本主题概述了使用 WIF 生成声明感知 ASP.NET Web 应用程序的方案。</span><span class="sxs-lookup"><span data-stu-id="99df5-106">This topic outlines the scenario of building claims-aware ASP.NET web applications using WIF.</span></span> <span data-ttu-id="99df5-107">声明感知应用程序方案通常涉及三个参与者：应用程序本身、最终用户和安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="99df5-107">There are usually three participants in a claims-aware application scenario: the application itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="99df5-108">下图描述了此方案：</span><span class="sxs-lookup"><span data-stu-id="99df5-108">The following figure describes this scenario:</span></span>  
  
 <span data-ttu-id="99df5-109">![WIF 基本 Web 应用](../../../docs/framework/security/media/wifbasicwebapp.gif "WIFBasicWebApp")</span><span class="sxs-lookup"><span data-stu-id="99df5-109">![WIF Basic Web App](../../../docs/framework/security/media/wifbasicwebapp.gif "WIFBasicWebApp")</span></span>  
  
1.  <span data-ttu-id="99df5-110">声明感知应用程序使用 WIF 来标识未经身份验证的请求并将这些请求重定向到 STS。</span><span class="sxs-lookup"><span data-stu-id="99df5-110">The claims-aware application uses WIF to identify unauthenticated requests and to redirect them to the STS.</span></span>  
  
2.  <span data-ttu-id="99df5-111">最终用户向 STS 提供凭据，在成功完成身份验证后，STS 将向用户颁发令牌。</span><span class="sxs-lookup"><span data-stu-id="99df5-111">The end user provides credentials to the STS and upon successful authentication the user is issued a token by the STS.</span></span>  
  
3.  <span data-ttu-id="99df5-112">使用请求中的 STS 颁发的令牌将用户从 STS 重定向到声明感知应用程序。</span><span class="sxs-lookup"><span data-stu-id="99df5-112">The user is redirected from the STS to the claims-aware application with the STS-issued token in the request.</span></span>  
  
4.  <span data-ttu-id="99df5-113">声明感知应用程序将配置为信任此 STS 及其颁发的令牌。</span><span class="sxs-lookup"><span data-stu-id="99df5-113">The claims-aware application is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="99df5-114">声明感知应用程序使用 WIF 验证此令牌并对其进行分析。</span><span class="sxs-lookup"><span data-stu-id="99df5-114">The claims-aware application uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="99df5-115">开发人员使用适当的 WIF API 和类型（例如 ClaimsPrincpal）来满足应用程序的需要，如对其实现授权。</span><span class="sxs-lookup"><span data-stu-id="99df5-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincpal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="99df5-116">从 .NET 4.5 开始，WIF 便已成为 .NET Framework 包的一部分。</span><span class="sxs-lookup"><span data-stu-id="99df5-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="99df5-117">通过使 WIF 类直接在框架中可用，可以在 .NET 中更深度地集成基于声明的标识，从而更轻松地使用声明。</span><span class="sxs-lookup"><span data-stu-id="99df5-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="99df5-118">如果使用 WIF 4.5，则无需安装任何带外组件即可开始开发声明感知 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="99df5-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="99df5-119">WIF 类现在分布在各种程序集中，主要为 System.Security.Claims、System.IdentityModel 和 System.IdentityModel.Services。</span><span class="sxs-lookup"><span data-stu-id="99df5-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="99df5-120">STS 是一项在身份验证成功后颁发令牌的服务。</span><span class="sxs-lookup"><span data-stu-id="99df5-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="99df5-121">Microsoft 提供两个行业标准 STS：</span><span class="sxs-lookup"><span data-stu-id="99df5-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   [<span data-ttu-id="99df5-122">Active Directory 联合身份验证服务 (AD FS) 2.0</span><span class="sxs-lookup"><span data-stu-id="99df5-122">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/?LinkID=247516)
  
-   [<span data-ttu-id="99df5-123">Windows Azure 访问控制服务 (ACS)</span><span class="sxs-lookup"><span data-stu-id="99df5-123">Windows Azure Access Control Service (ACS)</span></span>](https://go.microsoft.com/fwlink/?LinkID=247517)
  
 <span data-ttu-id="99df5-124">AD FS 2.0 是 Windows Server R2 的一部分并可用作本地方案的 STS。</span><span class="sxs-lookup"><span data-stu-id="99df5-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="99df5-125">ACS 是一项云服务，它作为 Microsoft Azure 平台的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="99df5-125">ACS is a cloud service, offered as part of the Windows Azure Platform.</span></span> <span data-ttu-id="99df5-126">出于测试或教学目的，你还可以使用其他 STS 以生成声明感知应用程序。</span><span class="sxs-lookup"><span data-stu-id="99df5-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="99df5-127">例如，可以使用属于本地开发 STS[标识和访问工具，用于 Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849)即联机免费提供。</span><span class="sxs-lookup"><span data-stu-id="99df5-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="99df5-128">若要使用 WIF 生成您的第一个声明感知 ASP.NET 应用程序，请按照下列主题之一中的说明进行操作：</span><span class="sxs-lookup"><span data-stu-id="99df5-128">To build your first claims-aware ASP.NET application using WIF, follow the instructions in one of the following:</span></span>  
  
-   [<span data-ttu-id="99df5-129">如何：使用 WIF 生成声明感知 ASP.NET MVC Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="99df5-129">How To: Build Claims-Aware ASP.NET MVC Web Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
-   [<span data-ttu-id="99df5-130">如何：使用 WIF 生成声明感知 ASP.NET Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="99df5-130">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
-   [<span data-ttu-id="99df5-131">如何：使用基于表单的身份验证生成声明感知 ASP.NET 应用程序</span><span class="sxs-lookup"><span data-stu-id="99df5-131">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>](../../../docs/framework/security/claims-aware-aspnet-app-forms-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="99df5-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="99df5-132">See Also</span></span>  
 [<span data-ttu-id="99df5-133">WIF 入门</span><span class="sxs-lookup"><span data-stu-id="99df5-133">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)
