---
title: 协议缓冲区 - 适用于 WCF 开发人员的 gRPC
description: 用于 gRPC 网络的协议缓冲区线格式简介。
ms.date: 09/09/2019
ms.openlocfilehash: 35319d299a8bc2866a87954b3e54bfda9314ffe8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147927"
---
# <a name="protocol-buffers"></a><span data-ttu-id="c6df5-103">协议缓冲区</span><span class="sxs-lookup"><span data-stu-id="c6df5-103">Protocol buffers</span></span>

<span data-ttu-id="c6df5-104">gRPC 服务以*协议缓冲区 （Protobuf） 消息*发送和接收数据，类似于 Windows 通信基础 （WCF） 中的数据协定。</span><span class="sxs-lookup"><span data-stu-id="c6df5-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to data contracts in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="c6df5-105">Protobuf 是一种用于计算机读取和写入的结构化数据序列化的有效方法，无需产生 XML 或 JSON 等人类可读格式的开销。</span><span class="sxs-lookup"><span data-stu-id="c6df5-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="c6df5-106">本章介绍 Protobuf 的工作原理，以及如何定义您自己的 Protobuf 消息。</span><span class="sxs-lookup"><span data-stu-id="c6df5-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="c6df5-107">普罗托布夫的工作原理</span><span class="sxs-lookup"><span data-stu-id="c6df5-107">How Protobuf works</span></span>

<span data-ttu-id="c6df5-108">大多数 .NET 对象序列化技术（包括 WCF 的数据协定）都使用反射来分析运行时的对象结构。</span><span class="sxs-lookup"><span data-stu-id="c6df5-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at runtime.</span></span> <span data-ttu-id="c6df5-109">相比之下，大多数 Protobuf 库要求您在`.proto`文件中使用专用语言（*协议缓冲区语言*）来预先定义结构。</span><span class="sxs-lookup"><span data-stu-id="c6df5-109">By contrast, most Protobuf libraries require you to define the structure up front by using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="c6df5-110">然后，编译器使用此文件为任何受支持的平台生成代码。</span><span class="sxs-lookup"><span data-stu-id="c6df5-110">A compiler then uses this file to generate code for any of the supported platforms.</span></span> <span data-ttu-id="c6df5-111">支持的平台包括 .NET、Java、C/C++、JavaScript 等。</span><span class="sxs-lookup"><span data-stu-id="c6df5-111">Supported platforms include .NET, Java, C/C++, JavaScript, and many more.</span></span>

<span data-ttu-id="c6df5-112">Protobuf 编译器`protoc`（） 由 Google 维护，尽管有替代实现可用。</span><span class="sxs-lookup"><span data-stu-id="c6df5-112">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="c6df5-113">生成的代码高效且优化，可快速序列化和数据反序列化。</span><span class="sxs-lookup"><span data-stu-id="c6df5-113">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="c6df5-114">Protobuf 线格式是二进制编码。</span><span class="sxs-lookup"><span data-stu-id="c6df5-114">The Protobuf wire format is a binary encoding.</span></span> <span data-ttu-id="c6df5-115">它使用一些巧妙的技巧来最小化用于表示消息的字节数。</span><span class="sxs-lookup"><span data-stu-id="c6df5-115">It uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="c6df5-116">使用 Protobuf 不需要了解二进制编码格式。</span><span class="sxs-lookup"><span data-stu-id="c6df5-116">Knowledge of the binary encoding format isn't necessary to use Protobuf.</span></span> <span data-ttu-id="c6df5-117">但是，如果你有兴趣，你可以了解更多关于它[的协议缓冲区网站](https://developers.google.com/protocol-buffers/docs/encoding)。</span><span class="sxs-lookup"><span data-stu-id="c6df5-117">But if you're interested, you can learn more about it on [the Protocol Buffers website](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c6df5-118">[上一个](why-grpc.md)
>[下一个](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="c6df5-118">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
