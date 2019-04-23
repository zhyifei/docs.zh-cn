---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: a9c16d1036a8177120cd152d4ac211ad084d588e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150379"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="768a6-101">\<workflowControlEndpoint></span><span class="sxs-lookup"><span data-stu-id="768a6-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="768a6-102">此配置元素定义用于控制工作流实例的执行（创建、运行、挂起、终止等）的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="768a6-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="768a6-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="768a6-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="768a6-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="768a6-104">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="768a6-105">语法</span><span class="sxs-lookup"><span data-stu-id="768a6-105">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="768a6-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="768a6-106">Attributes and Elements</span></span>  
 <span data-ttu-id="768a6-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="768a6-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="768a6-108">特性</span><span class="sxs-lookup"><span data-stu-id="768a6-108">Attributes</span></span>  
  
|<span data-ttu-id="768a6-109">特性</span><span class="sxs-lookup"><span data-stu-id="768a6-109">Attribute</span></span>|<span data-ttu-id="768a6-110">描述</span><span class="sxs-lookup"><span data-stu-id="768a6-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="768a6-111">name</span><span class="sxs-lookup"><span data-stu-id="768a6-111">name</span></span>|<span data-ttu-id="768a6-112">一个字符串，指定标准终结点的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="768a6-112">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="768a6-113">此名称在服务终结点的 `endpointConfiguration` 特性中用于将标准终结点链接到其配置。</span><span class="sxs-lookup"><span data-stu-id="768a6-113">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="768a6-114">子元素</span><span class="sxs-lookup"><span data-stu-id="768a6-114">Child Elements</span></span>  
 <span data-ttu-id="768a6-115">无。</span><span class="sxs-lookup"><span data-stu-id="768a6-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="768a6-116">父元素</span><span class="sxs-lookup"><span data-stu-id="768a6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="768a6-117">元素</span><span class="sxs-lookup"><span data-stu-id="768a6-117">Element</span></span>|<span data-ttu-id="768a6-118">描述</span><span class="sxs-lookup"><span data-stu-id="768a6-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="768a6-119">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="768a6-119">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="768a6-120">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="768a6-120">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="768a6-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="768a6-121">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
