---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 39dcb868bd3ff25451509616e1dac7d41f94cfa1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075869"
---
# <a name="resolver"></a><span data-ttu-id="b3987-101">\<resolver></span><span class="sxs-lookup"><span data-stu-id="b3987-101">\<resolver></span></span>
<span data-ttu-id="b3987-102">指定对等解析程序，对等解析程序用于将对等网格 ID 解析为一组对等节点地址，这些地址表示参与网格的若干节点。</span><span class="sxs-lookup"><span data-stu-id="b3987-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="b3987-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b3987-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b3987-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="b3987-104">\<bindings></span></span>  
<span data-ttu-id="b3987-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="b3987-105">\<netPeerBinding></span></span>  
<span data-ttu-id="b3987-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="b3987-106">\<binding></span></span>  
<span data-ttu-id="b3987-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="b3987-107">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3987-108">语法</span><span class="sxs-lookup"><span data-stu-id="b3987-108">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3987-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b3987-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b3987-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b3987-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3987-111">特性</span><span class="sxs-lookup"><span data-stu-id="b3987-111">Attributes</span></span>  
  
|<span data-ttu-id="b3987-112">特性</span><span class="sxs-lookup"><span data-stu-id="b3987-112">Attribute</span></span>|<span data-ttu-id="b3987-113">描述</span><span class="sxs-lookup"><span data-stu-id="b3987-113">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="b3987-114">一个字符串，指定与此服务关联的对等解析程序实例是特定于 PNRP，还是为自定义解析程序，或者是自动确定的。</span><span class="sxs-lookup"><span data-stu-id="b3987-114">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="b3987-115">此属性的类型为 <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>。</span><span class="sxs-lookup"><span data-stu-id="b3987-115">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="b3987-116">一个字符串，指定在对等端间共享引用的方式。</span><span class="sxs-lookup"><span data-stu-id="b3987-116">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="b3987-117">此属性的类型为 <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>。</span><span class="sxs-lookup"><span data-stu-id="b3987-117">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3987-118">子元素</span><span class="sxs-lookup"><span data-stu-id="b3987-118">Child Elements</span></span>  
  
|<span data-ttu-id="b3987-119">元素</span><span class="sxs-lookup"><span data-stu-id="b3987-119">Element</span></span>|<span data-ttu-id="b3987-120">描述</span><span class="sxs-lookup"><span data-stu-id="b3987-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3987-121">\<headers></span><span class="sxs-lookup"><span data-stu-id="b3987-121">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="b3987-122">指定自定义对等解析程序服务的设置。</span><span class="sxs-lookup"><span data-stu-id="b3987-122">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3987-123">父元素</span><span class="sxs-lookup"><span data-stu-id="b3987-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b3987-124">元素</span><span class="sxs-lookup"><span data-stu-id="b3987-124">Element</span></span>|<span data-ttu-id="b3987-125">描述</span><span class="sxs-lookup"><span data-stu-id="b3987-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3987-126">\<binding></span><span class="sxs-lookup"><span data-stu-id="b3987-126">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b3987-127">定义的所有绑定功能[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="b3987-127">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3987-128">备注</span><span class="sxs-lookup"><span data-stu-id="b3987-128">Remarks</span></span>  
 <span data-ttu-id="b3987-129">对等名解析程序是对等通道用于查找参与对等网格的对等节点的发现服务。</span><span class="sxs-lookup"><span data-stu-id="b3987-129">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="b3987-130">它还可以用于在对等网格中“注册”节点，即对等节点在对等网格中变为已知和可用的机制。</span><span class="sxs-lookup"><span data-stu-id="b3987-130">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="b3987-131">对等解析程序的详细信息，请参阅[对等解析程序](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)。</span><span class="sxs-lookup"><span data-stu-id="b3987-131">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3987-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3987-132">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="b3987-133">对等解析程序</span><span class="sxs-lookup"><span data-stu-id="b3987-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="b3987-134">[对等通道应用程序中添加自定义冲突解决程序](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="b3987-134">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
