---
title: <textMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e6d834d0-356e-45eb-b530-bbefbb9ec3f0
ms.openlocfilehash: d67d623736f3cbf50568356132a74d2b234fdfd9
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736215"
---
# <a name="textmessageencoding"></a><span data-ttu-id="5be1c-101">\<textMessageEncoding ></span><span class="sxs-lookup"><span data-stu-id="5be1c-101">\<textMessageEncoding></span></span>
<span data-ttu-id="5be1c-102">指定用于基于文本的 XML 消息的字符编码和消息版本控制。</span><span class="sxs-lookup"><span data-stu-id="5be1c-102">Specifies the character encoding and message versioning used for text-based XML messages.</span></span>  
  
<span data-ttu-id="5be1c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5be1c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5be1c-104">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="5be1c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5be1c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="5be1c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="5be1c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="5be1c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="5be1c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="5be1c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="5be1c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<textMessageEncoding >**</span><span class="sxs-lookup"><span data-stu-id="5be1c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<textMessageEncoding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5be1c-109">语法</span><span class="sxs-lookup"><span data-stu-id="5be1c-109">Syntax</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="Integer"
                     maxWritePoolSize="Integer"
                     messageVersion="Soap11Addressing10/Soap12Addressing10"
                     writeEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5be1c-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5be1c-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5be1c-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5be1c-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5be1c-112">特性</span><span class="sxs-lookup"><span data-stu-id="5be1c-112">Attributes</span></span>  
  
|<span data-ttu-id="5be1c-113">特性</span><span class="sxs-lookup"><span data-stu-id="5be1c-113">Attribute</span></span>|<span data-ttu-id="5be1c-114">描述</span><span class="sxs-lookup"><span data-stu-id="5be1c-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5be1c-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="5be1c-115">maxReadPoolSize</span></span>|<span data-ttu-id="5be1c-116">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="5be1c-116">An integer that specifies how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="5be1c-117">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="5be1c-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="5be1c-118">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="5be1c-118">The default is 64.</span></span>|  
|<span data-ttu-id="5be1c-119">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="5be1c-119">maxWritePoolSize</span></span>|<span data-ttu-id="5be1c-120">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="5be1c-120">An integer that specifies how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="5be1c-121">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="5be1c-121">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="5be1c-122">默认值为 16。</span><span class="sxs-lookup"><span data-stu-id="5be1c-122">The default is 16.</span></span>|  
|<span data-ttu-id="5be1c-123">messageVersion</span><span class="sxs-lookup"><span data-stu-id="5be1c-123">messageVersion</span></span>|<span data-ttu-id="5be1c-124">指定使用此绑定发送的消息的 SOAP 版本。</span><span class="sxs-lookup"><span data-stu-id="5be1c-124">Specifies the SOAP version of the messages sent using the binding.</span></span> <span data-ttu-id="5be1c-125">有效值为</span><span class="sxs-lookup"><span data-stu-id="5be1c-125">Valid values are</span></span><br /><br /> <span data-ttu-id="5be1c-126">- Soap11Addressing10</span><span class="sxs-lookup"><span data-stu-id="5be1c-126">-   Soap11Addressing10</span></span><br /><span data-ttu-id="5be1c-127">- Soap12Addressing10</span><span class="sxs-lookup"><span data-stu-id="5be1c-127">-   Soap12Addressing10</span></span><br /><span data-ttu-id="5be1c-128">- Soap11</span><span class="sxs-lookup"><span data-stu-id="5be1c-128">-   Soap11</span></span><br /><span data-ttu-id="5be1c-129">- Soap12</span><span class="sxs-lookup"><span data-stu-id="5be1c-129">-  Soap12</span></span><br /><br /><span data-ttu-id="5be1c-130">默认值为 Soap12Addressing10。</span><span class="sxs-lookup"><span data-stu-id="5be1c-130">The default is Soap12Addressing10.</span></span> <span data-ttu-id="5be1c-131">此属性的类型为 <xref:System.ServiceModel.Channels.MessageVersion>。</span><span class="sxs-lookup"><span data-stu-id="5be1c-131">This attribute is of type <xref:System.ServiceModel.Channels.MessageVersion>.</span></span>|  
|<span data-ttu-id="5be1c-132">writeEncoding</span><span class="sxs-lookup"><span data-stu-id="5be1c-132">writeEncoding</span></span>|<span data-ttu-id="5be1c-133">指定要用来在绑定上发出消息的字符集编码。</span><span class="sxs-lookup"><span data-stu-id="5be1c-133">Specifies the character set encoding to be used for emitting messages on the binding.</span></span> <span data-ttu-id="5be1c-134">有效值为</span><span class="sxs-lookup"><span data-stu-id="5be1c-134">Valid values are</span></span><br /><br /> <span data-ttu-id="5be1c-135">-UnicodeFffeTextEncoding： Unicode BigEndian 编码</span><span class="sxs-lookup"><span data-stu-id="5be1c-135">-   UnicodeFffeTextEncoding: Unicode BigEndian encoding</span></span><br /><span data-ttu-id="5be1c-136">-Utf16TextEncoding： Unicode 编码</span><span class="sxs-lookup"><span data-stu-id="5be1c-136">-   Utf16TextEncoding: Unicode encoding</span></span><br /><span data-ttu-id="5be1c-137">-Utf8TextEncoding：8位编码</span><span class="sxs-lookup"><span data-stu-id="5be1c-137">-   Utf8TextEncoding: 8-bit encoding</span></span><br /><br /> <span data-ttu-id="5be1c-138">默认值为 Utf8TextEncoding。</span><span class="sxs-lookup"><span data-stu-id="5be1c-138">The default is Utf8TextEncoding.</span></span> <span data-ttu-id="5be1c-139">此属性的类型为 <xref:System.Text.Encoding>。</span><span class="sxs-lookup"><span data-stu-id="5be1c-139">This attribute is of type <xref:System.Text.Encoding>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5be1c-140">子元素</span><span class="sxs-lookup"><span data-stu-id="5be1c-140">Child Elements</span></span>  
  
|<span data-ttu-id="5be1c-141">元素</span><span class="sxs-lookup"><span data-stu-id="5be1c-141">Element</span></span>|<span data-ttu-id="5be1c-142">描述</span><span class="sxs-lookup"><span data-stu-id="5be1c-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5be1c-143">[\<readerQuotas >](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5be1c-143">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="5be1c-144">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="5be1c-144">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="5be1c-145">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="5be1c-145">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5be1c-146">父元素</span><span class="sxs-lookup"><span data-stu-id="5be1c-146">Parent Elements</span></span>  
  
|<span data-ttu-id="5be1c-147">元素</span><span class="sxs-lookup"><span data-stu-id="5be1c-147">Element</span></span>|<span data-ttu-id="5be1c-148">描述</span><span class="sxs-lookup"><span data-stu-id="5be1c-148">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5be1c-149">\<binding ></span><span class="sxs-lookup"><span data-stu-id="5be1c-149">\<binding></span></span>](bindings.md)|<span data-ttu-id="5be1c-150">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="5be1c-150">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5be1c-151">备注</span><span class="sxs-lookup"><span data-stu-id="5be1c-151">Remarks</span></span>  
 <span data-ttu-id="5be1c-152">编码是将消息转换为一个字节序列的过程。</span><span class="sxs-lookup"><span data-stu-id="5be1c-152">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="5be1c-153">解码是反向过程。</span><span class="sxs-lookup"><span data-stu-id="5be1c-153">Decoding is the reverse process.</span></span> <span data-ttu-id="5be1c-154">Windows Communication Foundation (WCF) 包含三种类型的 SOAP 消息编码：文本、二进制和消息传输优化机制 (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="5be1c-154">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="5be1c-155">由 `textMessageEncoding` 元素表示的文本编码互操作性最强，但却是效率最低的 XML 消息编码器。</span><span class="sxs-lookup"><span data-stu-id="5be1c-155">The text encoding represented by the `textMessageEncoding` element is the most interoperable, but the least efficient encoder for XML messages.</span></span>  <span data-ttu-id="5be1c-156">文本编码器在网络上创建基于文本的消息。</span><span class="sxs-lookup"><span data-stu-id="5be1c-156">The text encoder creates text-based messages on the wire.</span></span> <span data-ttu-id="5be1c-157">此编码器产生的消息适合于基于 WS-\* 的互操作性。</span><span class="sxs-lookup"><span data-stu-id="5be1c-157">Messages produced by this encoder are suitable for WS-\* based interop.</span></span> <span data-ttu-id="5be1c-158">Web 服务或 Web 服务客户端通常可以理解文本 XML。</span><span class="sxs-lookup"><span data-stu-id="5be1c-158">Web service or Web service client can generally understand textual XML.</span></span> <span data-ttu-id="5be1c-159">但是，对于 XML 消息编码来说，以文本形式传输较大的二进制数据块是最低效的方法。</span><span class="sxs-lookup"><span data-stu-id="5be1c-159">However, transmitting large blocks of binary data as text is the least efficient method for encoding XML messages.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5be1c-160">示例</span><span class="sxs-lookup"><span data-stu-id="5be1c-160">Example</span></span>  
  
```xml  
<textMessageEncoding maxReadPoolSize="211"
                     maxWritePoolSize="2132"
                     messageVersion="Soap12Addressing10"
                     textEncoding="utf-8" />
```  
  
## <a name="see-also"></a><span data-ttu-id="5be1c-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="5be1c-161">See also</span></span>

- <xref:System.ServiceModel.Configuration.TextMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- [<span data-ttu-id="5be1c-162">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="5be1c-162">Choosing a Message Encoder</span></span>](../../../wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="5be1c-163">消息编码</span><span class="sxs-lookup"><span data-stu-id="5be1c-163">Message Encoding</span></span>](message-encoding.md)
- [<span data-ttu-id="5be1c-164">绑定</span><span class="sxs-lookup"><span data-stu-id="5be1c-164">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5be1c-165">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="5be1c-165">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5be1c-166">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="5be1c-166">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5be1c-167">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="5be1c-167">\<customBinding></span></span>](custombinding.md)
