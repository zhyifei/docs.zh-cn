---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: c00d5fe3e8b2ba05843e09aca6aaa79386541bad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937193"
---
# <a name="services"></a><span data-ttu-id="43d12-101">\<services></span><span class="sxs-lookup"><span data-stu-id="43d12-101">\<services></span></span>
<span data-ttu-id="43d12-102">服务是在配置文件的 `services` 节中定义的。</span><span class="sxs-lookup"><span data-stu-id="43d12-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="43d12-103">每个服务都有自己的 `service` 配置节。</span><span class="sxs-lookup"><span data-stu-id="43d12-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="43d12-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="43d12-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43d12-105">语法</span><span class="sxs-lookup"><span data-stu-id="43d12-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43d12-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="43d12-106">Attributes and Elements</span></span>  
 <span data-ttu-id="43d12-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="43d12-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43d12-108">特性</span><span class="sxs-lookup"><span data-stu-id="43d12-108">Attributes</span></span>  
 <span data-ttu-id="43d12-109">无</span><span class="sxs-lookup"><span data-stu-id="43d12-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="43d12-110">子元素</span><span class="sxs-lookup"><span data-stu-id="43d12-110">Child Elements</span></span>  
  
|<span data-ttu-id="43d12-111">元素</span><span class="sxs-lookup"><span data-stu-id="43d12-111">Element</span></span>|<span data-ttu-id="43d12-112">描述</span><span class="sxs-lookup"><span data-stu-id="43d12-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43d12-113">\<service></span><span class="sxs-lookup"><span data-stu-id="43d12-113">\<service></span></span>](service.md)|<span data-ttu-id="43d12-114">定义特定服务的服务协定、行为和终结点。</span><span class="sxs-lookup"><span data-stu-id="43d12-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="43d12-115">父元素</span><span class="sxs-lookup"><span data-stu-id="43d12-115">Parent Elements</span></span>  
  
|<span data-ttu-id="43d12-116">元素</span><span class="sxs-lookup"><span data-stu-id="43d12-116">Element</span></span>|<span data-ttu-id="43d12-117">描述</span><span class="sxs-lookup"><span data-stu-id="43d12-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43d12-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="43d12-118">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="43d12-119">所有 Windows Communication Foundation (WCF) 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="43d12-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="43d12-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="43d12-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
