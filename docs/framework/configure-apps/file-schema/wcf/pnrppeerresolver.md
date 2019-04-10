---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: 2404f00b2a3ba03e89c1e21fb25e13cabb8feed3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214048"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="6f661-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="6f661-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="6f661-102">指定要将 PNRP（对等名称解析协议）解析程序用作解析程序。</span><span class="sxs-lookup"><span data-stu-id="6f661-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="6f661-103">此元素是可选的，因为 PNRP 是默认解析程序。</span><span class="sxs-lookup"><span data-stu-id="6f661-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="6f661-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6f661-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6f661-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="6f661-105">\<bindings></span></span>  
<span data-ttu-id="6f661-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6f661-106">\<customBinding></span></span>  
<span data-ttu-id="6f661-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="6f661-107">\<binding></span></span>  
<span data-ttu-id="6f661-108">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="6f661-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f661-109">语法</span><span class="sxs-lookup"><span data-stu-id="6f661-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f661-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6f661-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6f661-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6f661-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f661-112">特性</span><span class="sxs-lookup"><span data-stu-id="6f661-112">Attributes</span></span>  
  
|<span data-ttu-id="6f661-113">特性</span><span class="sxs-lookup"><span data-stu-id="6f661-113">Attribute</span></span>|<span data-ttu-id="6f661-114">描述</span><span class="sxs-lookup"><span data-stu-id="6f661-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6f661-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="6f661-115">resolverType</span></span>|<span data-ttu-id="6f661-116">一个字符串，指定要使用的解析程序。</span><span class="sxs-lookup"><span data-stu-id="6f661-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="6f661-117">此属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="6f661-117">This attribute is optional.</span></span> <span data-ttu-id="6f661-118">如果不设置，或者将其设置为空字符串，则使用 PNRP。</span><span class="sxs-lookup"><span data-stu-id="6f661-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f661-119">子元素</span><span class="sxs-lookup"><span data-stu-id="6f661-119">Child Elements</span></span>  
 <span data-ttu-id="6f661-120">None</span><span class="sxs-lookup"><span data-stu-id="6f661-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f661-121">父元素</span><span class="sxs-lookup"><span data-stu-id="6f661-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6f661-122">元素</span><span class="sxs-lookup"><span data-stu-id="6f661-122">Element</span></span>|<span data-ttu-id="6f661-123">描述</span><span class="sxs-lookup"><span data-stu-id="6f661-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f661-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="6f661-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="6f661-125">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="6f661-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6f661-126">示例</span><span class="sxs-lookup"><span data-stu-id="6f661-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="6f661-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f661-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="6f661-128">绑定</span><span class="sxs-lookup"><span data-stu-id="6f661-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="6f661-129">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="6f661-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="6f661-130">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="6f661-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="6f661-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6f661-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="6f661-132">对等解析程序</span><span class="sxs-lookup"><span data-stu-id="6f661-132">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
