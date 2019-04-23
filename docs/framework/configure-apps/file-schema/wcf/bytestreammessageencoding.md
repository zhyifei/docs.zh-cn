---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: ce9f282ea1101befe3bf99762efa61e9b47b74cf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109897"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="2d13c-101">\<byteStreamMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="2d13c-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="2d13c-102">指定消息编码作为字节流，也可以选择指定字符编码。</span><span class="sxs-lookup"><span data-stu-id="2d13c-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="2d13c-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2d13c-103">\<system.serviceModel></span></span>  
<span data-ttu-id="2d13c-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2d13c-104">\<bindings></span></span>  
<span data-ttu-id="2d13c-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2d13c-105">\<customBinding></span></span>  
<span data-ttu-id="2d13c-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="2d13c-106">\<binding></span></span>  
<span data-ttu-id="2d13c-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="2d13c-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d13c-108">语法</span><span class="sxs-lookup"><span data-stu-id="2d13c-108">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d13c-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2d13c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2d13c-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2d13c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d13c-111">特性</span><span class="sxs-lookup"><span data-stu-id="2d13c-111">Attributes</span></span>  
  
|<span data-ttu-id="2d13c-112">特性</span><span class="sxs-lookup"><span data-stu-id="2d13c-112">Attribute</span></span>|<span data-ttu-id="2d13c-113">描述</span><span class="sxs-lookup"><span data-stu-id="2d13c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2d13c-114">messageVersion</span><span class="sxs-lookup"><span data-stu-id="2d13c-114">messageVersion</span></span>|<span data-ttu-id="2d13c-115">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="2d13c-115">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="2d13c-116">此属性只能设置为 <xref:System.ServiceModel.Channels.MessageVersion.None%2A> 的消息版本值。</span><span class="sxs-lookup"><span data-stu-id="2d13c-116">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="2d13c-117">字节流消息编码器不支持其他任何消息版本。</span><span class="sxs-lookup"><span data-stu-id="2d13c-117">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="2d13c-118">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="2d13c-118">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d13c-119">子元素</span><span class="sxs-lookup"><span data-stu-id="2d13c-119">Child Elements</span></span>  
  
|<span data-ttu-id="2d13c-120">元素</span><span class="sxs-lookup"><span data-stu-id="2d13c-120">Element</span></span>|<span data-ttu-id="2d13c-121">描述</span><span class="sxs-lookup"><span data-stu-id="2d13c-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2d13c-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="2d13c-122">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="2d13c-123">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="2d13c-123">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="2d13c-124">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="2d13c-124">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2d13c-125">父元素</span><span class="sxs-lookup"><span data-stu-id="2d13c-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2d13c-126">元素</span><span class="sxs-lookup"><span data-stu-id="2d13c-126">Element</span></span>|<span data-ttu-id="2d13c-127">描述</span><span class="sxs-lookup"><span data-stu-id="2d13c-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d13c-128">\<binding></span><span class="sxs-lookup"><span data-stu-id="2d13c-128">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="2d13c-129">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="2d13c-129">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d13c-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d13c-130">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="2d13c-131">消息编码</span><span class="sxs-lookup"><span data-stu-id="2d13c-131">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="2d13c-132">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="2d13c-132">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="2d13c-133">绑定</span><span class="sxs-lookup"><span data-stu-id="2d13c-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="2d13c-134">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="2d13c-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2d13c-135">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="2d13c-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="2d13c-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2d13c-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
