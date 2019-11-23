---
title: 协议缓冲区-适用于 WCF 开发人员的 gRPC
description: 用于 gRPC 网络的协议缓冲区网络格式简介。
ms.date: 09/09/2019
ms.openlocfilehash: dbe8cb43475cfeec19051daf68452ef86269372f
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967293"
---
# <a name="protocol-buffers"></a><span data-ttu-id="b2e5a-103">协议缓冲区</span><span class="sxs-lookup"><span data-stu-id="b2e5a-103">Protocol buffers</span></span>

<span data-ttu-id="b2e5a-104">gRPC services 以*协议缓冲区（Protobuf）消息*的形式发送和接收数据，类似于 WCF 的数据协定。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to WCF's data contracts.</span></span> <span data-ttu-id="b2e5a-105">Protobuf 是一种将结构化数据序列化到计算机以进行读取和写入的有效方法，不会产生诸如 XML 或 JSON 之类的用户可读格式产生的开销。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="b2e5a-106">本章介绍了 Protobuf 的工作原理，以及如何定义你自己的 Protobuf 消息。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="b2e5a-107">Protobuf 的工作原理</span><span class="sxs-lookup"><span data-stu-id="b2e5a-107">How Protobuf works</span></span>

<span data-ttu-id="b2e5a-108">大多数 .NET 对象序列化技术（包括 WCF 的数据协定）通过使用反射在运行时分析对象结构。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at run time.</span></span> <span data-ttu-id="b2e5a-109">与此相反，大多数 Protobuf 库要求在 `.proto` 文件中使用专用语言（*协议缓冲区语言*）预先定义结构。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-109">By contrast, most Protobuf libraries require you to define the structure up front using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="b2e5a-110">编译器将使用此文件为任何支持的平台（包括 .NET、Java、C/C++、JavaScript 等）生成代码。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-110">This file is then used by a compiler to generate code for any of the supported platforms, including .NET, Java, C/C++, JavaScript, and many more.</span></span> <span data-ttu-id="b2e5a-111">Protobuf 编译器（`protoc`）由 Google 维护，但其他实现可用。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-111">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="b2e5a-112">生成的代码是高效的并且经过优化，可快速序列化和反序列化数据。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-112">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="b2e5a-113">Protobuf 连网格式本身是二进制编码，使用一些巧妙的技巧来最大程度地减少用于表示消息的字节数。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-113">The Protobuf wire format itself is a binary encoding, which uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="b2e5a-114">不需要对二进制编码格式的了解使用 Protobuf，但如果您感兴趣，可以在[协议缓冲区网站](https://developers.google.com/protocol-buffers/docs/encoding)上了解有关该格式的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2e5a-114">Knowledge of the binary encoding format isn't necessary to use Protobuf, but if you're interested you can learn more about it on [the Protocol Buffers web site](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="b2e5a-115">[上一页](why-grpc.md)
>[下一页](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="b2e5a-115">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
