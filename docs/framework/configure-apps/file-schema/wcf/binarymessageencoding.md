---
title: '&lt;binaryMessageEncoding&gt;'
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: 2e29721104400c8a0352ebf5cd292689de0d6b14
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150118"
---
# <a name="ltbinarymessageencodinggt"></a><span data-ttu-id="0797e-102">&lt;binaryMessageEncoding&gt;</span><span class="sxs-lookup"><span data-stu-id="0797e-102">&lt;binaryMessageEncoding&gt;</span></span>
<span data-ttu-id="0797e-103">定义一个在网络上以二进制形式对 Windows Communication Foundation (WCF) 消息进行编码的二进制消息编码器。</span><span class="sxs-lookup"><span data-stu-id="0797e-103">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="0797e-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0797e-104">\<system.serviceModel></span></span>  
<span data-ttu-id="0797e-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="0797e-105">\<bindings></span></span>  
<span data-ttu-id="0797e-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0797e-106">\<customBinding></span></span>  
<span data-ttu-id="0797e-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="0797e-107">\<binding></span></span>  
<span data-ttu-id="0797e-108">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="0797e-108">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0797e-109">语法</span><span class="sxs-lookup"><span data-stu-id="0797e-109">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0797e-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0797e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0797e-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0797e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0797e-112">特性</span><span class="sxs-lookup"><span data-stu-id="0797e-112">Attributes</span></span>  
  
|<span data-ttu-id="0797e-113">特性</span><span class="sxs-lookup"><span data-stu-id="0797e-113">Attribute</span></span>|<span data-ttu-id="0797e-114">描述</span><span class="sxs-lookup"><span data-stu-id="0797e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0797e-115">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="0797e-115">maxReadPoolSize</span></span>|<span data-ttu-id="0797e-116">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="0797e-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="0797e-117">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="0797e-117">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="0797e-118">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="0797e-118">The default is 64.</span></span>|  
|<span data-ttu-id="0797e-119">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="0797e-119">maxSessionSize</span></span>|<span data-ttu-id="0797e-120">一个正整数，设置用于编码的缓冲区的大小（字节）。</span><span class="sxs-lookup"><span data-stu-id="0797e-120">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="0797e-121">较大的缓冲区能够提高编码速度，代价是增加了工作集的大小。</span><span class="sxs-lookup"><span data-stu-id="0797e-121">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="0797e-122">默认值为 2048。</span><span class="sxs-lookup"><span data-stu-id="0797e-122">The default is 2048.</span></span>|  
|<span data-ttu-id="0797e-123">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="0797e-123">maxWritePoolSize</span></span>|<span data-ttu-id="0797e-124">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="0797e-124">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="0797e-125">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="0797e-125">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="0797e-126">默认值为 16。</span><span class="sxs-lookup"><span data-stu-id="0797e-126">The default is 16.</span></span>|  
|<span data-ttu-id="0797e-127">messageVersion</span><span class="sxs-lookup"><span data-stu-id="0797e-127">messageVersion</span></span>|<span data-ttu-id="0797e-128">指定使用的或预期的 SOAP 消息和 WS-Addressing 版本。</span><span class="sxs-lookup"><span data-stu-id="0797e-128">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0797e-129">子元素</span><span class="sxs-lookup"><span data-stu-id="0797e-129">Child Elements</span></span>  
  
|<span data-ttu-id="0797e-130">元素</span><span class="sxs-lookup"><span data-stu-id="0797e-130">Element</span></span>|<span data-ttu-id="0797e-131">描述</span><span class="sxs-lookup"><span data-stu-id="0797e-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0797e-132">\<readerQuotas></span><span class="sxs-lookup"><span data-stu-id="0797e-132">\<readerQuotas></span></span>](https://msdn.microsoft.com/library/3e5e42ff-cef8-478f-bf14-034449239bfd)|<span data-ttu-id="0797e-133">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="0797e-133">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="0797e-134">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="0797e-134">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0797e-135">父元素</span><span class="sxs-lookup"><span data-stu-id="0797e-135">Parent Elements</span></span>  
  
|<span data-ttu-id="0797e-136">元素</span><span class="sxs-lookup"><span data-stu-id="0797e-136">Element</span></span>|<span data-ttu-id="0797e-137">描述</span><span class="sxs-lookup"><span data-stu-id="0797e-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0797e-138">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="0797e-138">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="0797e-139">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="0797e-139">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0797e-140">备注</span><span class="sxs-lookup"><span data-stu-id="0797e-140">Remarks</span></span>  
 <span data-ttu-id="0797e-141">编码是将消息转换为一个字节序列的过程。</span><span class="sxs-lookup"><span data-stu-id="0797e-141">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="0797e-142">解码是反向过程。</span><span class="sxs-lookup"><span data-stu-id="0797e-142">Decoding is the reverse process.</span></span> <span data-ttu-id="0797e-143">Windows Communication Foundation (WCF) 包含三种类型的 SOAP 消息编码：文本、 二进制和消息传输优化机制 (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="0797e-143">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="0797e-144">`binaryMessageEncoding` 元素为 XML 指定 .NET 二进制格式，且包含可用于指定要使用的字符编码以及 SOAP 和 WS-Addressing 版本的选项。</span><span class="sxs-lookup"><span data-stu-id="0797e-144">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="0797e-145">二进制消息编码器在网络上以二进制形式对 Windows Communication Foundation (WCF) 消息进行编码。</span><span class="sxs-lookup"><span data-stu-id="0797e-145">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="0797e-146">虽然这种编码有助于非常快速地传输消息，但是丢失了基于 WS-\* 标准的互操作性。</span><span class="sxs-lookup"><span data-stu-id="0797e-146">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0797e-147">示例</span><span class="sxs-lookup"><span data-stu-id="0797e-147">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="0797e-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="0797e-148">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>  
 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
 [<span data-ttu-id="0797e-149">消息编码</span><span class="sxs-lookup"><span data-stu-id="0797e-149">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)  
 [<span data-ttu-id="0797e-150">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="0797e-150">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 [<span data-ttu-id="0797e-151">绑定</span><span class="sxs-lookup"><span data-stu-id="0797e-151">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="0797e-152">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="0797e-152">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="0797e-153">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="0797e-153">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="0797e-154">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="0797e-154">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
