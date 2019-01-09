---
title: '&lt;mexEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 4e2fb4946ee68b3cbd5bd6bfbafe6bb5e9c9106f
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149145"
---
# <a name="ltmexendpointgt"></a><span data-ttu-id="aa95c-102">&lt;mexEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="aa95c-102">&lt;mexEndpoint&gt;</span></span>
<span data-ttu-id="aa95c-103">此配置元素定义具有固定 IMetadataExchange 协定的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="aa95c-103">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="aa95c-104">由于所有元数据交换终结点都指定 IMetadataExchange 作为其协定，因此可以使用此标准终结点，而不必定义您自己的终结点。</span><span class="sxs-lookup"><span data-stu-id="aa95c-104">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="aa95c-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="aa95c-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="aa95c-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="aa95c-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa95c-107">语法</span><span class="sxs-lookup"><span data-stu-id="aa95c-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa95c-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="aa95c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="aa95c-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="aa95c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa95c-110">特性</span><span class="sxs-lookup"><span data-stu-id="aa95c-110">Attributes</span></span>  
  
|<span data-ttu-id="aa95c-111">特性</span><span class="sxs-lookup"><span data-stu-id="aa95c-111">Attribute</span></span>|<span data-ttu-id="aa95c-112">描述</span><span class="sxs-lookup"><span data-stu-id="aa95c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa95c-113">name</span><span class="sxs-lookup"><span data-stu-id="aa95c-113">name</span></span>|<span data-ttu-id="aa95c-114">一个字符串，指定标准终结点的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="aa95c-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="aa95c-115">此名称在服务终结点的 `endpointConfiguration` 特性中用于将标准终结点链接到其配置。</span><span class="sxs-lookup"><span data-stu-id="aa95c-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa95c-116">子元素</span><span class="sxs-lookup"><span data-stu-id="aa95c-116">Child Elements</span></span>  
 <span data-ttu-id="aa95c-117">无。</span><span class="sxs-lookup"><span data-stu-id="aa95c-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aa95c-118">父元素</span><span class="sxs-lookup"><span data-stu-id="aa95c-118">Parent Elements</span></span>  
  
|<span data-ttu-id="aa95c-119">元素</span><span class="sxs-lookup"><span data-stu-id="aa95c-119">Element</span></span>|<span data-ttu-id="aa95c-120">描述</span><span class="sxs-lookup"><span data-stu-id="aa95c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa95c-121">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="aa95c-121">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="aa95c-122">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="aa95c-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
