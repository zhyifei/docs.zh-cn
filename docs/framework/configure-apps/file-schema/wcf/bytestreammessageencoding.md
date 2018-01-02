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
ms.workload: dotnet
ms.openlocfilehash: 1996a33666ac6b92f1b7bca8c2e2e0ef51456dea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltbytestreammessageencodinggt"></a><span data-ttu-id="f0701-102">&lt;byteStreamMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="f0701-102">&lt;byteStreamMessageEncoding&gt;</span></span>
<span data-ttu-id="f0701-103">指定消息编码作为字节流，也可以选择指定字符编码。</span><span class="sxs-lookup"><span data-stu-id="f0701-103">Specifies the message encoding as a stream of bytes, with the option to specify the character encoding.</span></span>  
  
 <span data-ttu-id="f0701-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f0701-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f0701-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="f0701-105">\<bindings></span></span>  
<span data-ttu-id="f0701-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f0701-106">\<customBinding></span></span>  
<span data-ttu-id="f0701-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="f0701-107">\<binding></span></span>  
<span data-ttu-id="f0701-108">\<binaryMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="f0701-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0701-109">语法</span><span class="sxs-lookup"><span data-stu-id="f0701-109">Syntax</span></span>  
  
```xml  
<byteStreamMessageEncoding/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0701-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f0701-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f0701-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f0701-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0701-112">特性</span><span class="sxs-lookup"><span data-stu-id="f0701-112">Attributes</span></span>  
  
|<span data-ttu-id="f0701-113">特性</span><span class="sxs-lookup"><span data-stu-id="f0701-113">Attribute</span></span>|<span data-ttu-id="f0701-114">描述</span><span class="sxs-lookup"><span data-stu-id="f0701-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f0701-115">messageVersion</span><span class="sxs-lookup"><span data-stu-id="f0701-115">messageVersion</span></span>|<span data-ttu-id="f0701-116">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="f0701-116">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="f0701-117">此属性只能设置为 <xref:System.ServiceModel.Channels.MessageVersion.None%2A> 的消息版本值。</span><span class="sxs-lookup"><span data-stu-id="f0701-117">This property can only be set to the message version value of <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.</span></span> <span data-ttu-id="f0701-118">字节流消息编码器不支持其他任何消息版本。</span><span class="sxs-lookup"><span data-stu-id="f0701-118">The byte stream message encoder does not support any other message versions.</span></span><br /><br /> <span data-ttu-id="f0701-119">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="f0701-119">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0701-120">子元素</span><span class="sxs-lookup"><span data-stu-id="f0701-120">Child Elements</span></span>  
  
|<span data-ttu-id="f0701-121">元素</span><span class="sxs-lookup"><span data-stu-id="f0701-121">Element</span></span>|<span data-ttu-id="f0701-122">描述</span><span class="sxs-lookup"><span data-stu-id="f0701-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0701-123">\<readerQuotas ></span><span class="sxs-lookup"><span data-stu-id="f0701-123">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="f0701-124">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="f0701-124">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="f0701-125">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="f0701-125">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f0701-126">父元素</span><span class="sxs-lookup"><span data-stu-id="f0701-126">Parent Elements</span></span>  
  
|<span data-ttu-id="f0701-127">元素</span><span class="sxs-lookup"><span data-stu-id="f0701-127">Element</span></span>|<span data-ttu-id="f0701-128">描述</span><span class="sxs-lookup"><span data-stu-id="f0701-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0701-129">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="f0701-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f0701-130">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="f0701-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f0701-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0701-131">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ByteStreamMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.ByteStreamMessageEncodingBindingElement>  
 [<span data-ttu-id="f0701-132">消息编码</span><span class="sxs-lookup"><span data-stu-id="f0701-132">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="f0701-133">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="f0701-133">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="f0701-134">绑定</span><span class="sxs-lookup"><span data-stu-id="f0701-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f0701-135">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="f0701-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="f0701-136">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="f0701-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="f0701-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f0701-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
