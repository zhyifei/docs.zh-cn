---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 76b3cbf6b867a983c203141bcd901b2b7b4038d5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855181"
---
# <a name="headers"></a><span data-ttu-id="9492e-101">\<标头 ></span><span class="sxs-lookup"><span data-stu-id="9492e-101">\<headers></span></span>
<span data-ttu-id="9492e-102">除了其基本 URI 外，终结点可以按一个或多个 SOAP 标头寻址。</span><span class="sxs-lookup"><span data-stu-id="9492e-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="9492e-103">这一点在其中很有用的一组方案是一组 SOAP 媒介方案，其中终结点要求该终结点的客户端包括以媒介为目标的 SOAP 头。</span><span class="sxs-lookup"><span data-stu-id="9492e-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="9492e-104">此配置元素可用于定义此类自定义地址标头。</span><span class="sxs-lookup"><span data-stu-id="9492e-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="9492e-105">终结点标头集合中的项是用户定义的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="9492e-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="9492e-106">每个元素必须是格式良好的 XML。</span><span class="sxs-lookup"><span data-stu-id="9492e-106">Each element has to be well-formed XML.</span></span>  
  
<span data-ttu-id="9492e-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9492e-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9492e-108">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9492e-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9492e-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<客户端 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="9492e-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="9492e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<终结点 >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="9492e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="9492e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<标头 >**</span><span class="sxs-lookup"><span data-stu-id="9492e-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9492e-112">语法</span><span class="sxs-lookup"><span data-stu-id="9492e-112">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9492e-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9492e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9492e-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9492e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9492e-115">特性</span><span class="sxs-lookup"><span data-stu-id="9492e-115">Attributes</span></span>  
 <span data-ttu-id="9492e-116">无。</span><span class="sxs-lookup"><span data-stu-id="9492e-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9492e-117">子元素</span><span class="sxs-lookup"><span data-stu-id="9492e-117">Child Elements</span></span>  
 <span data-ttu-id="9492e-118">用户定义的 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="9492e-118">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9492e-119">父元素</span><span class="sxs-lookup"><span data-stu-id="9492e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9492e-120">元素</span><span class="sxs-lookup"><span data-stu-id="9492e-120">Element</span></span>|<span data-ttu-id="9492e-121">描述</span><span class="sxs-lookup"><span data-stu-id="9492e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9492e-122">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="9492e-122">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="9492e-123">配置不同类型的终结点。</span><span class="sxs-lookup"><span data-stu-id="9492e-123">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9492e-124">备注</span><span class="sxs-lookup"><span data-stu-id="9492e-124">Remarks</span></span>  
 <span data-ttu-id="9492e-125">可选标头提供用于标识终结点或与终结点交互的更多详细寻址信息。</span><span class="sxs-lookup"><span data-stu-id="9492e-125">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="9492e-126">例如，标头可指示如何处理传入消息，终结点应发送答复消息的位置，或在多个实例可用时应使用哪个服务实例处理来自特定用户的传入消息。</span><span class="sxs-lookup"><span data-stu-id="9492e-126">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9492e-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="9492e-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="9492e-128">终结点地址、绑定和协定</span><span class="sxs-lookup"><span data-stu-id="9492e-128">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
