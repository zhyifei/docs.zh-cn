---
title: <workflowControlEndpoint>
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 670c1573fe4378a18c19d0a58fe58241745725bd
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854782"
---
# <a name="workflowcontrolendpoint"></a><span data-ttu-id="1a6d4-101">\<workflowControlEndpoint></span><span class="sxs-lookup"><span data-stu-id="1a6d4-101">\<workflowControlEndpoint></span></span>
<span data-ttu-id="1a6d4-102">此配置元素定义用于控制工作流实例的执行（创建、运行、挂起、终止等）的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="1a6d4-102">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="1a6d4-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1a6d4-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1a6d4-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1a6d4-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1a6d4-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="1a6d4-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="1a6d4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowControlEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="1a6d4-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowControlEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a6d4-107">语法</span><span class="sxs-lookup"><span data-stu-id="1a6d4-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a6d4-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1a6d4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1a6d4-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1a6d4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a6d4-110">特性</span><span class="sxs-lookup"><span data-stu-id="1a6d4-110">Attributes</span></span>  
  
|<span data-ttu-id="1a6d4-111">特性</span><span class="sxs-lookup"><span data-stu-id="1a6d4-111">Attribute</span></span>|<span data-ttu-id="1a6d4-112">描述</span><span class="sxs-lookup"><span data-stu-id="1a6d4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a6d4-113">NAME</span><span class="sxs-lookup"><span data-stu-id="1a6d4-113">name</span></span>|<span data-ttu-id="1a6d4-114">一个字符串，指定标准终结点的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="1a6d4-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="1a6d4-115">此名称在服务终结点的 `endpointConfiguration` 特性中用于将标准终结点链接到其配置。</span><span class="sxs-lookup"><span data-stu-id="1a6d4-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a6d4-116">子元素</span><span class="sxs-lookup"><span data-stu-id="1a6d4-116">Child Elements</span></span>  
 <span data-ttu-id="1a6d4-117">无。</span><span class="sxs-lookup"><span data-stu-id="1a6d4-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a6d4-118">父元素</span><span class="sxs-lookup"><span data-stu-id="1a6d4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="1a6d4-119">元素</span><span class="sxs-lookup"><span data-stu-id="1a6d4-119">Element</span></span>|<span data-ttu-id="1a6d4-120">描述</span><span class="sxs-lookup"><span data-stu-id="1a6d4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a6d4-121">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="1a6d4-121">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="1a6d4-122">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="1a6d4-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a6d4-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a6d4-123">See also</span></span>

- <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
