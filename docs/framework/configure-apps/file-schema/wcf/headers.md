---
title: "&lt;标头&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bcc81c0dd0628a6c5cab93841665b416f18a5bff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltheadersgt"></a><span data-ttu-id="48998-102">&lt;标头&gt;</span><span class="sxs-lookup"><span data-stu-id="48998-102">&lt;headers&gt;</span></span>
<span data-ttu-id="48998-103">除了其基本 URI 外，终结点可以按一个或多个 SOAP 标头寻址。</span><span class="sxs-lookup"><span data-stu-id="48998-103">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="48998-104">这一点在其中很有用的一组方案是一组 SOAP 媒介方案，其中终结点要求该终结点的客户端包括以媒介为目标的 SOAP 头。</span><span class="sxs-lookup"><span data-stu-id="48998-104">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="48998-105">此配置元素可用于定义此类自定义地址标头。</span><span class="sxs-lookup"><span data-stu-id="48998-105">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="48998-106">终结点标头集合中的项是用户定义的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="48998-106">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="48998-107">每个元素必须是格式良好的 XML。</span><span class="sxs-lookup"><span data-stu-id="48998-107">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="48998-108">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="48998-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="48998-109">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="48998-109">\<client></span></span>  
<span data-ttu-id="48998-110">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="48998-110">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48998-111">语法</span><span class="sxs-lookup"><span data-stu-id="48998-111">Syntax</span></span>  
  
```xml  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48998-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="48998-112">Attributes and Elements</span></span>  
 <span data-ttu-id="48998-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="48998-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48998-114">特性</span><span class="sxs-lookup"><span data-stu-id="48998-114">Attributes</span></span>  
 <span data-ttu-id="48998-115">无。</span><span class="sxs-lookup"><span data-stu-id="48998-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="48998-116">子元素</span><span class="sxs-lookup"><span data-stu-id="48998-116">Child Elements</span></span>  
  
|<span data-ttu-id="48998-117">元素</span><span class="sxs-lookup"><span data-stu-id="48998-117">Element</span></span>|<span data-ttu-id="48998-118">描述</span><span class="sxs-lookup"><span data-stu-id="48998-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48998-119">Region</span><span class="sxs-lookup"><span data-stu-id="48998-119">Region</span></span>||  
|<span data-ttu-id="48998-120">成员</span><span class="sxs-lookup"><span data-stu-id="48998-120">Member</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="48998-121">父元素</span><span class="sxs-lookup"><span data-stu-id="48998-121">Parent Elements</span></span>  
  
|<span data-ttu-id="48998-122">元素</span><span class="sxs-lookup"><span data-stu-id="48998-122">Element</span></span>|<span data-ttu-id="48998-123">描述</span><span class="sxs-lookup"><span data-stu-id="48998-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48998-124">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="48998-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="48998-125">配置不同类型的终结点。</span><span class="sxs-lookup"><span data-stu-id="48998-125">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48998-126">备注</span><span class="sxs-lookup"><span data-stu-id="48998-126">Remarks</span></span>  
 <span data-ttu-id="48998-127">可选标头提供用于标识终结点或与终结点交互的更多详细寻址信息。</span><span class="sxs-lookup"><span data-stu-id="48998-127">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="48998-128">例如，标头可指示如何处理传入消息，终结点应发送答复消息的位置，或在多个实例可用时应使用哪个服务实例处理来自特定用户的传入消息。</span><span class="sxs-lookup"><span data-stu-id="48998-128">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48998-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48998-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [<span data-ttu-id="48998-130">终结点： 地址、 绑定和协定</span><span class="sxs-lookup"><span data-stu-id="48998-130">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
