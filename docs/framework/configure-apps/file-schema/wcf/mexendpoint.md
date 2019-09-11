---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 7760ee4d3b118e339944317e8ec8d8217b5d909d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855111"
---
# <a name="mexendpoint"></a><span data-ttu-id="97e88-101">\<mexEndpoint></span><span class="sxs-lookup"><span data-stu-id="97e88-101">\<mexEndpoint></span></span>
<span data-ttu-id="97e88-102">此配置元素定义具有固定 IMetadataExchange 协定的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="97e88-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="97e88-103">由于所有元数据交换终结点都指定 IMetadataExchange 作为其协定，因此可以使用此标准终结点，而不必定义您自己的终结点。</span><span class="sxs-lookup"><span data-stu-id="97e88-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
<span data-ttu-id="97e88-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="97e88-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="97e88-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="97e88-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="97e88-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="97e88-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="97e88-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="97e88-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97e88-108">语法</span><span class="sxs-lookup"><span data-stu-id="97e88-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97e88-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="97e88-109">Attributes and Elements</span></span>  
 <span data-ttu-id="97e88-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="97e88-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97e88-111">特性</span><span class="sxs-lookup"><span data-stu-id="97e88-111">Attributes</span></span>  
  
|<span data-ttu-id="97e88-112">特性</span><span class="sxs-lookup"><span data-stu-id="97e88-112">Attribute</span></span>|<span data-ttu-id="97e88-113">描述</span><span class="sxs-lookup"><span data-stu-id="97e88-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="97e88-114">NAME</span><span class="sxs-lookup"><span data-stu-id="97e88-114">name</span></span>|<span data-ttu-id="97e88-115">一个字符串，指定标准终结点的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="97e88-115">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="97e88-116">此名称在服务终结点的 `endpointConfiguration` 特性中用于将标准终结点链接到其配置。</span><span class="sxs-lookup"><span data-stu-id="97e88-116">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97e88-117">子元素</span><span class="sxs-lookup"><span data-stu-id="97e88-117">Child Elements</span></span>  
 <span data-ttu-id="97e88-118">无。</span><span class="sxs-lookup"><span data-stu-id="97e88-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97e88-119">父元素</span><span class="sxs-lookup"><span data-stu-id="97e88-119">Parent Elements</span></span>  
  
|<span data-ttu-id="97e88-120">元素</span><span class="sxs-lookup"><span data-stu-id="97e88-120">Element</span></span>|<span data-ttu-id="97e88-121">描述</span><span class="sxs-lookup"><span data-stu-id="97e88-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97e88-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="97e88-122">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="97e88-123">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="97e88-123">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
