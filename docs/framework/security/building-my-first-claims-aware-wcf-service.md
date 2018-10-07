---
title: 生成我的第一个声明感知 WCF 服务
ms.date: 03/30/2017
ms.assetid: e0e6d091-9a97-4888-8f2c-cbcee42d90ee
author: BrucePerlerMS
ms.openlocfilehash: e6324087afa62f276766c733284dc69e425b89bc
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836228"
---
# <a name="building-my-first-claims-aware-wcf-service"></a><span data-ttu-id="6153a-102">生成我的第一个声明感知 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="6153a-102">Building My First Claims-Aware WCF Service</span></span>
## <a name="applies-to"></a><span data-ttu-id="6153a-103">适用于</span><span class="sxs-lookup"><span data-stu-id="6153a-103">Applies To</span></span>  
  
-   <span data-ttu-id="6153a-104">Windows Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="6153a-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="6153a-105">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="6153a-105">Windows Communication Foundation (WCF)</span></span>  
  
## <a name="overview"></a><span data-ttu-id="6153a-106">概述</span><span class="sxs-lookup"><span data-stu-id="6153a-106">Overview</span></span>  
 <span data-ttu-id="6153a-107">本主题概述了使用 WIF 生成声明感知 WCF 服务的方案。</span><span class="sxs-lookup"><span data-stu-id="6153a-107">This topic outlines the scenario of building claims-aware WCF services using WIF.</span></span> <span data-ttu-id="6153a-108">声明感知 Web 服务方案中通常涉及三个参与者：Web 服务本身、最终用户和安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="6153a-108">There are usually three participants in a claims-aware web service scenario: the web service itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="6153a-109">下图描述了此方案：</span><span class="sxs-lookup"><span data-stu-id="6153a-109">The following figure describes this scenario:</span></span>  
  
 <span data-ttu-id="6153a-110">![WIF 基本声明感知 WCF 服务](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span><span class="sxs-lookup"><span data-stu-id="6153a-110">![WIF Basic Claims Aware WCF Service](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span></span>  
  
1.  <span data-ttu-id="6153a-111">WCF 服务客户端（有时称为代理）使用 WIF 将凭据发送到 STS，在成功完成身份验证后，STS 将向此代理颁发令牌。</span><span class="sxs-lookup"><span data-stu-id="6153a-111">The WCF service client (sometimes called agent) uses WIF to send credentials to the STS and upon successful authentication, the agent is issued a token by the STS.</span></span>  
  
2.  <span data-ttu-id="6153a-112">代理会将 STS 颁发的令牌发送到 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="6153a-112">The agent sends this STS-issued token to the WCF service.</span></span>  
  
3.  <span data-ttu-id="6153a-113">声明感知 WCF 服务将配置为信任此 STS 及其颁发的令牌。</span><span class="sxs-lookup"><span data-stu-id="6153a-113">The claims-aware WCF service is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="6153a-114">声明感知 WCF 服务使用 WIF 验证此令牌并对其进行分析。</span><span class="sxs-lookup"><span data-stu-id="6153a-114">The claims-aware WCF service uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="6153a-115">开发人员使用适当的 WIF API 和类型（例如 ClaimsPrincipal）来满足应用程序的需要，如对其实现授权。</span><span class="sxs-lookup"><span data-stu-id="6153a-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincipal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="6153a-116">从 .NET 4.5 开始，WIF 便已成为 .NET Framework 包的一部分。</span><span class="sxs-lookup"><span data-stu-id="6153a-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="6153a-117">通过使 WIF 类直接在框架中可用，可以在 .NET 中更深度地集成基于声明的标识，从而更轻松地使用声明。</span><span class="sxs-lookup"><span data-stu-id="6153a-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="6153a-118">如果使用 WIF 4.5，则无需安装任何带外组件即可开始开发声明感知 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6153a-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="6153a-119">WIF 类现在分布在各种程序集中，主要为 System.Security.Claims、System.IdentityModel 和 System.IdentityModel.Services。</span><span class="sxs-lookup"><span data-stu-id="6153a-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="6153a-120">STS 是一项在身份验证成功后颁发令牌的服务。</span><span class="sxs-lookup"><span data-stu-id="6153a-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="6153a-121">Microsoft 提供两个行业标准 STS：</span><span class="sxs-lookup"><span data-stu-id="6153a-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   [<span data-ttu-id="6153a-122">Active Directory 联合身份验证服务 (AD FS) 2.0</span><span class="sxs-lookup"><span data-stu-id="6153a-122">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/?LinkID=247516)
  
-   [<span data-ttu-id="6153a-123">Windows Azure 访问控制服务 (ACS)</span><span class="sxs-lookup"><span data-stu-id="6153a-123">Windows Azure Access Control Service (ACS)</span></span>](https://go.microsoft.com/fwlink/?LinkID=247517)
  
 <span data-ttu-id="6153a-124">AD FS 2.0 是 Windows Server R2 的一部分并可用作本地方案的 STS。</span><span class="sxs-lookup"><span data-stu-id="6153a-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="6153a-125">Azure Active Directory 访问控制（也称为访问控制服务或 ACS）是作为 Microsoft Azure 的一部分提供的云服务。</span><span class="sxs-lookup"><span data-stu-id="6153a-125">Azure Active Directory Access Control (also known as Access Control Service or ACS) is a cloud service, offered as part of Microsoft Azure.</span></span> <span data-ttu-id="6153a-126">出于测试或教学目的，你还可以使用其他 STS 以生成声明感知应用程序。</span><span class="sxs-lookup"><span data-stu-id="6153a-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="6153a-127">例如，可以使用属于本地开发 STS[标识和访问工具，用于 Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849)即联机免费提供。</span><span class="sxs-lookup"><span data-stu-id="6153a-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="6153a-128">若要生成第一个声明感知 WCF 服务使用 WIF，请参阅[如何： 为 WCF Web 服务应用程序启用 WIF](../../../docs/framework/security/how-to-enable-wif-for-a-wcf-web-service-application.md)。</span><span class="sxs-lookup"><span data-stu-id="6153a-128">To build your first claims-aware WCF service using WIF, see [How To: Enable WIF for a WCF Web Service Application](../../../docs/framework/security/how-to-enable-wif-for-a-wcf-web-service-application.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6153a-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="6153a-129">See Also</span></span>  
 [<span data-ttu-id="6153a-130">WIF 入门</span><span class="sxs-lookup"><span data-stu-id="6153a-130">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)
