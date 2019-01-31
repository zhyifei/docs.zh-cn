---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: f98c358cc9891e9d7223d280fc8e50c19aad9759
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260642"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="5e6e0-101">\<pnrpPeerResolver></span><span class="sxs-lookup"><span data-stu-id="5e6e0-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="5e6e0-102">指定要将 PNRP（对等名称解析协议）解析程序用作解析程序。</span><span class="sxs-lookup"><span data-stu-id="5e6e0-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="5e6e0-103">此元素是可选的，因为 PNRP 是默认解析程序。</span><span class="sxs-lookup"><span data-stu-id="5e6e0-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="5e6e0-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5e6e0-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5e6e0-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5e6e0-105">\<bindings></span></span>  
<span data-ttu-id="5e6e0-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5e6e0-106">\<customBinding></span></span>  
<span data-ttu-id="5e6e0-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="5e6e0-107">\<binding></span></span>  
<span data-ttu-id="5e6e0-108">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="5e6e0-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e6e0-109">语法</span><span class="sxs-lookup"><span data-stu-id="5e6e0-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e6e0-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5e6e0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5e6e0-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5e6e0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e6e0-112">特性</span><span class="sxs-lookup"><span data-stu-id="5e6e0-112">Attributes</span></span>  
  
|<span data-ttu-id="5e6e0-113">特性</span><span class="sxs-lookup"><span data-stu-id="5e6e0-113">Attribute</span></span>|<span data-ttu-id="5e6e0-114">描述</span><span class="sxs-lookup"><span data-stu-id="5e6e0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e6e0-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="5e6e0-115">resolverType</span></span>|<span data-ttu-id="5e6e0-116">一个字符串，指定要使用的解析程序。</span><span class="sxs-lookup"><span data-stu-id="5e6e0-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="5e6e0-117">此属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="5e6e0-117">This attribute is optional.</span></span> <span data-ttu-id="5e6e0-118">如果不设置，或者将其设置为空字符串，则使用 PNRP。</span><span class="sxs-lookup"><span data-stu-id="5e6e0-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e6e0-119">子元素</span><span class="sxs-lookup"><span data-stu-id="5e6e0-119">Child Elements</span></span>  
 <span data-ttu-id="5e6e0-120">无</span><span class="sxs-lookup"><span data-stu-id="5e6e0-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e6e0-121">父元素</span><span class="sxs-lookup"><span data-stu-id="5e6e0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="5e6e0-122">元素</span><span class="sxs-lookup"><span data-stu-id="5e6e0-122">Element</span></span>|<span data-ttu-id="5e6e0-123">描述</span><span class="sxs-lookup"><span data-stu-id="5e6e0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e6e0-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="5e6e0-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="5e6e0-125">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="5e6e0-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5e6e0-126">示例</span><span class="sxs-lookup"><span data-stu-id="5e6e0-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="5e6e0-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e6e0-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5e6e0-128">绑定</span><span class="sxs-lookup"><span data-stu-id="5e6e0-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="5e6e0-129">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="5e6e0-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5e6e0-130">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="5e6e0-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5e6e0-131">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5e6e0-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="5e6e0-132">对等解析程序</span><span class="sxs-lookup"><span data-stu-id="5e6e0-132">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
