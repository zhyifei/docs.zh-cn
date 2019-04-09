---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: ce9f282ea1101befe3bf99762efa61e9b47b74cf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59109897"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="792de-101">\<byteStreamMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="792de-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="792de-102">指定消息编码作为字节流，也可以选择指定字符编码。</span><span class="sxs-lookup"><span data-stu-id="792de-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="792de-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="792de-103">\<system.serviceModel></span></span>  
<span data-ttu-id="792de-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="792de-104">\<bindings></span></span>  
<span data-ttu-id="792de-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="792de-105">\<customBinding></span></span>  
<span data-ttu-id="792de-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="792de-106">\<binding></span></span>  
<span data-ttu-id="792de-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="792de-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="792de-108">语法</span><span class="sxs-lookup"><span data-stu-id="792de-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="792de-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="792de-109">Attributes and Elements</span></span>  
 <span data-ttu-id="792de-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="792de-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="792de-111">特性</span><span class="sxs-lookup"><span data-stu-id="792de-111">Attributes</span></span>  
  
|<span data-ttu-id="792de-112">特性</span><span class="sxs-lookup"><span data-stu-id="792de-112">Attribute</span></span>|<span data-ttu-id="792de-113">描述</span><span class="sxs-lookup"><span data-stu-id="792de-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="792de-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="792de-114">messageVersion</span></span>|<span data-ttu-id="792de-115">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="792de-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="792de-116">此属性只能设置为 <xref:System.ServiceModel.Channels.MessageVersion.None%2A> 的消息版本值。</span><span class="sxs-lookup"><span data-stu-id="792de-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="792de-117">字节流消息编码器不支持其他任何消息版本。</span><span class="sxs-lookup"><span data-stu-id="792de-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="792de-118">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="792de-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="792de-119">子元素</span><span class="sxs-lookup"><span data-stu-id="792de-119">Child Elements</span></span>  
  
|<span data-ttu-id="792de-120">元素</span><span class="sxs-lookup"><span data-stu-id="792de-120">Element</span></span>|<span data-ttu-id="792de-121">描述</span><span class="sxs-lookup"><span data-stu-id="792de-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="792de-122">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="792de-122">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="792de-123">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="792de-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="792de-124">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="792de-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="792de-125">父元素</span><span class="sxs-lookup"><span data-stu-id="792de-125">Parent Elements</span></span>  
  
|<span data-ttu-id="792de-126">元素</span><span class="sxs-lookup"><span data-stu-id="792de-126">Element</span></span>|<span data-ttu-id="792de-127">描述</span><span class="sxs-lookup"><span data-stu-id="792de-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="792de-128">\<binding></span><span class="sxs-lookup"><span data-stu-id="792de-128">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="792de-129">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="792de-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="792de-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="792de-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="792de-131">消息编码</span><span class="sxs-lookup"><span data-stu-id="792de-131">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="792de-132">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="792de-132">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="792de-133">绑定</span><span class="sxs-lookup"><span data-stu-id="792de-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="792de-134">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="792de-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="792de-135">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="792de-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="792de-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="792de-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
