---
title: '&lt;services&gt;'
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 7b26224f1217e7f73a529c082c2c9272ec189a5a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573252"
---
# <a name="ltservicesgt"></a><span data-ttu-id="08cd7-102">&lt;services&gt;</span><span class="sxs-lookup"><span data-stu-id="08cd7-102">&lt;services&gt;</span></span>
<span data-ttu-id="08cd7-103">服务是在配置文件的 `services` 节中定义的。</span><span class="sxs-lookup"><span data-stu-id="08cd7-103">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="08cd7-104">每个服务都有自己的 `service` 配置节。</span><span class="sxs-lookup"><span data-stu-id="08cd7-104">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="08cd7-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="08cd7-105">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08cd7-106">语法</span><span class="sxs-lookup"><span data-stu-id="08cd7-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08cd7-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="08cd7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="08cd7-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="08cd7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08cd7-109">特性</span><span class="sxs-lookup"><span data-stu-id="08cd7-109">Attributes</span></span>  
 <span data-ttu-id="08cd7-110">无</span><span class="sxs-lookup"><span data-stu-id="08cd7-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="08cd7-111">子元素</span><span class="sxs-lookup"><span data-stu-id="08cd7-111">Child Elements</span></span>  
  
|<span data-ttu-id="08cd7-112">元素</span><span class="sxs-lookup"><span data-stu-id="08cd7-112">Element</span></span>|<span data-ttu-id="08cd7-113">描述</span><span class="sxs-lookup"><span data-stu-id="08cd7-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08cd7-114">\<service></span><span class="sxs-lookup"><span data-stu-id="08cd7-114">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="08cd7-115">定义特定服务的服务协定、行为和终结点。</span><span class="sxs-lookup"><span data-stu-id="08cd7-115">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="08cd7-116">父元素</span><span class="sxs-lookup"><span data-stu-id="08cd7-116">Parent Elements</span></span>  
  
|<span data-ttu-id="08cd7-117">元素</span><span class="sxs-lookup"><span data-stu-id="08cd7-117">Element</span></span>|<span data-ttu-id="08cd7-118">描述</span><span class="sxs-lookup"><span data-stu-id="08cd7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08cd7-119">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="08cd7-119">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="08cd7-120">所有 Windows Communication Foundation (WCF) 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="08cd7-120">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08cd7-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="08cd7-121">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServicesSection>
