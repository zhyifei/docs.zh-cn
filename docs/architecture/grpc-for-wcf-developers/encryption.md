---
title: 加密和网络安全-gRPC for WCF 开发人员
description: 有关 gRPC 中的网络安全和加密的一些注意事项
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 67ee1ffaf00ea0cc6b771ede9f49b6a691af0968
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841617"
---
# <a name="encryption-and-network-security"></a><span data-ttu-id="7c993-103">加密和网络安全</span><span class="sxs-lookup"><span data-stu-id="7c993-103">Encryption and network security</span></span>

<span data-ttu-id="7c993-104">WCF 的网络安全模型广泛而复杂，包括使用 HTTPS 或 over TCP 的传输级安全性，以及使用 WS 安全规范对各个消息进行加密的消息级安全性。</span><span class="sxs-lookup"><span data-stu-id="7c993-104">WCF's network security model is extensive and complex, including transport-level security using HTTPS or TLS-over-TCP, and message-level security using the WS-Security specification to encrypt individual messages.</span></span>

<span data-ttu-id="7c993-105">gRPC 会将安全网络留给基础 HTTP/2 协议，该协议可以使用常规 TLS 证书来保护。</span><span class="sxs-lookup"><span data-stu-id="7c993-105">gRPC leaves secure networking to the underlying HTTP/2 protocol, which can be secured using regular TLS certificates.</span></span>

<span data-ttu-id="7c993-106">Web 浏览器坚持使用 HTTP/2 的 TLS 连接，但大多数编程客户端（包括）都是如此。网络的 `HttpClient`，可以通过未加密的连接使用 HTTP/2。</span><span class="sxs-lookup"><span data-stu-id="7c993-106">Web browsers insist on using TLS connections for HTTP/2, but most programmatic clients, including .NET's `HttpClient`, can use HTTP/2 over unencrypted connections.</span></span> <span data-ttu-id="7c993-107">默认情况下，`HttpClient`*的确*需要加密，但你可以使用 <xref:System.AppContext> 开关来替代它。</span><span class="sxs-lookup"><span data-stu-id="7c993-107">`HttpClient` *does* require encryption by default, but you can override this using an <xref:System.AppContext> switch.</span></span>

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

<span data-ttu-id="7c993-108">对于公共 Api，应始终使用 TLS 连接，并从适当的 SSL 机构为你的服务提供有效的证书。</span><span class="sxs-lookup"><span data-stu-id="7c993-108">For public APIs, you should always use TLS connections and provide valid certificates for your services from a proper SSL authority.</span></span> <span data-ttu-id="7c993-109">[LetsEncrypt](https://letsencrypt.org)提供免费的自动 SSL 证书，并且目前大多数托管基础结构都支持通用插件或扩展的 LetsEncrypt 标准。</span><span class="sxs-lookup"><span data-stu-id="7c993-109">[LetsEncrypt](https://letsencrypt.org) provide free, automated SSL certificates, and most hosting infrastructure today supports the LetsEncrypt standard with common plug-ins or extensions.</span></span>

<span data-ttu-id="7c993-110">对于跨企业网络的内部服务，还应考虑使用 TLS 来保护进出 gRPC services 的网络流量。</span><span class="sxs-lookup"><span data-stu-id="7c993-110">For internal services across a corporate network, you should still consider using TLS to secure network traffic to and from your gRPC services.</span></span>

<span data-ttu-id="7c993-111">群集中的微服务之间的通信（如 Kubernetes 或 Docker Swarm）一般都是由容器网络层自动加密的，因此不需要在此类群集中以独占方式运行的服务实现 TLS。</span><span class="sxs-lookup"><span data-stu-id="7c993-111">Communication between microservices in a cluster like Kubernetes or Docker Swarm is in general automatically encrypted by the container networking layer, so implementing TLS in services running exclusively in such a cluster isn't necessary.</span></span> <span data-ttu-id="7c993-112">下一章的 "服务网格" 一节中将详细介绍这一主题。</span><span class="sxs-lookup"><span data-stu-id="7c993-112">There will be more on this subject in the "Service Mesh" section of the next chapter.</span></span>

<span data-ttu-id="7c993-113">如果需要在 Kubernetes 中运行的服务之间使用显式 TLS，请考虑使用群集内证书颁发机构和证书管理器控制器（如[cert manager](https://docs.cert-manager.io/en/latest/) ）在部署时将证书自动分配给服务。</span><span class="sxs-lookup"><span data-stu-id="7c993-113">If you need to use explicit TLS between services running in Kubernetes, consider using an in-cluster Certificate Authority and a Certificate Manager Controller like [cert-manager](https://docs.cert-manager.io/en/latest/) to assign automatically certificates to services at deployment time.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7c993-114">[上一页](channel-credentials.md)
>[下一页](grpc-in-production.md)</span><span class="sxs-lookup"><span data-stu-id="7c993-114">[Previous](channel-credentials.md)
[Next](grpc-in-production.md)</span></span>
