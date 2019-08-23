---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: a982fa87ab84725e36ee913f00200cd34f0b8f6f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925579"
---
# <a name="headers"></a><span data-ttu-id="0810b-101">\<标头 ></span><span class="sxs-lookup"><span data-stu-id="0810b-101">\<headers></span></span>
<span data-ttu-id="0810b-102">除了其基本 URI 外，终结点可以按一个或多个 SOAP 标头寻址。</span><span class="sxs-lookup"><span data-stu-id="0810b-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="0810b-103">这一点在其中很有用的一组方案是一组 SOAP 媒介方案，其中终结点要求该终结点的客户端包括以媒介为目标的 SOAP 头。</span><span class="sxs-lookup"><span data-stu-id="0810b-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="0810b-104">此配置元素可用于定义此类自定义地址标头。</span><span class="sxs-lookup"><span data-stu-id="0810b-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="0810b-105">终结点标头集合中的项是用户定义的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="0810b-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="0810b-106">每个元素必须是格式良好的 XML。</span><span class="sxs-lookup"><span data-stu-id="0810b-106">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="0810b-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0810b-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="0810b-108">\<客户端 ></span><span class="sxs-lookup"><span data-stu-id="0810b-108">\<client></span></span>  
<span data-ttu-id="0810b-109">\<终结点 ></span><span class="sxs-lookup"><span data-stu-id="0810b-109">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0810b-110">语法</span><span class="sxs-lookup"><span data-stu-id="0810b-110">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0810b-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0810b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0810b-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0810b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0810b-113">特性</span><span class="sxs-lookup"><span data-stu-id="0810b-113">Attributes</span></span>  
 <span data-ttu-id="0810b-114">无。</span><span class="sxs-lookup"><span data-stu-id="0810b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0810b-115">子元素</span><span class="sxs-lookup"><span data-stu-id="0810b-115">Child Elements</span></span>  
 <span data-ttu-id="0810b-116">用户定义的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="0810b-116">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0810b-117">父元素</span><span class="sxs-lookup"><span data-stu-id="0810b-117">Parent Elements</span></span>  
  
|<span data-ttu-id="0810b-118">元素</span><span class="sxs-lookup"><span data-stu-id="0810b-118">Element</span></span>|<span data-ttu-id="0810b-119">描述</span><span class="sxs-lookup"><span data-stu-id="0810b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0810b-120">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="0810b-120">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="0810b-121">配置不同类型的终结点。</span><span class="sxs-lookup"><span data-stu-id="0810b-121">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0810b-122">备注</span><span class="sxs-lookup"><span data-stu-id="0810b-122">Remarks</span></span>  
 <span data-ttu-id="0810b-123">可选标头提供用于标识终结点或与终结点交互的更多详细寻址信息。</span><span class="sxs-lookup"><span data-stu-id="0810b-123">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="0810b-124">例如，标头可指示如何处理传入消息，终结点应发送答复消息的位置，或在多个实例可用时应使用哪个服务实例处理来自特定用户的传入消息。</span><span class="sxs-lookup"><span data-stu-id="0810b-124">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0810b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="0810b-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="0810b-126">终结点地址、绑定和协定</span><span class="sxs-lookup"><span data-stu-id="0810b-126">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
