---
title: '&lt;mexEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 713c1c260f36d6d980903cce1ebcc9c5648116c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltmexendpointgt"></a><span data-ttu-id="895bf-102">&lt;mexEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="895bf-102">&lt;mexEndpoint&gt;</span></span>
<span data-ttu-id="895bf-103">此配置元素定义具有固定 IMetadataExchange 协定的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="895bf-103">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="895bf-104">由于所有元数据交换终结点都指定 IMetadataExchange 作为其协定，因此可以使用此标准终结点，而不必定义您自己的终结点。</span><span class="sxs-lookup"><span data-stu-id="895bf-104">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="895bf-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="895bf-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="895bf-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="895bf-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="895bf-107">语法</span><span class="sxs-lookup"><span data-stu-id="895bf-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="895bf-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="895bf-108">Attributes and Elements</span></span>  
 <span data-ttu-id="895bf-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="895bf-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="895bf-110">特性</span><span class="sxs-lookup"><span data-stu-id="895bf-110">Attributes</span></span>  
  
|<span data-ttu-id="895bf-111">特性</span><span class="sxs-lookup"><span data-stu-id="895bf-111">Attribute</span></span>|<span data-ttu-id="895bf-112">描述</span><span class="sxs-lookup"><span data-stu-id="895bf-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="895bf-113">name</span><span class="sxs-lookup"><span data-stu-id="895bf-113">name</span></span>|<span data-ttu-id="895bf-114">一个字符串，指定标准终结点的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="895bf-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="895bf-115">此名称在服务终结点的 `endpointConfiguration` 特性中用于将标准终结点链接到其配置。</span><span class="sxs-lookup"><span data-stu-id="895bf-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="895bf-116">子元素</span><span class="sxs-lookup"><span data-stu-id="895bf-116">Child Elements</span></span>  
 <span data-ttu-id="895bf-117">无。</span><span class="sxs-lookup"><span data-stu-id="895bf-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="895bf-118">父元素</span><span class="sxs-lookup"><span data-stu-id="895bf-118">Parent Elements</span></span>  
  
|<span data-ttu-id="895bf-119">元素</span><span class="sxs-lookup"><span data-stu-id="895bf-119">Element</span></span>|<span data-ttu-id="895bf-120">描述</span><span class="sxs-lookup"><span data-stu-id="895bf-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="895bf-121">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="895bf-121">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="895bf-122">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="895bf-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
