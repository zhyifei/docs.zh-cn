---
title: WS-* 协议-适用于 WCF 开发人员的 gRPC
description: 查看 WCF 支持的 WS-* 协议和 gRPC 提供的替代项
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: c8c06a5e23a4d7859165e1c562032055d63d76f7
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503298"
---
# <a name="ws--protocols"></a><span data-ttu-id="f7e5f-103">WS\* 协议</span><span class="sxs-lookup"><span data-stu-id="f7e5f-103">WS-\* protocols</span></span>

<span data-ttu-id="f7e5f-104">使用 Windows Communication Foundation （WCF）的一个真正优点是它支持许多现有的_WS\*_ 标准协议。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-104">One of the real benefits of working with Windows Communication Foundation (WCF) was that it supported many of the existing _WS-\*_ standard protocols.</span></span> <span data-ttu-id="f7e5f-105">本部分将简要介绍 gRPC 如何管理相同的 WS\* 协议，并讨论在没有替代方法时可用的选项。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-105">This section will briefly cover how gRPC manages the same WS-\* protocols and discuss what options are available when there's no alternative.</span></span>

## <a name="metadata-exchange-ws-policy-ws-discovery-and-so-on"></a><span data-ttu-id="f7e5f-106">元数据交换： WS 策略、WS 发现等</span><span class="sxs-lookup"><span data-stu-id="f7e5f-106">Metadata exchange: WS-Policy, WS-Discovery, and so on</span></span>

<span data-ttu-id="f7e5f-107">SOAP 服务公开 Web 服务描述语言（WSDL）架构文档，其中包含数据格式、操作或通信选项等信息。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-107">SOAP services expose Web Services Description Language (WSDL) schema documents with information such as data formats, operations, or communication options.</span></span> <span data-ttu-id="f7e5f-108">您可以使用此架构来生成客户端代码。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-108">You can use this schema to generate the client code.</span></span>

<span data-ttu-id="f7e5f-109">如果服务器和客户端是从同一个 `.proto` 文件生成的，则 gRPC 的效果最好，但服务器反射可选扩展提供了一种从正在运行的服务器中公开动态信息的方法。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-109">gRPC works best when servers and clients are generated from the same `.proto` files, but a Server Reflection optional extension does provide a way to expose dynamic information from a running server.</span></span> <span data-ttu-id="f7e5f-110">有关详细信息，请参阅[Grpc](https://nuget.org/packages/Grpc.Reflection) NuGet 包和[Grpc C#服务器反射](https://github.com/grpc/grpc/blob/master/doc/csharp/server_reflection.md)一文。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-110">For more information, see the [Grpc.Reflection](https://nuget.org/packages/Grpc.Reflection) NuGet package and the [gRPC C# Server Reflection](https://github.com/grpc/grpc/blob/master/doc/csharp/server_reflection.md) article.</span></span>

<span data-ttu-id="f7e5f-111">使用 WS 发现协议在本地网络上查找服务。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-111">The WS-Discovery protocol is used to locate services on a local network.</span></span> <span data-ttu-id="f7e5f-112">gRPC 服务通常位于 DNS 或服务注册表（如 Consul 或 ZooKeeper）中。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-112">gRPC services are generally located through DNS or a service registry such as Consul or ZooKeeper.</span></span>

## <a name="security-ws-security-ws-federation-xml-encryption-and-so-on"></a><span data-ttu-id="f7e5f-113">安全性： WS 安全性、WS 联合身份验证、XML 加密等</span><span class="sxs-lookup"><span data-stu-id="f7e5f-113">Security: WS-Security, WS-Federation, XML Encryption, and so on</span></span>

<span data-ttu-id="f7e5f-114">[第6章](security.md)中更详细地介绍了安全性、身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-114">Security, authentication, and authorization are covered in much more detail in [chapter 6](security.md).</span></span> <span data-ttu-id="f7e5f-115">但在此，值得注意的是，与 WCF 不同，gRPC 不支持 WS 安全性、WS 联合身份验证或 XML 加密。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-115">But it's worth noting here that, unlike WCF, gRPC doesn't support WS-Security, WS-Federation, or XML Encryption.</span></span> <span data-ttu-id="f7e5f-116">尽管如此，gRPC 也能提供卓越的安全性。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-116">Even so, gRPC provides excellent security.</span></span> <span data-ttu-id="f7e5f-117">所有 gRPC 网络流量在使用 HTTP/2 over TLS 时自动进行加密。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-117">All gRPC network traffic is automatically encrypted when it's using HTTP/2 over TLS.</span></span> <span data-ttu-id="f7e5f-118">您可以使用 X509 证书进行相互的客户端/服务器身份验证。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-118">You can use X509 certificates for mutual client/server authentication.</span></span>

## <a name="ws-reliablemessaging"></a><span data-ttu-id="f7e5f-119">WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="f7e5f-119">WS-ReliableMessaging</span></span>

<span data-ttu-id="f7e5f-120">gRPC 未提供与 WS-RELIABLEMESSAGING 等效的。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-120">gRPC does not provide an equivalent to WS-ReliableMessaging.</span></span> <span data-ttu-id="f7e5f-121">应该在代码中处理重试语义，如[Polly](https://github.com/App-vNext/Polly)。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-121">Retry semantics should be handled in code, possibly with a library like [Polly](https://github.com/App-vNext/Polly).</span></span> <span data-ttu-id="f7e5f-122">当你在 Kubernetes 或类似的业务流程环境中运行时，[服务网格](service-mesh.md)还有助于在服务之间提供可靠的消息传送。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-122">When you're running in Kubernetes or similar orchestration environments, [service meshes](service-mesh.md) can also help to provide reliable messaging between services.</span></span>

## <a name="ws-transaction-ws-coordination"></a><span data-ttu-id="f7e5f-123">WS 事务，WS 协调</span><span class="sxs-lookup"><span data-stu-id="f7e5f-123">WS-Transaction, WS-Coordination</span></span>

<span data-ttu-id="f7e5f-124">WCF 对分布式事务的实现使用 Microsoft 分布式事务处理协调器（MSDTC）。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-124">WCF's implementation of distributed transactions uses Microsoft Distributed Transaction Coordinator (MSDTC).</span></span> <span data-ttu-id="f7e5f-125">它适用于专门支持的资源管理器，例如 SQL Server、MSMQ 或 Windows 文件系统。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-125">It works with resource managers that specifically support it, like SQL Server, MSMQ, or Windows file systems.</span></span> <span data-ttu-id="f7e5f-126">由于使用的技术范围更广，因此在现代微服务世界上没有任何等效项。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-126">There's no equivalent yet in the modern microservices world, in part due to the wider range of technologies in use.</span></span> <span data-ttu-id="f7e5f-127">有关事务的讨论，请参阅[附录 a](appendix.md)。</span><span class="sxs-lookup"><span data-stu-id="f7e5f-127">For a discussion of transactions, see [Appendix A](appendix.md).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f7e5f-128">[上一页](error-handling.md)
>[下一页](migrate-wcf-to-grpc.md)</span><span class="sxs-lookup"><span data-stu-id="f7e5f-128">[Previous](error-handling.md)
[Next](migrate-wcf-to-grpc.md)</span></span>
