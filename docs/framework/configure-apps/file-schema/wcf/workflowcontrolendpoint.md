---
title: '&lt;workflowControlEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: 6c89e76c-643b-4b6a-9b25-628f753d7027
ms.openlocfilehash: 178ccc8ac35b0ac76d74c818dce43dcffc5c0835
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144946"
---
# <a name="ltworkflowcontrolendpointgt"></a><span data-ttu-id="803fa-102">&lt;workflowControlEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="803fa-102">&lt;workflowControlEndpoint&gt;</span></span>
<span data-ttu-id="803fa-103">此配置元素定义用于控制工作流实例的执行（创建、运行、挂起、终止等）的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="803fa-103">This configuration element defines a standard endpoint for controlling the execution of workflow instances (create, run, suspend, terminate, etc).</span></span>  
  
<span data-ttu-id="803fa-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="803fa-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="803fa-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="803fa-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="803fa-106">语法</span><span class="sxs-lookup"><span data-stu-id="803fa-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <workflowControlEndpoint>
      <standardEndpoint name="String" />
    </workflowControlEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="803fa-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="803fa-107">Attributes and Elements</span></span>  
 <span data-ttu-id="803fa-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="803fa-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="803fa-109">特性</span><span class="sxs-lookup"><span data-stu-id="803fa-109">Attributes</span></span>  
  
|<span data-ttu-id="803fa-110">特性</span><span class="sxs-lookup"><span data-stu-id="803fa-110">Attribute</span></span>|<span data-ttu-id="803fa-111">描述</span><span class="sxs-lookup"><span data-stu-id="803fa-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="803fa-112">name</span><span class="sxs-lookup"><span data-stu-id="803fa-112">name</span></span>|<span data-ttu-id="803fa-113">一个字符串，指定标准终结点的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="803fa-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="803fa-114">此名称在服务终结点的 `endpointConfiguration` 特性中用于将标准终结点链接到其配置。</span><span class="sxs-lookup"><span data-stu-id="803fa-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="803fa-115">子元素</span><span class="sxs-lookup"><span data-stu-id="803fa-115">Child Elements</span></span>  
 <span data-ttu-id="803fa-116">无。</span><span class="sxs-lookup"><span data-stu-id="803fa-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="803fa-117">父元素</span><span class="sxs-lookup"><span data-stu-id="803fa-117">Parent Elements</span></span>  
  
|<span data-ttu-id="803fa-118">元素</span><span class="sxs-lookup"><span data-stu-id="803fa-118">Element</span></span>|<span data-ttu-id="803fa-119">描述</span><span class="sxs-lookup"><span data-stu-id="803fa-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="803fa-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="803fa-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="803fa-121">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="803fa-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="803fa-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="803fa-122">See Also</span></span>  
 <xref:System.ServiceModel.Activities.WorkflowControlEndpoint>
