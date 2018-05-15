---
title: '&lt;binaryMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 298f211eca12d0e76821a2172d93d432dc830507
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltbinarymessageencodinggt"></a><span data-ttu-id="e96a0-102">&lt;binaryMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="e96a0-102">&lt;binaryMessageEncoding&gt;</span></span>
<span data-ttu-id="e96a0-103">定义一个在网络上以二进制形式对 Windows Communication Foundation (WCF) 消息进行编码的二进制消息编码器。</span><span class="sxs-lookup"><span data-stu-id="e96a0-103">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="e96a0-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e96a0-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e96a0-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="e96a0-105">\<bindings></span></span>  
<span data-ttu-id="e96a0-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e96a0-106">\<customBinding></span></span>  
<span data-ttu-id="e96a0-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="e96a0-107">\<binding></span></span>  
<span data-ttu-id="e96a0-108">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="e96a0-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e96a0-109">语法</span><span class="sxs-lookup"><span data-stu-id="e96a0-109">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding   
      maxReadPoolSize="Integer"  
   maxSessionSize="Integer"   
   maxWritePoolSize="Integer"   messageVersion="Soap11Addressing10/Soap12Addressing10" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e96a0-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e96a0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e96a0-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e96a0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e96a0-112">特性</span><span class="sxs-lookup"><span data-stu-id="e96a0-112">Attributes</span></span>  
  
|<span data-ttu-id="e96a0-113">特性</span><span class="sxs-lookup"><span data-stu-id="e96a0-113">Attribute</span></span>|<span data-ttu-id="e96a0-114">描述</span><span class="sxs-lookup"><span data-stu-id="e96a0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e96a0-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="e96a0-115">maxReadPoolSize</span></span>|<span data-ttu-id="e96a0-116">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="e96a0-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="e96a0-117">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="e96a0-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e96a0-118">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="e96a0-118">The default is 64.</span></span>|  
|<span data-ttu-id="e96a0-119">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="e96a0-119">maxSessionSize</span></span>|<span data-ttu-id="e96a0-120">一个正整数，设置用于编码的缓冲区的大小（字节）。</span><span class="sxs-lookup"><span data-stu-id="e96a0-120">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="e96a0-121">较大的缓冲区能够提高编码速度，代价是增加了工作集的大小。</span><span class="sxs-lookup"><span data-stu-id="e96a0-121">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="e96a0-122">默认值为 2048。</span><span class="sxs-lookup"><span data-stu-id="e96a0-122">The default is 2048.</span></span>|  
|<span data-ttu-id="e96a0-123">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="e96a0-123">maxWritePoolSize</span></span>|<span data-ttu-id="e96a0-124">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="e96a0-124">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="e96a0-125">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="e96a0-125">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="e96a0-126">默认值为 16。</span><span class="sxs-lookup"><span data-stu-id="e96a0-126">The default is 16.</span></span>|  
|<span data-ttu-id="e96a0-127">messageVersion</span><span class="sxs-lookup"><span data-stu-id="e96a0-127">messageVersion</span></span>|<span data-ttu-id="e96a0-128">指定使用的或预期的 SOAP 消息和 WS-Addressing 版本。</span><span class="sxs-lookup"><span data-stu-id="e96a0-128">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e96a0-129">子元素</span><span class="sxs-lookup"><span data-stu-id="e96a0-129">Child Elements</span></span>  
  
|<span data-ttu-id="e96a0-130">元素</span><span class="sxs-lookup"><span data-stu-id="e96a0-130">Element</span></span>|<span data-ttu-id="e96a0-131">描述</span><span class="sxs-lookup"><span data-stu-id="e96a0-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e96a0-132">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="e96a0-132">\<readerQuotas></span></span>](http://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="e96a0-133">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="e96a0-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="e96a0-134">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="e96a0-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e96a0-135">父元素</span><span class="sxs-lookup"><span data-stu-id="e96a0-135">Parent Elements</span></span>  
  
|<span data-ttu-id="e96a0-136">元素</span><span class="sxs-lookup"><span data-stu-id="e96a0-136">Element</span></span>|<span data-ttu-id="e96a0-137">描述</span><span class="sxs-lookup"><span data-stu-id="e96a0-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e96a0-138">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="e96a0-138">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="e96a0-139">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="e96a0-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e96a0-140">备注</span><span class="sxs-lookup"><span data-stu-id="e96a0-140">Remarks</span></span>  
 <span data-ttu-id="e96a0-141">编码是将消息转换为一个字节序列的过程。</span><span class="sxs-lookup"><span data-stu-id="e96a0-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="e96a0-142">解码是反向过程。</span><span class="sxs-lookup"><span data-stu-id="e96a0-142">Decoding is the reverse process.</span></span> <span data-ttu-id="e96a0-143">Windows Communication Foundation (WCF) 包含三种类型的 SOAP 消息编码：文本、二进制和消息传输优化机制 (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="e96a0-143">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="e96a0-144">`binaryMessageEncoding` 元素为 XML 指定 .NET 二进制格式，且包含可用于指定要使用的字符编码以及 SOAP 和 WS-Addressing 版本的选项。</span><span class="sxs-lookup"><span data-stu-id="e96a0-144">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="e96a0-145">二进制消息编码器在网络上以二进制形式对 Windows Communication Foundation (WCF) 消息进行编码。</span><span class="sxs-lookup"><span data-stu-id="e96a0-145">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="e96a0-146">虽然这种编码有助于非常快速地传输消息，但是丢失了基于 WS-\* 标准的互操作性。</span><span class="sxs-lookup"><span data-stu-id="e96a0-146">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e96a0-147">示例</span><span class="sxs-lookup"><span data-stu-id="e96a0-147">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"  
   maxWritePoolSize="2132"  
   maxSessionSize="3141" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="e96a0-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="e96a0-148">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
 [<span data-ttu-id="e96a0-149">消息编码</span><span class="sxs-lookup"><span data-stu-id="e96a0-149">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="e96a0-150">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="e96a0-150">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="e96a0-151">绑定</span><span class="sxs-lookup"><span data-stu-id="e96a0-151">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e96a0-152">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="e96a0-152">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="e96a0-153">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="e96a0-153">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="e96a0-154">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e96a0-154">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
