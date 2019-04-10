---
title: 如何：启用流处理
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6ca2cf4b-c7a1-49d8-a79b-843a90556ba4
ms.openlocfilehash: 0d8428487c3c320a634914b99219e23befb70d55
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312158"
---
# <a name="how-to-enable-streaming"></a><span data-ttu-id="a93b4-102">如何：启用流处理</span><span class="sxs-lookup"><span data-stu-id="a93b4-102">How to: Enable Streaming</span></span>
<span data-ttu-id="a93b4-103">Windows Communication Foundation (WCF) 可以发送使用缓冲还是流传输的消息。</span><span class="sxs-lookup"><span data-stu-id="a93b4-103">Windows Communication Foundation (WCF) can send messages using either buffered or streamed transfers.</span></span> <span data-ttu-id="a93b4-104">在默认的缓冲传输模式中，只有在一条消息全部传递完之后，接收方才能读取该消息。</span><span class="sxs-lookup"><span data-stu-id="a93b4-104">In the default buffered-transfer mode, a message must be completely delivered before a receiver can read it.</span></span> <span data-ttu-id="a93b4-105">在流传输模式中，不必等到消息全部传递完，接收方便可以开始处理该消息。</span><span class="sxs-lookup"><span data-stu-id="a93b4-105">In streaming transfer mode, the receiver can begin to process the message before it is completely delivered.</span></span> <span data-ttu-id="a93b4-106">当传递的信息很长且可以依次处理时，流模式非常有用。</span><span class="sxs-lookup"><span data-stu-id="a93b4-106">The streaming mode is useful when the information that is passed is lengthy and can be processed serially.</span></span> <span data-ttu-id="a93b4-107">当消息过长以致于无法全部缓冲时，流模式也非常有用。</span><span class="sxs-lookup"><span data-stu-id="a93b4-107">Streaming mode is also useful when the message is too large to be entirely buffered.</span></span>  
  
 <span data-ttu-id="a93b4-108">若要启用流处理，请适当地定义 `OperationContract` 并在传输级别上启用流处理。</span><span class="sxs-lookup"><span data-stu-id="a93b4-108">To enable streaming, define the `OperationContract` appropriately and enable streaming at the transport level.</span></span>  
  
### <a name="to-stream-data"></a><span data-ttu-id="a93b4-109">对数据进行流处理</span><span class="sxs-lookup"><span data-stu-id="a93b4-109">To stream data</span></span>  
  
1. <span data-ttu-id="a93b4-110">若要对数据进行流处理，服务的 `OperationContract` 必须满足两个要求：</span><span class="sxs-lookup"><span data-stu-id="a93b4-110">To stream data, the `OperationContract` for the service must satisfy two requirements:</span></span>  
  
    1.  <span data-ttu-id="a93b4-111">保留要进行流处理的数据的参数必须是方法中的唯一参数。</span><span class="sxs-lookup"><span data-stu-id="a93b4-111">The parameter that holds the data to be streamed must be the only parameter in the method.</span></span> <span data-ttu-id="a93b4-112">例如，如果要对输入消息进行流处理，则该操作必须正好具有一个输入参数。</span><span class="sxs-lookup"><span data-stu-id="a93b4-112">For example, if the input message is the one to be streamed, the operation must have exactly one input parameter.</span></span> <span data-ttu-id="a93b4-113">同样，如果要对输出消息进行流处理，则该操作必须正好具有一个输出参数或一个返回值。</span><span class="sxs-lookup"><span data-stu-id="a93b4-113">Similarly, if the output message is to be streamed, the operation must have either exactly one output parameter or a return value.</span></span>  
  
    2.  <span data-ttu-id="a93b4-114">参数和返回值的类型中至少有一个必须是 <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message> 或 <xref:System.Xml.Serialization.IXmlSerializable>。</span><span class="sxs-lookup"><span data-stu-id="a93b4-114">At least one of the types of the parameter and return value must be either <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, or <xref:System.Xml.Serialization.IXmlSerializable>.</span></span>  
  
     <span data-ttu-id="a93b4-115">下面是流处理数据的协定的示例。</span><span class="sxs-lookup"><span data-stu-id="a93b4-115">The following is an example of a contract for streamed data.</span></span>  
  
     [!code-csharp[c_HowTo_EnableStreaming#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#1)]
     [!code-vb[c_HowTo_EnableStreaming#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#1)]  
  
     <span data-ttu-id="a93b4-116">`GetStream` 操作接收一些缓冲输入数据作为经过缓冲的 `string`，并返回经过流处理的 `Stream`。</span><span class="sxs-lookup"><span data-stu-id="a93b4-116">The `GetStream` operation receives some buffered input data as a `string`, which is buffered, and returns a `Stream`, which is streamed.</span></span> <span data-ttu-id="a93b4-117">相反，`UploadStream` 接收一个经过流处理的 `Stream`，并返回一个经过缓冲的 `bool`。</span><span class="sxs-lookup"><span data-stu-id="a93b4-117">Conversely `UploadStream` takes in a `Stream` (streamed) and returns a `bool` (buffered).</span></span> `EchoStream` <span data-ttu-id="a93b4-118">采用并返回`Stream`和是操作的示例的输入和输出消息都流式的。</span><span class="sxs-lookup"><span data-stu-id="a93b4-118">takes and returns `Stream` and is an example of an operation whose input and output messages are both streamed.</span></span> <span data-ttu-id="a93b4-119">最后，`GetReversedStream` 将不接收输入，并返回一个 `Stream`（已经过流处理）。</span><span class="sxs-lookup"><span data-stu-id="a93b4-119">Finally, `GetReversedStream` takes no inputs and returns a `Stream` (streamed).</span></span>  
  
2. <span data-ttu-id="a93b4-120">必须在绑定上启用流处理。</span><span class="sxs-lookup"><span data-stu-id="a93b4-120">Streaming must be enabled on the binding.</span></span> <span data-ttu-id="a93b4-121">设置 `TransferMode` 属性，可以采用下面的值之一：</span><span class="sxs-lookup"><span data-stu-id="a93b4-121">You set a `TransferMode` property, which can take one of the following values:</span></span>  
  
    1.  `Buffered`<span data-ttu-id="a93b4-122">,</span><span class="sxs-lookup"><span data-stu-id="a93b4-122">,</span></span>  
  
    2.  `Streamed`<span data-ttu-id="a93b4-123">其中启用流通信在两个方向。</span><span class="sxs-lookup"><span data-stu-id="a93b4-123">, which enables streaming communication in both directions.</span></span>  
  
    3.  `StreamedRequest`<span data-ttu-id="a93b4-124">此启用流处理仅限请求。</span><span class="sxs-lookup"><span data-stu-id="a93b4-124">, which enables streaming the request only.</span></span>  
  
    4.  `StreamedResponse`<span data-ttu-id="a93b4-125">此启用流处理仅响应。</span><span class="sxs-lookup"><span data-stu-id="a93b4-125">, which enables streaming the response only.</span></span>  
  
     <span data-ttu-id="a93b4-126">`BasicHttpBinding` 公开绑定上的 `TransferMode` 属性，与 `NetTcpBinding` 和 `NetNamedPipeBinding` 一样。</span><span class="sxs-lookup"><span data-stu-id="a93b4-126">The `BasicHttpBinding` exposes the `TransferMode` property on the binding, as does `NetTcpBinding` and `NetNamedPipeBinding`.</span></span> <span data-ttu-id="a93b4-127">还可以在传输绑定元素上设置 `TransferMode` 属性，并且在自定义绑定中使用。</span><span class="sxs-lookup"><span data-stu-id="a93b4-127">The `TransferMode` property can also be set on the transport binding element and used in a custom binding.</span></span>  
  
     <span data-ttu-id="a93b4-128">下面的示例演示如何通过代码和通过更改配置文件来设置 `TransferMode`。</span><span class="sxs-lookup"><span data-stu-id="a93b4-128">The following samples show how to set `TransferMode` by code and by changing the configuration file.</span></span> <span data-ttu-id="a93b4-129">两个示例都将 `maxReceivedMessageSize` 属性设置为 64 MB，这是可以接收的最大消息大小。</span><span class="sxs-lookup"><span data-stu-id="a93b4-129">The samples also both set the `maxReceivedMessageSize` property to 64 MB, which places a cap on the maximum allowable size of messages on receive.</span></span> <span data-ttu-id="a93b4-130">默认的 `maxReceivedMessageSize` 为 64 KB，对于流处理方案而言，此值通常太低。</span><span class="sxs-lookup"><span data-stu-id="a93b4-130">The default `maxReceivedMessageSize` is 64 KB, which is usually too low for streaming scenarios.</span></span> <span data-ttu-id="a93b4-131">根据应用程序期望接收的消息的最大大小适当地设置此配额设置。</span><span class="sxs-lookup"><span data-stu-id="a93b4-131">Set this quota setting as appropriate depending on the maximum size of messages your application expects to receive.</span></span> <span data-ttu-id="a93b4-132">还请注意，`maxBufferSize` 可控制缓冲的最大大小，应适当地进行设置。</span><span class="sxs-lookup"><span data-stu-id="a93b4-132">Also note that `maxBufferSize` controls the maximum size that is buffered, and set it appropriately.</span></span>  
  
    1.  <span data-ttu-id="a93b4-133">下面示例中的配置段演示如何将 `TransferMode` 和自定义 HTTP 绑定上的 `basicHttpBinding` 属性设置为流处理。</span><span class="sxs-lookup"><span data-stu-id="a93b4-133">The following configuration snippet from the sample shows setting the `TransferMode` property to streaming on the `basicHttpBinding` and a custom HTTP binding.</span></span>  
  
         [!code-xml[c_HowTo_EnableStreaming#103](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/common/app.config#103)]   
  
    2.  <span data-ttu-id="a93b4-134">下面的代码段演示如何将 `TransferMode` 和自定义 HTTP 绑定上的 `basicHttpBinding` 属性设置为流处理。</span><span class="sxs-lookup"><span data-stu-id="a93b4-134">The following code snippet shows setting the `TransferMode` property to streaming on the `basicHttpBinding` and a custom HTTP binding.</span></span>  
  
         [!code-csharp[c_HowTo_EnableStreaming_code#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming_code/cs/c_howto_enablestreaming_code.cs#2)]
         [!code-vb[c_HowTo_EnableStreaming_code#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming_code/vb/c_howto_enablestreaming_code.vb#2)]  
  
    3.  <span data-ttu-id="a93b4-135">下面的代码段演示如何将自定义 TCP 绑定上的 `TransferMode` 属性设置为流处理。</span><span class="sxs-lookup"><span data-stu-id="a93b4-135">The following code snippet shows setting the `TransferMode` property to streaming on a custom TCP binding.</span></span>  
  
         [!code-csharp[c_HowTo_EnableStreaming_code#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming_code/cs/c_howto_enablestreaming_code.cs#3)]
         [!code-vb[c_HowTo_EnableStreaming_code#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming_code/vb/c_howto_enablestreaming_code.vb#3)]  
  
3. <span data-ttu-id="a93b4-136">`GetStream`、`UploadStream` 和 `EchoStream` 操作都可以处理直接从文件发送数据或将接收的数据直接保存到文件的情况。</span><span class="sxs-lookup"><span data-stu-id="a93b4-136">The operations `GetStream`, `UploadStream`, and `EchoStream` all deal with sending data directly from a file or saving received data directly to a file.</span></span> <span data-ttu-id="a93b4-137">下面的代码适用于 `GetStream`。</span><span class="sxs-lookup"><span data-stu-id="a93b4-137">The following code is for `GetStream`.</span></span>  
  
     [!code-csharp[c_HowTo_EnableStreaming#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#4)]
     [!code-vb[c_HowTo_EnableStreaming#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#4)]  
  
### <a name="writing-a-custom-stream"></a><span data-ttu-id="a93b4-138">编写自定义流</span><span class="sxs-lookup"><span data-stu-id="a93b4-138">Writing a custom stream</span></span>  
  
1. <span data-ttu-id="a93b4-139">若要在发送或接收数据流的每个块区时对其进行特殊处理，可从 <xref:System.IO.Stream> 派生一个自定义流类。</span><span class="sxs-lookup"><span data-stu-id="a93b4-139">To do special processing on each chunk of a data stream as it is being sent or received, derive a custom stream class from <xref:System.IO.Stream>.</span></span> <span data-ttu-id="a93b4-140">与自定义流的示例一样，下面的代码包含 `GetReversedStream` 方法和 `ReverseStream` 类。</span><span class="sxs-lookup"><span data-stu-id="a93b4-140">As an example of a custom stream, the following code contains a `GetReversedStream` method and a `ReverseStream` class-.</span></span>  
  
     `GetReversedStream` <span data-ttu-id="a93b4-141">创建并返回的新实例`ReverseStream`。</span><span class="sxs-lookup"><span data-stu-id="a93b4-141">creates and returns a new instance of `ReverseStream`.</span></span> <span data-ttu-id="a93b4-142">当系统从 `ReverseStream` 对象中读取时，发生实际处理。</span><span class="sxs-lookup"><span data-stu-id="a93b4-142">The actual processing happens as the system reads from the `ReverseStream` object.</span></span> <span data-ttu-id="a93b4-143">`ReverseStream.Read` 方法从基础文件中读取字节块区，反转字节，然后返回反转的字节。</span><span class="sxs-lookup"><span data-stu-id="a93b4-143">The `ReverseStream.Read` method reads a chunk of bytes from the underlying file, reverses them, then returns the reversed bytes.</span></span> <span data-ttu-id="a93b4-144">此方法不会反转整个文件内容；一次只能反转一个字节块区。</span><span class="sxs-lookup"><span data-stu-id="a93b4-144">This method does not reverse the entire file content; it reverses one chunk of bytes at a time.</span></span> <span data-ttu-id="a93b4-145">本示例演示在从流中读取内容或将内容写入到流中时如何执行流处理。</span><span class="sxs-lookup"><span data-stu-id="a93b4-145">This example shows how you can perform stream processing as the content is being read to or written from the stream.</span></span>  
  
     [!code-csharp[c_HowTo_EnableStreaming#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_enablestreaming/cs/service.cs#2)]
     [!code-vb[c_HowTo_EnableStreaming#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_enablestreaming/vb/service.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a93b4-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="a93b4-146">See also</span></span>

- [<span data-ttu-id="a93b4-147">大型数据和流</span><span class="sxs-lookup"><span data-stu-id="a93b4-147">Large Data and Streaming</span></span>](../../../../docs/framework/wcf/feature-details/large-data-and-streaming.md)
- [<span data-ttu-id="a93b4-148">流</span><span class="sxs-lookup"><span data-stu-id="a93b4-148">Stream</span></span>](../../../../docs/framework/wcf/samples/stream.md)
