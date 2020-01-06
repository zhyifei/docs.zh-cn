---
title: 流式处理服务与重复字段-gRPC for WCF 开发人员
description: 将重复字段比较流式处理服务，作为通过 gRPC 传递数据集合的方式。
ms.date: 09/02/2019
ms.openlocfilehash: 46586ab08df6b136cdafb990ce8be75435a6bf6c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75337871"
---
# <a name="grpc-streaming-services-versus-repeated-fields"></a><span data-ttu-id="fc20a-103">gRPC 流式处理服务与重复字段</span><span class="sxs-lookup"><span data-stu-id="fc20a-103">gRPC streaming services versus repeated fields</span></span>

<span data-ttu-id="fc20a-104">gRPC services 提供两种方法来返回数据集或对象的列表。</span><span class="sxs-lookup"><span data-stu-id="fc20a-104">gRPC services provide two ways of returning datasets, or lists of objects.</span></span> <span data-ttu-id="fc20a-105">协议缓冲区消息规范使用 `repeated` 关键字来声明另一消息内的列表或消息的数组。</span><span class="sxs-lookup"><span data-stu-id="fc20a-105">The Protocol Buffers message specification uses the `repeated` keyword for declaring lists or arrays of messages within another message.</span></span> <span data-ttu-id="fc20a-106">GRPC service 规范使用 `stream` 关键字声明一个长时间运行的持久连接，其中发送多条消息，并可单独处理。</span><span class="sxs-lookup"><span data-stu-id="fc20a-106">The gRPC service specification uses the `stream` keyword to declare a long-running persistent connection over which multiple messages are sent, and can be processed, individually.</span></span> <span data-ttu-id="fc20a-107">`stream` 功能还可用于长时间运行的临时数据（如通知或日志消息），但本章会将其用于返回单个数据集。</span><span class="sxs-lookup"><span data-stu-id="fc20a-107">The `stream` feature can also be used for long-running temporal data such as notifications or log messages, but this chapter will consider its use for returning a single dataset.</span></span>

<span data-ttu-id="fc20a-108">使用哪种方法取决于各种因素，例如数据集的总体大小、在客户端或服务器端创建数据集所用的时间，以及在第一项可用时数据集的使用者是否可以开始操作，或需要完整的数据集来执行任何有用的操作。</span><span class="sxs-lookup"><span data-stu-id="fc20a-108">Which you should use depends on various factors, such as the overall size of the dataset, the time it took to create the dataset at either the client or server end, and whether the consumer of the dataset can start acting on it as soon as the first item is available, or needs the complete dataset to do anything useful.</span></span>

## <a name="when-to-use-repeated-fields"></a><span data-ttu-id="fc20a-109">何时使用 `repeated` 字段</span><span class="sxs-lookup"><span data-stu-id="fc20a-109">When to use `repeated` fields</span></span>

<span data-ttu-id="fc20a-110">对于任何大小都受限制并且可以在短时间内完全生成的数据集（例如，在一秒钟内），你应在常规 Protobuf 消息中使用 `repeated` 字段。</span><span class="sxs-lookup"><span data-stu-id="fc20a-110">For any dataset that is constrained in size and that can be generated in its entirety in a short time—say, under one second—you should use a `repeated` field in a regular Protobuf message.</span></span> <span data-ttu-id="fc20a-111">例如，在电子商务系统中，若要在订单内生成项列表，可能会很快，并且列表将不会太大。</span><span class="sxs-lookup"><span data-stu-id="fc20a-111">For example, in an e-commerce system, to build a list of items within an order is probably quick and the list won't be very large.</span></span> <span data-ttu-id="fc20a-112">使用 `repeated` 字段返回一条消息比使用 `stream` 更快，导致网络开销更少。</span><span class="sxs-lookup"><span data-stu-id="fc20a-112">Returning a single message with a `repeated` field is an order of magnitude faster than using a `stream` and incurs less network overhead.</span></span>

<span data-ttu-id="fc20a-113">如果客户端在开始处理数据之前需要所有数据，并且数据集足够小，可以在内存中构造，则即使服务器内存中实际创建的数据集速度较慢，也应考虑使用 `repeated` 字段。</span><span class="sxs-lookup"><span data-stu-id="fc20a-113">If the client needs all the data before starting to process it and the dataset is small enough to construct in memory, then consider using a `repeated` field even if the actual creation of the dataset in memory on the server is slower.</span></span>

## <a name="when-to-use-stream-methods"></a><span data-ttu-id="fc20a-114">何时使用 `stream` 方法</span><span class="sxs-lookup"><span data-stu-id="fc20a-114">When to use `stream` methods</span></span>

<span data-ttu-id="fc20a-115">使用流式处理请求或响应最好地传输消息对象很大的数据集。</span><span class="sxs-lookup"><span data-stu-id="fc20a-115">Datasets where the message objects are potentially very large are best transferred using streaming requests or responses.</span></span> <span data-ttu-id="fc20a-116">在内存中构造大型对象、将其写入网络，然后释放资源更有效。</span><span class="sxs-lookup"><span data-stu-id="fc20a-116">It's more efficient to construct a large object in memory, write it to the network and then free up the resources.</span></span> <span data-ttu-id="fc20a-117">此方法可提高服务的可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="fc20a-117">This approach will improve the scalability of your service.</span></span>

<span data-ttu-id="fc20a-118">同样，不约束大小的数据集应通过流发送，以避免在构造这些数据时内存不足。</span><span class="sxs-lookup"><span data-stu-id="fc20a-118">Similarly, datasets of unconstrained size should be sent over streams to avoid running out of memory while constructing them.</span></span>

<span data-ttu-id="fc20a-119">对于每个单独项可由使用者单独处理的数据集，如果它表示可以向最终用户指示进度，则应考虑使用流。</span><span class="sxs-lookup"><span data-stu-id="fc20a-119">For datasets where each individual item can be processed separately by the consumer, you should consider using a stream if it means that progress can be indicated to the end user.</span></span> <span data-ttu-id="fc20a-120">这可以提高应用程序的明显响应能力，尽管这应该与应用程序的总体性能进行平衡。</span><span class="sxs-lookup"><span data-stu-id="fc20a-120">This could improve the apparent responsiveness of an application, although this should be balanced against the overall performance of the application.</span></span>

<span data-ttu-id="fc20a-121">流可能很有用的另一种情况是跨多个服务对消息进行处理。</span><span class="sxs-lookup"><span data-stu-id="fc20a-121">Another scenario where streams can be useful is where a message is being processed across multiple services.</span></span> <span data-ttu-id="fc20a-122">如果链中的每个服务都返回一个流，则终端服务（即该链中的最后一个服务）可以开始返回消息，这些消息可通过链进行处理并传递回原始请求者，后者可以返回流或聚合生成单个响应消息。</span><span class="sxs-lookup"><span data-stu-id="fc20a-122">If each service in a chain returns a stream, then the terminal service (that is, the last one in the chain) can start returning messages that can be processed and passed back along the chain to the original requestor, which can either return a stream or aggregate the results into a single response message.</span></span> <span data-ttu-id="fc20a-123">此方法非常适合映射/减少等模式。</span><span class="sxs-lookup"><span data-stu-id="fc20a-123">This approach lends itself well to patterns like Map/Reduce.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fc20a-124">[上一页](migrate-duplex-services.md)
>[下一页](client-libraries.md)</span><span class="sxs-lookup"><span data-stu-id="fc20a-124">[Previous](migrate-duplex-services.md)
[Next](client-libraries.md)</span></span>
