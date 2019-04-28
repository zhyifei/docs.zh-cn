---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 266b33e9b0386d0346a86ba8bd82cc65def4f0c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673051"
---
# <a name="endtoendtracing"></a><span data-ttu-id="8a201-101">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="8a201-101">\<endToEndTracing></span></span>
<span data-ttu-id="8a201-102">一个配置元素，用于启用和禁用服务应用程序运行过程中端对端跟踪的不同方面。</span><span class="sxs-lookup"><span data-stu-id="8a201-102">A configuration element that allows you to enable and disable different aspects of end-to-end tracing during the running of a service application.</span></span>  
  
 <span data-ttu-id="8a201-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8a201-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="8a201-104">\<diagnostic></span><span class="sxs-lookup"><span data-stu-id="8a201-104">\<diagnostic></span></span>  
<span data-ttu-id="8a201-105">\<endToEndTracing></span><span class="sxs-lookup"><span data-stu-id="8a201-105">\<endToEndTracing></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a201-106">语法</span><span class="sxs-lookup"><span data-stu-id="8a201-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <diagnostics>
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
  </diagnostics>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a201-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8a201-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8a201-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8a201-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a201-109">特性</span><span class="sxs-lookup"><span data-stu-id="8a201-109">Attributes</span></span>  
  
|<span data-ttu-id="8a201-110">特性</span><span class="sxs-lookup"><span data-stu-id="8a201-110">Attribute</span></span>|<span data-ttu-id="8a201-111">描述</span><span class="sxs-lookup"><span data-stu-id="8a201-111">Description</span></span>|  
|---------------|-----------------|  
|`activityTracing`|<span data-ttu-id="8a201-112">一个布尔值，指定是否启用活动跟踪。</span><span class="sxs-lookup"><span data-stu-id="8a201-112">A Boolean value that specifies whether activity tracing is enabled.</span></span>|  
|`messageFlowTracing`|<span data-ttu-id="8a201-113">一个布尔值，指定是否启用消息流跟踪。</span><span class="sxs-lookup"><span data-stu-id="8a201-113">A Boolean value that specifies whether message flow tracing in enabled.</span></span>|  
|`propagateActivity`|<span data-ttu-id="8a201-114">一个布尔值，指定是否将传播特性设置为 true。</span><span class="sxs-lookup"><span data-stu-id="8a201-114">A Boolean value that specifies whether the propagate attribute is set to true.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a201-115">子元素</span><span class="sxs-lookup"><span data-stu-id="8a201-115">Child Elements</span></span>  
 <span data-ttu-id="8a201-116">无。</span><span class="sxs-lookup"><span data-stu-id="8a201-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a201-117">父元素</span><span class="sxs-lookup"><span data-stu-id="8a201-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8a201-118">元素</span><span class="sxs-lookup"><span data-stu-id="8a201-118">Element</span></span>|<span data-ttu-id="8a201-119">描述</span><span class="sxs-lookup"><span data-stu-id="8a201-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a201-120">\<diagnostics></span><span class="sxs-lookup"><span data-stu-id="8a201-120">\<diagnostics></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|<span data-ttu-id="8a201-121">定义管理员运行时检查和控制的 WCF 设置。</span><span class="sxs-lookup"><span data-stu-id="8a201-121">Defines WCF settings for runtime inspection and control for the administrator.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a201-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a201-122">See also</span></span>

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [<span data-ttu-id="8a201-123">端到端跟踪</span><span class="sxs-lookup"><span data-stu-id="8a201-123">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
