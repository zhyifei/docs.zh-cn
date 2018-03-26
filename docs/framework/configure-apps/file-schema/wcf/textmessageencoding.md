---
title: '&lt;textMessageEncoding&gt;'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5ac17ead3c7054f0125527e3992fe865624770a9
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2018
---
# <a name="lttextmessageencodinggt"></a><span data-ttu-id="67964-102">&lt;textMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="67964-102">&lt;textMessageEncoding&gt;</span></span>
<span data-ttu-id="67964-103">指定用于基于文本的 XML 消息的字符编码和消息版本控制。</span><span class="sxs-lookup"><span data-stu-id="67964-103">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="67964-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="67964-104">\<system.serviceModel></span></span>  
<span data-ttu-id="67964-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="67964-105">\<bindings></span></span>  
<span data-ttu-id="67964-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="67964-106">\<customBinding></span></span>  
<span data-ttu-id="67964-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="67964-107">\<binding></span></span>  
<span data-ttu-id="67964-108">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="67964-108">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67964-109">语法</span><span class="sxs-lookup"><span data-stu-id="67964-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"  
   maxWritePoolSize="Integer"  
   messageVersion="Soap11Addressing10/Soap12Addressing10"  
      writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67964-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="67964-110">Attributes and Elements</span></span>  
 <span data-ttu-id="67964-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="67964-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67964-112">特性</span><span class="sxs-lookup"><span data-stu-id="67964-112">Attributes</span></span>  
  
|<span data-ttu-id="67964-113">特性</span><span class="sxs-lookup"><span data-stu-id="67964-113">Attribute</span></span>|<span data-ttu-id="67964-114">描述</span><span class="sxs-lookup"><span data-stu-id="67964-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="67964-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="67964-115">maxReadPoolSize</span></span>|<span data-ttu-id="67964-116">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="67964-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="67964-117">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="67964-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="67964-118">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="67964-118">The default is 64.</span></span>|  
|<span data-ttu-id="67964-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="67964-119">maxWritePoolSize</span></span>|<span data-ttu-id="67964-120">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="67964-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="67964-121">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="67964-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="67964-122">默认值为 16。</span><span class="sxs-lookup"><span data-stu-id="67964-122">The default is 16.</span></span>|  
|<span data-ttu-id="67964-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="67964-123">messageVersion</span></span>|<span data-ttu-id="67964-124">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="67964-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="67964-125">有效值为</span><span class="sxs-lookup"><span data-stu-id="67964-125">Valid values are</span></span><br /><br /> <span data-ttu-id="67964-126">-   Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="67964-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="67964-127">-   Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="67964-127">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="67964-128">默认值为 Soap12Addressing10。</span><span class="sxs-lookup"><span data-stu-id="67964-128">The default is Soap12Addressing10.</span></span> <span data-ttu-id="67964-129">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="67964-129">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="67964-130">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="67964-130">writeEncoding</span></span>|<span data-ttu-id="67964-131">指定要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="67964-131">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="67964-132">有效值为</span><span class="sxs-lookup"><span data-stu-id="67964-132">Valid values are</span></span><br /><br /> <span data-ttu-id="67964-133">-UnicodeFffeTextEncoding: Unicode BigEndian 编码</span><span class="sxs-lookup"><span data-stu-id="67964-133">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="67964-134">-Utf16TextEncoding: Unicode 编码</span><span class="sxs-lookup"><span data-stu-id="67964-134">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="67964-135">-Utf8TextEncoding: 8 位编码</span><span class="sxs-lookup"><span data-stu-id="67964-135">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="67964-136">默认值为 Utf8TextEncoding。</span><span class="sxs-lookup"><span data-stu-id="67964-136">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="67964-137">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="67964-137">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67964-138">子元素</span><span class="sxs-lookup"><span data-stu-id="67964-138">Child Elements</span></span>  
  
|<span data-ttu-id="67964-139">元素</span><span class="sxs-lookup"><span data-stu-id="67964-139">Element</span></span>|<span data-ttu-id="67964-140">描述</span><span class="sxs-lookup"><span data-stu-id="67964-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67964-141">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="67964-141">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="67964-142">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="67964-142">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="67964-143">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="67964-143">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="67964-144">父元素</span><span class="sxs-lookup"><span data-stu-id="67964-144">Parent Elements</span></span>  
  
|<span data-ttu-id="67964-145">元素</span><span class="sxs-lookup"><span data-stu-id="67964-145">Element</span></span>|<span data-ttu-id="67964-146">描述</span><span class="sxs-lookup"><span data-stu-id="67964-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67964-147">\<binding></span><span class="sxs-lookup"><span data-stu-id="67964-147">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="67964-148">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="67964-148">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67964-149">备注</span><span class="sxs-lookup"><span data-stu-id="67964-149">Remarks</span></span>  
 <span data-ttu-id="67964-150">编码是将消息转换为一个字节序列的过程。</span><span class="sxs-lookup"><span data-stu-id="67964-150">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="67964-151">解码是反向过程。</span><span class="sxs-lookup"><span data-stu-id="67964-151">Decoding is the reverse process.</span></span> <span data-ttu-id="67964-152">Windows Communication Foundation (WCF) 包含三种类型的 SOAP 消息编码：文本、二进制和消息传输优化机制 (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="67964-152">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="67964-153">由 `textMessageEncoding` 元素表示的文本编码互操作性最强，但却是效率最低的 XML 消息编码器。</span><span class="sxs-lookup"><span data-stu-id="67964-153">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="67964-154">文本编码器在网络上创建基于文本的消息。</span><span class="sxs-lookup"><span data-stu-id="67964-154">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="67964-155">此编码器产生的消息适合于基于 WS-\* 的互操作性。</span><span class="sxs-lookup"><span data-stu-id="67964-155">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="67964-156">Web 服务或 Web 服务客户端通常可以理解文本 XML。</span><span class="sxs-lookup"><span data-stu-id="67964-156">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="67964-157">但是，对于 XML 消息编码来说，以文本形式传输较大的二进制数据块是最低效的方法。</span><span class="sxs-lookup"><span data-stu-id="67964-157">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67964-158">示例</span><span class="sxs-lookup"><span data-stu-id="67964-158">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"  
    maxWritePoolSize="2132"  
    messageVersion="Soap12Addressing10"  
    textEncoding="utf-8" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="67964-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67964-159">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
 [<span data-ttu-id="67964-160">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="67964-160">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="67964-161">消息编码</span><span class="sxs-lookup"><span data-stu-id="67964-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="67964-162">绑定</span><span class="sxs-lookup"><span data-stu-id="67964-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="67964-163">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="67964-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="67964-164">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="67964-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="67964-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="67964-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
