---
title: "WIF API 参考"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a027d902-9314-4bfd-b172-4e81847b1d68
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e3209ac32314e2ac3f4e3e1920991ed29f956832
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="wif-api-reference"></a><span data-ttu-id="11a41-102">WIF API 参考</span><span class="sxs-lookup"><span data-stu-id="11a41-102">WIF API Reference</span></span>
<span data-ttu-id="11a41-103">Windows Identity Foundation (WIF) 类可分为以下程序集：`mscorlib` (mscorlib.dll)、`System.IdentityModel` (System.IdentityModel.dll)、`System.IdentityModel.Services` (System.IdentityModel.Services.dll) 和 `System.ServiceModel` (System.ServiceModel.dll)。</span><span class="sxs-lookup"><span data-stu-id="11a41-103">Windows Identity Foundation (WIF) classes are split across the following assemblies: `mscorlib` (mscorlib.dll), `System.IdentityModel` (System.IdentityModel.dll), `System.IdentityModel.Services` (System.IdentityModel.Services.dll), and `System.ServiceModel` (System.ServiceModel.dll).</span></span> <span data-ttu-id="11a41-104">本主题提供指向 WIF 命名空间的链接和每个命名空间包含的类的简短说明。</span><span class="sxs-lookup"><span data-stu-id="11a41-104">This topic provides links to the WIF namespaces and brief explanations of the classes that each namespace contains.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="11a41-105">以下 `System.IdentityModel` 命名空间包含实现 WCF 基于声明的标识模型的类：<xref:System.IdentityModel.Claims?displayProperty=nameWithType>、<xref:System.IdentityModel.Policy?displayProperty=nameWithType> 和 <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="11a41-105">The following `System.IdentityModel` namespaces contain classes that implement the WCF claims-based identity model: <xref:System.IdentityModel.Claims?displayProperty=nameWithType>, <xref:System.IdentityModel.Policy?displayProperty=nameWithType>, and <xref:System.IdentityModel.Selectors?displayProperty=nameWithType>.</span></span> <span data-ttu-id="11a41-106">从 .NET Framework 4.5 开始，WCF 基于声明的标识模型已被 WIF 取代。</span><span class="sxs-lookup"><span data-stu-id="11a41-106">Starting with .NET Framework 4.5, the WCF claims-based identity model is superseded by WIF.</span></span> <span data-ttu-id="11a41-107">在基于 WIF 生成解决方案时，不应该使用这三个命名空间中的类。</span><span class="sxs-lookup"><span data-stu-id="11a41-107">You should not use classes in these three namespaces when building solutions based on WIF.</span></span>  
  
 <xref:System.IdentityModel?displayProperty=nameWithType>  
 <span data-ttu-id="11a41-108">包含表示 cookie 转换、安全令牌服务和专业 XML 字典读取器的类。</span><span class="sxs-lookup"><span data-stu-id="11a41-108">Contains classes that represent cookie transforms, security token services, and specialized XML dictionary readers.</span></span>  
  
 <xref:System.IdentityModel.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="11a41-109">包含为使用 Windows Identity Foundation (WIF) 生成的应用程序和服务提供配置的类。</span><span class="sxs-lookup"><span data-stu-id="11a41-109">Contains classes that provide configuration for applications and services built using the Windows Identity Foundation (WIF).</span></span> <span data-ttu-id="11a41-110">此命名空间中的类表示 [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 元素下的设置。</span><span class="sxs-lookup"><span data-stu-id="11a41-110">The classes in this namespace represent settings under the [\<identityConfiguration>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
 <xref:System.IdentityModel.Metadata?displayProperty=nameWithType>  
 <span data-ttu-id="11a41-111">包含表示联合元数据文档中的元素。</span><span class="sxs-lookup"><span data-stu-id="11a41-111">Contains classes that represent elements in a Federation Metadata document.</span></span>  
  
 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=nameWithType>  
 <span data-ttu-id="11a41-112">包含表示 WS-Trust 项目的类。</span><span class="sxs-lookup"><span data-stu-id="11a41-112">Contains classes that represent WS-Trust artifacts.</span></span>  
  
 <xref:System.IdentityModel.Services?displayProperty=nameWithType>  
 <span data-ttu-id="11a41-113">包含被动（WS 联合身份验证）方案中使用的类。</span><span class="sxs-lookup"><span data-stu-id="11a41-113">Contains classes that are used in passive (WS-Federation) scenarios.</span></span> <span data-ttu-id="11a41-114">还包含表示 [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) 元素下的设置的某些类。</span><span class="sxs-lookup"><span data-stu-id="11a41-114">Also contains some classes that represent settings under the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="11a41-115">此元素下的设置为应用程序配置 WS 联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="11a41-115">Settings under this element configure WS-Federation for applications.</span></span> <span data-ttu-id="11a41-116">`System.IdentityModel.Services.Configuration` 命名空间包含用于配置 WS 联合身份验证的大多数类。</span><span class="sxs-lookup"><span data-stu-id="11a41-116">The `System.IdentityModel.Services.Configuration` namespace contains most of the classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Configuration?displayProperty=nameWithType>  
 <span data-ttu-id="11a41-117">包含为使用 WS 联合身份验证协议的 WIF 应用程序提供配置的类。</span><span class="sxs-lookup"><span data-stu-id="11a41-117">Contains classes that provide configuration for WIF applications that use the WS-Federation protocol.</span></span> <span data-ttu-id="11a41-118">此命名空间中的类表示 [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) 元素下的设置。</span><span class="sxs-lookup"><span data-stu-id="11a41-118">The classes in this namespace represent settings under the [\<system.identityModel.services>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md) element.</span></span> <span data-ttu-id="11a41-119">`System.IdentityModel.Services` 命名空间还包含用于配置 WS 联合身份验证的某些类。</span><span class="sxs-lookup"><span data-stu-id="11a41-119">The `System.IdentityModel.Services` namespace also contains some classes that are used to configure WS-Federation.</span></span>  
  
 <xref:System.IdentityModel.Services.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="11a41-120">包含 Web 场方案专用的安全令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="11a41-120">Contains specialized security token handlers for Web farm scenarios.</span></span>  
  
 <xref:System.IdentityModel.Tokens?displayProperty=nameWithType>  
 <span data-ttu-id="11a41-121">包含表示安全令牌、安全令牌处理程序和其他安全令牌项目的类。</span><span class="sxs-lookup"><span data-stu-id="11a41-121">Contains classes that represent security tokens, security token handlers, and other security token artifacts.</span></span>  
  
 <xref:System.Security.Claims?displayProperty=nameWithType>  
 <span data-ttu-id="11a41-122">包含表示声明、基于声明的标识、基于声明的主体和其他基于声明的标识模型项目。</span><span class="sxs-lookup"><span data-stu-id="11a41-122">Contains classes that represent claims, claims-based identities, claims-based principals, and other claims-based identity model artifacts.</span></span>  
  
 <xref:System.ServiceModel.Security?displayProperty=nameWithType>  
 <span data-ttu-id="11a41-123">包含表示 WCF 协定、通道、服务主机和主动 (WS-Trust) 方案中使用的其他项目的类。</span><span class="sxs-lookup"><span data-stu-id="11a41-123">Contains classes that represent WCF contracts, channels, service hosts and other artifacts that are used in active (WS-Trust) scenarios.</span></span> <span data-ttu-id="11a41-124">命名空间还包括特定于 Windows Communication Foundation (WCF) 并不被 WIF 使用的类。</span><span class="sxs-lookup"><span data-stu-id="11a41-124">This namespace also contains classes that are specific to Windows Communication Foundation (WCF) and that are not used by WIF.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a41-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="11a41-125">See Also</span></span>  
 [<span data-ttu-id="11a41-126">WIF 配置参考</span><span class="sxs-lookup"><span data-stu-id="11a41-126">WIF Configuration Reference</span></span>](../../../docs/framework/security/wif-configuration-reference.md)  
 [<span data-ttu-id="11a41-127">WIF 3.5 和 WIF 4.5 之间的命名空间映射</span><span class="sxs-lookup"><span data-stu-id="11a41-127">Namespace Mapping between WIF 3.5 and WIF 4.5</span></span>](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)
