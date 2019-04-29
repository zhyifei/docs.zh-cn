---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: e6e6d1907d89a09a72594a836f2192e9ad9c4290
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758283"
---
# <a name="textmessageencoding"></a><span data-ttu-id="4b619-101">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="4b619-101">\<textMessageEncoding></span></span>
<span data-ttu-id="4b619-102">指定用于基于文本的 XML 消息的字符编码和消息版本控制。</span><span class="sxs-lookup"><span data-stu-id="4b619-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
 <span data-ttu-id="4b619-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4b619-103">\<system.serviceModel></span></span>  
<span data-ttu-id="4b619-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4b619-104">\<bindings></span></span>  
<span data-ttu-id="4b619-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4b619-105">\<customBinding></span></span>  
<span data-ttu-id="4b619-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="4b619-106">\<binding></span></span>  
<span data-ttu-id="4b619-107">\<textMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="4b619-107">\<textMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b619-108">语法</span><span class="sxs-lookup"><span data-stu-id="4b619-108">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b619-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4b619-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4b619-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4b619-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b619-111">特性</span><span class="sxs-lookup"><span data-stu-id="4b619-111">Attributes</span></span>  
  
|<span data-ttu-id="4b619-112">特性</span><span class="sxs-lookup"><span data-stu-id="4b619-112">Attribute</span></span>|<span data-ttu-id="4b619-113">描述</span><span class="sxs-lookup"><span data-stu-id="4b619-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4b619-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="4b619-114">maxReadPoolSize</span></span>|<span data-ttu-id="4b619-115">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="4b619-115">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="4b619-116">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="4b619-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4b619-117">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="4b619-117">The default is 64.</span></span>|  
|<span data-ttu-id="4b619-118">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="4b619-118">maxWritePoolSize</span></span>|<span data-ttu-id="4b619-119">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="4b619-119">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="4b619-120">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="4b619-120">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="4b619-121">默认值为 16。</span><span class="sxs-lookup"><span data-stu-id="4b619-121">The default is 16.</span></span>|  
|<span data-ttu-id="4b619-122">messageVersion</span><span class="sxs-lookup"><span data-stu-id="4b619-122">messageVersion</span></span>|<span data-ttu-id="4b619-123">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="4b619-123">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="4b619-124">有效值为</span><span class="sxs-lookup"><span data-stu-id="4b619-124">Valid values are</span></span><br /><br /> <span data-ttu-id="4b619-125">-   Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="4b619-125">-   Soap11Addressing10</span></span><br /><span data-ttu-id="4b619-126">-   Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="4b619-126">-   Soap12Addressing10</span></span><br /><span data-ttu-id="4b619-127">-   Soap11</span><span class="sxs-lookup"><span data-stu-id="4b619-127">-   Soap11</span></span><br /><span data-ttu-id="4b619-128">-  Soap12</span><span class="sxs-lookup"><span data-stu-id="4b619-128">-  Soap12</span></span><br /><br /><span data-ttu-id="4b619-129">默认值为 Soap12Addressing10。</span><span class="sxs-lookup"><span data-stu-id="4b619-129">The default is Soap12Addressing10.</span></span> <span data-ttu-id="4b619-130">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="4b619-130">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="4b619-131">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="4b619-131">writeEncoding</span></span>|<span data-ttu-id="4b619-132">指定要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="4b619-132">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="4b619-133">有效值为</span><span class="sxs-lookup"><span data-stu-id="4b619-133">Valid values are</span></span><br /><br /> <span data-ttu-id="4b619-134">-UnicodeFffeTextEncoding:Unicode BigEndian 编码</span><span class="sxs-lookup"><span data-stu-id="4b619-134">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="4b619-135">-Utf16TextEncoding:Unicode 编码</span><span class="sxs-lookup"><span data-stu-id="4b619-135">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="4b619-136">-Utf8TextEncoding:8 位编码</span><span class="sxs-lookup"><span data-stu-id="4b619-136">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="4b619-137">默认值为 Utf8TextEncoding。</span><span class="sxs-lookup"><span data-stu-id="4b619-137">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="4b619-138">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="4b619-138">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4b619-139">子元素</span><span class="sxs-lookup"><span data-stu-id="4b619-139">Child Elements</span></span>  
  
|<span data-ttu-id="4b619-140">元素</span><span class="sxs-lookup"><span data-stu-id="4b619-140">Element</span></span>|<span data-ttu-id="4b619-141">描述</span><span class="sxs-lookup"><span data-stu-id="4b619-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b619-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4b619-142">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="4b619-143">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="4b619-143">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="4b619-144">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="4b619-144">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b619-145">父元素</span><span class="sxs-lookup"><span data-stu-id="4b619-145">Parent Elements</span></span>  
  
|<span data-ttu-id="4b619-146">元素</span><span class="sxs-lookup"><span data-stu-id="4b619-146">Element</span></span>|<span data-ttu-id="4b619-147">描述</span><span class="sxs-lookup"><span data-stu-id="4b619-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4b619-148">\<binding></span><span class="sxs-lookup"><span data-stu-id="4b619-148">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4b619-149">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="4b619-149">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b619-150">备注</span><span class="sxs-lookup"><span data-stu-id="4b619-150">Remarks</span></span>  
 <span data-ttu-id="4b619-151">编码是将消息转换为一个字节序列的过程。</span><span class="sxs-lookup"><span data-stu-id="4b619-151">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="4b619-152">解码是反向过程。</span><span class="sxs-lookup"><span data-stu-id="4b619-152">Decoding is the reverse process.</span></span> <span data-ttu-id="4b619-153">Windows Communication Foundation (WCF) 包含三种类型的 SOAP 消息编码：文本、 二进制和消息传输优化机制 (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="4b619-153">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="4b619-154">由 `textMessageEncoding` 元素表示的文本编码互操作性最强，但却是效率最低的 XML 消息编码器。</span><span class="sxs-lookup"><span data-stu-id="4b619-154">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="4b619-155">文本编码器在网络上创建基于文本的消息。</span><span class="sxs-lookup"><span data-stu-id="4b619-155">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="4b619-156">此编码器产生的消息适合于基于 WS-\* 的互操作性。</span><span class="sxs-lookup"><span data-stu-id="4b619-156">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="4b619-157">Web 服务或 Web 服务客户端通常可以理解文本 XML。</span><span class="sxs-lookup"><span data-stu-id="4b619-157">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="4b619-158">但是，对于 XML 消息编码来说，以文本形式传输较大的二进制数据块是最低效的方法。</span><span class="sxs-lookup"><span data-stu-id="4b619-158">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b619-159">示例</span><span class="sxs-lookup"><span data-stu-id="4b619-159">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="4b619-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b619-160">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="4b619-161">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="4b619-161">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="4b619-162">消息编码</span><span class="sxs-lookup"><span data-stu-id="4b619-162">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="4b619-163">绑定</span><span class="sxs-lookup"><span data-stu-id="4b619-163">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="4b619-164">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="4b619-164">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4b619-165">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="4b619-165">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4b619-166">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="4b619-166">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
