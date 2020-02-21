---
title: 流式处理服务与重复字段-gRPC for WCF 开发人员
description: 将重复字段比较流式处理服务，作为通过使用 gRPC 传递数据集合的方式。
ms.date: 09/02/2019
ms.openlocfilehash: 0e717df57ba2bb52d63a063072d8a45bf0f7e395
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503371"
---
# <a name="grpc-streaming-services-vs-repeated-fields"></a><span data-ttu-id="6485a-103">gRPC 流式处理服务与重复字段</span><span class="sxs-lookup"><span data-stu-id="6485a-103">gRPC streaming services vs. repeated fields</span></span>

<span data-ttu-id="6485a-104">gRPC services 提供两种方法来返回数据集或对象的列表。</span><span class="sxs-lookup"><span data-stu-id="6485a-104">gRPC services provide two ways of returning datasets, or lists of objects.</span></span> <span data-ttu-id="6485a-105">协议缓冲区消息规范使用 `repeated` 关键字来声明另一消息内的列表或消息的数组。</span><span class="sxs-lookup"><span data-stu-id="6485a-105">The Protocol Buffers message specification uses the `repeated` keyword for declaring lists or arrays of messages within another message.</span></span> <span data-ttu-id="6485a-106">GRPC service 规范使用 `stream` 关键字声明长时间运行的永久性连接。</span><span class="sxs-lookup"><span data-stu-id="6485a-106">The gRPC service specification uses the `stream` keyword to declare a long-running persistent connection.</span></span> <span data-ttu-id="6485a-107">在该连接上，将发送多条消息，并可单独处理。</span><span class="sxs-lookup"><span data-stu-id="6485a-107">Over that connection, multiple messages are sent, and can be processed, individually.</span></span> 

<span data-ttu-id="6485a-108">你还可以使用 `stream` 功能来执行长时间运行的临时数据，如通知或日志消息。</span><span class="sxs-lookup"><span data-stu-id="6485a-108">You can also use the `stream` feature for long-running temporal data such as notifications or log messages.</span></span> <span data-ttu-id="6485a-109">但本章会将其用于返回单个数据集。</span><span class="sxs-lookup"><span data-stu-id="6485a-109">But this chapter will consider its use for returning a single dataset.</span></span>

<span data-ttu-id="6485a-110">使用哪种方式取决于以下因素：</span><span class="sxs-lookup"><span data-stu-id="6485a-110">Which you should use depends on factors such as:</span></span>

- <span data-ttu-id="6485a-111">数据集的总体大小。</span><span class="sxs-lookup"><span data-stu-id="6485a-111">The overall size of the dataset.</span></span>
- <span data-ttu-id="6485a-112">在客户端或服务器端创建数据集所用的时间。</span><span class="sxs-lookup"><span data-stu-id="6485a-112">The time it took to create the dataset at either the client or server end.</span></span>
- <span data-ttu-id="6485a-113">数据集的使用者是否可以在第一项可用时立即开始处理它，或者需要完整的数据集来执行任何有用的操作。</span><span class="sxs-lookup"><span data-stu-id="6485a-113">Whether the consumer of the dataset can start acting on it as soon as the first item is available, or needs the complete dataset to do anything useful.</span></span>

## <a name="when-to-use-repeated-fields"></a><span data-ttu-id="6485a-114">何时使用 `repeated` 字段</span><span class="sxs-lookup"><span data-stu-id="6485a-114">When to use `repeated` fields</span></span>

<span data-ttu-id="6485a-115">对于任何大小受限制并且可以在短时间内完全生成的数据集（例如，在一秒钟内），你应在常规 Protobuf 消息中使用 `repeated` 字段。</span><span class="sxs-lookup"><span data-stu-id="6485a-115">For any dataset that's constrained in size and that can be generated in its entirety in a short time—say, under one second—you should use a `repeated` field in a regular Protobuf message.</span></span> <span data-ttu-id="6485a-116">例如，在电子商务系统中，若要在订单内生成项列表，可能会很快，并且列表将不会太大。</span><span class="sxs-lookup"><span data-stu-id="6485a-116">For example, in an e-commerce system, to build a list of items within an order is probably quick and the list won't be very large.</span></span> <span data-ttu-id="6485a-117">使用 `repeated` 字段返回一条消息比使用 `stream` 更快，导致网络开销降低。</span><span class="sxs-lookup"><span data-stu-id="6485a-117">Returning a single message with a `repeated` field is an order of magnitude faster than using `stream` and incurs less network overhead.</span></span>

<span data-ttu-id="6485a-118">如果客户端在开始处理之前需要所有数据，并且数据集足够小，可以在内存中构造，则考虑使用 `repeated` 字段。</span><span class="sxs-lookup"><span data-stu-id="6485a-118">If the client needs all the data before starting to process it and the dataset is small enough to construct in memory, then consider using a `repeated` field.</span></span> <span data-ttu-id="6485a-119">即使在服务器内存中创建数据集的速度较慢，也应考虑此情况。</span><span class="sxs-lookup"><span data-stu-id="6485a-119">Consider it even if the creation of the dataset in memory on the server is slower.</span></span>

## <a name="when-to-use-stream-methods"></a><span data-ttu-id="6485a-120">何时使用 `stream` 方法</span><span class="sxs-lookup"><span data-stu-id="6485a-120">When to use `stream` methods</span></span>

<span data-ttu-id="6485a-121">当数据集中的消息对象可能非常大时，最好是使用流式处理请求或响应传输这些对象。</span><span class="sxs-lookup"><span data-stu-id="6485a-121">When the message objects in your datasets are potentially very large, it's best for you transfer them by using streaming requests or responses.</span></span> <span data-ttu-id="6485a-122">在内存中构造大型对象、将其写入网络，然后释放资源更有效。</span><span class="sxs-lookup"><span data-stu-id="6485a-122">It's more efficient to construct a large object in memory, write it to the network, and then free up the resources.</span></span> <span data-ttu-id="6485a-123">此方法可提高服务的可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="6485a-123">This approach will improve the scalability of your service.</span></span>

<span data-ttu-id="6485a-124">同样，你应该在流上发送无限制大小的数据集，以避免在构造这些数据时内存不足。</span><span class="sxs-lookup"><span data-stu-id="6485a-124">Similarly, you should send datasets of unconstrained size over streams to avoid running out of memory while constructing them.</span></span>

<span data-ttu-id="6485a-125">对于使用者可单独处理每个项的数据集，如果它表示可以向用户指示进度，则应考虑使用流。</span><span class="sxs-lookup"><span data-stu-id="6485a-125">For datasets where the consumer can separately process each item, you should consider using a stream if it means that progress can be indicated to the user.</span></span> <span data-ttu-id="6485a-126">使用流可以提高应用程序的响应能力，但应将其与应用程序的总体性能进行平衡。</span><span class="sxs-lookup"><span data-stu-id="6485a-126">Using a stream can improve the responsiveness of an application, but you should balance it against the overall performance of the application.</span></span>

<span data-ttu-id="6485a-127">流可能很有用的另一种情况是跨多个服务对消息进行处理。</span><span class="sxs-lookup"><span data-stu-id="6485a-127">Another scenario where streams can be useful is where a message is being processed across multiple services.</span></span> <span data-ttu-id="6485a-128">如果链中的每个服务都返回一个流，则终端服务（即该链中的最后一个服务）可以开始返回消息。</span><span class="sxs-lookup"><span data-stu-id="6485a-128">If each service in a chain returns a stream, then the terminal service (that is, the last one in the chain) can start returning messages.</span></span> <span data-ttu-id="6485a-129">可以处理这些消息并将其传递回原始请求者。</span><span class="sxs-lookup"><span data-stu-id="6485a-129">These messages can be processed and passed back along the chain to the original requestor.</span></span> <span data-ttu-id="6485a-130">请求者可以返回流，或将结果聚合到单个响应消息中。</span><span class="sxs-lookup"><span data-stu-id="6485a-130">The requestor can either return a stream or aggregate the results into a single response message.</span></span> <span data-ttu-id="6485a-131">此方法非常适合于 MapReduce 等模式。</span><span class="sxs-lookup"><span data-stu-id="6485a-131">This approach lends itself well to patterns like MapReduce.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6485a-132">[上一页](migrate-duplex-services.md)
>[下一页](client-libraries.md)</span><span class="sxs-lookup"><span data-stu-id="6485a-132">[Previous](migrate-duplex-services.md)
[Next](client-libraries.md)</span></span>
