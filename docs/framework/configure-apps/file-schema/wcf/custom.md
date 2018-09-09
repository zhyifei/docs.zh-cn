---
title: '&lt;custom&gt;'
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 7d558be66b8a1e46d9743c5f8bf0bb9a8b4c349e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44225420"
---
# <a name="ltcustomgt"></a><span data-ttu-id="3c850-102">&lt;custom&gt;</span><span class="sxs-lookup"><span data-stu-id="3c850-102">&lt;custom&gt;</span></span>
<span data-ttu-id="3c850-103">指定自定义对等解析程序服务的设置。</span><span class="sxs-lookup"><span data-stu-id="3c850-103">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="3c850-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3c850-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3c850-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="3c850-105">\<bindings></span></span>  
<span data-ttu-id="3c850-106">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="3c850-106">\<netPeerBinding></span></span>  
<span data-ttu-id="3c850-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="3c850-107">\<binding></span></span>  
<span data-ttu-id="3c850-108">\<resolver></span><span class="sxs-lookup"><span data-stu-id="3c850-108">\<resolver></span></span>  
<span data-ttu-id="3c850-109">\<custom></span><span class="sxs-lookup"><span data-stu-id="3c850-109">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c850-110">语法</span><span class="sxs-lookup"><span data-stu-id="3c850-110">Syntax</span></span>  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c850-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3c850-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3c850-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3c850-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c850-113">特性</span><span class="sxs-lookup"><span data-stu-id="3c850-113">Attributes</span></span>  
  
|<span data-ttu-id="3c850-114">特性</span><span class="sxs-lookup"><span data-stu-id="3c850-114">Attribute</span></span>|<span data-ttu-id="3c850-115">描述</span><span class="sxs-lookup"><span data-stu-id="3c850-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="3c850-116">一个 URI，指定承载自定义对等解析程序服务的对等节点的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="3c850-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="3c850-117">一个字符串值，指定自定义对等解析程序服务的类型。</span><span class="sxs-lookup"><span data-stu-id="3c850-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3c850-118">子元素</span><span class="sxs-lookup"><span data-stu-id="3c850-118">Child Elements</span></span>  
  
|<span data-ttu-id="3c850-119">元素</span><span class="sxs-lookup"><span data-stu-id="3c850-119">Element</span></span>|<span data-ttu-id="3c850-120">描述</span><span class="sxs-lookup"><span data-stu-id="3c850-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c850-121">\<标识 ></span><span class="sxs-lookup"><span data-stu-id="3c850-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="3c850-122">指定配置了此元素的自定义对等解析程序的标识。</span><span class="sxs-lookup"><span data-stu-id="3c850-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="3c850-123">此元素的类型为 <xref:System.ServiceModel.Configuration.IdentityElement>。</span><span class="sxs-lookup"><span data-stu-id="3c850-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="3c850-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="3c850-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="3c850-125">一个地址标头集合，可用于由自定义对等解析程序处理的 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="3c850-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3c850-126">父元素</span><span class="sxs-lookup"><span data-stu-id="3c850-126">Parent Elements</span></span>  
  
|<span data-ttu-id="3c850-127">元素</span><span class="sxs-lookup"><span data-stu-id="3c850-127">Element</span></span>|<span data-ttu-id="3c850-128">描述</span><span class="sxs-lookup"><span data-stu-id="3c850-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c850-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="3c850-129">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="3c850-130">一个对等解析程序，可用于将对等网格 ID 解析为一组对等节点地址，这些地址表示参与网格的若干节点。</span><span class="sxs-lookup"><span data-stu-id="3c850-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c850-131">备注</span><span class="sxs-lookup"><span data-stu-id="3c850-131">Remarks</span></span>  
 <span data-ttu-id="3c850-132">此元素可定义自定义对等解析程序服务的基本设置，其中包括执行服务的对等解析程序的终结点地址和所有特定绑定设置。</span><span class="sxs-lookup"><span data-stu-id="3c850-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="3c850-133">有关创建自定义冲突解决程序的详细信息，请参阅[PeerChannel 应用程序中添加自定义冲突解决程序](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)。</span><span class="sxs-lookup"><span data-stu-id="3c850-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c850-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c850-134">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [<span data-ttu-id="3c850-135">对等解析程序</span><span class="sxs-lookup"><span data-stu-id="3c850-135">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="3c850-136">对等通道应用程序中添加自定义冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="3c850-136">Adding a Custom Resolver to a PeerChannel Application</span></span>](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
