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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75886c08d3e358d4ed6d3d3048594ef28f06a7af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltmexendpointgt"></a><span data-ttu-id="24ea4-102">&lt;mexEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="24ea4-102">&lt;mexEndpoint&gt;</span></span>
<span data-ttu-id="24ea4-103">此配置元素定义具有固定 IMetadataExchange 协定的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="24ea4-103">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="24ea4-104">由于所有元数据交换终结点都指定 IMetadataExchange 作为其协定，因此可以使用此标准终结点，而不必定义您自己的终结点。</span><span class="sxs-lookup"><span data-stu-id="24ea4-104">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="24ea4-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="24ea4-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="24ea4-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="24ea4-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24ea4-107">语法</span><span class="sxs-lookup"><span data-stu-id="24ea4-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24ea4-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="24ea4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="24ea4-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="24ea4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24ea4-110">特性</span><span class="sxs-lookup"><span data-stu-id="24ea4-110">Attributes</span></span>  
  
|<span data-ttu-id="24ea4-111">特性</span><span class="sxs-lookup"><span data-stu-id="24ea4-111">Attribute</span></span>|<span data-ttu-id="24ea4-112">描述</span><span class="sxs-lookup"><span data-stu-id="24ea4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="24ea4-113">name</span><span class="sxs-lookup"><span data-stu-id="24ea4-113">name</span></span>|<span data-ttu-id="24ea4-114">一个字符串，指定标准终结点的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="24ea4-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="24ea4-115">此名称在服务终结点的 `endpointConfiguration` 特性中用于将标准终结点链接到其配置。</span><span class="sxs-lookup"><span data-stu-id="24ea4-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24ea4-116">子元素</span><span class="sxs-lookup"><span data-stu-id="24ea4-116">Child Elements</span></span>  
 <span data-ttu-id="24ea4-117">无。</span><span class="sxs-lookup"><span data-stu-id="24ea4-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24ea4-118">父元素</span><span class="sxs-lookup"><span data-stu-id="24ea4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="24ea4-119">元素</span><span class="sxs-lookup"><span data-stu-id="24ea4-119">Element</span></span>|<span data-ttu-id="24ea4-120">描述</span><span class="sxs-lookup"><span data-stu-id="24ea4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="24ea4-121">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="24ea4-121">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="24ea4-122">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="24ea4-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
