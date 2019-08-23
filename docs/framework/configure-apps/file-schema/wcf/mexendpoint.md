---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 78788f9dfbf6cdf3439fd6e33eddfe721e49840d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931261"
---
# <a name="mexendpoint"></a><span data-ttu-id="463dc-101">\<mexEndpoint></span><span class="sxs-lookup"><span data-stu-id="463dc-101">\<mexEndpoint></span></span>
<span data-ttu-id="463dc-102">此配置元素定义具有固定 IMetadataExchange 协定的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="463dc-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="463dc-103">由于所有元数据交换终结点都指定 IMetadataExchange 作为其协定，因此可以使用此标准终结点，而不必定义您自己的终结点。</span><span class="sxs-lookup"><span data-stu-id="463dc-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="463dc-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="463dc-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="463dc-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="463dc-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="463dc-106">语法</span><span class="sxs-lookup"><span data-stu-id="463dc-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="463dc-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="463dc-107">Attributes and Elements</span></span>  
 <span data-ttu-id="463dc-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="463dc-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="463dc-109">特性</span><span class="sxs-lookup"><span data-stu-id="463dc-109">Attributes</span></span>  
  
|<span data-ttu-id="463dc-110">特性</span><span class="sxs-lookup"><span data-stu-id="463dc-110">Attribute</span></span>|<span data-ttu-id="463dc-111">描述</span><span class="sxs-lookup"><span data-stu-id="463dc-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="463dc-112">NAME</span><span class="sxs-lookup"><span data-stu-id="463dc-112">name</span></span>|<span data-ttu-id="463dc-113">一个字符串，指定标准终结点的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="463dc-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="463dc-114">此名称在服务终结点的 `endpointConfiguration` 特性中用于将标准终结点链接到其配置。</span><span class="sxs-lookup"><span data-stu-id="463dc-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="463dc-115">子元素</span><span class="sxs-lookup"><span data-stu-id="463dc-115">Child Elements</span></span>  
 <span data-ttu-id="463dc-116">无。</span><span class="sxs-lookup"><span data-stu-id="463dc-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="463dc-117">父元素</span><span class="sxs-lookup"><span data-stu-id="463dc-117">Parent Elements</span></span>  
  
|<span data-ttu-id="463dc-118">元素</span><span class="sxs-lookup"><span data-stu-id="463dc-118">Element</span></span>|<span data-ttu-id="463dc-119">描述</span><span class="sxs-lookup"><span data-stu-id="463dc-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="463dc-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="463dc-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="463dc-121">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="463dc-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
