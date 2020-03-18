---
title: 流服务与重复字段 - gRPC 面向 WCF 开发人员
description: 将重复字段与流服务进行比较，作为使用 gRPC 传递数据集合的方法。
ms.date: 09/02/2019
ms.openlocfilehash: 542ebc393f9c9c1ad717d02d01fab33d85c18917
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147745"
---
# <a name="grpc-streaming-services-vs-repeated-fields"></a><span data-ttu-id="8f79b-103">gRPC 流式处理服务与重复字段</span><span class="sxs-lookup"><span data-stu-id="8f79b-103">gRPC streaming services vs. repeated fields</span></span>

<span data-ttu-id="8f79b-104">gRPC 服务提供两种返回数据集或对象列表的方法。</span><span class="sxs-lookup"><span data-stu-id="8f79b-104">gRPC services provide two ways of returning datasets, or lists of objects.</span></span> <span data-ttu-id="8f79b-105">协议缓冲区消息规范使用 关键字`repeated`声明另一消息中的消息列表或数组。</span><span class="sxs-lookup"><span data-stu-id="8f79b-105">The Protocol Buffers message specification uses the `repeated` keyword for declaring lists or arrays of messages within another message.</span></span> <span data-ttu-id="8f79b-106">gRPC 服务规范使用`stream`关键字声明长时间运行的持久连接。</span><span class="sxs-lookup"><span data-stu-id="8f79b-106">The gRPC service specification uses the `stream` keyword to declare a long-running persistent connection.</span></span> <span data-ttu-id="8f79b-107">通过该连接，将发送多条消息，并可以单独处理。</span><span class="sxs-lookup"><span data-stu-id="8f79b-107">Over that connection, multiple messages are sent, and can be processed, individually.</span></span>

<span data-ttu-id="8f79b-108">您还可以使用该`stream`功能对长时间运行的时间数据（如通知或日志消息）使用。</span><span class="sxs-lookup"><span data-stu-id="8f79b-108">You can also use the `stream` feature for long-running temporal data such as notifications or log messages.</span></span> <span data-ttu-id="8f79b-109">但本章将考虑用于返回单个数据集。</span><span class="sxs-lookup"><span data-stu-id="8f79b-109">But this chapter will consider its use for returning a single dataset.</span></span>

<span data-ttu-id="8f79b-110">您应该使用哪些取决于如下因素：</span><span class="sxs-lookup"><span data-stu-id="8f79b-110">Which you should use depends on factors such as:</span></span>

- <span data-ttu-id="8f79b-111">数据集的总体大小。</span><span class="sxs-lookup"><span data-stu-id="8f79b-111">The overall size of the dataset.</span></span>
- <span data-ttu-id="8f79b-112">在客户端或服务器端创建数据集所花的时间。</span><span class="sxs-lookup"><span data-stu-id="8f79b-112">The time it took to create the dataset at either the client or server end.</span></span>
- <span data-ttu-id="8f79b-113">数据集的使用者是否可以在第一个项目可用时立即开始对它进行操作，或者需要完整的数据集执行任何有用的操作。</span><span class="sxs-lookup"><span data-stu-id="8f79b-113">Whether the consumer of the dataset can start acting on it as soon as the first item is available, or needs the complete dataset to do anything useful.</span></span>

## <a name="when-to-use-repeated-fields"></a><span data-ttu-id="8f79b-114">何时使用`repeated`字段</span><span class="sxs-lookup"><span data-stu-id="8f79b-114">When to use `repeated` fields</span></span>

<span data-ttu-id="8f79b-115">对于大小受限且可以在短时间内生成完整数据集的任何数据集（例如，在一秒以下），应在常规 Protobuf 消息中使用`repeated`字段。</span><span class="sxs-lookup"><span data-stu-id="8f79b-115">For any dataset that's constrained in size and that can be generated in its entirety in a short time—say, under one second—you should use a `repeated` field in a regular Protobuf message.</span></span> <span data-ttu-id="8f79b-116">例如，在电子商务系统中，在订单中生成项目列表可能很快，并且列表不会很大。</span><span class="sxs-lookup"><span data-stu-id="8f79b-116">For example, in an e-commerce system, to build a list of items within an order is probably quick and the list won't be very large.</span></span> <span data-ttu-id="8f79b-117">使用`repeated`字段返回单个消息比使用`stream`快一个数量级，并且产生的网络开销更少。</span><span class="sxs-lookup"><span data-stu-id="8f79b-117">Returning a single message with a `repeated` field is an order of magnitude faster than using `stream` and incurs less network overhead.</span></span>

<span data-ttu-id="8f79b-118">如果客户端在开始处理之前需要所有数据，并且数据集足够小，足以在内存中构造，则请考虑使用字段`repeated`。</span><span class="sxs-lookup"><span data-stu-id="8f79b-118">If the client needs all the data before starting to process it and the dataset is small enough to construct in memory, then consider using a `repeated` field.</span></span> <span data-ttu-id="8f79b-119">即使服务器上的内存中数据集的创建速度较慢，也请考虑它。</span><span class="sxs-lookup"><span data-stu-id="8f79b-119">Consider it even if the creation of the dataset in memory on the server is slower.</span></span>

## <a name="when-to-use-stream-methods"></a><span data-ttu-id="8f79b-120">何时使用`stream`方法</span><span class="sxs-lookup"><span data-stu-id="8f79b-120">When to use `stream` methods</span></span>

<span data-ttu-id="8f79b-121">当数据集中的消息对象可能非常大时，最好使用流式处理请求或响应来传输它们。</span><span class="sxs-lookup"><span data-stu-id="8f79b-121">When the message objects in your datasets are potentially very large, it's best for you transfer them by using streaming requests or responses.</span></span> <span data-ttu-id="8f79b-122">在内存中构造大型对象、将其写入网络，然后释放资源会更有效。</span><span class="sxs-lookup"><span data-stu-id="8f79b-122">It's more efficient to construct a large object in memory, write it to the network, and then free up the resources.</span></span> <span data-ttu-id="8f79b-123">此方法将提高服务的可扩展性。</span><span class="sxs-lookup"><span data-stu-id="8f79b-123">This approach will improve the scalability of your service.</span></span>

<span data-ttu-id="8f79b-124">同样，您应该在流上发送无约束大小的数据集，以避免在构造时内存不足。</span><span class="sxs-lookup"><span data-stu-id="8f79b-124">Similarly, you should send datasets of unconstrained size over streams to avoid running out of memory while constructing them.</span></span>

<span data-ttu-id="8f79b-125">对于使用者可以单独处理每个项目的数据集，如果意味着可以向用户指示进度，则应考虑使用流。</span><span class="sxs-lookup"><span data-stu-id="8f79b-125">For datasets where the consumer can separately process each item, you should consider using a stream if it means that progress can be indicated to the user.</span></span> <span data-ttu-id="8f79b-126">使用流可以提高应用程序的响应能力，但应平衡它与应用程序的整体性能。</span><span class="sxs-lookup"><span data-stu-id="8f79b-126">Using a stream can improve the responsiveness of an application, but you should balance it against the overall performance of the application.</span></span>

<span data-ttu-id="8f79b-127">流可能有用的另一个方案是跨多个服务处理消息。</span><span class="sxs-lookup"><span data-stu-id="8f79b-127">Another scenario where streams can be useful is where a message is being processed across multiple services.</span></span> <span data-ttu-id="8f79b-128">如果链中的每个服务返回一个流，则终端服务（即链中的最后一个服务）可以开始返回消息。</span><span class="sxs-lookup"><span data-stu-id="8f79b-128">If each service in a chain returns a stream, then the terminal service (that is, the last one in the chain) can start returning messages.</span></span> <span data-ttu-id="8f79b-129">这些消息可以处理，并沿链传回原始请求者。</span><span class="sxs-lookup"><span data-stu-id="8f79b-129">These messages can be processed and passed back along the chain to the original requestor.</span></span> <span data-ttu-id="8f79b-130">请求者可以返回流或将结果聚合到单个响应消息中。</span><span class="sxs-lookup"><span data-stu-id="8f79b-130">The requestor can either return a stream or aggregate the results into a single response message.</span></span> <span data-ttu-id="8f79b-131">此方法非常适合像 MapReduce 这样的模式。</span><span class="sxs-lookup"><span data-stu-id="8f79b-131">This approach lends itself well to patterns like MapReduce.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8f79b-132">[上一个](migrate-duplex-services.md)
>[下一个](client-libraries.md)</span><span class="sxs-lookup"><span data-stu-id="8f79b-132">[Previous](migrate-duplex-services.md)
[Next](client-libraries.md)</span></span>
