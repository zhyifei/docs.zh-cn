---
title: 加密和网络安全-gRPC for WCF 开发人员
description: 有关 gRPC 中的网络安全和加密的一些注意事项
ms.date: 09/02/2019
ms.openlocfilehash: fd993a2d75e97011c6c92cee02c24c5358a211ad
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967781"
---
# <a name="encryption-and-network-security"></a>加密和网络安全

WCF 的网络安全模型广泛而复杂，包括使用 HTTPS 或 over TCP 的传输级安全性，以及使用 WS 安全规范对各个消息进行加密的消息级安全性。

gRPC 会将安全网络留给基础 HTTP/2 协议，该协议可以使用常规 TLS 证书来保护。

Web 浏览器坚持使用 HTTP/2 的 TLS 连接，但大多数编程客户端（包括）都是如此。网络的 `HttpClient`，可以通过未加密的连接使用 HTTP/2。 默认情况下，`HttpClient`*的确*需要加密，但你可以使用 <xref:System.AppContext> 开关来替代它。

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

对于公共 Api，应始终使用 TLS 连接，并从适当的 SSL 机构为你的服务提供有效的证书。 [LetsEncrypt](https://letsencrypt.org)提供免费的自动 SSL 证书，并且目前大多数托管基础结构都支持通用插件或扩展的 LetsEncrypt 标准。

对于跨企业网络的内部服务，还应考虑使用 TLS 来保护进出 gRPC services 的网络流量。

群集中的微服务之间的通信（如 Kubernetes 或 Docker Swarm）一般都是由容器网络层自动加密的，因此不需要在此类群集中以独占方式运行的服务实现 TLS。 下一章的 "服务网格" 一节中将详细介绍这一主题。

如果需要在 Kubernetes 中运行的服务之间使用显式 TLS，请考虑使用群集内证书颁发机构和证书管理器控制器（如[cert manager](https://docs.cert-manager.io/en/latest/) ）在部署时将证书自动分配给服务。

>[!div class="step-by-step"]
>[上一页](channel-credentials.md)
>[下一页](grpc-in-production.md)
