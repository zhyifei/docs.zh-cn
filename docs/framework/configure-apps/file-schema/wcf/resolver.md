---
title: "&lt;冲突解决程序&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc6e919600fbea15937a61eaa65299b3a372caaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltresolvergt"></a><span data-ttu-id="94924-102">&lt;冲突解决程序&gt;</span><span class="sxs-lookup"><span data-stu-id="94924-102">&lt;resolver&gt;</span></span>
<span data-ttu-id="94924-103">指定对等解析程序，对等解析程序用于将对等网格 ID 解析为一组对等节点地址，这些地址表示参与网格的若干节点。</span><span class="sxs-lookup"><span data-stu-id="94924-103">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
 <span data-ttu-id="94924-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="94924-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="94924-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="94924-105">\<bindings></span></span>  
<span data-ttu-id="94924-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="94924-106">\<netPeerBinding></span></span>  
<span data-ttu-id="94924-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="94924-107">\<binding></span></span>  
<span data-ttu-id="94924-108">\<冲突解决程序 ></span><span class="sxs-lookup"><span data-stu-id="94924-108">\<resolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94924-109">语法</span><span class="sxs-lookup"><span data-stu-id="94924-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="94924-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="94924-110">Attributes and Elements</span></span>  
 <span data-ttu-id="94924-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="94924-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="94924-112">特性</span><span class="sxs-lookup"><span data-stu-id="94924-112">Attributes</span></span>  
  
|<span data-ttu-id="94924-113">特性</span><span class="sxs-lookup"><span data-stu-id="94924-113">Attribute</span></span>|<span data-ttu-id="94924-114">描述</span><span class="sxs-lookup"><span data-stu-id="94924-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="94924-115">一个字符串，指定与此服务关联的对等解析程序实例是特定于 PNRP，还是为自定义解析程序，或者是自动确定的。</span><span class="sxs-lookup"><span data-stu-id="94924-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="94924-116">此属性的类型为 <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>。</span><span class="sxs-lookup"><span data-stu-id="94924-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="94924-117">一个字符串，指定在对等端间共享引用的方式。</span><span class="sxs-lookup"><span data-stu-id="94924-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="94924-118">此属性的类型为 <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>。</span><span class="sxs-lookup"><span data-stu-id="94924-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="94924-119">子元素</span><span class="sxs-lookup"><span data-stu-id="94924-119">Child Elements</span></span>  
  
|<span data-ttu-id="94924-120">元素</span><span class="sxs-lookup"><span data-stu-id="94924-120">Element</span></span>|<span data-ttu-id="94924-121">描述</span><span class="sxs-lookup"><span data-stu-id="94924-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94924-122">\<标头 ></span><span class="sxs-lookup"><span data-stu-id="94924-122">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|<span data-ttu-id="94924-123">指定自定义对等解析程序服务的设置。</span><span class="sxs-lookup"><span data-stu-id="94924-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="94924-124">父元素</span><span class="sxs-lookup"><span data-stu-id="94924-124">Parent Elements</span></span>  
  
|<span data-ttu-id="94924-125">元素</span><span class="sxs-lookup"><span data-stu-id="94924-125">Element</span></span>|<span data-ttu-id="94924-126">描述</span><span class="sxs-lookup"><span data-stu-id="94924-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="94924-127">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="94924-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="94924-128">定义的所有绑定功能[ \<netPeerTcpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="94924-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94924-129">备注</span><span class="sxs-lookup"><span data-stu-id="94924-129">Remarks</span></span>  
 <span data-ttu-id="94924-130">对等名解析程序是对等通道用于查找参与对等网格的对等节点的发现服务。</span><span class="sxs-lookup"><span data-stu-id="94924-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="94924-131">它还可以用于在对等网格中“注册”节点，即对等节点在对等网格中变为已知和可用的机制。</span><span class="sxs-lookup"><span data-stu-id="94924-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="94924-132">对等解析程序的详细信息，请参阅[对等解析程序](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)。</span><span class="sxs-lookup"><span data-stu-id="94924-132">For more information on peer resolvers, see [Peer Resolvers](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94924-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="94924-133">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolver>  
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>  
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement>  
 [<span data-ttu-id="94924-134">对等解析程序</span><span class="sxs-lookup"><span data-stu-id="94924-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="94924-135">将自定义解析程序添加到对等通道应用程序</span><span class="sxs-lookup"><span data-stu-id="94924-135">Adding a Custom Resolver to a PeerChannel Application</span></span>](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419)
