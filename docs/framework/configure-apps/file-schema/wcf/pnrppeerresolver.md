---
title: '&lt;pnrpPeerResolver&gt;'
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: 882974ea29804c7218d4c6c21da2b9ddd7551c54
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150132"
---
# <a name="ltpnrppeerresolvergt"></a><span data-ttu-id="9b736-102">&lt;pnrpPeerResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="9b736-102">&lt;pnrpPeerResolver&gt;</span></span>
<span data-ttu-id="9b736-103">指定要将 PNRP（对等名称解析协议）解析程序用作解析程序。</span><span class="sxs-lookup"><span data-stu-id="9b736-103">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="9b736-104">此元素是可选的，因为 PNRP 是默认解析程序。</span><span class="sxs-lookup"><span data-stu-id="9b736-104">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="9b736-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9b736-105">\<system.serviceModel></span></span>  
<span data-ttu-id="9b736-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="9b736-106">\<bindings></span></span>  
<span data-ttu-id="9b736-107">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9b736-107">\<customBinding></span></span>  
<span data-ttu-id="9b736-108">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="9b736-108">\<binding></span></span>  
<span data-ttu-id="9b736-109">\<pnrpResolver ></span><span class="sxs-lookup"><span data-stu-id="9b736-109">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b736-110">语法</span><span class="sxs-lookup"><span data-stu-id="9b736-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b736-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9b736-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9b736-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9b736-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b736-113">特性</span><span class="sxs-lookup"><span data-stu-id="9b736-113">Attributes</span></span>  
  
|<span data-ttu-id="9b736-114">特性</span><span class="sxs-lookup"><span data-stu-id="9b736-114">Attribute</span></span>|<span data-ttu-id="9b736-115">描述</span><span class="sxs-lookup"><span data-stu-id="9b736-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b736-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="9b736-116">resolverType</span></span>|<span data-ttu-id="9b736-117">一个字符串，指定要使用的解析程序。</span><span class="sxs-lookup"><span data-stu-id="9b736-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="9b736-118">此属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="9b736-118">This attribute is optional.</span></span> <span data-ttu-id="9b736-119">如果不设置，或者将其设置为空字符串，则使用 PNRP。</span><span class="sxs-lookup"><span data-stu-id="9b736-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b736-120">子元素</span><span class="sxs-lookup"><span data-stu-id="9b736-120">Child Elements</span></span>  
 <span data-ttu-id="9b736-121">无</span><span class="sxs-lookup"><span data-stu-id="9b736-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b736-122">父元素</span><span class="sxs-lookup"><span data-stu-id="9b736-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9b736-123">元素</span><span class="sxs-lookup"><span data-stu-id="9b736-123">Element</span></span>|<span data-ttu-id="9b736-124">描述</span><span class="sxs-lookup"><span data-stu-id="9b736-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b736-125">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="9b736-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="9b736-126">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="9b736-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9b736-127">示例</span><span class="sxs-lookup"><span data-stu-id="9b736-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="9b736-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b736-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>  
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="9b736-129">绑定</span><span class="sxs-lookup"><span data-stu-id="9b736-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="9b736-130">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="9b736-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="9b736-131">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="9b736-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="9b736-132">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9b736-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="9b736-133">对等解析程序</span><span class="sxs-lookup"><span data-stu-id="9b736-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
