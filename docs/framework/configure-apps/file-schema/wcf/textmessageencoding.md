---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: c9f8347b4ee5f8fdbcf5c65c9a38b171ea6309de
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289596"
---
# <a name="textmessageencoding"></a><span data-ttu-id="0c32f-101">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="0c32f-101">\<textMessageEncoding></span></span>
<span data-ttu-id="0c32f-102">指定用于基于文本的 XML 消息的字符编码和消息版本控制。</span><span class="sxs-lookup"><span data-stu-id="0c32f-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="0c32f-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0c32f-103">\<system.serviceModel></span></span>  
<span data-ttu-id="0c32f-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0c32f-104">\<bindings></span></span>  
<span data-ttu-id="0c32f-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0c32f-105">\<customBinding></span></span>  
<span data-ttu-id="0c32f-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="0c32f-106">\<binding></span></span>  
<span data-ttu-id="0c32f-107">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="0c32f-107">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c32f-108">语法</span><span class="sxs-lookup"><span data-stu-id="0c32f-108">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c32f-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0c32f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0c32f-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0c32f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c32f-111">特性</span><span class="sxs-lookup"><span data-stu-id="0c32f-111">Attributes</span></span>  
  
|<span data-ttu-id="0c32f-112">特性</span><span class="sxs-lookup"><span data-stu-id="0c32f-112">Attribute</span></span>|<span data-ttu-id="0c32f-113">描述</span><span class="sxs-lookup"><span data-stu-id="0c32f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c32f-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="0c32f-114">maxReadPoolSize</span></span>|<span data-ttu-id="0c32f-115">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="0c32f-115">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="0c32f-116">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="0c32f-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="0c32f-117">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="0c32f-117">The default is 64.</span></span>|  
|<span data-ttu-id="0c32f-118">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="0c32f-118">maxWritePoolSize</span></span>|<span data-ttu-id="0c32f-119">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="0c32f-119">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="0c32f-120">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="0c32f-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="0c32f-121">默认值为 16。</span><span class="sxs-lookup"><span data-stu-id="0c32f-121">The default is 16.</span></span>|  
|<span data-ttu-id="0c32f-122">messageVersion</span><span class="sxs-lookup"><span data-stu-id="0c32f-122">messageVersion</span></span>|<span data-ttu-id="0c32f-123">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="0c32f-123">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="0c32f-124">有效值为</span><span class="sxs-lookup"><span data-stu-id="0c32f-124">Valid values are</span></span><br /><br /> <span data-ttu-id="0c32f-125">-   Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="0c32f-125">-   Soap11Addressing10</span></span><br /><span data-ttu-id="0c32f-126">-   Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="0c32f-126">-   Soap12Addressing10</span></span><br /><br /> <span data-ttu-id="0c32f-127">默认值为 Soap12Addressing10。</span><span class="sxs-lookup"><span data-stu-id="0c32f-127">The default is Soap12Addressing10.</span></span> <span data-ttu-id="0c32f-128">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="0c32f-128">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="0c32f-129">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="0c32f-129">writeEncoding</span></span>|<span data-ttu-id="0c32f-130">指定要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="0c32f-130">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="0c32f-131">有效值为</span><span class="sxs-lookup"><span data-stu-id="0c32f-131">Valid values are</span></span><br /><br /> <span data-ttu-id="0c32f-132">-UnicodeFffeTextEncoding:Unicode BigEndian 编码</span><span class="sxs-lookup"><span data-stu-id="0c32f-132">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="0c32f-133">-Utf16TextEncoding:Unicode 编码</span><span class="sxs-lookup"><span data-stu-id="0c32f-133">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="0c32f-134">-Utf8TextEncoding:8 位编码</span><span class="sxs-lookup"><span data-stu-id="0c32f-134">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="0c32f-135">默认值为 Utf8TextEncoding。</span><span class="sxs-lookup"><span data-stu-id="0c32f-135">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="0c32f-136">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="0c32f-136">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c32f-137">子元素</span><span class="sxs-lookup"><span data-stu-id="0c32f-137">Child Elements</span></span>  
  
|<span data-ttu-id="0c32f-138">元素</span><span class="sxs-lookup"><span data-stu-id="0c32f-138">Element</span></span>|<span data-ttu-id="0c32f-139">描述</span><span class="sxs-lookup"><span data-stu-id="0c32f-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c32f-140">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="0c32f-140">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="0c32f-141">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="0c32f-141">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="0c32f-142">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="0c32f-142">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0c32f-143">父元素</span><span class="sxs-lookup"><span data-stu-id="0c32f-143">Parent Elements</span></span>  
  
|<span data-ttu-id="0c32f-144">元素</span><span class="sxs-lookup"><span data-stu-id="0c32f-144">Element</span></span>|<span data-ttu-id="0c32f-145">描述</span><span class="sxs-lookup"><span data-stu-id="0c32f-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0c32f-146">\<binding></span><span class="sxs-lookup"><span data-stu-id="0c32f-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="0c32f-147">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="0c32f-147">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c32f-148">备注</span><span class="sxs-lookup"><span data-stu-id="0c32f-148">Remarks</span></span>  
 <span data-ttu-id="0c32f-149">编码是将消息转换为一个字节序列的过程。</span><span class="sxs-lookup"><span data-stu-id="0c32f-149">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="0c32f-150">解码是反向过程。</span><span class="sxs-lookup"><span data-stu-id="0c32f-150">Decoding is the reverse process.</span></span> <span data-ttu-id="0c32f-151">Windows Communication Foundation (WCF) 包含三种类型的 SOAP 消息编码：文本、 二进制和消息传输优化机制 (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="0c32f-151">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="0c32f-152">由 `textMessageEncoding` 元素表示的文本编码互操作性最强，但却是效率最低的 XML 消息编码器。</span><span class="sxs-lookup"><span data-stu-id="0c32f-152">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="0c32f-153">文本编码器在网络上创建基于文本的消息。</span><span class="sxs-lookup"><span data-stu-id="0c32f-153">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="0c32f-154">此编码器产生的消息适合于基于 WS-\* 的互操作性。</span><span class="sxs-lookup"><span data-stu-id="0c32f-154">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="0c32f-155">Web 服务或 Web 服务客户端通常可以理解文本 XML。</span><span class="sxs-lookup"><span data-stu-id="0c32f-155">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="0c32f-156">但是，对于 XML 消息编码来说，以文本形式传输较大的二进制数据块是最低效的方法。</span><span class="sxs-lookup"><span data-stu-id="0c32f-156">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c32f-157">示例</span><span class="sxs-lookup"><span data-stu-id="0c32f-157">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="0c32f-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c32f-158">See also</span></span>
- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="0c32f-159">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="0c32f-159">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="0c32f-160">消息编码</span><span class="sxs-lookup"><span data-stu-id="0c32f-160">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="0c32f-161">绑定</span><span class="sxs-lookup"><span data-stu-id="0c32f-161">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="0c32f-162">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="0c32f-162">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="0c32f-163">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="0c32f-163">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="0c32f-164">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0c32f-164">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
