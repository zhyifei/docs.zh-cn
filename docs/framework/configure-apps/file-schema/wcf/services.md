---
title: "&lt;服务&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46a2e0d810068db6409bc7b0fd1443a41c3d3ec3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltservicesgt"></a><span data-ttu-id="7f24d-102">&lt;服务&gt;</span><span class="sxs-lookup"><span data-stu-id="7f24d-102">&lt;services&gt;</span></span>
<span data-ttu-id="7f24d-103">服务是在配置文件的 `services` 节中定义的。</span><span class="sxs-lookup"><span data-stu-id="7f24d-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="7f24d-104">每个服务都有自己的 `service` 配置节。</span><span class="sxs-lookup"><span data-stu-id="7f24d-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="7f24d-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="7f24d-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f24d-106">语法</span><span class="sxs-lookup"><span data-stu-id="7f24d-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
        <service>  
        </service>  
        </services>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f24d-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7f24d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7f24d-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7f24d-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f24d-109">特性</span><span class="sxs-lookup"><span data-stu-id="7f24d-109">Attributes</span></span>  
 <span data-ttu-id="7f24d-110">无</span><span class="sxs-lookup"><span data-stu-id="7f24d-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7f24d-111">子元素</span><span class="sxs-lookup"><span data-stu-id="7f24d-111">Child Elements</span></span>  
  
|<span data-ttu-id="7f24d-112">元素</span><span class="sxs-lookup"><span data-stu-id="7f24d-112">Element</span></span>|<span data-ttu-id="7f24d-113">描述</span><span class="sxs-lookup"><span data-stu-id="7f24d-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f24d-114">\<服务 ></span><span class="sxs-lookup"><span data-stu-id="7f24d-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="7f24d-115">定义特定服务的服务协定、行为和终结点。</span><span class="sxs-lookup"><span data-stu-id="7f24d-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f24d-116">父元素</span><span class="sxs-lookup"><span data-stu-id="7f24d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="7f24d-117">元素</span><span class="sxs-lookup"><span data-stu-id="7f24d-117">Element</span></span>|<span data-ttu-id="7f24d-118">描述</span><span class="sxs-lookup"><span data-stu-id="7f24d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f24d-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7f24d-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="7f24d-120">所有 Windows Communication Foundation (WCF) 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="7f24d-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7f24d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f24d-121">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServicesSection>
