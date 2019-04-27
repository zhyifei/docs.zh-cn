---
title: <binaryMessageEncoding>
ms.date: 03/30/2017
ms.assetid: e4ae3cd4-6b67-4ce1-af4b-9400e0a38dba
ms.openlocfilehash: e02ed6ef79fcf52bbe9c33bd9b36a14113e19d1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673441"
---
# <a name="binarymessageencoding"></a><span data-ttu-id="f017e-101">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="f017e-101">\<binaryMessageEncoding></span></span>
<span data-ttu-id="f017e-102">定义一个在网络上以二进制形式对 Windows Communication Foundation (WCF) 消息进行编码的二进制消息编码器。</span><span class="sxs-lookup"><span data-stu-id="f017e-102">Defines a binary message encoder that encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span>  
  
 <span data-ttu-id="f017e-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f017e-103">\<system.serviceModel></span></span>  
<span data-ttu-id="f017e-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="f017e-104">\<bindings></span></span>  
<span data-ttu-id="f017e-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f017e-105">\<customBinding></span></span>  
<span data-ttu-id="f017e-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="f017e-106">\<binding></span></span>  
<span data-ttu-id="f017e-107">\<binaryMessageEncoding></span><span class="sxs-lookup"><span data-stu-id="f017e-107">\<binaryMessageEncoding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f017e-108">语法</span><span class="sxs-lookup"><span data-stu-id="f017e-108">Syntax</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="Integer"
                       maxSessionSize="Integer"
                       maxWritePoolSize="Integer"
                       messageVersion="Soap11Addressing10/Soap12Addressing10" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f017e-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f017e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f017e-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f017e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f017e-111">特性</span><span class="sxs-lookup"><span data-stu-id="f017e-111">Attributes</span></span>  
  
|<span data-ttu-id="f017e-112">特性</span><span class="sxs-lookup"><span data-stu-id="f017e-112">Attribute</span></span>|<span data-ttu-id="f017e-113">描述</span><span class="sxs-lookup"><span data-stu-id="f017e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f017e-114">maxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="f017e-114">maxReadPoolSize</span></span>|<span data-ttu-id="f017e-115">一个整数，指定在无需分配新读取器的情况下可以同时读取的消息数。</span><span class="sxs-lookup"><span data-stu-id="f017e-115">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span> <span data-ttu-id="f017e-116">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="f017e-116">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="f017e-117">默认值为 64。</span><span class="sxs-lookup"><span data-stu-id="f017e-117">The default is 64.</span></span>|  
|<span data-ttu-id="f017e-118">maxSessionSize</span><span class="sxs-lookup"><span data-stu-id="f017e-118">maxSessionSize</span></span>|<span data-ttu-id="f017e-119">一个正整数，设置用于编码的缓冲区的大小（字节）。</span><span class="sxs-lookup"><span data-stu-id="f017e-119">A positive integer that sets the size, in bytes, of the buffer used for encoding.</span></span> <span data-ttu-id="f017e-120">较大的缓冲区能够提高编码速度，代价是增加了工作集的大小。</span><span class="sxs-lookup"><span data-stu-id="f017e-120">A larger buffer increases encoding speed at the expense of the size of the working set.</span></span> <span data-ttu-id="f017e-121">默认值为 2048。</span><span class="sxs-lookup"><span data-stu-id="f017e-121">The default is 2048.</span></span>|  
|<span data-ttu-id="f017e-122">maxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="f017e-122">maxWritePoolSize</span></span>|<span data-ttu-id="f017e-123">一个整数，指定在无需分配新编写器的情况下可以同时发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="f017e-123">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span> <span data-ttu-id="f017e-124">池越大，系统允许的活动峰值就越大，但工作集也会随之增大。</span><span class="sxs-lookup"><span data-stu-id="f017e-124">Larger pool sizes make the system more tolerant to activity spikes at the cost of a larger working set.</span></span> <span data-ttu-id="f017e-125">默认值为 16。</span><span class="sxs-lookup"><span data-stu-id="f017e-125">The default is 16.</span></span>|  
|<span data-ttu-id="f017e-126">messageVersion</span><span class="sxs-lookup"><span data-stu-id="f017e-126">messageVersion</span></span>|<span data-ttu-id="f017e-127">指定使用的或预期的 SOAP 消息和 WS-Addressing 版本。</span><span class="sxs-lookup"><span data-stu-id="f017e-127">Specifies the SOAP message and WS-Addressing versions that are used or expected.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f017e-128">子元素</span><span class="sxs-lookup"><span data-stu-id="f017e-128">Child Elements</span></span>  
  
|<span data-ttu-id="f017e-129">元素</span><span class="sxs-lookup"><span data-stu-id="f017e-129">Element</span></span>|<span data-ttu-id="f017e-130">描述</span><span class="sxs-lookup"><span data-stu-id="f017e-130">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f017e-131">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f017e-131">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="f017e-132">定义可由采用此绑定配置的终结点进行处理的 SOAP 消息的复杂性约束。</span><span class="sxs-lookup"><span data-stu-id="f017e-132">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="f017e-133">此元素的类型为 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>。</span><span class="sxs-lookup"><span data-stu-id="f017e-133">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f017e-134">父元素</span><span class="sxs-lookup"><span data-stu-id="f017e-134">Parent Elements</span></span>  
  
|<span data-ttu-id="f017e-135">元素</span><span class="sxs-lookup"><span data-stu-id="f017e-135">Element</span></span>|<span data-ttu-id="f017e-136">描述</span><span class="sxs-lookup"><span data-stu-id="f017e-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f017e-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="f017e-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f017e-138">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="f017e-138">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f017e-139">备注</span><span class="sxs-lookup"><span data-stu-id="f017e-139">Remarks</span></span>  
 <span data-ttu-id="f017e-140">编码是将消息转换为一个字节序列的过程。</span><span class="sxs-lookup"><span data-stu-id="f017e-140">Encoding is the process of transforming a message into a sequence of bytes.</span></span> <span data-ttu-id="f017e-141">解码是反向过程。</span><span class="sxs-lookup"><span data-stu-id="f017e-141">Decoding is the reverse process.</span></span> <span data-ttu-id="f017e-142">Windows Communication Foundation (WCF) 包含三种类型的 SOAP 消息编码：文本、 二进制和消息传输优化机制 (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="f017e-142">Windows Communication Foundation (WCF) includes three types of encoding for SOAP messages: Text, Binary and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="f017e-143">`binaryMessageEncoding` 元素为 XML 指定 .NET 二进制格式，且包含可用于指定要使用的字符编码以及 SOAP 和 WS-Addressing 版本的选项。</span><span class="sxs-lookup"><span data-stu-id="f017e-143">The `binaryMessageEncoding` element specifies the .NET Binary Format for XML and has options to specify the character encoding and the SOAP and WS-Addressing version to be used.</span></span> <span data-ttu-id="f017e-144">二进制消息编码器在网络上以二进制形式对 Windows Communication Foundation (WCF) 消息进行编码。</span><span class="sxs-lookup"><span data-stu-id="f017e-144">The binary message encoder encodes Windows Communication Foundation (WCF) messages in binary on the wire.</span></span> <span data-ttu-id="f017e-145">虽然这种编码有助于非常快速地传输消息，但是丢失了基于 WS-\* 标准的互操作性。</span><span class="sxs-lookup"><span data-stu-id="f017e-145">While this encoding results in very fast transmission of messages, interoperability based on the WS-\* standards is lost.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f017e-146">示例</span><span class="sxs-lookup"><span data-stu-id="f017e-146">Example</span></span>  
  
```xml  
<binaryMessageEncoding maxReadPoolSize="211"
                       maxWritePoolSize="2132"
                       maxSessionSize="3141" />
```  
  
## <a name="see-also"></a><span data-ttu-id="f017e-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="f017e-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.BinaryMessageEncodingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
- [<span data-ttu-id="f017e-148">消息编码</span><span class="sxs-lookup"><span data-stu-id="f017e-148">Message Encoding</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-encoding.md)
- [<span data-ttu-id="f017e-149">选择消息编码器</span><span class="sxs-lookup"><span data-stu-id="f017e-149">Choosing a Message Encoder</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)
- [<span data-ttu-id="f017e-150">绑定</span><span class="sxs-lookup"><span data-stu-id="f017e-150">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f017e-151">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="f017e-151">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f017e-152">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="f017e-152">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f017e-153">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="f017e-153">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
