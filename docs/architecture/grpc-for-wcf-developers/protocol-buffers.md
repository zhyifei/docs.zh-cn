---
title: 协议缓冲区-适用于 WCF 开发人员的 gRPC
description: 用于 gRPC 网络的协议缓冲区网络格式简介。
ms.date: 09/09/2019
ms.openlocfilehash: cc4ff272a9912d6f2dd8f8ddb1972c7369f980fe
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503453"
---
# <a name="protocol-buffers"></a><span data-ttu-id="4bc32-103">协议缓冲区</span><span class="sxs-lookup"><span data-stu-id="4bc32-103">Protocol buffers</span></span>

<span data-ttu-id="4bc32-104">gRPC services 以*协议缓冲区（Protobuf）消息*的形式发送和接收数据，类似于 WINDOWS COMMUNICATION FOUNDATION （WCF）中的数据约定。</span><span class="sxs-lookup"><span data-stu-id="4bc32-104">gRPC services send and receive data as *Protocol Buffer (Protobuf) messages*, similar to data contracts in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="4bc32-105">Protobuf 是一种将结构化数据序列化到计算机以进行读取和写入的有效方法，不会产生诸如 XML 或 JSON 之类的用户可读格式产生的开销。</span><span class="sxs-lookup"><span data-stu-id="4bc32-105">Protobuf is an efficient way of serializing structured data for machines to read and write, without the overhead that human-readable formats like XML or JSON incur.</span></span>

<span data-ttu-id="4bc32-106">本章介绍了 Protobuf 的工作原理，以及如何定义你自己的 Protobuf 消息。</span><span class="sxs-lookup"><span data-stu-id="4bc32-106">This chapter covers how Protobuf works, and how to define your own Protobuf messages.</span></span>

## <a name="how-protobuf-works"></a><span data-ttu-id="4bc32-107">Protobuf 的工作原理</span><span class="sxs-lookup"><span data-stu-id="4bc32-107">How Protobuf works</span></span>

<span data-ttu-id="4bc32-108">大多数 .NET 对象序列化技术（包括 WCF 的数据协定）都可以通过使用反射在运行时分析对象结构。</span><span class="sxs-lookup"><span data-stu-id="4bc32-108">Most .NET object serialization techniques, including WCF's data contracts, work by using reflection to analyze the object structure at runtime.</span></span> <span data-ttu-id="4bc32-109">与此相反，大多数 Protobuf 库都要求您在 `.proto` 文件中使用专用语言（*协议缓冲区语言*）预先定义结构。</span><span class="sxs-lookup"><span data-stu-id="4bc32-109">By contrast, most Protobuf libraries require you to define the structure up front by using a dedicated language (*Protocol Buffer Language*) in a `.proto` file.</span></span> <span data-ttu-id="4bc32-110">然后，编译器使用此文件为任何支持的平台生成代码。</span><span class="sxs-lookup"><span data-stu-id="4bc32-110">A compiler then uses this file to generate code for any of the supported platforms.</span></span> <span data-ttu-id="4bc32-111">支持的平台包括 .NET、Java、CC++/、JavaScript 等。</span><span class="sxs-lookup"><span data-stu-id="4bc32-111">Supported platforms include .NET, Java, C/C++, JavaScript, and many more.</span></span> 

<span data-ttu-id="4bc32-112">Protobuf 编译器（`protoc`）由 Google 维护，但其他实现可用。</span><span class="sxs-lookup"><span data-stu-id="4bc32-112">The Protobuf compiler, `protoc`, is maintained by Google, although alternative implementations are available.</span></span> <span data-ttu-id="4bc32-113">生成的代码是高效的并且经过优化，可快速序列化和反序列化数据。</span><span class="sxs-lookup"><span data-stu-id="4bc32-113">The generated code is efficient and optimized for fast serialization and deserialization of data.</span></span>

<span data-ttu-id="4bc32-114">Protobuf 网络格式为二进制编码。</span><span class="sxs-lookup"><span data-stu-id="4bc32-114">The Protobuf wire format is a binary encoding.</span></span> <span data-ttu-id="4bc32-115">它使用一些巧妙的技巧来最大程度地减少用于表示消息的字节数。</span><span class="sxs-lookup"><span data-stu-id="4bc32-115">It uses some clever tricks to minimize the number of bytes used to represent messages.</span></span> <span data-ttu-id="4bc32-116">不需要使用 Protobuf 的二进制编码格式知识。</span><span class="sxs-lookup"><span data-stu-id="4bc32-116">Knowledge of the binary encoding format isn't necessary to use Protobuf.</span></span> <span data-ttu-id="4bc32-117">但是，如果您感兴趣，可以在[协议缓冲区网站](https://developers.google.com/protocol-buffers/docs/encoding)上了解有关它的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4bc32-117">But if you're interested, you can learn more about it on [the Protocol Buffers website](https://developers.google.com/protocol-buffers/docs/encoding).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4bc32-118">[上一页](why-grpc.md)
>[下一页](protobuf-messages.md)</span><span class="sxs-lookup"><span data-stu-id="4bc32-118">[Previous](why-grpc.md)
[Next](protobuf-messages.md)</span></span>
