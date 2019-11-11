---
title: Interface 定义 Language-适用于 WCF 开发人员的 gRPC
description: 引入协议缓冲区 IDL。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 00c73619c5c27003e200385d5f67d8b8b7546f9e
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841563"
---
# <a name="interface-definition-language"></a><span data-ttu-id="eb244-103">接口定义语言</span><span class="sxs-lookup"><span data-stu-id="eb244-103">Interface Definition Language</span></span>

<span data-ttu-id="eb244-104">使用 WCF，服务可以使用 Web 服务定义语言（WSDL）（在运行时使用 .NET 反射动态生成）公开说明元数据。</span><span class="sxs-lookup"><span data-stu-id="eb244-104">With WCF, services can expose description metadata using the Web Service Definition Language (WSDL), which is generated dynamically using .NET Reflection at runtime.</span></span> <span data-ttu-id="eb244-105">如果使用的是平台中立的绑定（如 SOAP over HTTP），开发人员可以使用此元数据来生成这些服务的客户端。</span><span class="sxs-lookup"><span data-stu-id="eb244-105">Developers can use this metadata to generate clients for those services, potentially in other languages if a platform-neutral binding such as SOAP over HTTP is used.</span></span>

<span data-ttu-id="eb244-106">gRPC 从协议缓冲区使用接口定义语言（IDL）。</span><span class="sxs-lookup"><span data-stu-id="eb244-106">gRPC uses the Interface Definition Language (IDL) from Protocol Buffers.</span></span> <span data-ttu-id="eb244-107">协议缓冲区 IDL 是一种独立于平台的自定义语言，具有开放规范。</span><span class="sxs-lookup"><span data-stu-id="eb244-107">The Protocol Buffers IDL is a custom, platform-neutral language with an open specification.</span></span> <span data-ttu-id="eb244-108">开发人员 `.proto` 文件中编写代码，以描述服务及其输入和输出。</span><span class="sxs-lookup"><span data-stu-id="eb244-108">Developers hand-code `.proto` files to describe services along with their inputs and outputs.</span></span> <span data-ttu-id="eb244-109">然后，可以使用这些 `.proto` 文件为客户端和服务器生成特定于语言或平台的存根，允许多个不同的平台进行通信。</span><span class="sxs-lookup"><span data-stu-id="eb244-109">These `.proto` files can then be used to generate language- or platform-specific stubs for clients and servers, allowing multiple different platforms to communicate.</span></span> <span data-ttu-id="eb244-110">通过共享 `.proto` 文件，团队可生成代码以使用他人的服务而无需进行代码依赖。</span><span class="sxs-lookup"><span data-stu-id="eb244-110">By sharing `.proto` files, teams can generate code to use each others' services without needing to take a code dependency.</span></span>

<span data-ttu-id="eb244-111">Protobuf IDL 的优点之一就是作为一种自定义语言，它允许 gRPC 完全语言和平台不可知，而不是 favoring 其他任何技术。</span><span class="sxs-lookup"><span data-stu-id="eb244-111">One of the advantages of the Protobuf IDL is that as a custom language it enables gRPC to be completely language and platform agnostic, not favoring any technology over another.</span></span>

<span data-ttu-id="eb244-112">Protobuf IDL 还设计用于读取和写入，而 WSDL 旨在用作计算机可读/可写格式。</span><span class="sxs-lookup"><span data-stu-id="eb244-112">The Protobuf IDL is also designed for humans to both read and write, whereas WSDL is intended as a machine-readable/writable format.</span></span> <span data-ttu-id="eb244-113">更改 WCF 服务的 WSDL 通常需要更改服务代码本身，运行服务并从服务器重新生成 WSDL 文件。</span><span class="sxs-lookup"><span data-stu-id="eb244-113">Changing the WSDL of a WCF service typically requires making the changes to the service code itself, running the service and regenerating the WSDL file from the server.</span></span> <span data-ttu-id="eb244-114">与此相反，使用 `.proto` 文件时，更改很简单，可与文本编辑器一起应用，并自动流过生成的代码。</span><span class="sxs-lookup"><span data-stu-id="eb244-114">By contrast, with a `.proto` file, changes are simple to apply with a text editor, and automatically flow through the generated code.</span></span> <span data-ttu-id="eb244-115">Visual Studio 2019 在保存时在后台生成 `.proto` 文件;使用其他编辑器（如 VS Code）时，将在生成项目时应用更改。</span><span class="sxs-lookup"><span data-stu-id="eb244-115">Visual Studio 2019 builds `.proto` files in the background when they are saved; when using other editors such as VS Code the changes will be applied when the project is built.</span></span>

<span data-ttu-id="eb244-116">与 XML 进行比较时，尤其是 SOAP，使用 Protobuf 编码的消息具有很多优点。</span><span class="sxs-lookup"><span data-stu-id="eb244-116">When compared with XML, and particularly SOAP, messages encoded using Protobuf have many advantages.</span></span> <span data-ttu-id="eb244-117">Protobuf 消息往往比作为 SOAP XML 序列化的数据更小，并通过网络对它们进行编码、解码和传输变得更快。</span><span class="sxs-lookup"><span data-stu-id="eb244-117">Protobuf messages tend to be smaller than the same data serialized as SOAP XML, and encoding, decoding and transmitting them over a network can be faster.</span></span>

<span data-ttu-id="eb244-118">与 SOAP 相比，Protobuf 的潜在缺点是，因为消息不能人工读取，所以调试消息内容需要额外的工具。</span><span class="sxs-lookup"><span data-stu-id="eb244-118">The potential disadvantage of Protobuf compared to SOAP is that, because the messages are not human readable, additional tooling is required to debug message content.</span></span>

> [!TIP]
> <span data-ttu-id="eb244-119">gRPC*支持*服务器反射以动态访问服务而无需预编译的存根，尽管它更适用于通用工具，而不是特定于应用程序的客户端。</span><span class="sxs-lookup"><span data-stu-id="eb244-119">gRPC *does* support server reflection for dynamically accessing services without pre-compiled stubs, although it is intended more for general-purpose tools than application-specific clients.</span></span> <span data-ttu-id="eb244-120">有关 gRPC Server 反射的详细信息，请参阅 GitHub 上的[gRPC/gRPC](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md)存储库。</span><span class="sxs-lookup"><span data-stu-id="eb244-120">For more information about gRPC Server Reflection, see [grpc/grpc](https://github.com/grpc/grpc/blob/master/doc/server-reflection.md) repository on GitHub.</span></span>

> [!NOTE]
> <span data-ttu-id="eb244-121">与 Wcf-nettcp 绑定一起使用的 WCF 二进制格式比 Protobuf 更接近紧凑性和性能，但 Wcf-nettcp 只能在 .NET 客户端和服务器之间使用，而 Protobuf 是一个跨平台解决方案。</span><span class="sxs-lookup"><span data-stu-id="eb244-121">WCF's binary format, used with the NetTCP binding, is much closer to Protobuf in terms of compactness and performance, but NetTCP is only usable between .NET clients and servers, whereas Protobuf is a cross-platform solution.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="eb244-122">[上一页](approach.md)
>[下一页](network-protocols.md)</span><span class="sxs-lookup"><span data-stu-id="eb244-122">[Previous](approach.md)
[Next](network-protocols.md)</span></span>
