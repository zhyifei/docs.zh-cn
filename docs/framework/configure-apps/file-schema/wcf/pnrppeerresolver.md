---
title: '&lt;pnrpPeerResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0152dfaa498b84b6e8cfa277abe858cc24ad34cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltpnrppeerresolvergt"></a><span data-ttu-id="a56e0-102">&lt;pnrpPeerResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="a56e0-102">&lt;pnrpPeerResolver&gt;</span></span>
<span data-ttu-id="a56e0-103">指定要将 PNRP（对等名称解析协议）解析程序用作解析程序。</span><span class="sxs-lookup"><span data-stu-id="a56e0-103">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="a56e0-104">此元素是可选的，因为 PNRP 是默认解析程序。</span><span class="sxs-lookup"><span data-stu-id="a56e0-104">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="a56e0-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="a56e0-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a56e0-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a56e0-106">\<bindings></span></span>  
<span data-ttu-id="a56e0-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a56e0-107">\<customBinding></span></span>  
<span data-ttu-id="a56e0-108">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a56e0-108">\<binding></span></span>  
<span data-ttu-id="a56e0-109">\<pnrpResolver ></span><span class="sxs-lookup"><span data-stu-id="a56e0-109">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a56e0-110">语法</span><span class="sxs-lookup"><span data-stu-id="a56e0-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a56e0-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a56e0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a56e0-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a56e0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a56e0-113">特性</span><span class="sxs-lookup"><span data-stu-id="a56e0-113">Attributes</span></span>  
  
|<span data-ttu-id="a56e0-114">特性</span><span class="sxs-lookup"><span data-stu-id="a56e0-114">Attribute</span></span>|<span data-ttu-id="a56e0-115">描述</span><span class="sxs-lookup"><span data-stu-id="a56e0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a56e0-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="a56e0-116">resolverType</span></span>|<span data-ttu-id="a56e0-117">一个字符串，指定要使用的解析程序。</span><span class="sxs-lookup"><span data-stu-id="a56e0-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="a56e0-118">此属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="a56e0-118">This attribute is optional.</span></span> <span data-ttu-id="a56e0-119">如果不设置，或者将其设置为空字符串，则使用 PNRP。</span><span class="sxs-lookup"><span data-stu-id="a56e0-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a56e0-120">子元素</span><span class="sxs-lookup"><span data-stu-id="a56e0-120">Child Elements</span></span>  
 <span data-ttu-id="a56e0-121">无</span><span class="sxs-lookup"><span data-stu-id="a56e0-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a56e0-122">父元素</span><span class="sxs-lookup"><span data-stu-id="a56e0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a56e0-123">元素</span><span class="sxs-lookup"><span data-stu-id="a56e0-123">Element</span></span>|<span data-ttu-id="a56e0-124">描述</span><span class="sxs-lookup"><span data-stu-id="a56e0-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a56e0-125">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="a56e0-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a56e0-126">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="a56e0-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a56e0-127">示例</span><span class="sxs-lookup"><span data-stu-id="a56e0-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="a56e0-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="a56e0-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>  
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="a56e0-129">绑定</span><span class="sxs-lookup"><span data-stu-id="a56e0-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a56e0-130">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="a56e0-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="a56e0-131">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="a56e0-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="a56e0-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="a56e0-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="a56e0-133">对等解析程序</span><span class="sxs-lookup"><span data-stu-id="a56e0-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
