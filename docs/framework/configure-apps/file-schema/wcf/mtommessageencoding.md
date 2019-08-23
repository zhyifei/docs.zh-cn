---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 70a124fda5bc0e52e1271716f7e2166b7717b49a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933190"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="add7b-101">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="add7b-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="add7b-102">指定用于基于 SOAP 消息传输优化机制 (MTOM) 的消息的编码和消息版本控制。</span><span class="sxs-lookup"><span data-stu-id="add7b-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="add7b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="add7b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="add7b-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="add7b-104">\<bindings></span></span>  
<span data-ttu-id="add7b-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="add7b-105">\<customBinding></span></span>  
<span data-ttu-id="add7b-106">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="add7b-106">\<binding></span></span>  
<span data-ttu-id="add7b-107">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="add7b-107">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="add7b-108">语法</span><span class="sxs-lookup"><span data-stu-id="add7b-108">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="add7b-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="add7b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="add7b-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="add7b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="add7b-111">特性</span><span class="sxs-lookup"><span data-stu-id="add7b-111">Attributes</span></span>  
  
|<span data-ttu-id="add7b-112">特性</span><span class="sxs-lookup"><span data-stu-id="add7b-112">Attribute</span></span>|<span data-ttu-id="add7b-113">描述</span><span class="sxs-lookup"><span data-stu-id="add7b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="add7b-114">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="add7b-114">maxBufferSize</span></span>|<span data-ttu-id="add7b-115">一个指定可以使用的缓冲区最大大小的整数。</span><span class="sxs-lookup"><span data-stu-id="add7b-115">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="add7b-116">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="add7b-116">maxReadPoolSize</span></span>|<span data-ttu-id="add7b-117">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="add7b-117">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="add7b-118">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="add7b-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="add7b-119">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="add7b-119">The default is 64.</span></span>|  
|<span data-ttu-id="add7b-120">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="add7b-120">maxWritePoolSize</span></span>|<span data-ttu-id="add7b-121">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="add7b-121">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="add7b-122">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="add7b-122">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="add7b-123">默认值为 16。</span><span class="sxs-lookup"><span data-stu-id="add7b-123">The default is 16.</span></span>|  
|<span data-ttu-id="add7b-124">messageVersion</span><span class="sxs-lookup"><span data-stu-id="add7b-124">messageVersion</span></span>|<span data-ttu-id="add7b-125">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="add7b-125">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="add7b-126">有效值为</span><span class="sxs-lookup"><span data-stu-id="add7b-126">Valid values are</span></span><br /><br /> <span data-ttu-id="add7b-127">-   Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="add7b-127">-   Soap11Addressing1</span></span><br /><span data-ttu-id="add7b-128">-   Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="add7b-128">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="add7b-129">默认值为 Soap12Addressing10。</span><span class="sxs-lookup"><span data-stu-id="add7b-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="add7b-130">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="add7b-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="add7b-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="add7b-131">writeEncoding</span></span>|<span data-ttu-id="add7b-132">指定要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="add7b-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="add7b-133">有效值为</span><span class="sxs-lookup"><span data-stu-id="add7b-133">Valid values are</span></span><br /><br /> <span data-ttu-id="add7b-134">UnicodeFffeTextEncodingUnicode BigEndian 编码</span><span class="sxs-lookup"><span data-stu-id="add7b-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="add7b-135">Utf16TextEncodingUnicode 编码</span><span class="sxs-lookup"><span data-stu-id="add7b-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="add7b-136">Utf8TextEncoding8位编码</span><span class="sxs-lookup"><span data-stu-id="add7b-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="add7b-137">默认值为 Utf8TextEncoding。</span><span class="sxs-lookup"><span data-stu-id="add7b-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="add7b-138">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="add7b-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="add7b-139">子元素</span><span class="sxs-lookup"><span data-stu-id="add7b-139">Child Elements</span></span>  
  
|<span data-ttu-id="add7b-140">元素</span><span class="sxs-lookup"><span data-stu-id="add7b-140">Element</span></span>|<span data-ttu-id="add7b-141">描述</span><span class="sxs-lookup"><span data-stu-id="add7b-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="add7b-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="add7b-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="add7b-143">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="add7b-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="add7b-144">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="add7b-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="add7b-145">父元素</span><span class="sxs-lookup"><span data-stu-id="add7b-145">Parent Elements</span></span>  
  
|<span data-ttu-id="add7b-146">元素</span><span class="sxs-lookup"><span data-stu-id="add7b-146">Element</span></span>|<span data-ttu-id="add7b-147">描述</span><span class="sxs-lookup"><span data-stu-id="add7b-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="add7b-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="add7b-148">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="add7b-149">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="add7b-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="add7b-150">备注</span><span class="sxs-lookup"><span data-stu-id="add7b-150">Remarks</span></span>  
 <span data-ttu-id="add7b-151">编码是将消息转换为一个字节序列的过程。</span><span class="sxs-lookup"><span data-stu-id="add7b-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="add7b-152">解码是反向过程。</span><span class="sxs-lookup"><span data-stu-id="add7b-152">Decoding is the reverse process.</span></span> <span data-ttu-id="add7b-153">Windows Communication Foundation (WCF) 包含三种类型的 SOAP 消息编码:文本、二进制和消息传输优化机制 (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="add7b-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="add7b-154">`MtomMessageEncoding` 元素指定使用消息传输优化机制 (MTOM) 编码的消息所用的字符编码和消息版本管理以及其他设置。</span><span class="sxs-lookup"><span data-stu-id="add7b-154">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="add7b-155">MTOM 是一种用于在 WCF 消息中传输二进制数据的有效技术。</span><span class="sxs-lookup"><span data-stu-id="add7b-155">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="add7b-156">MTOM 编码器会尝试在效率和互操作性之间建立平衡。</span><span class="sxs-lookup"><span data-stu-id="add7b-156">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="add7b-157">MTOM 编码以文本形式传输大多数 XML，但通过按原样传输来优化大型二进制数据块的传输，无需将其转换为 base64 编码格式。</span><span class="sxs-lookup"><span data-stu-id="add7b-157">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="add7b-158">示例</span><span class="sxs-lookup"><span data-stu-id="add7b-158">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="add7b-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="add7b-159">See also</span></span>

- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="add7b-160">消息编码</span><span class="sxs-lookup"><span data-stu-id="add7b-160">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="add7b-161">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="add7b-161">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="add7b-162">绑定</span><span class="sxs-lookup"><span data-stu-id="add7b-162">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="add7b-163">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="add7b-163">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="add7b-164">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="add7b-164">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="add7b-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="add7b-165">\<customBinding></span></span>](custombinding.md)
