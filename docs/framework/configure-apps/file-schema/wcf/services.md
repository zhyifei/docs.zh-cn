---
title: <services>
ms.date: 03/30/2017
ms.assetid: 80d76ba9-2058-48ad-9b91-5e4be7e5c113
ms.openlocfilehash: 2db168d48e3959a7d80a10ca27134f58e3fcb2de
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758153"
---
# <a name="services"></a><span data-ttu-id="d5f5b-101">\<services></span><span class="sxs-lookup"><span data-stu-id="d5f5b-101">\<services></span></span>
<span data-ttu-id="d5f5b-102">服务是在配置文件的 `services` 节中定义的。</span><span class="sxs-lookup"><span data-stu-id="d5f5b-102">Services are defined in the `services` section of the configuration file.</span></span> <span data-ttu-id="d5f5b-103">每个服务都有自己的 `service` 配置节。</span><span class="sxs-lookup"><span data-stu-id="d5f5b-103">Each service has its own `service` configuration section.</span></span>  
  
 <span data-ttu-id="d5f5b-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d5f5b-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5f5b-105">语法</span><span class="sxs-lookup"><span data-stu-id="d5f5b-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service>
    </service>
  </services>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5f5b-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d5f5b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="d5f5b-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d5f5b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5f5b-108">特性</span><span class="sxs-lookup"><span data-stu-id="d5f5b-108">Attributes</span></span>  
 <span data-ttu-id="d5f5b-109">None</span><span class="sxs-lookup"><span data-stu-id="d5f5b-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d5f5b-110">子元素</span><span class="sxs-lookup"><span data-stu-id="d5f5b-110">Child Elements</span></span>  
  
|<span data-ttu-id="d5f5b-111">元素</span><span class="sxs-lookup"><span data-stu-id="d5f5b-111">Element</span></span>|<span data-ttu-id="d5f5b-112">描述</span><span class="sxs-lookup"><span data-stu-id="d5f5b-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5f5b-113">\<service></span><span class="sxs-lookup"><span data-stu-id="d5f5b-113">\<service></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|<span data-ttu-id="d5f5b-114">定义特定服务的服务协定、行为和终结点。</span><span class="sxs-lookup"><span data-stu-id="d5f5b-114">Define the service contract, behavior, and endpoints of the particular service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d5f5b-115">父元素</span><span class="sxs-lookup"><span data-stu-id="d5f5b-115">Parent Elements</span></span>  
  
|<span data-ttu-id="d5f5b-116">元素</span><span class="sxs-lookup"><span data-stu-id="d5f5b-116">Element</span></span>|<span data-ttu-id="d5f5b-117">描述</span><span class="sxs-lookup"><span data-stu-id="d5f5b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5f5b-118">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d5f5b-118">\<system.serviceModel></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|<span data-ttu-id="d5f5b-119">所有 Windows Communication Foundation (WCF) 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="d5f5b-119">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d5f5b-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5f5b-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServicesSection>
