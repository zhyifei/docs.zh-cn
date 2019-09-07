---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: fb974492dee6b2a4244cedc06e3f5e40334dd02a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399984"
---
# <a name="resolver"></a><span data-ttu-id="b27a1-101">\<resolver></span><span class="sxs-lookup"><span data-stu-id="b27a1-101">\<resolver></span></span>
<span data-ttu-id="b27a1-102">指定对等解析程序，对等解析程序用于将对等网格 ID 解析为一组对等节点地址，这些地址表示参与网格的若干节点。</span><span class="sxs-lookup"><span data-stu-id="b27a1-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
<span data-ttu-id="b27a1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b27a1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b27a1-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b27a1-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b27a1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="b27a1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="b27a1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="b27a1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="b27a1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="b27a1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="b27a1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<解析程序 >**</span><span class="sxs-lookup"><span data-stu-id="b27a1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b27a1-109">语法</span><span class="sxs-lookup"><span data-stu-id="b27a1-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b27a1-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b27a1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b27a1-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b27a1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b27a1-112">特性</span><span class="sxs-lookup"><span data-stu-id="b27a1-112">Attributes</span></span>  
  
|<span data-ttu-id="b27a1-113">特性</span><span class="sxs-lookup"><span data-stu-id="b27a1-113">Attribute</span></span>|<span data-ttu-id="b27a1-114">描述</span><span class="sxs-lookup"><span data-stu-id="b27a1-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="b27a1-115">一个字符串，指定与此服务关联的对等解析程序实例是特定于 PNRP，还是为自定义解析程序，或者是自动确定的。</span><span class="sxs-lookup"><span data-stu-id="b27a1-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="b27a1-116">此属性的类型为 <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>。</span><span class="sxs-lookup"><span data-stu-id="b27a1-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="b27a1-117">一个字符串，指定在对等端间共享引用的方式。</span><span class="sxs-lookup"><span data-stu-id="b27a1-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="b27a1-118">此属性的类型为 <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>。</span><span class="sxs-lookup"><span data-stu-id="b27a1-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b27a1-119">子元素</span><span class="sxs-lookup"><span data-stu-id="b27a1-119">Child Elements</span></span>  
  
|<span data-ttu-id="b27a1-120">元素</span><span class="sxs-lookup"><span data-stu-id="b27a1-120">Element</span></span>|<span data-ttu-id="b27a1-121">描述</span><span class="sxs-lookup"><span data-stu-id="b27a1-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b27a1-122">\<headers></span><span class="sxs-lookup"><span data-stu-id="b27a1-122">\<headers></span></span>](headers.md)|<span data-ttu-id="b27a1-123">指定自定义对等解析程序服务的设置。</span><span class="sxs-lookup"><span data-stu-id="b27a1-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b27a1-124">父元素</span><span class="sxs-lookup"><span data-stu-id="b27a1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b27a1-125">元素</span><span class="sxs-lookup"><span data-stu-id="b27a1-125">Element</span></span>|<span data-ttu-id="b27a1-126">描述</span><span class="sxs-lookup"><span data-stu-id="b27a1-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b27a1-127">\<binding></span><span class="sxs-lookup"><span data-stu-id="b27a1-127">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="b27a1-128">定义[ \<netPeerTcpBinding >](netpeertcpbinding.md)的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="b27a1-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b27a1-129">备注</span><span class="sxs-lookup"><span data-stu-id="b27a1-129">Remarks</span></span>  
 <span data-ttu-id="b27a1-130">对等名解析程序是对等通道用于查找参与对等网格的对等节点的发现服务。</span><span class="sxs-lookup"><span data-stu-id="b27a1-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="b27a1-131">它还可以用于在对等网格中“注册”节点，即对等节点在对等网格中变为已知和可用的机制。</span><span class="sxs-lookup"><span data-stu-id="b27a1-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="b27a1-132">有关对等解析程序的详细信息，请参阅[对等解析](../../../wcf/feature-details/peer-resolvers.md)程序。</span><span class="sxs-lookup"><span data-stu-id="b27a1-132">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b27a1-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="b27a1-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="b27a1-134">对等解析程序</span><span class="sxs-lookup"><span data-stu-id="b27a1-134">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="b27a1-135">[向 PeerChannel 应用程序添加自定义冲突解决程序](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b27a1-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
