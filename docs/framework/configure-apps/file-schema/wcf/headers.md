---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 660497012dd057e4ecf95524833e2573fe03a8b0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670672"
---
# <a name="headers"></a><span data-ttu-id="55abe-101">\<headers></span><span class="sxs-lookup"><span data-stu-id="55abe-101">\<headers></span></span>
<span data-ttu-id="55abe-102">除了其基本 URI 外，终结点可以按一个或多个 SOAP 标头寻址。</span><span class="sxs-lookup"><span data-stu-id="55abe-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="55abe-103">这一点在其中很有用的一组方案是一组 SOAP 媒介方案，其中终结点要求该终结点的客户端包括以媒介为目标的 SOAP 头。</span><span class="sxs-lookup"><span data-stu-id="55abe-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="55abe-104">此配置元素可用于定义此类自定义地址标头。</span><span class="sxs-lookup"><span data-stu-id="55abe-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="55abe-105">终结点标头集合中的项是用户定义的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="55abe-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="55abe-106">每个元素必须是格式良好的 XML。</span><span class="sxs-lookup"><span data-stu-id="55abe-106">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="55abe-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="55abe-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="55abe-108">\<client></span><span class="sxs-lookup"><span data-stu-id="55abe-108">\<client></span></span>  
<span data-ttu-id="55abe-109">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="55abe-109">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55abe-110">语法</span><span class="sxs-lookup"><span data-stu-id="55abe-110">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55abe-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="55abe-111">Attributes and Elements</span></span>  
 <span data-ttu-id="55abe-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="55abe-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55abe-113">特性</span><span class="sxs-lookup"><span data-stu-id="55abe-113">Attributes</span></span>  
 <span data-ttu-id="55abe-114">无。</span><span class="sxs-lookup"><span data-stu-id="55abe-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="55abe-115">子元素</span><span class="sxs-lookup"><span data-stu-id="55abe-115">Child Elements</span></span>  
 <span data-ttu-id="55abe-116">用户定义的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="55abe-116">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55abe-117">父元素</span><span class="sxs-lookup"><span data-stu-id="55abe-117">Parent Elements</span></span>  
  
|<span data-ttu-id="55abe-118">元素</span><span class="sxs-lookup"><span data-stu-id="55abe-118">Element</span></span>|<span data-ttu-id="55abe-119">描述</span><span class="sxs-lookup"><span data-stu-id="55abe-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55abe-120">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="55abe-120">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="55abe-121">配置不同类型的终结点。</span><span class="sxs-lookup"><span data-stu-id="55abe-121">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55abe-122">备注</span><span class="sxs-lookup"><span data-stu-id="55abe-122">Remarks</span></span>  
 <span data-ttu-id="55abe-123">可选标头提供用于标识终结点或与终结点交互的更多详细寻址信息。</span><span class="sxs-lookup"><span data-stu-id="55abe-123">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="55abe-124">例如，标头可指示如何处理传入消息，终结点应发送答复消息的位置，或在多个实例可用时应使用哪个服务实例处理来自特定用户的传入消息。</span><span class="sxs-lookup"><span data-stu-id="55abe-124">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55abe-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="55abe-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="55abe-126">终结点：地址、 绑定和协定</span><span class="sxs-lookup"><span data-stu-id="55abe-126">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
