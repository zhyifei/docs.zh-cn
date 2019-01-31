---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 2b268d9d040bbeed2b3563783226f7ca8c18e3b5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254283"
---
# <a name="custom"></a><span data-ttu-id="fd2a5-101">\<custom></span><span class="sxs-lookup"><span data-stu-id="fd2a5-101">\<custom></span></span>
<span data-ttu-id="fd2a5-102">指定自定义对等解析程序服务的设置。</span><span class="sxs-lookup"><span data-stu-id="fd2a5-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="fd2a5-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="fd2a5-103">\<system.serviceModel></span></span>  
<span data-ttu-id="fd2a5-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="fd2a5-104">\<bindings></span></span>  
<span data-ttu-id="fd2a5-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="fd2a5-105">\<netPeerBinding></span></span>  
<span data-ttu-id="fd2a5-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="fd2a5-106">\<binding></span></span>  
<span data-ttu-id="fd2a5-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="fd2a5-107">\<resolver></span></span>  
<span data-ttu-id="fd2a5-108">\<custom></span><span class="sxs-lookup"><span data-stu-id="fd2a5-108">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd2a5-109">语法</span><span class="sxs-lookup"><span data-stu-id="fd2a5-109">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fd2a5-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fd2a5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fd2a5-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fd2a5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fd2a5-112">特性</span><span class="sxs-lookup"><span data-stu-id="fd2a5-112">Attributes</span></span>  
  
|<span data-ttu-id="fd2a5-113">特性</span><span class="sxs-lookup"><span data-stu-id="fd2a5-113">Attribute</span></span>|<span data-ttu-id="fd2a5-114">描述</span><span class="sxs-lookup"><span data-stu-id="fd2a5-114">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="fd2a5-115">一个 URI，指定承载自定义对等解析程序服务的对等节点的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="fd2a5-115">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="fd2a5-116">一个字符串值，指定自定义对等解析程序服务的类型。</span><span class="sxs-lookup"><span data-stu-id="fd2a5-116">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fd2a5-117">子元素</span><span class="sxs-lookup"><span data-stu-id="fd2a5-117">Child Elements</span></span>  
  
|<span data-ttu-id="fd2a5-118">元素</span><span class="sxs-lookup"><span data-stu-id="fd2a5-118">Element</span></span>|<span data-ttu-id="fd2a5-119">描述</span><span class="sxs-lookup"><span data-stu-id="fd2a5-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd2a5-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="fd2a5-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="fd2a5-121">指定配置了此元素的自定义对等解析程序的标识。</span><span class="sxs-lookup"><span data-stu-id="fd2a5-121">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="fd2a5-122">此元素的类型为 <xref:System.ServiceModel.Configuration.IdentityElement>。</span><span class="sxs-lookup"><span data-stu-id="fd2a5-122">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="fd2a5-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="fd2a5-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="fd2a5-124">一个地址标头集合，可用于由自定义对等解析程序处理的 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="fd2a5-124">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fd2a5-125">父元素</span><span class="sxs-lookup"><span data-stu-id="fd2a5-125">Parent Elements</span></span>  
  
|<span data-ttu-id="fd2a5-126">元素</span><span class="sxs-lookup"><span data-stu-id="fd2a5-126">Element</span></span>|<span data-ttu-id="fd2a5-127">描述</span><span class="sxs-lookup"><span data-stu-id="fd2a5-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fd2a5-128">\<resolver></span><span class="sxs-lookup"><span data-stu-id="fd2a5-128">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="fd2a5-129">一个对等解析程序，可用于将对等网格 ID 解析为一组对等节点地址，这些地址表示参与网格的若干节点。</span><span class="sxs-lookup"><span data-stu-id="fd2a5-129">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fd2a5-130">备注</span><span class="sxs-lookup"><span data-stu-id="fd2a5-130">Remarks</span></span>  
 <span data-ttu-id="fd2a5-131">此元素可定义自定义对等解析程序服务的基本设置，其中包括执行服务的对等解析程序的终结点地址和所有特定绑定设置。</span><span class="sxs-lookup"><span data-stu-id="fd2a5-131">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="fd2a5-132">有关创建自定义冲突解决程序的详细信息，请参阅[PeerChannel 应用程序中添加自定义冲突解决程序](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)。</span><span class="sxs-lookup"><span data-stu-id="fd2a5-132">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd2a5-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd2a5-133">See also</span></span>
- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="fd2a5-134">对等解析程序</span><span class="sxs-lookup"><span data-stu-id="fd2a5-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- [<span data-ttu-id="fd2a5-135">对等通道应用程序中添加自定义冲突解决程序</span><span class="sxs-lookup"><span data-stu-id="fd2a5-135">Adding a Custom Resolver to a PeerChannel Application</span></span>](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
