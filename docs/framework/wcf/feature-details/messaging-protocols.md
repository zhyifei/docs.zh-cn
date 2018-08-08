---
title: 消息协议
ms.date: 03/30/2017
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
ms.openlocfilehash: d188c79d3879ef383d24f56c81d66973266636bc
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2018
ms.locfileid: "37072717"
---
# <a name="messaging-protocols"></a><span data-ttu-id="dc4d4-102">消息协议</span><span class="sxs-lookup"><span data-stu-id="dc4d4-102">Messaging Protocols</span></span>
<span data-ttu-id="dc4d4-103">Windows Communication Foundation (WCF) 通道堆栈采用编码和传输通道将转换成其网络传输格式的内部消息表示，并且使用特定传输进行发送。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-103">The Windows Communication Foundation (WCF) channel stack employs encoding and transport channels to transform internal message representation into its wire format and send it by using a particular transport.</span></span> <span data-ttu-id="dc4d4-104">用于 Web 服务互操作性的最常见传输是 HTTP，Web 服务使用的最常见编码是基于 XML 的 SOAP 1.1、SOAP 1.2 和消息传输优化机制 (MTOM)。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-104">The most common transport used for Web services interoperability is HTTP, and the most common encodings used by Web services are XML-based SOAP 1.1, SOAP 1.2, and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="dc4d4-105">本主题介绍以下协议由 WCF 实现细节<xref:System.ServiceModel.Channels.HttpTransportBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-105">This topic covers WCF implementation details for the following protocols employed by <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span>  
  
|<span data-ttu-id="dc4d4-106">规范/文档</span><span class="sxs-lookup"><span data-stu-id="dc4d4-106">Specification/document</span></span>|<span data-ttu-id="dc4d4-107">Link</span><span class="sxs-lookup"><span data-stu-id="dc4d4-107">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="dc4d4-108">HTTP 1.1</span><span class="sxs-lookup"><span data-stu-id="dc4d4-108">HTTP 1.1</span></span>|http://www.ietf.org/rfc/rfc2616.txt|  
|<span data-ttu-id="dc4d4-109">SOAP 1.1 HTTP 绑定</span><span class="sxs-lookup"><span data-stu-id="dc4d4-109">SOAP 1.1 HTTP Binding</span></span>|<span data-ttu-id="dc4d4-110">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/第 7 节</span><span class="sxs-lookup"><span data-stu-id="dc4d4-110">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/, Section 7</span></span>|  
|<span data-ttu-id="dc4d4-111">SOAP 1.2 HTTP 绑定</span><span class="sxs-lookup"><span data-stu-id="dc4d4-111">SOAP 1.2 HTTP Binding</span></span>|<span data-ttu-id="dc4d4-112">http://www.w3.org/TR/soap12-part2/第 7 节</span><span class="sxs-lookup"><span data-stu-id="dc4d4-112">http://www.w3.org/TR/soap12-part2/, Section 7</span></span>|  
  
 <span data-ttu-id="dc4d4-113">本主题介绍 WCF 的实现详细信息的以下协议<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>和<xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>采用。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-113">This topic covers WCF implementation details for the following protocols  that <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employ.</span></span>  
  
|<span data-ttu-id="dc4d4-114">规范/文档</span><span class="sxs-lookup"><span data-stu-id="dc4d4-114">Specification/Document</span></span>|<span data-ttu-id="dc4d4-115">Link</span><span class="sxs-lookup"><span data-stu-id="dc4d4-115">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="dc4d4-116">XML</span><span class="sxs-lookup"><span data-stu-id="dc4d4-116">XML</span></span>|http://www.w3.org/TR/REC-xml|  
|<span data-ttu-id="dc4d4-117">SOAP 1.1</span><span class="sxs-lookup"><span data-stu-id="dc4d4-117">SOAP 1.1</span></span>|http://www.w3.org/TR/2000/NOTE-SOAP-20000508/|  
|<span data-ttu-id="dc4d4-118">SOAP 1.2 核心</span><span class="sxs-lookup"><span data-stu-id="dc4d4-118">SOAP 1.2 Core</span></span>|http://www.w3.org/TR/soap12-part1/|  
|<span data-ttu-id="dc4d4-119">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="dc4d4-119">WS-Addressing 2004/08</span></span>|http://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/|  
|<span data-ttu-id="dc4d4-120">W3C Web 服务寻址 1.0 - 核心</span><span class="sxs-lookup"><span data-stu-id="dc4d4-120">W3C Web Services Addressing 1.0 - Core</span></span>|http://www.w3.org/TR/2006/REC-ws-addr-core-20060509|  
|<span data-ttu-id="dc4d4-121">W3C Web 服务寻址 1.0 - SOAP 绑定</span><span class="sxs-lookup"><span data-stu-id="dc4d4-121">W3C Web Services Addressing 1.0 - SOAP Binding</span></span>|http://www.w3.org/TR/2006/REC-ws-addr-soap-20060509|  
|<span data-ttu-id="dc4d4-122">W3C Web 服务寻址 1.0 - WSDL 绑定</span><span class="sxs-lookup"><span data-stu-id="dc4d4-122">W3C Web Services Addressing 1.0 - WSDL Binding</span></span>|http://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/|  
<span data-ttu-id="dc4d4-123">W3C Web 服务寻址 1.0 - 元数据</span><span class="sxs-lookup"><span data-stu-id="dc4d4-123">W3C Web Services Addressing 1.0 - Metadata</span></span>|http://www.w3.org/TR/ws-addr-metadata/|  
|<span data-ttu-id="dc4d4-124">WSDL SOAP1.1 绑定</span><span class="sxs-lookup"><span data-stu-id="dc4d4-124">WSDL SOAP1.1 Binding</span></span>|http://www.w3.org/TR/wsdl/|  
|<span data-ttu-id="dc4d4-125">WSDL SOAP1.2 绑定</span><span class="sxs-lookup"><span data-stu-id="dc4d4-125">WSDL SOAP1.2 Binding</span></span>|http://www.w3.org/Submission/wsdl11soap12/|  
  
 <span data-ttu-id="dc4d4-126">本主题介绍 WCF 的实现详细信息的以下协议<xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>采用。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-126">This topic covers WCF implementation details for the following protocols that <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employs.</span></span>  
  
|<span data-ttu-id="dc4d4-127">规范/文档</span><span class="sxs-lookup"><span data-stu-id="dc4d4-127">Specification/document</span></span>|<span data-ttu-id="dc4d4-128">Link</span><span class="sxs-lookup"><span data-stu-id="dc4d4-128">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="dc4d4-129">XOP</span><span class="sxs-lookup"><span data-stu-id="dc4d4-129">XOP</span></span>|http://www.w3.org/TR/xop10/|  
|<span data-ttu-id="dc4d4-130">MTOM + SOAP 1.2 绑定</span><span class="sxs-lookup"><span data-stu-id="dc4d4-130">MTOM + SOAP 1.2 Binding</span></span>|http://www.w3.org/TR/soap12-mtom/|  
|<span data-ttu-id="dc4d4-131">MTOM SOAP 1.1 绑定</span><span class="sxs-lookup"><span data-stu-id="dc4d4-131">MTOM SOAP 1.1 Binding</span></span>|http://www.w3.org/Submission/soap11mtom10/|  
|<span data-ttu-id="dc4d4-132">MTOM WS-Policy 断言</span><span class="sxs-lookup"><span data-stu-id="dc4d4-132">MTOM WS-Policy Assertion</span></span>|<span data-ttu-id="dc4d4-133">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-133">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/.</span></span>|  
  
 <span data-ttu-id="dc4d4-134">本主题通篇使用以下 XML 命名空间和关联的前缀。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-134">The following XML namespaces and associated prefixes are used throughout this topic.</span></span>  
  
|<span data-ttu-id="dc4d4-135">前缀</span><span class="sxs-lookup"><span data-stu-id="dc4d4-135">Prefix</span></span>|<span data-ttu-id="dc4d4-136">命名空间统一资源标识符 (URI)</span><span class="sxs-lookup"><span data-stu-id="dc4d4-136">Namespace Uniform Resource Identifier (URI)</span></span>|  
|------------|---------------------------------------------------|  
|<span data-ttu-id="dc4d4-137">s11</span><span class="sxs-lookup"><span data-stu-id="dc4d4-137">s11</span></span>|http://schemas.xmlsoap.org/soap/envelope|  
|<span data-ttu-id="dc4d4-138">s12</span><span class="sxs-lookup"><span data-stu-id="dc4d4-138">s12</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="dc4d4-139">wsa</span><span class="sxs-lookup"><span data-stu-id="dc4d4-139">wsa</span></span>|http://www.w3.org/2004/08/addressing|  
|<span data-ttu-id="dc4d4-140">wsam</span><span class="sxs-lookup"><span data-stu-id="dc4d4-140">wsam</span></span>|http://www.w3.org/2007/05/addressing/metadata|  
|<span data-ttu-id="dc4d4-141">wsap</span><span class="sxs-lookup"><span data-stu-id="dc4d4-141">wsap</span></span>|http://schemas.xmlsoap.org/ws/2004/09/policy/addressing|  
|<span data-ttu-id="dc4d4-142">wsa10</span><span class="sxs-lookup"><span data-stu-id="dc4d4-142">wsa10</span></span>|http://www.w3.org/2005/08/addressing|  
|<span data-ttu-id="dc4d4-143">wsaw10</span><span class="sxs-lookup"><span data-stu-id="dc4d4-143">wsaw10</span></span>|http://www.w3.org/2006/05/addressing/wsdl|  
|<span data-ttu-id="dc4d4-144">xop</span><span class="sxs-lookup"><span data-stu-id="dc4d4-144">xop</span></span>|http://www.w3.org/2004/08/xop/include|  
|<span data-ttu-id="dc4d4-145">xmime</span><span class="sxs-lookup"><span data-stu-id="dc4d4-145">xmime</span></span>|http://www.w3.org/2004/06/xmlmime<br /><br /> http://www.w3.org/2005/05/xmlmime|  
<span data-ttu-id="dc4d4-146">dp</span><span class="sxs-lookup"><span data-stu-id="dc4d4-146">dp</span></span>|http://schemas.microsoft.com/net/2006/06/duplex|  
  
## <a name="soap-11-and-soap-12"></a><span data-ttu-id="dc4d4-147">SOAP 1.1 和 SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="dc4d4-147">SOAP 1.1 and SOAP 1.2</span></span>  
  
### <a name="envelope-and-processing-model"></a><span data-ttu-id="dc4d4-148">信封和处理模型</span><span class="sxs-lookup"><span data-stu-id="dc4d4-148">Envelope and Processing Model</span></span>  
 <span data-ttu-id="dc4d4-149">WCF 实现遵循 Basic Profile 1.1 (BP11) 和基本配置文件 1.0 (SSBP10) 的 SOAP 1.1 信封处理。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-149">WCF implements SOAP 1.1 envelope processing following Basic Profile 1.1 (BP11) and Basic Profile 1.0 (SSBP10).</span></span> <span data-ttu-id="dc4d4-150">SOAP 1.2 信封处理是遵循 SOAP12-Part1 实现的。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-150">SOAP 1.2 Envelope processing is implemented following SOAP12-Part1.</span></span>  
  
 <span data-ttu-id="dc4d4-151">本部分介绍在涉及 BP11 和 SOAP12 Part1 WCF 执行某些实现选项。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-151">This section explains certain implementation choices taken by WCF with regard to BP11 and SOAP12-Part1.</span></span>  
  
#### <a name="mandatory-header-processing"></a><span data-ttu-id="dc4d4-152">强制标头处理</span><span class="sxs-lookup"><span data-stu-id="dc4d4-152">Mandatory Header Processing</span></span>  
 <span data-ttu-id="dc4d4-153">WCF 遵循规则处理标头标记`mustUnderstand`有以下变化的 SOAP 1.1 和 SOAP 1.2 规范中所述。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-153">WCF follows rules for processing headers marked `mustUnderstand` described in the SOAP 1.1 and SOAP 1.2 specifications, with the following variations.</span></span>  
  
 <span data-ttu-id="dc4d4-154">输入 WCF 通道堆栈的消息由关联的绑定元素，例如配置的各个通道、 文本消息编码、 安全、 可靠消息传递和事务处理。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-154">A message that enters the WCF channel stack is processed by individual channels configured by associated binding elements, for example, Text Message Encoding, Security, Reliable Messaging, and Transactions.</span></span> <span data-ttu-id="dc4d4-155">每个通道都识别来自关联命名空间的标头，并将其标记为已理解。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-155">Each channel recognizes headers from the associated namespace and marks them as understood.</span></span> <span data-ttu-id="dc4d4-156">消息进入调度程序后，操作格式化程序读取相应消息/操作协定所期望的标头，并将其标记为已理解。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-156">Once a message enters the dispatcher, the operation formatter reads headers expected by the corresponding message/operation contract and marks them understood.</span></span> <span data-ttu-id="dc4d4-157">然后，调度程序验证是否还有任何标头未被理解，但仍标记为 `mustUnderstand`，如果是这样，则引发异常。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-157">Then the dispatcher verifies whether any remaining headers are not understood but marked as `mustUnderstand` and throws an exception.</span></span> <span data-ttu-id="dc4d4-158">包含 `mustUnderstand` 标头并且目标为接收方的消息不会由接收方应用程序代码进行处理。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-158">Messages that contain `mustUnderstand` headers that are targeted at the recipient are not processed by recipient application code.</span></span>  
  
 <span data-ttu-id="dc4d4-159">这样的分层处理实现了 SOAP 节点的基础结构层和应用层之间的分离。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-159">Such layered processing allows for separation between infrastructure layers and application layers of the SOAP node:</span></span>  
  
-   <span data-ttu-id="dc4d4-160">B1111： 不理解的标头检测到由 WCF 基础结构通道堆栈中，处理消息之后但在应用程序处理之前</span><span class="sxs-lookup"><span data-stu-id="dc4d4-160">B1111: Headers that are not understood are detected after the message is processed by the WCF infrastructure channel stack, but before it is processed by application</span></span>  
  
     <span data-ttu-id="dc4d4-161">在 SOAP 1.1 和 SOAP 1.2 中，`mustUnderstand` 标头值不相同。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-161">The `mustUnderstand` header value differs between SOAP 1.1 and SOAP 1.2.</span></span> <span data-ttu-id="dc4d4-162">Basic Profile 1.1 要求，在 SOAP 1.1 消息中，`mustUnderstand` 值为 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-162">Basic Profile 1.1 requires that the `mustUnderstand` value be 0 or 1 for SOAP 1.1 messages.</span></span> <span data-ttu-id="dc4d4-163">SOAP 1.2 可以使用 0、1、`false` 和 `true` 作为值，但建议使用 `xs:boolean` 值的规范表示形式（`false` 和 `true`）。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-163">SOAP 1.2 allows 0, 1, `false`, and `true` as values, but recommends emitting a canonical representation of `xs:boolean` values (`false`, `true`).</span></span>  
  
-   <span data-ttu-id="dc4d4-164">B1112: WCF 发出`mustUnderstand`值 0 和 1 为 SOAP 1.1 和 SOAP 1.2 版本的 SOAP 信封。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-164">B1112: WCF emits `mustUnderstand` values 0 and 1 for both SOAP 1.1 and SOAP 1.2 versions of the SOAP envelope.</span></span> <span data-ttu-id="dc4d4-165">WCF 接受的整个值空间`xs:boolean`为`mustUnderstand`标头 (0、 1、 `false`， `true`)</span><span class="sxs-lookup"><span data-stu-id="dc4d4-165">WCF accepts the entire value space of `xs:boolean` for the `mustUnderstand` header (0, 1, `false`, `true`)</span></span>  
  
#### <a name="soap-faults"></a><span data-ttu-id="dc4d4-166">SOAP 错误</span><span class="sxs-lookup"><span data-stu-id="dc4d4-166">SOAP Faults</span></span>  
 <span data-ttu-id="dc4d4-167">下面是特定于 WCF 的 SOAP 错误实现的列表。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-167">The following is a list of WCF-specific SOAP fault implementations.</span></span>  
  
-   <span data-ttu-id="dc4d4-168">B2121: WCF 返回以下 SOAP 1.1 错误代码： `s11:mustUnderstand`， `s11:Client`，和`s11:Server`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-168">B2121: WCF returns the following SOAP 1.1 Fault Codes: `s11:mustUnderstand`, `s11:Client`, and `s11:Server`.</span></span>  
  
-   <span data-ttu-id="dc4d4-169">B2122: WCF 返回以下 SOAP 1.2 错误代码： `s12:MustUnderstand`， `s12:Sender`，和`s12:Receiver`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-169">B2122: WCF returns the following SOAP 1.2 Fault Codes: `s12:MustUnderstand`, `s12:Sender`, and `s12:Receiver`.</span></span>  
  
### <a name="http-binding"></a><span data-ttu-id="dc4d4-170">HTTP 绑定</span><span class="sxs-lookup"><span data-stu-id="dc4d4-170">HTTP Binding</span></span>  
  
#### <a name="soap-11-http-binding"></a><span data-ttu-id="dc4d4-171">SOAP 1.1 HTTP 绑定</span><span class="sxs-lookup"><span data-stu-id="dc4d4-171">SOAP 1.1 HTTP Binding</span></span>  
 <span data-ttu-id="dc4d4-172">WCF 实现 SOAP1.1 HTTP 绑定，并遵循 Basic Profile 1.1 规范第 3.4 节提供如下说明：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-172">WCF implements SOAP1.1 HTTP binding following the Basic Profile 1.1 specification section 3.4 with the following clarifications:</span></span>  
  
-   <span data-ttu-id="dc4d4-173">B2211: WCF 服务不实现 HTTP POST 请求的重定向。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-173">B2211: WCF service does not implement redirection of HTTP POST requests.</span></span>  
  
-   <span data-ttu-id="dc4d4-174">B2212: WCF 客户端依据 3.4.8 支持 HTTP Cookie。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-174">B2212: WCF clients support HTTP Cookies in accordance with 3.4.8.</span></span>  
  
#### <a name="soap-12-http-binding"></a><span data-ttu-id="dc4d4-175">SOAP 1.2 HTTP 绑定</span><span class="sxs-lookup"><span data-stu-id="dc4d4-175">SOAP 1.2 HTTP Binding</span></span>  
 <span data-ttu-id="dc4d4-176">SOAP 1.2 一部分 2 (SOAP12Part2) 规范提供如下说明中所述，WCF 实现 SOAP 1.2 HTTP 绑定。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-176">WCF implements SOAP 1.2 HTTP binding as described in the SOAP 1.2-part 2 (SOAP12Part2) specification with the following clarifications.</span></span>  
  
 <span data-ttu-id="dc4d4-177">SOAP 1.2 为 `application/soap+xml` 媒体类型提供了一个可选的操作参数。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-177">SOAP 1.2 introduced an optional action parameter for the `application/soap+xml` media type.</span></span> <span data-ttu-id="dc4d4-178">在未使用 WS-Addressing 时，采用此参数优化消息调度很有用，这种情况下，不需要分析 SOAP 消息的正文。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-178">This parameter is useful to optimize message dispatch without requiring that the body of the SOAP message be parsed when WS-Addressing is not used.</span></span>  
  
-   <span data-ttu-id="dc4d4-179">R2221：`application/soap+xml` 操作参数出现在 SOAP 1.2 请求中时，必须与相应 WSDL 绑定内的 `soapAction` 元素的 `wsoap12:operation` 属性匹配。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-179">R2221: The `application/soap+xml` action parameter, when present on a SOAP 1.2 request, must match the `soapAction` attribute on the `wsoap12:operation` element inside the corresponding WSDL binding.</span></span>  
  
-   <span data-ttu-id="dc4d4-180">R2222：如果使用 WS-Addressing 2004/08 或 WS-Addressing 1.0，`application/soap+xml` 操作参数出现在 SOAP 1.2 消息中时，必须与 `wsa:Action` 匹配。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-180">R2222: The `application/soap+xml` action parameter, when present on a SOAP 1.2 message, must match `wsa:Action` when WS-Addressing 2004/08 or WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="dc4d4-181">如果 WS-Addressing 禁用，并且传入的请求不包含操作参数，则视为未指定消息 `Action`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-181">When WS-Addressing is disabled and an incoming request does not contain an action parameter, message `Action` is considered not specified.</span></span>  
  
## <a name="ws-addressing"></a><span data-ttu-id="dc4d4-182">WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="dc4d4-182">WS-Addressing</span></span>  
 <span data-ttu-id="dc4d4-183">WCF 实现三个版本的 Ws-addressing:</span><span class="sxs-lookup"><span data-stu-id="dc4d4-183">WCF implements 3 versions of WS-Addressing:</span></span>  
  
-   <span data-ttu-id="dc4d4-184">WS-Addressing 2004/08</span><span class="sxs-lookup"><span data-stu-id="dc4d4-184">WS-Addressing 2004/08</span></span>  
  
-   <span data-ttu-id="dc4d4-185">W3C Web 服务寻址 1.0 核心 (ADDR10-CORE) 和 SOAP 绑定 (ADDR10-SOAP)</span><span class="sxs-lookup"><span data-stu-id="dc4d4-185">W3C Web Services Addressing 1.0 Core  (ADDR10-CORE) and SOAP Binding (ADDR10-SOAP)</span></span>  
  
-   <span data-ttu-id="dc4d4-186">WS-Addressing 1.0 - 元数据</span><span class="sxs-lookup"><span data-stu-id="dc4d4-186">WS-Addressing 1.0 - Metadata</span></span>  
  
### <a name="endpoint-references"></a><span data-ttu-id="dc4d4-187">终结点引用</span><span class="sxs-lookup"><span data-stu-id="dc4d4-187">Endpoint References</span></span>  
 <span data-ttu-id="dc4d4-188">所有版本的 Ws-addressing WCF 实现都使用终结点引用来描述终结点。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-188">All versions of WS-Addressing that WCF implements use endpoint references to describe endpoints.</span></span>  
  
#### <a name="endpoint-references-and-ws-addressing-versions"></a><span data-ttu-id="dc4d4-189">终结点引用和 WS-Addressing 版本</span><span class="sxs-lookup"><span data-stu-id="dc4d4-189">Endpoint References and WS-Addressing Versions</span></span>  
 <span data-ttu-id="dc4d4-190">WCF 实现许多基础结构使用的协议的 Ws-addressing，并且在特定`EndpointReference`元素和`W3C.WsAddressing.EndpointReferenceType`类 （例如，WS ReliableMessaging、 Ws-secureconversation 和 Ws-trust）。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-190">WCF implements a number of the infrastructure protocols that use WS-Addressing and in particular the `EndpointReference` element and `W3C.WsAddressing.EndpointReferenceType` class (for example, WS-ReliableMessaging, WS-SecureConversation, and WS-Trust).</span></span> <span data-ttu-id="dc4d4-191">WCF 支持使用的 WS 寻址采用其他基础结构协议的任一版本。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-191">WCF supports the use of either version of WS-Addressing with other infrastructure protocols.</span></span> <span data-ttu-id="dc4d4-192">WCF 终结点支持每个终结点的 Ws-addressing 的一个版本。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-192">WCF endpoints support one version of WS-Addressing per endpoint.</span></span>  
  
 <span data-ttu-id="dc4d4-193">对于 R3111 的命名空间`EndpointReference`元素或在与 WCF 终结点交换的消息中使用的类型必须与 Ws-addressing 指导此终结点实现的版本匹配。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-193">For R3111, the namespace for the `EndpointReference` element or type used in messages exchanged with a WCF endpoint must match the version of WS-Addressing implemented by this endpoint.</span></span>  
  
 <span data-ttu-id="dc4d4-194">例如，如果的 WCF 终结点实现 Ws-reliablemessaging，`AcksTo`内这样的终结点返回的标头`CreateSequenceResponse`使用 Ws-addressing 的版本，`EncodingBinding`元素指定此终结点。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-194">For example, if a WCF endpoint implements WS-ReliableMessaging, the `AcksTo` header returned by such an endpoint inside `CreateSequenceResponse` uses the WS-Addressing version that the `EncodingBinding` element specifies for this endpoint.</span></span>  
  
#### <a name="endpoint-references-and-metadata"></a><span data-ttu-id="dc4d4-195">终结点引用和元数据</span><span class="sxs-lookup"><span data-stu-id="dc4d4-195">Endpoint References and Metadata</span></span>  
 <span data-ttu-id="dc4d4-196">很多情况下，需要对给定终结点进行元数据或元数据引用通信。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-196">A number of scenarios require communicating metadata or a reference to metadata for a given endpoint.</span></span>  
  
 <span data-ttu-id="dc4d4-197">B3121: WCF 采用 Ws-metadataexchange (MEX) 规范第 6 部分以通过值或引用包括终结点引用的元数据中所述的机制。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-197">B3121: WCF employs mechanisms described in the WS-MetadataExchange (MEX) specification Section 6 to include metadata for endpoint references by value or by reference.</span></span>  
  
 <span data-ttu-id="dc4d4-198">其中的 WCF 服务需要使用在令牌颁发者颁发的安全断言标记语言 (SAML) 令牌身份验证的方案，请考虑http://sts.fabrikam123.com。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-198">Consider a scenario where a WCF service requires authentication using a Security Assertions Markup Language (SAML) token issued by the token issuer at http://sts.fabrikam123.com.</span></span> <span data-ttu-id="dc4d4-199">WCF 终结点描述此身份验证要求使用`sp:IssuedToken`与嵌套断言`sp:Issuer`指向令牌颁发者的断言。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-199">The WCF endpoint describes this authentication requirement by using `sp:IssuedToken` assertion with a nested `sp:Issuer` assertion pointing to the token issuer.</span></span> <span data-ttu-id="dc4d4-200">访问该 `sp:Issuer` 断言的客户端应用程序需要知道如何与令牌颁发机构终结点进行通信。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-200">Client applications that access the `sp:Issuer` assertion need to know how to communicate with the token issuer endpoint.</span></span> <span data-ttu-id="dc4d4-201">客户端需要知道令牌颁发机构的有关元数据。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-201">The client needs to know metadata about the token issuer.</span></span> <span data-ttu-id="dc4d4-202">WCF 使用 MEX 中定义的终结点引用元数据扩展，提供了对令牌颁发者元数据的引用。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-202">Using the endpoint reference metadata extensions defined in MEX, WCF provides a reference to the token issuer metadata.</span></span>  
  
```xml  
<sp:IssuedToken>  
  <sp:Issuer>  
    <wsa10:Address>  
      http://sts.fabrikam123.com  
    </wsa10:Address>  
    <wsa10:Metadata>  
      <mex:Metadata>  
        <mex:MetadataSection>  
          <mex:MetadataReference>  
            <wsa10:Address>  
              http://sts.fabrikam123.com/mex  
            </wsa10:Address>  
          </mex:MetadataReference>  
        </mex:MetadataSection>  
      </mex:Metadata>  
    </wsa10:Metadata>  
  </sp:Issuer>  
</sp:IssuedToken>  
```  
  
### <a name="message-addressing-headers"></a><span data-ttu-id="dc4d4-203">消息寻址标头</span><span class="sxs-lookup"><span data-stu-id="dc4d4-203">Message Addressing Headers</span></span>  
  
#### <a name="message-headers"></a><span data-ttu-id="dc4d4-204">消息头</span><span class="sxs-lookup"><span data-stu-id="dc4d4-204">Message Headers</span></span>  
 <span data-ttu-id="dc4d4-205">对于这两个 Ws-addressing 版本，WCF 使用以下的消息标头，这些规范的规定`wsa:To`， `wsa:ReplyTo`， `wsa:Action`， `wsa:MessageID`，和`wsa:RelatesTo`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-205">For both WS-Addressing versions, WCF uses the following message headers as prescribed by the specifications `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`,and `wsa:RelatesTo`.</span></span>  
  
 <span data-ttu-id="dc4d4-206">B3211： 对于所有 Ws-addressing 版本，WCF 承认但不会生成现成，Ws-addressing 消息头`wsa:FaultTo`和`wsa:From`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-206">B3211: For all WS-Addressing versions, WCF honors, but does not produce out of the box, WS-Addressing message headers `wsa:FaultTo` and `wsa:From`.</span></span>  
  
 <span data-ttu-id="dc4d4-207">可以添加与 WCF 应用程序的应用程序进行交互，这些消息标头和 WCF 将进行相应处理它们。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-207">Applications that interact with WCF applications can add these message headers and WCF will process them accordingly.</span></span>  
  
#### <a name="reference-parameters-and-properties"></a><span data-ttu-id="dc4d4-208">引用参数和属性</span><span class="sxs-lookup"><span data-stu-id="dc4d4-208">Reference Parameters and Properties</span></span>  
 <span data-ttu-id="dc4d4-209">WCF 实现终结点引用参数和引用 p 的处理</span><span class="sxs-lookup"><span data-stu-id="dc4d4-209">WCF implements processing of endpoint reference parameters and reference p</span></span>  
  
 <span data-ttu-id="dc4d4-210">理。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-210">roperties in accordance with respective specifications.</span></span>  
  
 <span data-ttu-id="dc4d4-211">B3221： 配置为使用 Ws-addressing 2004/08 时，WCF 终结点不区分引用属性和引用参数的处理。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-211">B3221: When configured to use WS-Addressing 2004/08, WCF endpoints do not differentiate between processing Reference Properties and Reference Parameters.</span></span>  
  
### <a name="message-exchange-patterns"></a><span data-ttu-id="dc4d4-212">消息交换模式</span><span class="sxs-lookup"><span data-stu-id="dc4d4-212">Message Exchange Patterns</span></span>  
 <span data-ttu-id="dc4d4-213">Web 服务操作调用所涉及的消息序列称为*消息交换模式*。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-213">The sequence of messages involved in the Web service operation invocation is referred to as the *message exchange pattern*.</span></span> <span data-ttu-id="dc4d4-214">WCF 支持单向、 请求-答复和双工消息交换模式。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-214">WCF supports one-way, request-reply, and duplex message exchange patterns.</span></span> <span data-ttu-id="dc4d4-215">本节根据所用的消息交换模式说明 WS-Addressing 对消息处理的需求。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-215">This section clarifies WS-Addressing requirements on message processing depending on the message exchange pattern being used.</span></span>  
  
 <span data-ttu-id="dc4d4-216">本节通篇都是由请求方发送第一条消息，响应方接收第一条消息。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-216">Throughout this section, the requester sends the first message and the responder receives the first message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="dc4d4-217">单向消息</span><span class="sxs-lookup"><span data-stu-id="dc4d4-217">One-Way Message</span></span>  
 <span data-ttu-id="dc4d4-218">当 WCF 终结点配置为支持消息与给定`Action`为了遵循单向模式时，WCF 终结点按照以下行为和要求。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-218">When a WCF endpoint is configured to support messages with a given `Action` to follow a one-way pattern, the WCF endpoint follows the following behaviors and requirements.</span></span> <span data-ttu-id="dc4d4-219">除非另行指定，行为和规则将适用于这两个版本的 Ws-addressing 指导在 WCF 中受支持：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-219">Unless otherwise specified, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>  
  
-   <span data-ttu-id="dc4d4-220">R3311：请求方必须包含 `wsa:To`、`wsa:Action` 以及表示终结点引用所指定的所有引用参数的标头。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-220">R3311: The requester must include `wsa:To`, `wsa:Action`, and headers for all reference parameters specified by the endpoint reference.</span></span> <span data-ttu-id="dc4d4-221">如果使用 WS-Addressing 2004/08 并且终结点引用指定了 [reference properties]，则对应的标头必须也添加到消息中。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-221">When WS-Addressing 2004/08 is used and [reference properties] are specified by the endpoint reference, the corresponding headers must be added to the message too.</span></span>  
  
-   <span data-ttu-id="dc4d4-222">B3312：请求方可以包含 `MessageID`、`ReplyTo` 和 `FaultTo` 标头。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-222">B3312: The requester may include `MessageID`, `ReplyTo`, and `FaultTo` headers.</span></span> <span data-ttu-id="dc4d4-223">接收方基础结构将忽略这些标头，并且这些标头将传给应用程序。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-223">The receiver infrastructure will ignore them, and they will be passed to the application.</span></span>  
  
-   <span data-ttu-id="dc4d4-224">R3313：在使用 HTTP 并且没有通过 HTTP 响应发送任何消息时，响应方必须发送一个正文为空且 HTTP 状态码为 202 的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-224">R3313: When HTTP is used and no message is being sent on the HTTP response leg, the responder must send an HTTP response with an empty body and an HTTP 202 status code.</span></span>  
  
     <span data-ttu-id="dc4d4-225">如果使用的是 HTTP 传输，并且操作协定声明消息是单向的，则 HTTP 响应仍可用于发送基础结构消息 — 例如，可靠消息传递可通过 HTTP 响应发送 `SequenceAcknowledgement` 消息。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-225">When the HTTP transport is in use and the operation contract declares a message one-way, the HTTP response can still be used for sending infrastructure messages—for example, reliable messaging can send a `SequenceAcknowledgement` message on an HTTP response.</span></span>  
  
-   <span data-ttu-id="dc4d4-226">B3314: WCF 响应方不发送响应的单向消息的错误消息。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-226">B3314: The WCF responder does not send a fault message in response to a one-way message.</span></span>  
  
#### <a name="request-reply"></a><span data-ttu-id="dc4d4-227">请求-答复</span><span class="sxs-lookup"><span data-stu-id="dc4d4-227">Request-Reply</span></span>  
 <span data-ttu-id="dc4d4-228">在 WCF 终结点配置为使用一条消息给定`Action`为了遵循请求-答复模式，则 WCF 终结点按照以下行为和要求。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-228">When a WCF endpoint is configured for a message with a given `Action` to follow the request-reply pattern, the WCF endpoint follows the behaviors and requirements below.</span></span> <span data-ttu-id="dc4d4-229">除非另有指定，行为和规则将适用于这两个版本的 Ws-addressing 指导在 WCF 中受支持：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-229">Unless specified otherwise, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>  
  
-   <span data-ttu-id="dc4d4-230">R3321： 请求方必须包含在请求中`wsa:To`， `wsa:Action`， `wsa:MessageID`，和的所有引用参数或引用属性 （或两者） 终结点引用所指定的标头。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-230">R3321: The requester must include in the request `wsa:To`, `wsa:Action`, `wsa:MessageID`, and headers for all reference parameters or reference properties (or both) specified by the endpoint reference.</span></span>  
  
-   <span data-ttu-id="dc4d4-231">R3322：使用 WS-Addressing 2004/08 时，还必须在请求中包含 `ReplyTo`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-231">R3322: When WS-Addressing 2004/08 is used, `ReplyTo` must also be included in the request.</span></span>  
  
-   <span data-ttu-id="dc4d4-232">R3323： 当使用 Ws-addressing 1.0 和`ReplyTo`不存在在请求中，使用 [address] 属性等于的默认终结点引用"http://www.w3.org/2005/08/addressing/anonymous"使用。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-232">R3323: When WS-Addressing 1.0 is used and `ReplyTo` is not present in the request, a default endpoint reference with the [address] property equal to "http://www.w3.org/2005/08/addressing/anonymous" is used.</span></span>  
  
-   <span data-ttu-id="dc4d4-233">R3324： 请求方必须包含`wsa:To`， `wsa:Action`，和`wsa:RelatesTo`中答复消息的标头，以及所有引用参数或引用属性 （或两者） 指定的标头`ReplyTo`中的终结点引用请求。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-233">R3324: The requester must include `wsa:To`, `wsa:Action`, and `wsa:RelatesTo` headers in the reply message, as well as headers for all reference parameters or reference properties (or both) specified by the `ReplyTo` endpoint reference in the request.</span></span>  
  
### <a name="web-services-addressing-faults"></a><span data-ttu-id="dc4d4-234">Web 服务寻址错误</span><span class="sxs-lookup"><span data-stu-id="dc4d4-234">Web Services Addressing Faults</span></span>  
 <span data-ttu-id="dc4d4-235">R3411: WCF 生成 Ws-addressing 2004/08 定义的以下错误。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-235">R3411: WCF produces the following faults defined by WS-Addressing 2004/08.</span></span>  
  
|<span data-ttu-id="dc4d4-236">代码</span><span class="sxs-lookup"><span data-stu-id="dc4d4-236">Code</span></span>|<span data-ttu-id="dc4d4-237">原因</span><span class="sxs-lookup"><span data-stu-id="dc4d4-237">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="dc4d4-238">wsa:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="dc4d4-238">wsa:DestinationUnreachable</span></span>|<span data-ttu-id="dc4d4-239">到达的消息所带有的 `ReplyTo` 不同于为此通道建立的答复地址；在 To 标头中指定的地址上，没有终结点在进行侦听。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-239">The message arrived with a `ReplyTo` that is different from the reply address established for this channel; there is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="dc4d4-240">wsa:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="dc4d4-240">wsa:ActionNotSupported</span></span>|<span data-ttu-id="dc4d4-241">与终结点关联的基础结构通道或调度程序不能识别在 `Action` 标头中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-241">the infrastructure channels or dispatcher associated with the endpoint do not recognize the action specified in the `Action` header.</span></span>|  
  
 <span data-ttu-id="dc4d4-242">R3412: WCF 生成由 Ws-addressing 1.0 定义的以下错误。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-242">R3412: WCF produces the following faults defined by WS-Addressing 1.0.</span></span>  
  
|<span data-ttu-id="dc4d4-243">代码</span><span class="sxs-lookup"><span data-stu-id="dc4d4-243">Code</span></span>|<span data-ttu-id="dc4d4-244">原因</span><span class="sxs-lookup"><span data-stu-id="dc4d4-244">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="dc4d4-245">wsa10:InvalidAddressingHeader</span><span class="sxs-lookup"><span data-stu-id="dc4d4-245">wsa10:InvalidAddressingHeader</span></span>|<span data-ttu-id="dc4d4-246">重复`wsa:To`， `wsa:ReplyTo`，`wsa:From`或`wsa:MessageID`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-246">Duplicate `wsa:To`, `wsa:ReplyTo`, `wsa:From` or `wsa:MessageID`.</span></span> <span data-ttu-id="dc4d4-247">重复`wsa:RelatesTo`具有相同`RelationshipType`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-247">Duplicate `wsa:RelatesTo` with the same `RelationshipType`.</span></span>|  
|<span data-ttu-id="dc4d4-248">wsa10:MessageAddressingHeaderRequired</span><span class="sxs-lookup"><span data-stu-id="dc4d4-248">wsa10:MessageAddressingHeaderRequired</span></span>|<span data-ttu-id="dc4d4-249">缺少必需的 Addressing 标头。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-249">The required Addressing header is missing.</span></span>|  
|<span data-ttu-id="dc4d4-250">wsa10:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="dc4d4-250">wsa10:DestinationUnreachable</span></span>|<span data-ttu-id="dc4d4-251">到达的消息所带有的 `ReplyTo` 不同于为此通道建立的答复地址。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-251">The message arrived with a `ReplyTo` that is different from the reply address established for this channel.</span></span> <span data-ttu-id="dc4d4-252">在 To 标头中指定的地址上没有终结点在进行侦听。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-252">There is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="dc4d4-253">wsa10:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="dc4d4-253">wsa10:ActionNotSupported</span></span>|<span data-ttu-id="dc4d4-254">与终结点关联的基础结构通道或调度程序不能识别在 `Action` 标头中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-254">An action specified in the `Action` header is not recognized by the infrastructure channels or dispatcher associated with the endpoint.</span></span>|  
|<span data-ttu-id="dc4d4-255">wsa10:EndpointUnavailable</span><span class="sxs-lookup"><span data-stu-id="dc4d4-255">wsa10:EndpointUnavailable</span></span>|<span data-ttu-id="dc4d4-256">RM 通道发送回此错误，指示终结点将不会根据对 `CreateSequence` 消息的寻址标头的检查结果来处理序列。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-256">The RM channel sends this fault back, indicating the endpoint will not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>|  
  
 <span data-ttu-id="dc4d4-257">上表中的代码对应于 SOAP 1.1 中的 `FaultCode` 和 SOAP 1.2 中的 `SubCode` (Code=Sender)。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-257">Code in the preceding tables maps to `FaultCode` in SOAP 1.1 and `SubCode` (with Code=Sender) in SOAP 1.2.</span></span>  
  
### <a name="wsdl-11-binding-and-ws-policy-assertions"></a><span data-ttu-id="dc4d4-258">WSDL 1.1 绑定和 WS-Policy 断言</span><span class="sxs-lookup"><span data-stu-id="dc4d4-258">WSDL 1.1 Binding and WS-Policy Assertions</span></span>  
  
#### <a name="indicating-use-of-ws-addressing"></a><span data-ttu-id="dc4d4-259">指示使用 WS-Addressing</span><span class="sxs-lookup"><span data-stu-id="dc4d4-259">Indicating Use of WS-Addressing</span></span>  
 <span data-ttu-id="dc4d4-260">WCF 使用策略断言来指示终结点支持特定的 Ws-addressing 版本。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-260">WCF uses policy assertions to indicate endpoint support for a particular WS-Addressing version.</span></span>  
  
 <span data-ttu-id="dc4d4-261">下面的策略断言具有终结点策略主题 [WS-PA]，并指示从终结点收发的消息必须使用 WS-Addressing 2004/08。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-261">The following policy assertion has Endpoint Policy Subject [WS-PA] and indicates messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsap:UsingAddressing />  
```  
  
 <span data-ttu-id="dc4d4-262">此策略断言扩充了 WS-Addressing 2004/08 规范。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-262">This policy assertion augments the WS-Addressing 2004/08 specification.</span></span>  
  
 <span data-ttu-id="dc4d4-263">下面的策略断言指示发送/接收的消息必须使用 WS-Addressing 1.0。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-263">The following policy assertion this indicates that messages sent/received must use WS-Addressing 1.0.</span></span>  
  
```xml
<wsam:Addressing/>   
```  
  
 <span data-ttu-id="dc4d4-264">下面的策略断言具有终结点策略主题 [WS-PA]，并指示从终结点收发的消息必须使用 WS-Addressing 2004/08。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-264">The following policy assertion has an Endpoint Policy Subject [WS-PA] and indicates that messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsaw10:UsingAddressing />  
```  
  
 <span data-ttu-id="dc4d4-265">`wsaw10:UsingAddressing` 元素借自于 [WS-Addressing-WSDL]，并在符合该规范第 3.1.2 节的 WS-Policy 的上下文中使用。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-265">The `wsaw10:UsingAddressing` element is borrowed from [WS-Addressing-WSDL] and is used in the context of WS-Policy in compliance with that specification, section 3.1.2.</span></span>  
  
 <span data-ttu-id="dc4d4-266">使用 Addressing 不会更改 WSDL 1.1、SOAP 1.1 和 SOAP 1.2 HTTP 绑定的语义。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-266">Use of Addressing does not alter the semantics of WSDL 1.1, SOAP 1.1, and SOAP 1.2 HTTP Bindings.</span></span> <span data-ttu-id="dc4d4-267">例如，如果某个请求发送到使用 Addressing 和 WSDL SOAP 1.x HTTP 绑定的终结点，并且该请求期望得到一个答复，则该答复必须用 HTTP 响应发送。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-267">For example, if a reply is expected to a request that is sent to an endpoint that uses Addressing and WSDL SOAP 1.x HTTP binding, the reply must be sent by using the HTTP response.</span></span>  
  
 <span data-ttu-id="dc4d4-268">对于通过 http 响应发送的答复，WS-AM 断言是：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-268">For replies sent over the http response, the WS-AM assertion is:</span></span>  
  
```xml  
<wsam:AnonymousResponses/>  
```  
  
 <span data-ttu-id="dc4d4-269">完整的策略断言可能类似于：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-269">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
        <wsam:AnonymousResponses />   
    </wsp:Policy>  
</wsam:Addressing>  
```  
  
 <span data-ttu-id="dc4d4-270">但是，有些消息交换模式可以从在请求方和响应方之间建立两个独立的反向 HTTP 连接中获益，例如，由响应方发送的主动单向消息。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-270">However, there are message exchange patterns that benefit from having two independent converse HTTP connections established between the requester and the responder, for example, unsolicited one-way messages sent by the responder.</span></span>  
  
 <span data-ttu-id="dc4d4-271">WCF 提供了一个实用工具依据两个基础传输通道可构成一个复合双工通道，其中一个通道用于输入消息和其他用于输出消息。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-271">WCF offers a feature by which two underlying transport channels can form a Composite Duplex channel, where one channel is used for input messages and the other is used for output messages.</span></span> <span data-ttu-id="dc4d4-272">对于 HTTP 传输，复合双工提供了两个反向 HTTP 连接。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-272">In the case of the HTTP Transport, Composite Duplex provides two converse HTTP connections.</span></span> <span data-ttu-id="dc4d4-273">请求方使用一个连接将消息发送到响应方，而响应方使用另一个连接将消息发送回请求方。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-273">The requester uses one connection to send messages to the responder, and the responder uses the other to send messages back to the requester.</span></span>  
  
 <span data-ttu-id="dc4d4-274">对于通过单独的 http 请求发送的答复，ws-am 断言是：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-274">For replies sent over separate http requests, the ws-am assertion is</span></span>  
  
```xml  
<wsam:NonAnonymousResponses/>  
```  
  
 <span data-ttu-id="dc4d4-275">完整的策略断言可能类似于：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-275">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
      <wsam:NonAnonymousResponses />   
   </wsp:Policy>  
  </wsam:Addressing>  
```  
  
 <span data-ttu-id="dc4d4-276">在使用 WSDL 1.1 SOAP 1.x HTTP 绑定的终结点上，如果要使用以下具有终结点策略主题 [WS-PA] 的断言，要求将两个单独的反向 HTTP 连接分别用于从请求方到响应方以及从响应方到请求方传送消息。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-276">Use of the following assertion that has Endpoint Policy Subject [WS-PA] on endpoints that use WSDL 1.1 SOAP 1.x HTTP bindings requires two separate converse HTTP connections to be used for messages flowing from requester to responder and responder to requester, respectively.</span></span>  
  
```xml  
<cdp:CompositeDuplex/>  
```  
  
 <span data-ttu-id="dc4d4-277">上面的陈述对于请求消息的 `wsa:ReplyTo` 标头提出了以下要求：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-277">The previous statement leads to the following requirements on the `wsa:ReplyTo` header for request messages:</span></span>  
  
-   <span data-ttu-id="dc4d4-278">R3514： 请求消息发送到终结点必须有`ReplyTo`具有标头`[address]`属性不等于"http://www.w3.org/2005/08/addressing/anonymous"如果终结点使用 WSDL 1.1 SOAP 1.x HTTP 绑定，并且有的策略备`wsap10:UsingAddressing`或`wsap:UsingAddressing`断言结合`cdp:CompositeDuplex`附加。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-278">R3514: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property not equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with a `wsap10:UsingAddressing` or `wsap:UsingAddressing` assertion coupled with `cdp:CompositeDuplex` attached.</span></span>  
  
-   <span data-ttu-id="dc4d4-279">R3515： 请求消息发送到终结点必须有`ReplyTo`具有标头`[address]`属性等于"http://www.w3.org/2005/08/addressing/anonymous"，或者没有`ReplyTo`如果终结点使用 WSDL 1.1 SOAP 1.x HTTP 绑定，并且有策略替代项的标头与`wsap10:UsingAddressing`断言，但未`cdp:CompositeDuplex`附加的断言。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-279">R3515: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous", or not have a `ReplyTo` header at all, if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap10:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
-   <span data-ttu-id="dc4d4-280">R3516： 请求消息发送到终结点必须有`ReplyTo`具有标头`[address]`属性等于"http://www.w3.org/2005/08/addressing/anonymous"如果终结点使用 WSDL 1.1 SOAP 1.x HTTP 绑定，并且有的策略备`wsap:UsingAddressing`断言，并没有`cdp:CompositeDuplex`附加的断言。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-280">R3516: Request messages sent to an endpoint must have a `ReplyTo` header with an `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
 <span data-ttu-id="dc4d4-281">WS-addressing WSDL 规范力图描述类似协议绑定，它引入了一个带有 3 个文本值（required、optional 和 prohibited）的 `<wsaw:Anonymous/>` 元素来指示对 `wsa:ReplyTo` 标头的要求（第 3.2 节）。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-281">The WS-addressing WSDL specification attempts to describe similar protocol bindings by introducing an element `<wsaw:Anonymous/>` with three textual values (required, optional, and prohibited) to indicate requirements on the `wsa:ReplyTo` header (section 3.2).</span></span> <span data-ttu-id="dc4d4-282">遗憾的是，在 WS-Policy 的上下文中，这样的元素定义不特别适合用作断言，因为它要求使用特定于域的扩展来支持将此类元素用作断言的备选项的交集。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-282">Unfortunately, such element definition is not particularly usable as an assertion in the context of WS-Policy, because it requires domain-specific extensions to support the intersection of alternatives using such an element as an assertion.</span></span> <span data-ttu-id="dc4d4-283">这样的元素定义还指示 `ReplyTo` 标头的值在传输时与终结点行为相反，这使它只能特定于 HTTP 传输。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-283">Such element definition also indicates the value of the `ReplyTo` header as opposed to the endpoint behavior on the wire, which makes it specific to HTTP transport.</span></span>  
  
#### <a name="action-definition"></a><span data-ttu-id="dc4d4-284">操作定义</span><span class="sxs-lookup"><span data-stu-id="dc4d4-284">Action Definition</span></span>  
 <span data-ttu-id="dc4d4-285">WS-Addressing 2004/08 为 `wsa:Action` 元素定义了一个 `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` 属性。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-285">WS-Addressing 2004/08 defines a `wsa:Action` attribute for the `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements.</span></span> <span data-ttu-id="dc4d4-286">WS-Addressing 1.0 WSDL 绑定 (WS-ADDR10-WSDL) 定义了一个类似属性 `wsaw10:Action`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-286">WS-Addressing 1.0 WSDL Binding (WS-ADDR10-WSDL) defines a similar attribute, `wsaw10:Action`.</span></span>  
  
 <span data-ttu-id="dc4d4-287">两者之间唯一的区别在于默认 Action 模式语义（分别在 WS-ADDR 第 3.3.2 节和 WS-ADDR10-WSDL 第 4.4.4 节描述）。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-287">The only difference between the two is the default Action pattern semantics described in section 3.3.2 of WS-ADDR and section 4.4.4 of WS-ADDR10-WSDL, respectively.</span></span>  
  
 <span data-ttu-id="dc4d4-288">它是个共享相同的两个终结点`portType`（或中 WCF 术语协定） 但使用不同 Ws-addressing 版本。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-288">It is a reasonable to have two endpoints that share the same `portType` (or contract, in WCF terminology) but using different versions of WS-Addressing.</span></span> <span data-ttu-id="dc4d4-289">但是，如果 Action 是由 `portType` 定义的，并且在实现该 `portType` 的终结点之间不应更改，则不可能同时支持这两种默认操作模式。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-289">But given that Action is defined by the `portType` and should not change across the endpoints that implement the `portType`, it becomes impossible to support both default action patterns.</span></span>  
  
 <span data-ttu-id="dc4d4-290">若要解决这一矛盾，WCF 支持单个版本`Action`属性。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-290">To resolve this controversy, WCF supports a single version of the `Action` attribute.</span></span>  
  
 <span data-ttu-id="dc4d4-291">B3521: WCF 使用`wsaw10:Action`属性`wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`WS-ADDR10 的 WSDL 来确定中定义的元素`Action`而不考虑终结点使用的 Ws-addressing 版本对应的消息的 URI。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-291">B3521: WCF uses the `wsaw10:Action` attribute on `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements as defined in WS-ADDR10-WSDL to determine the `Action` URI for the corresponding messages irrespective of the WS-Addressing version used by the endpoint.</span></span>  
  
#### <a name="use-endpoint-reference-inside-wsdl-port"></a><span data-ttu-id="dc4d4-292">在 WSDL 端口内使用终结点引用</span><span class="sxs-lookup"><span data-stu-id="dc4d4-292">Use Endpoint Reference Inside WSDL Port</span></span>  
 <span data-ttu-id="dc4d4-293">WS-ADDR10-WSDL 4.1 节扩展了 `wsdl:port` 元素以包含 `<wsa10:EndpointReference…/>` 子元素，从而以 WS-Addressing 方式描述终结点。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-293">WS-ADDR10-WSDL section 4.1 extends the `wsdl:port` element to include the `<wsa10:EndpointReference…/>` child element to describe the endpoint in WS-Addressing terms.</span></span> <span data-ttu-id="dc4d4-294">WCF 扩展了 Ws-addressing 2004/08 时，此实用工具允许`<wsa:EndpointReference…/>`显示的子元素为`wsdl:port`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-294">WCF expands this utility on WS-Addressing 2004/08, allowing `<wsa:EndpointReference…/>` to appear as a child element of `wsdl:port`.</span></span>  
  
-   <span data-ttu-id="dc4d4-295">R3531：如果终结点有一个带有 `<wsaw10:UsingAddressing/>`wsdl:port 策略断言的附加策略备选项，则对应的`wsdl:port`元素可包含子元素`<wsa10:EndpointReference …/>`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-295">R3531: If an endpoint has an attached policy alternative with a `<wsaw10:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa10:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="dc4d4-296">R3532： 如果`wsdl:port`包含子元素`<wsa10:EndpointReference …/>`、`wsa10:EndpointReference/wsa10:Address`子元素值必须与匹配的值`@address`的同级的特性`wsdl:port` / `wsdl:location`元素。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-296">R3532: If a `wsdl:port` contains a child element `<wsa10:EndpointReference …/>`, the `wsa10:EndpointReference/wsa10:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
-   <span data-ttu-id="dc4d4-297">R3533：如果终结点有一个带有 `<wsap:UsingAddressing/>`wsdl:port 策略断言的附加策略备选项，则对应的`wsdl:port` 元素可包含子元素`<wsa:EndpointReference …/>`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-297">R3533: If an endpoint has an attached policy alternative with `<wsap:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="dc4d4-298">R3534： 如果`wsdl:port`包含子元素`<wsa:EndpointReference …/>`、`wsa:EndpointReference/wsa:Address`子元素值必须与匹配的值`@address`的同级的特性`wsdl:port` / `wsdl:location`元素。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-298">R3534: If a `wsdl:port` contains a child element `<wsa:EndpointReference …/>`, the `wsa:EndpointReference/wsa:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="dc4d4-299">与 WS-Security 的结合</span><span class="sxs-lookup"><span data-stu-id="dc4d4-299">Composition with WS-Security</span></span>  
 <span data-ttu-id="dc4d4-300">根据 WS-ADDR 和 WS-ADDR10 中的安全注意事项章节，建议将所有寻址消息头和消息正文一起签名，以便将它们绑定在一起。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-300">According to security consideration sections in WS-ADDR and WS-ADDR10, all addressing message headers are recommended to be signed together with the message body to bind them together.</span></span>  
  
 <span data-ttu-id="dc4d4-301">当 WS-Security 用于消息完整性保护时，WS-Addressing 消息头和从引用参数或/和属性产生的标头必须与消息正文一起签名。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-301">When WS-Security is used for message integrity protection, WS-Addressing message headers as well as headers resulted from reference parameters or properties (or both) must be signed together with the body of the message.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="dc4d4-302">示例</span><span class="sxs-lookup"><span data-stu-id="dc4d4-302">Examples</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="dc4d4-303">单向消息</span><span class="sxs-lookup"><span data-stu-id="dc4d4-303">One-Way Message</span></span>  
 <span data-ttu-id="dc4d4-304">在此方案中，发送方向接收方发出单向消息。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-304">In this scenario, the sender sends a one-way message to the receiver.</span></span> <span data-ttu-id="dc4d4-305">使用 SOAP 1.2、HTTP 1.1 和 W3C WS-Addressing 1.0。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-305">SOAP 1.2, HTTP 1.1, and W3C WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="dc4d4-306">请求消息结构：消息头包含 `wsa10:To` 和 `wsa10:Action` 元素。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-306">The Request Message Structure: The message headers include `wsa10:To` and `wsa10:Action` elements.</span></span> <span data-ttu-id="dc4d4-307">消息正文包含来自应用程序命名空间的一个特定 `<app:Ping>` 元素。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-307">The message body includes a specific `<app:Ping>` element from the application namespace.</span></span>  
  
 <span data-ttu-id="dc4d4-308">HTTP 标头： POST 中的目标与中的 URI 匹配`wsa10:To`元素。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-308">HTTP Headers: The destination in POST matches the URI in the `wsa10:To` element.</span></span>  
  
 <span data-ttu-id="dc4d4-309">按照 SOAP 1.2 的要求，Content-Type 标头的值为 `application/soap+xml`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-309">The Content-Type header has the value of `application/soap+xml` as required by SOAP 1.2.</span></span> <span data-ttu-id="dc4d4-310">此外，还包含参数 `charset` 和 `action`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-310">Parameters `charset` and `action` are included.</span></span> <span data-ttu-id="dc4d4-311">Content-Type 标头的 `action` 参数与 `wsa10:Action` 消息头的值匹配。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-311">The `action` parameter of the Content-Type header matches the value of the `wsa10:Action` message header.</span></span>  
  
```  
POST http://fabrikam123.com/Service HTTP/1.1  
Content-Type: application/soap+xml; charset=utf-8;    
              action="http://fabrikam123.com/Service/OneWay"  
Host: 131.107.72.15  
Content-Length: 1501  
Expect: 100-continue  
Proxy-Connection: Keep-Alive  
<s12:Envelope>  
  <s12:Header>  
    <wsa10:To s12:mustUnderstand="1">  
        http://fabrikam123.com/Service  
    </wsa10:To>  
    <wsa10:Action s12:mustUnderstand="1">  
        http://fabrikam123.com/Service/OneWay   
    </wsa10:Action>  
  </s12:Header>  
  <s12:Body>  
    <Ping xmlns="http://fabrikam123.com/Service/">  
      <Text>Hello World</Text>  
    </Ping>  
  </s12:Body>  
</s12:Envelope>  
```  
  
 <span data-ttu-id="dc4d4-312">接收方以一个状态为 202 的空 HTTP 响应进行回应。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-312">The receiver responds with an empty HTTP response and status 202.</span></span> <span data-ttu-id="dc4d4-313">HTTP 响应的一个示例为：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-313">An example of the HTTP response:</span></span>  
  
```  
HTTP/1.1 202 Accepted  
Date: Fri, 15 Jul 2005 08:56:07 GMT  
Server: Microsoft-IIS/6.0  
MicrosoftOfficeWebServer: 5.0_Pub  
X-Powered-By: ASP.NET  
X-AspNet-Version: 2.0.50215  
Cache-Control: private  
Content-Length: 0  
```  
  
## <a name="soap-message-transmission-optimization-mechanism"></a><span data-ttu-id="dc4d4-314">SOAP Message Transmission Optimization Mechanism（SOAP 消息传输优化机制）</span><span class="sxs-lookup"><span data-stu-id="dc4d4-314">SOAP Message Transmission Optimization Mechanism</span></span>  
 <span data-ttu-id="dc4d4-315">本节介绍用于对 HTTP SOAP MTOM WCF 实现详细信息。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-315">This section describes the WCF implementation details for the HTTP SOAP MTOM.</span></span> <span data-ttu-id="dc4d4-316">MTOM 技术是作为传统的 text/XML 编码或 WCF 二进制编码同类的 SOAP 消息编码机制。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-316">MTOM technology is SOAP message encoding mechanism of the same class as traditional text/XML encoding or WCF Binary encoding.</span></span> <span data-ttu-id="dc4d4-317">MTOM 包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-317">MTOM includes the following:</span></span>  
  
-   <span data-ttu-id="dc4d4-318">[XOP] 描述的 XML 编码和打包机制，用于将包含 base64 编码的二进制数据的 XML 信息项优化为多个独立的二进制部分。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-318">An XML encoding and packaging mechanism described by [XOP] that optimizes XML information items containing base64-encoded binary data into separate binary parts.</span></span>  
  
-   <span data-ttu-id="dc4d4-319">XOP 包的 MIME 封装，用于将 XML Infoset 和 XOP 包的每一个二进制部分序列化为单独的 MIME 部分。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-319">A MIME encapsulation of the XOP package that serializes the XML Infoset and each binary part of the XOP package into a separate MIME part.</span></span>  
  
-   <span data-ttu-id="dc4d4-320">应用于 SOAP 1.x 信封的 MIME XOP 编码。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-320">A MIME XOP encoding applied to SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="dc4d4-321">HTTP 传输绑定。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-321">An HTTP transport binding.</span></span>  
  
 <span data-ttu-id="dc4d4-322">就可以将 MTOM 用于与 WCF 非 HTTP 传输。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-322">It is possible to use MTOM with non-HTTP transports with WCF.</span></span> <span data-ttu-id="dc4d4-323">不过，在本主题中，我们将着重讨论 HTTP 上的应用。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-323">However, in this topic we will focus on HTTP.</span></span>  
  
 <span data-ttu-id="dc4d4-324">MTOM 格式利用了包含 MTOM 本身、XOP 以及 MIME 在内的大型规范集。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-324">The MTOM format leverages a large set of specifications covering MTOM itself, XOP, and MIME.</span></span> <span data-ttu-id="dc4d4-325">在某种程度上，此规范集的模块性使得重新构造格式和处理语义的确切要求变得有点困难。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-325">Modularity of this specification set makes it somewhat difficult to reconstruct exact requirements on the format and processing semantics.</span></span> <span data-ttu-id="dc4d4-326">本节介绍 MTOM HTTP 绑定的格式和处理要求。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-326">This section describes the format and processing requirements for MTOM HTTP binding.</span></span>  
  
### <a name="mtom-message-encoding"></a><span data-ttu-id="dc4d4-327">MTOM 消息编码</span><span class="sxs-lookup"><span data-stu-id="dc4d4-327">MTOM Message Encoding</span></span>  
  
#### <a name="generating-mtom-messages"></a><span data-ttu-id="dc4d4-328">生成 MTOM 消息</span><span class="sxs-lookup"><span data-stu-id="dc4d4-328">Generating MTOM messages</span></span>  
 <span data-ttu-id="dc4d4-329">[XOP] 第 3.1 节描述了将具有元素信息项（包含 base64 值）的 XML 编码为抽象定义的 XOP 包的过程。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-329">The [XOP] section 3.1 describes the process of encoding XML with element information items that contain base64 values into an abstractly defined XOP package.</span></span>  
  
 <span data-ttu-id="dc4d4-330">下面的一系列步骤描述了特定于 MTOM 的编码过程：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-330">The following sequence of steps describes the MTOM-specific encoding process:</span></span>  
  
1.  <span data-ttu-id="dc4d4-331">确保要编码 SOAP 信封包含任何元素信息项替换为`[namespace name]`的"http://www.w3.org/2004/08/xop/include"和`[local name]`的`Include`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-331">Ensure that the SOAP Envelope to be encoded contains no element information item with a `[namespace name]` of "http://www.w3.org/2004/08/xop/include" and a `[local name]` of `Include`.</span></span>  
  
2.  <span data-ttu-id="dc4d4-332">创建一个空 MIME 包。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-332">Create an empty MIME package.</span></span>  
  
3.  <span data-ttu-id="dc4d4-333">在原始 XML Infoset 中标识要优化的元素信息项。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-333">Identify within the Original XML Infoset the element information items to be optimized.</span></span> <span data-ttu-id="dc4d4-334">对于要优化的项，组成该元素信息项的 `[children]` 的字符必须是 `xs:base64Binary` 的规范形式（请参见 XSD-2，3.2.16 base64Binary），在非空格内容前面、中间或后面，都不得包含任何空格字符。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-334">For the items to be optimized, the characters that make up the `[children]` of the element information item must be in the canonical form of `xs:base64Binary` (see XSD-2, 3.2.16 base64Binary) and must not contain any whitespace characters preceding, inline with, or following the non-whitespace content.</span></span>  
  
4.  <span data-ttu-id="dc4d4-335">创建一个是原始 SOAP 信封副本的 XOP SOAP 信封，但是，在上一步中标识的每个元素信息项的 children 都替换为如下构造的 `xop:Include` 元素信息项：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-335">Create an XOP SOAP Envelope that is a copy of the Original SOAP Envelope, but with the children of each element information item identified in the previous step replaced by an `xop:Include` element information item constructed as follows:</span></span>  
  
    1.  <span data-ttu-id="dc4d4-336">通过将被替换字符处理为 base64 编码的数据，将其转换为二进制数据。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-336">Transform the replaced characters into binary data by processing them as base64-encoded data.</span></span>  
  
    2.  <span data-ttu-id="dc4d4-337">生成一个符合 R3133 和 R3134 要求的唯一 Content-ID 标头值。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-337">Generate a unique Content-ID header value that satisfies requirements R3133 and R3134.</span></span>  
  
    3.  <span data-ttu-id="dc4d4-338">生成一个具有二进制值的 Content-Transfer-Encoding MIME 标头。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-338">Generate a Content-Transfer-Encoding MIME header with the value binary.</span></span>  
  
    4.  <span data-ttu-id="dc4d4-339">如果要优化的元素信息项（新插入的 `xop:Include` 元素信息项的 [parent]）有一个 `xmime:contentType` 属性信息项，则生成一个带有 `xmime:contentType` 属性的值的 Content-Type MIME 标头。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-339">If the element information item being optimized (the [parent] of the newly inserted `xop:Include` element information item) has an `xmime:contentType` attribute information item, generate a Content-Type MIME header with the value of the `xmime:contentType` attribute.</span></span>  
  
    5.  <span data-ttu-id="dc4d4-340">生成一个新的二进制 MIME 部分，其内容由以下几项组成：从处理为 base64 的被替换数据解码的二进制数据、4b 中的 Content-ID、4c 中的 Content- Transfer-Encoding 标头，以及 Content-Type 标头（如果在步骤 4d 中生成）。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-340">Generate a new binary MIME part with content formed by binary data decoded from the replaced characters processed as base64, Content-ID header from 4b, Content- Transfer-Encoding header from 4c, Content-Type header if generated in step 4d.</span></span>  
  
    6.  <span data-ttu-id="dc4d4-341">将一个 `href` 属性添加到 `xop:Include` 元素，其值为从 Content-ID 标头值（在步骤 4b 中生成）派生的 cid: uri。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-341">Add an `href` attribute to the `xop:Include` element with the value cid: uri derived from Content-ID header value generated in step 4b.</span></span> <span data-ttu-id="dc4d4-342">移除外层"\<"和">"字符，则 URL 转义剩余的字符串，并添加前缀`cid:`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-342">Remove the enclosing "\<" and ">" characters, URL-escape the remaining string, and add the prefix `cid:`.</span></span> <span data-ttu-id="dc4d4-343">以下最小字符集需要根据 RFC1738 和 RFC2396 进行转义。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-343">The following minimum character set is required to be escaped by RFC1738 and RFC2396.</span></span> <span data-ttu-id="dc4d4-344">其他字符也可转义。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-344">Other characters can be escaped.</span></span>  
  
        ```  
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">  
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"  
        ```  
  
5.  <span data-ttu-id="dc4d4-345">用步骤 4 中的 XOP SOAP 信封创建一个根 MIME 部分。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-345">Create a root MIME part with the XOP SOAP Envelope from step 4.</span></span>  
  
6.  <span data-ttu-id="dc4d4-346">写入 HTTP 标头，包括 HTTP Content-Type 标头。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-346">Write the HTTP headers, including the HTTP Content-Type header.</span></span>  
  
7.  <span data-ttu-id="dc4d4-347">写入 MIME 包。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-347">Write the MIME package.</span></span>  
  
#### <a name="processing-mtom-messages"></a><span data-ttu-id="dc4d4-348">处理 MTOM 消息</span><span class="sxs-lookup"><span data-stu-id="dc4d4-348">Processing MTOM messages</span></span>  
 <span data-ttu-id="dc4d4-349">处理 MTOM 消息的过程与前面“生成 MTOM 消息”一节中所述的过程完全相反：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-349">Processing of an MTOM message is the exact reverse of the process described in the preceding "Generating MTOM messages" section:</span></span>  
  
1.  <span data-ttu-id="dc4d4-350">确保根 MIME 部分有 Content-Type `application/xop+xml`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-350">Ensure the root MIME part has the Content-Type `application/xop+xml`.</span></span>  
  
2.  <span data-ttu-id="dc4d4-351">通过将包的根 MIME 部分作为 XML 文档进行分析，构造一个 SOAP 信封。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-351">Construct a SOAP Envelope by parsing the root MIME part of the package as an XML document.</span></span> <span data-ttu-id="dc4d4-352">字符编码由根 MIME 部分的 Content-Type 的 `charset` 参数确定。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-352">Character encoding is determined by the `charset` parameter of the Content-Type of the root MIME part.</span></span>  
  
3.  <span data-ttu-id="dc4d4-353">对于构造的 SOAP 信封中的每个元素信息项（有一个 `xop:Include` 元素信息项作为其 [children] 属性的唯一成员）：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-353">For each element information item in the constructed SOAP Envelope, which has, as the sole member of its [children] property, an `xop:Include` element information item:</span></span>  
  
    1.  <span data-ttu-id="dc4d4-354">移除 `cid:` 前缀，取消转义 `@href` 元素的 `xop:Include` 属性的值中所有 URI 转义序列 (RFC 2396)。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-354">Remove the `cid:` prefix and unescape all URI-escape sequences (RFC 2396) in the value of the `@href` attribute of the `xop:Include` element.</span></span> <span data-ttu-id="dc4d4-355">将在结果字符串括"\<"，">"。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-355">Enclose the result string in "\<", ">".</span></span>  
  
    2.  <span data-ttu-id="dc4d4-356">找到 Content-ID 标头值与步骤 3a 中派生的字符串匹配的 MIME 部分。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-356">Locate the MIME part with the Content-ID header value that matches the string derived in step 3a.</span></span>  
  
    3.  <span data-ttu-id="dc4d4-357">将出现在每一项的 `xop:Include` 属性中的 `children` 元素信息项替换为字符信息项，这些字符信息项表示的是 MIME 部分（在步骤 3b 中标识）全部正文的规范 base64 编码（请参见 XSD-2，3.2.16 base64Binary）（实际是将 `xop:Include` 元素信息项替换为从包部分重新构造的数据）。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-357">Replace the `xop:Include` element information item that appears in the `children` property of each item with the character information items that represent the canonical base64 encoding (see XSD-2, 3.2.16 base64Binary) of the entity body of the MIME part identified in step 3b (effectively replace the `xop:Include` element information item with the data reconstructed from the package part).</span></span>  
  
#### <a name="http-content-type-header"></a><span data-ttu-id="dc4d4-358">HTTP Content-Type 标头</span><span class="sxs-lookup"><span data-stu-id="dc4d4-358">HTTP Content-Type Header</span></span>  
 <span data-ttu-id="dc4d4-359">下面是格式的 HTTP Content-type 标头的 SOAP 1.x MTOM 编码消息派生自根据 MTOM 规范本身中所述的 WCF 所说明的列表，并从 MTOM 和 RFC 2387 派生。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-359">The following is a list of WCF clarifications for the format of the HTTP Content-Type header of a SOAP 1.x MTOM-encoded message derived from requirements stated in the MTOM specification itself and are derived from MTOM and RFC 2387.</span></span>  
  
-   <span data-ttu-id="dc4d4-360">R4131：HTTP Content-Type 标头必须具有值 multipart/related（不区分大小写）及其参数。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-360">R4131: An HTTP Content-Type header must have the value of multipart/related (case-insensitive) and its parameters.</span></span> <span data-ttu-id="dc4d4-361">参数名不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-361">Parameter names are case-insensitive.</span></span> <span data-ttu-id="dc4d4-362">参数顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-362">Parameter order is not significant.</span></span>  
  
-   <span data-ttu-id="dc4d4-363">RFC 2045 第 5.1 节中列出了 MIME 消息 Content-Type 标头的完全 Backus-Naur 形式 (BNF)。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-363">The full Backus-Naur Form (BNF) of the Content-Type header for MIME messages is listed in RFC 2045, section 5.1.</span></span>  
  
-   <span data-ttu-id="dc4d4-364">R4132：HTTP Content-Type 标头必须具有一个类型参数，并且值 `application/xop+xml` 括在双引号中。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-364">R4132: An HTTP Content-Type header must have a type parameter with the value `application/xop+xml` enclosed in double quotation marks.</span></span>  
  
 <span data-ttu-id="dc4d4-365">要求使用双引号括起来，尽管不是在 RFC 2387 中显式其文字提到所有 multipart/related 媒体类型参数最有可能包含之类的保留的字符"\@"或"/"，因此需要双引号将标记。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-365">While the requirement to use double quotation marks is not explicit in RFC 2387, the text observes that all of the multipart/related media type parameters most likely contain reserved characters like "\@" or "/" and therefore need double quotation marks.</span></span>  
  
-   <span data-ttu-id="dc4d4-366">R4133：HTTP Content-Type 标头应该有一个 start 参数，其值为包含 SOAP 1.x 信封的 MIME 部分的 Content-ID 标头，并且括在双引号中。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-366">R4133: An HTTP Content-Type header should have a start parameter with the value of the Content-ID header of the MIME part that contains the SOAP 1.x Envelope, enclosed in double quotation marks.</span></span> <span data-ttu-id="dc4d4-367">如果省略 start 参数，则第一个 MIME 部分必须包含 SOAP 1.x 信封。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-367">If the start parameter is omitted, the first MIME part must contain the SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="dc4d4-368">R4134：SOAP 1.1 MTOM 编码消息的 HTTP Content-Type 标头必须包含值为 text/xml（括在双引号中）的 start-info 参数。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-368">R4134: An HTTP Content-Type header for a SOAP 1.1 MTOM encoded message must include the start-info parameter with the value of text/xml, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="dc4d4-369">R4135：SOAP 1.2 MTOM 编码消息的 HTTP Content-Type 标头必须包含值为 `application/soap+xml`（括在双引号中）的 start-info 参数。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-369">R4135: An HTTP Content-Type header for a SOAP 1.2 MTOM-encoded message must include the start-info parameter with the value of `application/soap+xml`, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="dc4d4-370">R4136：SOAP 1.x MTOM 编码消息的 HTTP Content-Type 标头必须具有边界参数，其值（括在双引号中）与 RFC 2046 第 5.1.1 节中定义的 MIME 边界 BNF 匹配。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-370">R4136: HTTP Content-Type header for a SOAP 1.x MTOM-encoded message must have the boundary parameter with the value (enclosed in double quotation marks) that matches the MIME boundary BNF defined in RFC 2046, section 5.1.1</span></span>  
  
    ```  
    boundary := 0*69<bchars> bcharsnospace   
    bchars := bcharsnospace / " "   
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+"   
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"  
    ```  
  
     <span data-ttu-id="dc4d4-371">示例：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-371">Examples:</span></span>  
  
     <span data-ttu-id="dc4d4-372">正确</span><span class="sxs-lookup"><span data-stu-id="dc4d4-372">CORRECT</span></span>  
  
    ```  
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"  
    ```  
  
     <span data-ttu-id="dc4d4-373">正确</span><span class="sxs-lookup"><span data-stu-id="dc4d4-373">CORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"  
    ```  
  
     <span data-ttu-id="dc4d4-374">不正确</span><span class="sxs-lookup"><span data-stu-id="dc4d4-374">INCORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"   
    ```  
  
#### <a name="infoset-mime-part"></a><span data-ttu-id="dc4d4-375">Infoset MIME 部分</span><span class="sxs-lookup"><span data-stu-id="dc4d4-375">Infoset MIME Part</span></span>  
 <span data-ttu-id="dc4d4-376">SOAP 1.x 信封封装为 XOP MIME 包的根部分，通常称为 `infoset` 部分。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-376">The SOAP 1.x Envelope is encapsulated as a root part of the XOP MIME package and is often called the `infoset` part.</span></span>  
  
-   <span data-ttu-id="dc4d4-377">R4141：SOAP 1.x 信封必须封装为 XOP MIME 包的根部分，称为 `infoset` 部分，并从 HTTP Content-Type 引用。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-377">R4141: The SOAP 1.x Envelope must be encapsulated as a root part of the XOP MIME package, called the `infoset` part and referenced from the HTTP Content-Type.</span></span>  
  
-   <span data-ttu-id="dc4d4-378">R4142：SOAP `Infoset` 部分必须包含以下 MIME 标头：`Content-ID`、`Content-Transfer-Encoding` 和 `Content-Type`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-378">R4142: The SOAP `Infoset` part must include the following MIME headers: `Content-ID`, `Content-Transfer-Encoding`, and `Content-Type`.</span></span>  
  
 <span data-ttu-id="dc4d4-379">Content-ID 标头的格式根据 RFC 2045 定义为</span><span class="sxs-lookup"><span data-stu-id="dc4d4-379">The format of the Content-ID header is defined by RFC 2045 as</span></span>  
  
```  
"Content-ID" ":" msg-id  
```  
  
 <span data-ttu-id="dc4d4-380">其中 `msg-id` 在 RFC 2822（取代 RFC 822，在 RFC 2045 中引用）定义：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-380">where `msg-id` is defined in RFC 2822 (that supersedes RFC 822, referenced in RFC 2045) as:</span></span>  
  
```  
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]  
```  
  
 <span data-ttu-id="dc4d4-381">并将有效地电子邮件地址括在"\<"和">"。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-381">and is effectively an email address enclosed within "\<" and  ">".</span></span> <span data-ttu-id="dc4d4-382">RFC 2822 中增加了 `[CFWS]` 前缀和后缀，用于携带注释，不应用于保持互操作性。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-382">The `[CFWS]` prefix and suffix were added in RFC 2822 to carry comments and should not be used to preserve interoperability.</span></span>  
  
 <span data-ttu-id="dc4d4-383">R4143：Infoset MIME 部分的 Content-ID 标头的值必须遵循 RFC 2822 中的 `msg-id` 结果，并省略 `[CFWS]` 前缀和后缀部分。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-383">R4143: The value of the Content-ID header for the Infoset MIME part must follow `msg-id` production from RFC 2822 with the `[CFWS]` prefix and suffix parts omitted.</span></span>  
  
 <span data-ttu-id="dc4d4-384">多 MIME 实现内包含的值的要求很宽松"\<"和">"应为电子邮件地址，并用`absoluteURI`括在"\<"，">"除了电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-384">A number of MIME implementations relaxed requirements for the value enclosed within "\<" and ">" to be an email address and used `absoluteURI` enclosed in "\<" , ">" in addition to the email address.</span></span> <span data-ttu-id="dc4d4-385">此版本的 WCF 使用窗体的 CONTENT-ID MIME 标头的值：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-385">This version of WCF uses values of the Content-ID MIME header of the form:</span></span>  
  
```  
Content-ID: <http://tempuri.org/0>   
```  
  
 <span data-ttu-id="dc4d4-386">R4144：MTOM 处理程序应接受符合以下宽松 `msg-id` 的 Content-ID 标头值。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-386">R4144: MTOM processors should accept Content-ID header values that match the following relaxed `msg-id`.</span></span>  
  
```  
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]  
mail-address   =     id-left "@" id-right  
```  
  
 <span data-ttu-id="dc4d4-387">MIME (RFC 2045) 提供 Content-Transfer-Encoding 标头来传递 MIME 部分内容的编码。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-387">MIME (RFC 2045) provides the Content-Transfer-Encoding header to communicate encoding of the content of the MIME part.</span></span> <span data-ttu-id="dc4d4-388">为 Content-Transfer-Encoding 定义的默认值为 7-bit，它不适合于大多数 SOAP 消息，因此，需要使用 Content-Transfer-Encoding 标头以获得更好的互操作性：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-388">The default defined for Content-Transfer-Encoding is 7-bit, which is not suitable for most SOAP messages, so the Content-Transfer-Encoding header is needed for greater interoperability:</span></span>  
  
-   <span data-ttu-id="dc4d4-389">R4145：SOAP Infoset 部分必须包含 Content-Transfer-Encoding 标头。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-389">R4145: The SOAP Infoset part must contain the Content-Transfer-Encoding header.</span></span>  
  
-   <span data-ttu-id="dc4d4-390">R4146：如果 SOAP 信封字符编码为 UTF-8，则 Content-Transfer-Encoding 标头的值必须为 8-bit。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-390">R4146: If the SOAP Envelope character encoding is UTF-8, the value of the Content-Transfer-Encoding header must be 8-bit.</span></span>  
  
-   <span data-ttu-id="dc4d4-391">R4147：如果 SOAP 信封字符编码为 UTF-16，则 Content-Transfer-Encoding 标头的值必须为 binary。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-391">R4147: If the SOAP Envelope character encoding is UTF-16, the value of the Content-Transfer-Encoding header must be binary.</span></span>  
  
-   <span data-ttu-id="dc4d4-392">根据 [XOP] 第 5 节，</span><span class="sxs-lookup"><span data-stu-id="dc4d4-392">According to [XOP] section 5,</span></span>  
  
-   <span data-ttu-id="dc4d4-393">R4148: SOAP1.1 Infoset 部分必须包含媒体类型为 application/xop + xml 的 Content-type 标头以及参数 type ="text/xml"和 charset</span><span class="sxs-lookup"><span data-stu-id="dc4d4-393">R4148: SOAP1.1 Infoset part must contain Content-Type header with media type application/xop+xml and parameters type="text/xml" and charset</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="text/xml"  
    ```  
  
-   <span data-ttu-id="dc4d4-394">R4149: SOAP 1.2 Infoset 部分必须包含媒体类型的内容类型标头`application/xop+xml`以及参数 type ="`application/soap+xml`"和`charset`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-394">R4149: The SOAP 1.2 Infoset part must contain the Content-Type header with media type `application/xop+xml` and parameters type="`application/soap+xml`" and `charset`.</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="application/soap+xml"  
    ```  
  
     <span data-ttu-id="dc4d4-395">虽然 XOP 定义 `charset` 参数对于 `application/xop+xml` 是可选的，但是对于类似于 BP 1.1 对 `charset` 媒体类型要求有 `text/xml` 参数的互操作性，该参数仍然是需要的。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-395">While XOP defines the `charset` parameter for `application/xop+xml` to be optional, it is needed for interoperability similar to the BP 1.1 requirement on the `charset` parameter for the `text/xml` media type.</span></span>  
  
-   <span data-ttu-id="dc4d4-396">R41410：`type` 和 `charset` 参数必须出现在 SOAP 1.x Infoset 部分的 Content-Type 标头中。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-396">R41410: The `type` and `charset` parameters must be present on the Content-Type header of the SOAP 1.x Infoset part.</span></span>  
  
#### <a name="wcf-endpoint-support-for-mtom"></a><span data-ttu-id="dc4d4-397">WCF 对 MTOM 的终结点支持</span><span class="sxs-lookup"><span data-stu-id="dc4d4-397">WCF Endpoint Support for MTOM</span></span>  
 <span data-ttu-id="dc4d4-398">MTOM 的用途是对 SOAP 消息进行编码，以优化 base64 编码数据。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-398">The purpose of MTOM is to encode a SOAP message to optimize base64-encoded data.</span></span> <span data-ttu-id="dc4d4-399">下面列出了相关约束：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-399">The following is a list of constraints:</span></span>  
  
-   <span data-ttu-id="dc4d4-400">R4151：任何包含 base64 编码数据的元素信息项都可以优化。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-400">R4151: Any element information item that contains base64-encoded data may be optimized.</span></span>  
  
-   <span data-ttu-id="dc4d4-401">B4152: WCF 优化包含 base64 编码数据并且超过 1024 个字节的长度的元素信息项。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-401">B4152: WCF optimizes element information items that contain base64-encoded data and exceed 1024 bytes in length.</span></span>  
  
 <span data-ttu-id="dc4d4-402">配置为使用 MTOM 的 WCF 终结点将始终发送 MTOM 编码消息。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-402">A WCF endpoint configured to use MTOM will always send MTOM-encoded messages.</span></span> <span data-ttu-id="dc4d4-403">即使没有一个部分符合必需的标准，消息仍然是 MTOM 编码消息（序列化为一个 MIME 包，具有包含 SOAP 信封的单个 MIME 部分）。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-403">Even if no parts meet the required criteria, the message is still MTOM-encoded (serialized as a MIME package with a single MIME part containing the SOAP envelope).</span></span>  
  
### <a name="ws-policy-assertion-for-mtom"></a><span data-ttu-id="dc4d4-404">MTOM 的 WS-Policy 断言</span><span class="sxs-lookup"><span data-stu-id="dc4d4-404">WS-Policy Assertion for MTOM</span></span>  
 <span data-ttu-id="dc4d4-405">WCF 使用下面的策略断言来指示 MTOM 使用率终结点：</span><span class="sxs-lookup"><span data-stu-id="dc4d4-405">WCF uses the following policy assertion to indicate MTOM usage by endpoint:</span></span>  
  
```xml  
<wsoma:OptimizedMimeSerialization ... />  
```  
  
-   <span data-ttu-id="dc4d4-406">R4211：上面的策略断言有一个终结点策略主题，并指定终结点收发的所有消息都必须使用 MTOM 进行优化。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-406">R4211: The preceding policy assertion has an Endpoint Policy Subject and specifies that all messages sent to and received from the endpoint must be optimized using MTOM.</span></span>  
  
-   <span data-ttu-id="dc4d4-407">B4212： 配置为使用 MTOM 优化时，WCF 终结点向一个 MTOM 策略断言附加到相应的策略`wsdl:binding`。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-407">B4212: When configured to use MTOM optimization, an WCF endpoint adds an MTOM Policy assertion to the policy attached to the corresponding `wsdl:binding`.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="dc4d4-408">与 WS-Security 的结合</span><span class="sxs-lookup"><span data-stu-id="dc4d4-408">Composition with WS-Security</span></span>  
 <span data-ttu-id="dc4d4-409">MTOM 是一种编码机制类似于`text/xml`和 WCF 二进制 XML。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-409">MTOM is an encoding mechanism that is similar to `text/xml` and WCF Binary XML.</span></span> <span data-ttu-id="dc4d4-410">MTOM 可以与 WS-Security 及其他 WS-\* 协议自然结合：使用 WS-Security 进行保护的消息可使用 MTOM 优化。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-410">MTOM offers natural composition with WS-Security and other WS-\* protocols: a message secured using WS-Security can be optimized using MTOM.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="dc4d4-411">示例</span><span class="sxs-lookup"><span data-stu-id="dc4d4-411">Examples</span></span>  
  
#### <a name="wcf-soap-11-message-encoded-using-mtom"></a><span data-ttu-id="dc4d4-412">使用 MTOM 编码的 WCF SOAP 1.1 消息</span><span class="sxs-lookup"><span data-stu-id="dc4d4-412">WCF SOAP 1.1 Message Encoded Using MTOM</span></span>  
  
```  
POST http://131.107.72.15/Mtom/svc/service.svc/Soap11MtomUTF8 HTTP/1.1  
SOAPAction: "http://xmlsoap.org/echoBinaryAsString"  
Content-Type: multipart/related;type="application/xop+xml";  
              start="<http://tempuri.org/0>";start-info="text/xml";  
       boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"  
Host: 131.107.72.15  
Content-Length: 1501  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
Content-ID: <http://tempuri.org/0>  
Content-Transfer-Encoding: 8bit  
Content-Type: application/xop+xml;charset=utf-8;type="text/xml"  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Body>  
    <EchoBinaryAsString xmlns="http://xmlsoap.org/Ping">  
      <array>  
        <xop:Include   
         href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206521093670"   
         xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
      </array>  
    </EchoBinaryAsString>  
  </s:Body>  
</s:Envelope>  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
Content-ID: <http://tempuri.org/1/632618206521093670>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
…Binary Content..  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
```  
  
#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a><span data-ttu-id="dc4d4-413">使用 MTOM 编码的 WCF 安全 SOAP 1.2 消息</span><span class="sxs-lookup"><span data-stu-id="dc4d4-413">WCF Secure SOAP 1.2 Message Encoded Using MTOM</span></span>  
 <span data-ttu-id="dc4d4-414">此示例中，消息是使用 MTOM 以及采用 WS-Security 进行保护的 SOAP 1.2 编码的。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-414">In this example, a message is encoded using MTOM and SOAP 1.2 that is protected using WS-Security.</span></span> <span data-ttu-id="dc4d4-415">标识来进行编码的二进制部分为 `BinarySecurityToken` 的内容、对应于加密签名的 `CipherValue` 的 `EncryptedData`，以及经过加密的正文。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-415">The binary parts identified for encoding are the contents of the `BinarySecurityToken`, `CipherValue` of the `EncryptedData` corresponding to the encrypted signature and encrypted body.</span></span> <span data-ttu-id="dc4d4-416">请注意，`CipherValue`的`EncryptedKey`未识别出的优化由 WCF，因为其长度小于 1024 个字节。</span><span class="sxs-lookup"><span data-stu-id="dc4d4-416">Note that the `CipherValue` of the `EncryptedKey` was not identified for optimization by WCF, because its length is less then 1024 bytes.</span></span>  
  
```  
POST http://131.107.72.15/Mtom/service.svc/Soap12MtomSecureSignEncrypt HTTP/1.1  
Content-Type: multipart/related; type="application/xop+xml";  
              start="<http://tempuri.org/0>";  
            boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3";  
              start-info="application/soap+xml";   
              action="http://xmlsoap.org/echoBinaryAsString"  
Host: 131.107.72.15  
Content-Length: 1941  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/0>  
Content-Transfer-Encoding: 8bit  
Content-Type: application/xop+xml;charset=utf-8;type="application/soap+xml"  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
  <s:Header>  
    <o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-5">  
        <u:Created>2005-09-09T06:57:32.488Z</u:Created>  
        <u:Expires>2005-09-09T07:02:32.488Z</u:Expires>  
      </u:Timestamp>  
      <o:BinarySecurityToken u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-2" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">  
        <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
      </o:BinarySecurityToken>  
      <e:EncryptedKey Id="_1" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>  
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
          <o:SecurityTokenReference>  
            <o:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509SubjectKeyIdentifier">Xeg55vRyK3ZhAEhEf+YT0z986L0=</o:KeyIdentifier>  
          </o:SecurityTokenReference>  
        </KeyInfo>  
        <e:CipherData>          <e:CipherValue>oQfpxwT8/SAGyZQzKE2b4yO6dXuQj7pwJ+5CGL3Rf7C06bQ5ttMoQ9GLJcQYkXTzin+WwHEgs5bj5ml9HKTW9QAU5JJ6lksdymmQvWP5ZtGPBVchO4sofEGoCKmBiZL/DYS/cnbzgnc/3a6NYnc10y2fWGaGLiqa00zijAw7o0Y=</e:CipherValue>  
        </e:CipherData>  
      </e:EncryptedKey>  
      <c:DerivedKeyToken u:Id="_2" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc">  
        <o:SecurityTokenReference>  
          <o:Reference URI="#_1"/>  
        </o:SecurityTokenReference>  
        <c:Nonce>OrEPRX7fISIS4sXYWPMv3g==</c:Nonce>  
      </c:DerivedKeyToken>  
      <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:DataReference URI="#_3"/>  
        <e:DataReference URI="#_4"/>  
      </e:ReferenceList>  
      <e:EncryptedData Id="_4" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>  
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
          <o:SecurityTokenReference>  
            <o:Reference URI="#_2"/>  
          </o:SecurityTokenReference>  
        </KeyInfo>  
        <e:CipherData>  
          <e:CipherValue>  
            <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F2%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
          </e:CipherValue>  
        </e:CipherData>  
      </e:EncryptedData>  
    </o:Security>  
  </s:Header>  
  <s:Body u:Id="_0">  
    <e:EncryptedData Id="_3" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
      <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>  
      <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <o:SecurityTokenReference xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
          <o:Reference URI="#_2"/>  
        </o:SecurityTokenReference>  
      </KeyInfo>  
      <e:CipherData>  
        <e:CipherValue>  
          <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F3%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
        </e:CipherValue>  
      </e:CipherData>  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/1/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary content of BinarySecurityToken - X509 Certificate...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/2/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary serialization of the encrypted primary signature...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/3/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary serialization of the encrypted Body...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3--  
```
