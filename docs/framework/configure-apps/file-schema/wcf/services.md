---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 1f9cb6c95fa14a5b8a55cc561699e2a07e1dc80c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399585"
---
# <a name="services"></a><span data-ttu-id="5dbe8-101">\<services></span><span class="sxs-lookup"><span data-stu-id="5dbe8-101">\<services></span></span>
<span data-ttu-id="5dbe8-102">服务是在配置文件的 `services` 节中定义的。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="5dbe8-103">每个服务都有自己的 `service` 配置节。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-103">Each service has its own `service` configuration section.</span></span>  
  
<span data-ttu-id="5dbe8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5dbe8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5dbe8-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5dbe8-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5dbe8-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<服务 >**</span><span class="sxs-lookup"><span data-stu-id="5dbe8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<services>**</span></span>  
## <a name="syntax"></a><span data-ttu-id="5dbe8-107">语法</span><span class="sxs-lookup"><span data-stu-id="5dbe8-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5dbe8-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5dbe8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5dbe8-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5dbe8-110">特性</span><span class="sxs-lookup"><span data-stu-id="5dbe8-110">Attributes</span></span>  
 <span data-ttu-id="5dbe8-111">无</span><span class="sxs-lookup"><span data-stu-id="5dbe8-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5dbe8-112">子元素</span><span class="sxs-lookup"><span data-stu-id="5dbe8-112">Child Elements</span></span>  
  
|<span data-ttu-id="5dbe8-113">元素</span><span class="sxs-lookup"><span data-stu-id="5dbe8-113">Element</span></span>|<span data-ttu-id="5dbe8-114">描述</span><span class="sxs-lookup"><span data-stu-id="5dbe8-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5dbe8-115">\<service></span><span class="sxs-lookup"><span data-stu-id="5dbe8-115">\<service></span></span>](service.md)|<span data-ttu-id="5dbe8-116">定义特定服务的服务协定、行为和终结点。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-116">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5dbe8-117">父元素</span><span class="sxs-lookup"><span data-stu-id="5dbe8-117">Parent Elements</span></span>  
  
|<span data-ttu-id="5dbe8-118">元素</span><span class="sxs-lookup"><span data-stu-id="5dbe8-118">Element</span></span>|<span data-ttu-id="5dbe8-119">描述</span><span class="sxs-lookup"><span data-stu-id="5dbe8-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5dbe8-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5dbe8-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="5dbe8-121">所有 Windows Communication Foundation (WCF) 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="5dbe8-121">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5dbe8-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="5dbe8-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
