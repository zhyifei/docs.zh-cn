---
title: '&lt;mtomMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: 7865d171-cd1e-430a-8421-39cc13541d1b
ms.openlocfilehash: a59f4f4ca5024b492a1e99b50776870032077818
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149608"
---
# <a name="ltmtommessageencodinggt"></a><span data-ttu-id="b8b38-102">&lt;mtomMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="b8b38-102">&lt;mtomMessageEncoding&gt;</span></span>
<span data-ttu-id="b8b38-103">指定用于基于 SOAP 消息传输优化机制 (MTOM) 的消息的编码和消息版本控制。</span><span class="sxs-lookup"><span data-stu-id="b8b38-103">Specifies the encoding and message versioning used for SOAP Message Transmission Optimization Mechanism (MTOM) based messages.</span></span>  
  
 <span data-ttu-id="b8b38-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b8b38-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b8b38-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="b8b38-105">\<bindings></span></span>  
<span data-ttu-id="b8b38-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b8b38-106">\<customBinding></span></span>  
<span data-ttu-id="b8b38-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="b8b38-107">\<binding></span></span>  
<span data-ttu-id="b8b38-108">\<mtomMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="b8b38-108">\<mtomMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8b38-109">语法</span><span class="sxs-lookup"><span data-stu-id="b8b38-109">Syntax</span></span>  
  
```xml  
<mtomMessageEncoding maxBufferSize="Integer"
                     maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing1/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8b38-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b8b38-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b8b38-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b8b38-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8b38-112">特性</span><span class="sxs-lookup"><span data-stu-id="b8b38-112">Attributes</span></span>  
  
|<span data-ttu-id="b8b38-113">特性</span><span class="sxs-lookup"><span data-stu-id="b8b38-113">Attribute</span></span>|<span data-ttu-id="b8b38-114">描述</span><span class="sxs-lookup"><span data-stu-id="b8b38-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b8b38-115">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="b8b38-115">maxBufferSize</span></span>|<span data-ttu-id="b8b38-116">一个指定可以使用的缓冲区最大大小的整数。</span><span class="sxs-lookup"><span data-stu-id="b8b38-116">An integer that specifies the maximum size of the buffer that can be used.</span></span>|  
|<span data-ttu-id="b8b38-117">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="b8b38-117">maxReadPoolSize</span></span>|<span data-ttu-id="b8b38-118">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="b8b38-118">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="b8b38-119">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="b8b38-119">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="b8b38-120">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="b8b38-120">The default is 64.</span></span>|  
|<span data-ttu-id="b8b38-121">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="b8b38-121">maxWritePoolSize</span></span>|<span data-ttu-id="b8b38-122">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="b8b38-122">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="b8b38-123">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="b8b38-123">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="b8b38-124">默认值为 16。</span><span class="sxs-lookup"><span data-stu-id="b8b38-124">The default is 16.</span></span>|  
|<span data-ttu-id="b8b38-125">messageVersion</span><span class="sxs-lookup"><span data-stu-id="b8b38-125">messageVersion</span></span>|<span data-ttu-id="b8b38-126">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="b8b38-126">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="b8b38-127">有效值为</span><span class="sxs-lookup"><span data-stu-id="b8b38-127">Valid values are</span></span><br /><br /> <span data-ttu-id="b8b38-128">-Soap11Addressing1</span><span class="sxs-lookup"><span data-stu-id="b8b38-128">-   Soap11Addressing1</span></span><br /><span data-ttu-id="b8b38-129">-   Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="b8b38-129">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="b8b38-130">默认值为 Soap12Addressing10。</span><span class="sxs-lookup"><span data-stu-id="b8b38-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="b8b38-131">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="b8b38-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="b8b38-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="b8b38-132">writeEncoding</span></span>|<span data-ttu-id="b8b38-133">指定要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="b8b38-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="b8b38-134">有效值为</span><span class="sxs-lookup"><span data-stu-id="b8b38-134">Valid values are</span></span><br /><br /> <span data-ttu-id="b8b38-135">-UnicodeFffeTextEncoding:Unicode BigEndian 编码</span><span class="sxs-lookup"><span data-stu-id="b8b38-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="b8b38-136">-Utf16TextEncoding:Unicode 编码</span><span class="sxs-lookup"><span data-stu-id="b8b38-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="b8b38-137">-Utf8TextEncoding:8 位编码</span><span class="sxs-lookup"><span data-stu-id="b8b38-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="b8b38-138">默认值为 Utf8TextEncoding。</span><span class="sxs-lookup"><span data-stu-id="b8b38-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="b8b38-139">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="b8b38-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b8b38-140">子元素</span><span class="sxs-lookup"><span data-stu-id="b8b38-140">Child Elements</span></span>  
  
|<span data-ttu-id="b8b38-141">元素</span><span class="sxs-lookup"><span data-stu-id="b8b38-141">Element</span></span>|<span data-ttu-id="b8b38-142">描述</span><span class="sxs-lookup"><span data-stu-id="b8b38-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8b38-143">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="b8b38-143">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="b8b38-144">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="b8b38-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="b8b38-145">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="b8b38-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8b38-146">父元素</span><span class="sxs-lookup"><span data-stu-id="b8b38-146">Parent Elements</span></span>  
  
|<span data-ttu-id="b8b38-147">元素</span><span class="sxs-lookup"><span data-stu-id="b8b38-147">Element</span></span>|<span data-ttu-id="b8b38-148">描述</span><span class="sxs-lookup"><span data-stu-id="b8b38-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8b38-149">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="b8b38-149">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="b8b38-150">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="b8b38-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8b38-151">备注</span><span class="sxs-lookup"><span data-stu-id="b8b38-151">Remarks</span></span>  
 <span data-ttu-id="b8b38-152">编码是将消息转换为一个字节序列的过程。</span><span class="sxs-lookup"><span data-stu-id="b8b38-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="b8b38-153">解码是反向过程。</span><span class="sxs-lookup"><span data-stu-id="b8b38-153">Decoding is the reverse process.</span></span> <span data-ttu-id="b8b38-154">Windows Communication Foundation (WCF) 包含三种类型的 SOAP 消息编码：文本、 二进制和消息传输优化机制 (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="b8b38-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="b8b38-155">`MtomMessageEncoding` 元素指定使用消息传输优化机制 (MTOM) 编码的消息所用的字符编码和消息版本管理以及其他设置。</span><span class="sxs-lookup"><span data-stu-id="b8b38-155">The `MtomMessageEncoding` element specifies the character encoding and message versioning and other settings used for messages using a Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="b8b38-156">MTOM 是一种用于在 WCF 消息中传输二进制数据的有效技术。</span><span class="sxs-lookup"><span data-stu-id="b8b38-156">MTOM is an efficient technology for transmitting binary data in WCF messages.</span></span> <span data-ttu-id="b8b38-157">MTOM 编码器会尝试在效率和互操作性之间建立平衡。</span><span class="sxs-lookup"><span data-stu-id="b8b38-157">The MTOM encoder attempts to create a balance between efficiency and interoperability.</span></span> <span data-ttu-id="b8b38-158">MTOM 编码以文本形式传输大多数 XML，但通过按原样传输来优化大型二进制数据块的传输，无需将其转换为 base64 编码格式。</span><span class="sxs-lookup"><span data-stu-id="b8b38-158">The MTOM encoding transmits most XML in textual form, but optimizes large blocks of binary data by transmitting them as-is, without conversion to their base64 encoded format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8b38-159">示例</span><span class="sxs-lookup"><span data-stu-id="b8b38-159">Example</span></span>  
  
```xml  
<mtomMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap11Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="b8b38-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8b38-160">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.MtomMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
 [<span data-ttu-id="b8b38-161">消息编码</span><span class="sxs-lookup"><span data-stu-id="b8b38-161">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="b8b38-162">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="b8b38-162">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="b8b38-163">绑定</span><span class="sxs-lookup"><span data-stu-id="b8b38-163">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b8b38-164">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="b8b38-164">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="b8b38-165">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="b8b38-165">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="b8b38-166">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="b8b38-166">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
