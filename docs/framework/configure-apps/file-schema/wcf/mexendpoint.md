---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 8fffcc05d5f53f719efce182083fbf103b1230ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772471"
---
# <a name="mexendpoint"></a><span data-ttu-id="13bfe-101">\<mexEndpoint></span><span class="sxs-lookup"><span data-stu-id="13bfe-101">\<mexEndpoint></span></span>
<span data-ttu-id="13bfe-102">此配置元素定义具有固定 IMetadataExchange 协定的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="13bfe-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="13bfe-103">由于所有元数据交换终结点都指定 IMetadataExchange 作为其协定，因此可以使用此标准终结点，而不必定义您自己的终结点。</span><span class="sxs-lookup"><span data-stu-id="13bfe-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="13bfe-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="13bfe-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="13bfe-105">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="13bfe-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13bfe-106">语法</span><span class="sxs-lookup"><span data-stu-id="13bfe-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13bfe-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="13bfe-107">Attributes and Elements</span></span>  
 <span data-ttu-id="13bfe-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="13bfe-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13bfe-109">特性</span><span class="sxs-lookup"><span data-stu-id="13bfe-109">Attributes</span></span>  
  
|<span data-ttu-id="13bfe-110">特性</span><span class="sxs-lookup"><span data-stu-id="13bfe-110">Attribute</span></span>|<span data-ttu-id="13bfe-111">描述</span><span class="sxs-lookup"><span data-stu-id="13bfe-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="13bfe-112">name</span><span class="sxs-lookup"><span data-stu-id="13bfe-112">name</span></span>|<span data-ttu-id="13bfe-113">一个字符串，指定标准终结点的配置的名称。</span><span class="sxs-lookup"><span data-stu-id="13bfe-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="13bfe-114">此名称在服务终结点的 `endpointConfiguration` 特性中用于将标准终结点链接到其配置。</span><span class="sxs-lookup"><span data-stu-id="13bfe-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="13bfe-115">子元素</span><span class="sxs-lookup"><span data-stu-id="13bfe-115">Child Elements</span></span>  
 <span data-ttu-id="13bfe-116">无。</span><span class="sxs-lookup"><span data-stu-id="13bfe-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="13bfe-117">父元素</span><span class="sxs-lookup"><span data-stu-id="13bfe-117">Parent Elements</span></span>  
  
|<span data-ttu-id="13bfe-118">元素</span><span class="sxs-lookup"><span data-stu-id="13bfe-118">Element</span></span>|<span data-ttu-id="13bfe-119">描述</span><span class="sxs-lookup"><span data-stu-id="13bfe-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13bfe-120">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="13bfe-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="13bfe-121">具有一个或多个固定属性（地址、绑定和协定）的预定义终结点的标准终结点集合。</span><span class="sxs-lookup"><span data-stu-id="13bfe-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
