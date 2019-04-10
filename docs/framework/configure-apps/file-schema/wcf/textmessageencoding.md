---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e9942ce3ccbec949160ee70dd103d3c1799bd44d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186298"
---
# <a name="textmessageencoding"></a><span data-ttu-id="f23f5-101">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="f23f5-101">\<textMessageEncoding></span></span>
<span data-ttu-id="f23f5-102">指定用于基于文本的 XML 消息的字符编码和消息版本控制。</span><span class="sxs-lookup"><span data-stu-id="f23f5-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="f23f5-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f23f5-103">\<system.serviceModel></span></span>  
<span data-ttu-id="f23f5-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f23f5-104">\<bindings></span></span>  
<span data-ttu-id="f23f5-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f23f5-105">\<customBinding></span></span>  
<span data-ttu-id="f23f5-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="f23f5-106">\<binding></span></span>  
<span data-ttu-id="f23f5-107">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="f23f5-107">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f23f5-108">语法</span><span class="sxs-lookup"><span data-stu-id="f23f5-108">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f23f5-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f23f5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f23f5-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f23f5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f23f5-111">特性</span><span class="sxs-lookup"><span data-stu-id="f23f5-111">Attributes</span></span>  
  
|<span data-ttu-id="f23f5-112">特性</span><span class="sxs-lookup"><span data-stu-id="f23f5-112">Attribute</span></span>|<span data-ttu-id="f23f5-113">描述</span><span class="sxs-lookup"><span data-stu-id="f23f5-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f23f5-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="f23f5-114">maxReadPoolSize</span></span>|<span data-ttu-id="f23f5-115">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="f23f5-115">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="f23f5-116">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="f23f5-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="f23f5-117">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="f23f5-117">The default is 64.</span></span>|  
|<span data-ttu-id="f23f5-118">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="f23f5-118">maxWritePoolSize</span></span>|<span data-ttu-id="f23f5-119">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="f23f5-119">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="f23f5-120">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="f23f5-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="f23f5-121">默认值为 16。</span><span class="sxs-lookup"><span data-stu-id="f23f5-121">The default is 16.</span></span>|  
|<span data-ttu-id="f23f5-122">messageVersion</span><span class="sxs-lookup"><span data-stu-id="f23f5-122">messageVersion</span></span>|<span data-ttu-id="f23f5-123">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="f23f5-123">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="f23f5-124">有效值为</span><span class="sxs-lookup"><span data-stu-id="f23f5-124">Valid values are</span></span><br /><br /> <span data-ttu-id="f23f5-125">-   Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="f23f5-125">-   Soap11Addressing10</span></span><br /><span data-ttu-id="f23f5-126">-   Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="f23f5-126">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="f23f5-127">默认值为 Soap12Addressing10。</span><span class="sxs-lookup"><span data-stu-id="f23f5-127">The default is Soap12Addressing10.</span></span> <span data-ttu-id="f23f5-128">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="f23f5-128">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="f23f5-129">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="f23f5-129">writeEncoding</span></span>|<span data-ttu-id="f23f5-130">指定要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="f23f5-130">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="f23f5-131">有效值为</span><span class="sxs-lookup"><span data-stu-id="f23f5-131">Valid values are</span></span><br /><br /> <span data-ttu-id="f23f5-132">-UnicodeFffeTextEncoding:Unicode BigEndian 编码</span><span class="sxs-lookup"><span data-stu-id="f23f5-132">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="f23f5-133">-Utf16TextEncoding:Unicode 编码</span><span class="sxs-lookup"><span data-stu-id="f23f5-133">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="f23f5-134">-Utf8TextEncoding:8 位编码</span><span class="sxs-lookup"><span data-stu-id="f23f5-134">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="f23f5-135">默认值为 Utf8TextEncoding。</span><span class="sxs-lookup"><span data-stu-id="f23f5-135">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="f23f5-136">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="f23f5-136">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f23f5-137">子元素</span><span class="sxs-lookup"><span data-stu-id="f23f5-137">Child Elements</span></span>  
  
|<span data-ttu-id="f23f5-138">元素</span><span class="sxs-lookup"><span data-stu-id="f23f5-138">Element</span></span>|<span data-ttu-id="f23f5-139">描述</span><span class="sxs-lookup"><span data-stu-id="f23f5-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f23f5-140">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="f23f5-140">\<readerQuotas></span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="f23f5-141">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="f23f5-141">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="f23f5-142">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="f23f5-142">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f23f5-143">父元素</span><span class="sxs-lookup"><span data-stu-id="f23f5-143">Parent Elements</span></span>  
  
|<span data-ttu-id="f23f5-144">元素</span><span class="sxs-lookup"><span data-stu-id="f23f5-144">Element</span></span>|<span data-ttu-id="f23f5-145">描述</span><span class="sxs-lookup"><span data-stu-id="f23f5-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f23f5-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="f23f5-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f23f5-147">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="f23f5-147">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f23f5-148">备注</span><span class="sxs-lookup"><span data-stu-id="f23f5-148">Remarks</span></span>  
 <span data-ttu-id="f23f5-149">编码是将消息转换为一个字节序列的过程。</span><span class="sxs-lookup"><span data-stu-id="f23f5-149">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="f23f5-150">解码是反向过程。</span><span class="sxs-lookup"><span data-stu-id="f23f5-150">Decoding is the reverse process.</span></span> <span data-ttu-id="f23f5-151">Windows Communication Foundation (WCF) 包含三种类型的 SOAP 消息编码：文本、 二进制和消息传输优化机制 (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="f23f5-151">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="f23f5-152">由 `textMessageEncoding` 元素表示的文本编码互操作性最强，但却是效率最低的 XML 消息编码器。</span><span class="sxs-lookup"><span data-stu-id="f23f5-152">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="f23f5-153">文本编码器在网络上创建基于文本的消息。</span><span class="sxs-lookup"><span data-stu-id="f23f5-153">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="f23f5-154">此编码器产生的消息适合于基于 WS-\* 的互操作性。</span><span class="sxs-lookup"><span data-stu-id="f23f5-154">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="f23f5-155">Web 服务或 Web 服务客户端通常可以理解文本 XML。</span><span class="sxs-lookup"><span data-stu-id="f23f5-155">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="f23f5-156">但是，对于 XML 消息编码来说，以文本形式传输较大的二进制数据块是最低效的方法。</span><span class="sxs-lookup"><span data-stu-id="f23f5-156">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f23f5-157">示例</span><span class="sxs-lookup"><span data-stu-id="f23f5-157">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="f23f5-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="f23f5-158">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="f23f5-159">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="f23f5-159">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="f23f5-160">消息编码</span><span class="sxs-lookup"><span data-stu-id="f23f5-160">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="f23f5-161">绑定</span><span class="sxs-lookup"><span data-stu-id="f23f5-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f23f5-162">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="f23f5-162">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f23f5-163">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="f23f5-163">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f23f5-164">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f23f5-164">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
