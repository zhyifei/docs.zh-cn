---
title: <byteStreamMessageEncoding>
ms.date: 03/30/2017
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
ms.openlocfilehash: 1d4109bde9c1668bc0832689b05e5d1dc3b198e9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739063"
---
# <a name="bytestreammessageencoding"></a><span data-ttu-id="28829-101">\<byteStreamMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="28829-101">\<byteStreamMessageEncoding></span></span>
<span data-ttu-id="28829-102">指定消息编码作为字节流，也可以选择指定字符编码。</span><span class="sxs-lookup"><span data-stu-id="28829-102">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
<span data-ttu-id="28829-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="28829-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="28829-104">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="28829-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="28829-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="28829-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="28829-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="28829-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="28829-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="28829-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="28829-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<byteStreamMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="28829-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<byteStreamMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28829-109">语法</span><span class="sxs-lookup"><span data-stu-id="28829-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28829-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="28829-110">Attributes and Elements</span></span>  
 <span data-ttu-id="28829-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="28829-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28829-112">特性</span><span class="sxs-lookup"><span data-stu-id="28829-112">Attributes</span></span>  
  
|<span data-ttu-id="28829-113">特性</span><span class="sxs-lookup"><span data-stu-id="28829-113">Attribute</span></span>|<span data-ttu-id="28829-114">描述</span><span class="sxs-lookup"><span data-stu-id="28829-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="28829-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="28829-115">messageVersion</span></span>|<span data-ttu-id="28829-116">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="28829-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="28829-117">此属性只能设置为 <xref:System.ServiceModel.Channels.MessageVersion.None%2A> 的消息版本值。</span><span class="sxs-lookup"><span data-stu-id="28829-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="28829-118">字节流消息编码器不支持其他任何消息版本。</span><span class="sxs-lookup"><span data-stu-id="28829-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="28829-119">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="28829-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28829-120">子元素</span><span class="sxs-lookup"><span data-stu-id="28829-120">Child Elements</span></span>  
  
|<span data-ttu-id="28829-121">元素</span><span class="sxs-lookup"><span data-stu-id="28829-121">Element</span></span>|<span data-ttu-id="28829-122">描述</span><span class="sxs-lookup"><span data-stu-id="28829-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28829-123">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="28829-123">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="28829-124">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="28829-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="28829-125">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="28829-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="28829-126">父元素</span><span class="sxs-lookup"><span data-stu-id="28829-126">Parent Elements</span></span>  
  
|<span data-ttu-id="28829-127">元素</span><span class="sxs-lookup"><span data-stu-id="28829-127">Element</span></span>|<span data-ttu-id="28829-128">描述</span><span class="sxs-lookup"><span data-stu-id="28829-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28829-129">\<binding ></span><span class="sxs-lookup"><span data-stu-id="28829-129">\<binding></span></span>](bindings.md)|<span data-ttu-id="28829-130">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="28829-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28829-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="28829-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>
- [<span data-ttu-id="28829-132">消息编码</span><span class="sxs-lookup"><span data-stu-id="28829-132">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="28829-133">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="28829-133">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="28829-134">绑定</span><span class="sxs-lookup"><span data-stu-id="28829-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="28829-135">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="28829-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="28829-136">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="28829-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="28829-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="28829-137">\<customBinding></span></span>](custombinding.md)
