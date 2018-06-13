---
title: '&lt;标头&gt;'
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 7683b07093719cda6b210a4174d47e5785d4644d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747146"
---
# <a name="ltheadersgt"></a><span data-ttu-id="3c572-102">&lt;标头&gt;</span><span class="sxs-lookup"><span data-stu-id="3c572-102">&lt;headers&gt;</span></span>
<span data-ttu-id="3c572-103">除了其基本 URI 外，终结点可以按一个或多个 SOAP 标头寻址。</span><span class="sxs-lookup"><span data-stu-id="3c572-103">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="3c572-104">这一点在其中很有用的一组方案是一组 SOAP 媒介方案，其中终结点要求该终结点的客户端包括以媒介为目标的 SOAP 头。</span><span class="sxs-lookup"><span data-stu-id="3c572-104">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="3c572-105">此配置元素可用于定义此类自定义地址标头。</span><span class="sxs-lookup"><span data-stu-id="3c572-105">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="3c572-106">终结点标头集合中的项是用户定义的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="3c572-106">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="3c572-107">每个元素必须是格式良好的 XML。</span><span class="sxs-lookup"><span data-stu-id="3c572-107">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="3c572-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="3c572-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="3c572-109">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="3c572-109">\<client></span></span>  
<span data-ttu-id="3c572-110">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="3c572-110">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c572-111">语法</span><span class="sxs-lookup"><span data-stu-id="3c572-111">Syntax</span></span>  
  
```xml  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c572-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3c572-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3c572-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3c572-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c572-114">特性</span><span class="sxs-lookup"><span data-stu-id="3c572-114">Attributes</span></span>  
 <span data-ttu-id="3c572-115">无。</span><span class="sxs-lookup"><span data-stu-id="3c572-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3c572-116">子元素</span><span class="sxs-lookup"><span data-stu-id="3c572-116">Child Elements</span></span>  
  
|<span data-ttu-id="3c572-117">元素</span><span class="sxs-lookup"><span data-stu-id="3c572-117">Element</span></span>|<span data-ttu-id="3c572-118">描述</span><span class="sxs-lookup"><span data-stu-id="3c572-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3c572-119">Region</span><span class="sxs-lookup"><span data-stu-id="3c572-119">Region</span></span>||  
|<span data-ttu-id="3c572-120">成员</span><span class="sxs-lookup"><span data-stu-id="3c572-120">Member</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="3c572-121">父元素</span><span class="sxs-lookup"><span data-stu-id="3c572-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3c572-122">元素</span><span class="sxs-lookup"><span data-stu-id="3c572-122">Element</span></span>|<span data-ttu-id="3c572-123">描述</span><span class="sxs-lookup"><span data-stu-id="3c572-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3c572-124">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="3c572-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="3c572-125">配置不同类型的终结点。</span><span class="sxs-lookup"><span data-stu-id="3c572-125">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c572-126">备注</span><span class="sxs-lookup"><span data-stu-id="3c572-126">Remarks</span></span>  
 <span data-ttu-id="3c572-127">可选标头提供用于标识终结点或与终结点交互的更多详细寻址信息。</span><span class="sxs-lookup"><span data-stu-id="3c572-127">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="3c572-128">例如，标头可指示如何处理传入消息，终结点应发送答复消息的位置，或在多个实例可用时应使用哪个服务实例处理来自特定用户的传入消息。</span><span class="sxs-lookup"><span data-stu-id="3c572-128">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c572-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c572-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [<span data-ttu-id="3c572-130">终结点：地址、绑定和协定</span><span class="sxs-lookup"><span data-stu-id="3c572-130">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
