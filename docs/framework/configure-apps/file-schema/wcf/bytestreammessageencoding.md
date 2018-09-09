---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 4b031bfb0d0979dc99df13c104a712d6dd771e8a
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44225183"
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="6a1e8-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="6a1e8-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="6a1e8-103">指定消息编码作为字节流，也可以选择指定字符编码。</span><span class="sxs-lookup"><span data-stu-id="6a1e8-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="6a1e8-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6a1e8-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6a1e8-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="6a1e8-105">\<bindings></span></span>  
<span data-ttu-id="6a1e8-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6a1e8-106">\<customBinding></span></span>  
<span data-ttu-id="6a1e8-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="6a1e8-107">\<binding></span></span>  
<span data-ttu-id="6a1e8-108">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="6a1e8-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a1e8-109">语法</span><span class="sxs-lookup"><span data-stu-id="6a1e8-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a1e8-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6a1e8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6a1e8-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6a1e8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a1e8-112">特性</span><span class="sxs-lookup"><span data-stu-id="6a1e8-112">Attributes</span></span>  
  
|<span data-ttu-id="6a1e8-113">特性</span><span class="sxs-lookup"><span data-stu-id="6a1e8-113">Attribute</span></span>|<span data-ttu-id="6a1e8-114">描述</span><span class="sxs-lookup"><span data-stu-id="6a1e8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a1e8-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="6a1e8-115">messageVersion</span></span>|<span data-ttu-id="6a1e8-116">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="6a1e8-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="6a1e8-117">此属性只能设置为 <xref:System.ServiceModel.Channels.MessageVersion.None%2A> 的消息版本值。</span><span class="sxs-lookup"><span data-stu-id="6a1e8-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="6a1e8-118">字节流消息编码器不支持其他任何消息版本。</span><span class="sxs-lookup"><span data-stu-id="6a1e8-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="6a1e8-119">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="6a1e8-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a1e8-120">子元素</span><span class="sxs-lookup"><span data-stu-id="6a1e8-120">Child Elements</span></span>  
  
|<span data-ttu-id="6a1e8-121">元素</span><span class="sxs-lookup"><span data-stu-id="6a1e8-121">Element</span></span>|<span data-ttu-id="6a1e8-122">描述</span><span class="sxs-lookup"><span data-stu-id="6a1e8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a1e8-123">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="6a1e8-123">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="6a1e8-124">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="6a1e8-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="6a1e8-125">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="6a1e8-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a1e8-126">父元素</span><span class="sxs-lookup"><span data-stu-id="6a1e8-126">Parent Elements</span></span>  
  
|<span data-ttu-id="6a1e8-127">元素</span><span class="sxs-lookup"><span data-stu-id="6a1e8-127">Element</span></span>|<span data-ttu-id="6a1e8-128">描述</span><span class="sxs-lookup"><span data-stu-id="6a1e8-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a1e8-129">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="6a1e8-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="6a1e8-130">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="6a1e8-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a1e8-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a1e8-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>  
 [<span data-ttu-id="6a1e8-132">消息编码</span><span class="sxs-lookup"><span data-stu-id="6a1e8-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="6a1e8-133">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="6a1e8-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="6a1e8-134">绑定</span><span class="sxs-lookup"><span data-stu-id="6a1e8-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="6a1e8-135">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="6a1e8-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="6a1e8-136">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="6a1e8-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="6a1e8-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6a1e8-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
