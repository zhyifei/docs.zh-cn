---
title: '&lt;byteStreamMessageEncoding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbadd8dd-60a2-4007-b959-89373a8a7d60
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 165bf4cd1c0c5c1a6adae91650d38984bc47ef6e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="0d17b-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="0d17b-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="0d17b-103">指定消息编码作为字节流，也可以选择指定字符编码。</span><span class="sxs-lookup"><span data-stu-id="0d17b-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="0d17b-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="0d17b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0d17b-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="0d17b-105">\<bindings></span></span>  
<span data-ttu-id="0d17b-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="0d17b-106">\<customBinding></span></span>  
<span data-ttu-id="0d17b-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="0d17b-107">\<binding></span></span>  
<span data-ttu-id="0d17b-108">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="0d17b-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d17b-109">语法</span><span class="sxs-lookup"><span data-stu-id="0d17b-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d17b-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0d17b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0d17b-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0d17b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d17b-112">特性</span><span class="sxs-lookup"><span data-stu-id="0d17b-112">Attributes</span></span>  
  
|<span data-ttu-id="0d17b-113">特性</span><span class="sxs-lookup"><span data-stu-id="0d17b-113">Attribute</span></span>|<span data-ttu-id="0d17b-114">描述</span><span class="sxs-lookup"><span data-stu-id="0d17b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d17b-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="0d17b-115">messageVersion</span></span>|<span data-ttu-id="0d17b-116">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="0d17b-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="0d17b-117">此属性只能设置为 <xref:System.ServiceModel.Channels.MessageVersion.None%2A> 的消息版本值。</span><span class="sxs-lookup"><span data-stu-id="0d17b-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="0d17b-118">字节流消息编码器不支持其他任何消息版本。</span><span class="sxs-lookup"><span data-stu-id="0d17b-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="0d17b-119">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="0d17b-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d17b-120">子元素</span><span class="sxs-lookup"><span data-stu-id="0d17b-120">Child Elements</span></span>  
  
|<span data-ttu-id="0d17b-121">元素</span><span class="sxs-lookup"><span data-stu-id="0d17b-121">Element</span></span>|<span data-ttu-id="0d17b-122">描述</span><span class="sxs-lookup"><span data-stu-id="0d17b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d17b-123">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="0d17b-123">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="0d17b-124">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="0d17b-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="0d17b-125">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="0d17b-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d17b-126">父元素</span><span class="sxs-lookup"><span data-stu-id="0d17b-126">Parent Elements</span></span>  
  
|<span data-ttu-id="0d17b-127">元素</span><span class="sxs-lookup"><span data-stu-id="0d17b-127">Element</span></span>|<span data-ttu-id="0d17b-128">描述</span><span class="sxs-lookup"><span data-stu-id="0d17b-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d17b-129">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="0d17b-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="0d17b-130">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="0d17b-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d17b-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d17b-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>  
 [<span data-ttu-id="0d17b-132">消息编码</span><span class="sxs-lookup"><span data-stu-id="0d17b-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="0d17b-133">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="0d17b-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="0d17b-134">绑定</span><span class="sxs-lookup"><span data-stu-id="0d17b-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="0d17b-135">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="0d17b-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="0d17b-136">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="0d17b-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="0d17b-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="0d17b-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
