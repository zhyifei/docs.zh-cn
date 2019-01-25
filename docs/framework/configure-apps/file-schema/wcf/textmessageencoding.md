---
title: '&lt;textMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: 68b5c9f1f158f7f78f4ea31dedb9b72eab409e05
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540697"
---
# <a name="lttextmessageencodinggt"></a><span data-ttu-id="0b095-102">&lt;textMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="0b095-102">&lt;textMessageEncoding&gt;</span></span>
<span data-ttu-id="0b095-103">指定用于基于文本的 XML 消息的字符编码和消息版本控制。</span><span class="sxs-lookup"><span data-stu-id="0b095-103">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="0b095-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0b095-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0b095-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0b095-105">\<bindings></span></span>  
<span data-ttu-id="0b095-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0b095-106">\<customBinding></span></span>  
<span data-ttu-id="0b095-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="0b095-107">\<binding></span></span>  
<span data-ttu-id="0b095-108">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="0b095-108">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b095-109">语法</span><span class="sxs-lookup"><span data-stu-id="0b095-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b095-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0b095-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0b095-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0b095-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b095-112">特性</span><span class="sxs-lookup"><span data-stu-id="0b095-112">Attributes</span></span>  
  
|<span data-ttu-id="0b095-113">特性</span><span class="sxs-lookup"><span data-stu-id="0b095-113">Attribute</span></span>|<span data-ttu-id="0b095-114">描述</span><span class="sxs-lookup"><span data-stu-id="0b095-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b095-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="0b095-115">maxReadPoolSize</span></span>|<span data-ttu-id="0b095-116">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="0b095-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="0b095-117">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="0b095-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="0b095-118">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="0b095-118">The default is 64.</span></span>|  
|<span data-ttu-id="0b095-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="0b095-119">maxWritePoolSize</span></span>|<span data-ttu-id="0b095-120">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="0b095-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="0b095-121">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="0b095-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="0b095-122">默认值为 16。</span><span class="sxs-lookup"><span data-stu-id="0b095-122">The default is 16.</span></span>|  
|<span data-ttu-id="0b095-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="0b095-123">messageVersion</span></span>|<span data-ttu-id="0b095-124">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="0b095-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="0b095-125">有效值为</span><span class="sxs-lookup"><span data-stu-id="0b095-125">Valid values are</span></span><br /><br /> <span data-ttu-id="0b095-126">-   Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="0b095-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="0b095-127">-   Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="0b095-127">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="0b095-128">默认值为 Soap12Addressing10。</span><span class="sxs-lookup"><span data-stu-id="0b095-128">The default is Soap12Addressing10.</span></span> <span data-ttu-id="0b095-129">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="0b095-129">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="0b095-130">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="0b095-130">writeEncoding</span></span>|<span data-ttu-id="0b095-131">指定要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="0b095-131">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="0b095-132">有效值为</span><span class="sxs-lookup"><span data-stu-id="0b095-132">Valid values are</span></span><br /><br /> <span data-ttu-id="0b095-133">-UnicodeFffeTextEncoding:Unicode BigEndian 编码</span><span class="sxs-lookup"><span data-stu-id="0b095-133">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="0b095-134">-Utf16TextEncoding:Unicode 编码</span><span class="sxs-lookup"><span data-stu-id="0b095-134">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="0b095-135">-Utf8TextEncoding:8 位编码</span><span class="sxs-lookup"><span data-stu-id="0b095-135">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="0b095-136">默认值为 Utf8TextEncoding。</span><span class="sxs-lookup"><span data-stu-id="0b095-136">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="0b095-137">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="0b095-137">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b095-138">子元素</span><span class="sxs-lookup"><span data-stu-id="0b095-138">Child Elements</span></span>  
  
|<span data-ttu-id="0b095-139">元素</span><span class="sxs-lookup"><span data-stu-id="0b095-139">Element</span></span>|<span data-ttu-id="0b095-140">描述</span><span class="sxs-lookup"><span data-stu-id="0b095-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b095-141">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="0b095-141">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="0b095-142">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="0b095-142">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="0b095-143">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="0b095-143">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b095-144">父元素</span><span class="sxs-lookup"><span data-stu-id="0b095-144">Parent Elements</span></span>  
  
|<span data-ttu-id="0b095-145">元素</span><span class="sxs-lookup"><span data-stu-id="0b095-145">Element</span></span>|<span data-ttu-id="0b095-146">描述</span><span class="sxs-lookup"><span data-stu-id="0b095-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b095-147">\<binding></span><span class="sxs-lookup"><span data-stu-id="0b095-147">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="0b095-148">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="0b095-148">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b095-149">备注</span><span class="sxs-lookup"><span data-stu-id="0b095-149">Remarks</span></span>  
 <span data-ttu-id="0b095-150">编码是将消息转换为一个字节序列的过程。</span><span class="sxs-lookup"><span data-stu-id="0b095-150">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="0b095-151">解码是反向过程。</span><span class="sxs-lookup"><span data-stu-id="0b095-151">Decoding is the reverse process.</span></span> <span data-ttu-id="0b095-152">Windows Communication Foundation (WCF) 包含三种类型的 SOAP 消息编码：文本、 二进制和消息传输优化机制 (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="0b095-152">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="0b095-153">由 `textMessageEncoding` 元素表示的文本编码互操作性最强，但却是效率最低的 XML 消息编码器。</span><span class="sxs-lookup"><span data-stu-id="0b095-153">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="0b095-154">文本编码器在网络上创建基于文本的消息。</span><span class="sxs-lookup"><span data-stu-id="0b095-154">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="0b095-155">此编码器产生的消息适合于基于 WS-\* 的互操作性。</span><span class="sxs-lookup"><span data-stu-id="0b095-155">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="0b095-156">Web 服务或 Web 服务客户端通常可以理解文本 XML。</span><span class="sxs-lookup"><span data-stu-id="0b095-156">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="0b095-157">但是，对于 XML 消息编码来说，以文本形式传输较大的二进制数据块是最低效的方法。</span><span class="sxs-lookup"><span data-stu-id="0b095-157">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b095-158">示例</span><span class="sxs-lookup"><span data-stu-id="0b095-158">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="0b095-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b095-159">See also</span></span>
- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="0b095-160">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="0b095-160">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="0b095-161">消息编码</span><span class="sxs-lookup"><span data-stu-id="0b095-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="0b095-162">绑定</span><span class="sxs-lookup"><span data-stu-id="0b095-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="0b095-163">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="0b095-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0b095-164">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="0b095-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0b095-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0b095-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
