---
title: <mtomMessageEncoding>
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: 7867b99a11bc82aac4ed2cd28ec7acf8347259d3
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759426"
---
# <a name="mtommessageencoding"></a><span data-ttu-id="cca6a-101">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="cca6a-101">\<mtomMessageEncoding></span></span>
<span data-ttu-id="cca6a-102">指定用于基于 SOAP 消息传输优化机制 (MTOM) 的消息的编码和消息版本控制。</span><span class="sxs-lookup"><span data-stu-id="cca6a-102">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="cca6a-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cca6a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="cca6a-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="cca6a-104">\<bindings></span></span>  
<span data-ttu-id="cca6a-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="cca6a-105">\<customBinding></span></span>  
<span data-ttu-id="cca6a-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="cca6a-106">\<binding></span></span>  
<span data-ttu-id="cca6a-107">\<mtomMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="cca6a-107">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cca6a-108">语法</span><span class="sxs-lookup"><span data-stu-id="cca6a-108">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cca6a-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cca6a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cca6a-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cca6a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cca6a-111">特性</span><span class="sxs-lookup"><span data-stu-id="cca6a-111">Attributes</span></span>  
  
|<span data-ttu-id="cca6a-112">特性</span><span class="sxs-lookup"><span data-stu-id="cca6a-112">Attribute</span></span>|<span data-ttu-id="cca6a-113">描述</span><span class="sxs-lookup"><span data-stu-id="cca6a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cca6a-114">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="cca6a-114">maxBufferSize</span></span>|<span data-ttu-id="cca6a-115">一个指定可以使用的缓冲区最大大小的整数。</span><span class="sxs-lookup"><span data-stu-id="cca6a-115">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="cca6a-116">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="cca6a-116">maxReadPoolSize</span></span>|<span data-ttu-id="cca6a-117">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="cca6a-117">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="cca6a-118">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="cca6a-118">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="cca6a-119">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="cca6a-119">The default is 64.</span></span>|  
|<span data-ttu-id="cca6a-120">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="cca6a-120">maxWritePoolSize</span></span>|<span data-ttu-id="cca6a-121">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="cca6a-121">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="cca6a-122">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="cca6a-122">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="cca6a-123">默认值为 16。</span><span class="sxs-lookup"><span data-stu-id="cca6a-123">The default is 16.</span></span>|  
|<span data-ttu-id="cca6a-124">messageVersion</span><span class="sxs-lookup"><span data-stu-id="cca6a-124">messageVersion</span></span>|<span data-ttu-id="cca6a-125">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="cca6a-125">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="cca6a-126">有效值为</span><span class="sxs-lookup"><span data-stu-id="cca6a-126">Valid values are</span></span><br /><br /> <span data-ttu-id="cca6a-127">-   Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="cca6a-127">-   Soap11Addressing1</span></span><br /><span data-ttu-id="cca6a-128">-   Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="cca6a-128">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="cca6a-129">默认值为 Soap12Addressing10。</span><span class="sxs-lookup"><span data-stu-id="cca6a-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="cca6a-130">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="cca6a-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="cca6a-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="cca6a-131">writeEncoding</span></span>|<span data-ttu-id="cca6a-132">指定要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="cca6a-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="cca6a-133">有效值为</span><span class="sxs-lookup"><span data-stu-id="cca6a-133">Valid values are</span></span><br /><br /> <span data-ttu-id="cca6a-134">-UnicodeFffeTextEncoding:Unicode BigEndian 编码</span><span class="sxs-lookup"><span data-stu-id="cca6a-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="cca6a-135">-Utf16TextEncoding:Unicode 编码</span><span class="sxs-lookup"><span data-stu-id="cca6a-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="cca6a-136">-Utf8TextEncoding:8 位编码</span><span class="sxs-lookup"><span data-stu-id="cca6a-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="cca6a-137">默认值为 Utf8TextEncoding。</span><span class="sxs-lookup"><span data-stu-id="cca6a-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="cca6a-138">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="cca6a-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cca6a-139">子元素</span><span class="sxs-lookup"><span data-stu-id="cca6a-139">Child Elements</span></span>  
  
|<span data-ttu-id="cca6a-140">元素</span><span class="sxs-lookup"><span data-stu-id="cca6a-140">Element</span></span>|<span data-ttu-id="cca6a-141">描述</span><span class="sxs-lookup"><span data-stu-id="cca6a-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cca6a-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="cca6a-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="cca6a-143">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="cca6a-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="cca6a-144">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="cca6a-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cca6a-145">父元素</span><span class="sxs-lookup"><span data-stu-id="cca6a-145">Parent Elements</span></span>  
  
|<span data-ttu-id="cca6a-146">元素</span><span class="sxs-lookup"><span data-stu-id="cca6a-146">Element</span></span>|<span data-ttu-id="cca6a-147">描述</span><span class="sxs-lookup"><span data-stu-id="cca6a-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cca6a-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="cca6a-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="cca6a-149">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="cca6a-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cca6a-150">备注</span><span class="sxs-lookup"><span data-stu-id="cca6a-150">Remarks</span></span>  
 <span data-ttu-id="cca6a-151">编码是将消息转换为一个字节序列的过程。</span><span class="sxs-lookup"><span data-stu-id="cca6a-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="cca6a-152">解码是反向过程。</span><span class="sxs-lookup"><span data-stu-id="cca6a-152">Decoding is the reverse process.</span></span> <span data-ttu-id="cca6a-153">Windows Communication Foundation (WCF) 包含三种类型的 SOAP 消息编码：文本、 二进制和消息传输优化机制 (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="cca6a-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="cca6a-154">`MtomMessageEncoding` 元素指定使用消息传输优化机制 (MTOM) 编码的消息所用的字符编码和消息版本管理以及其他设置。</span><span class="sxs-lookup"><span data-stu-id="cca6a-154">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="cca6a-155">MTOM 是一种用于在 WCF 消息中传输二进制数据的有效技术。</span><span class="sxs-lookup"><span data-stu-id="cca6a-155">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="cca6a-156">MTOM 编码器会尝试在效率和互操作性之间建立平衡。</span><span class="sxs-lookup"><span data-stu-id="cca6a-156">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="cca6a-157">MTOM 编码以文本形式传输大多数 XML，但通过按原样传输来优化大型二进制数据块的传输，无需将其转换为 base64 编码格式。</span><span class="sxs-lookup"><span data-stu-id="cca6a-157">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cca6a-158">示例</span><span class="sxs-lookup"><span data-stu-id="cca6a-158">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="cca6a-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="cca6a-159">See also</span></span>
- <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
- [<span data-ttu-id="cca6a-160">消息编码</span><span class="sxs-lookup"><span data-stu-id="cca6a-160">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="cca6a-161">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="cca6a-161">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="cca6a-162">绑定</span><span class="sxs-lookup"><span data-stu-id="cca6a-162">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="cca6a-163">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="cca6a-163">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="cca6a-164">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="cca6a-164">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="cca6a-165">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="cca6a-165">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
