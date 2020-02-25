---
title: 加密和网络安全-gRPC for WCF 开发人员
description: 有关 gRPC 中的网络安全和加密的一些注意事项
ms.date: 09/02/2019
ms.openlocfilehash: f8a7aeaf2a65e4ff56ac33d728e40f09a436f7a6
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "77542762"
---
# <a name="encryption-and-network-security"></a>加密和网络安全

Windows Communication Foundation （WCF）的网络安全模型广泛而复杂。 它包括使用 HTTPS 或经由 TCP 的传输级安全性，以及使用 WS 安全规范对单个消息进行加密的消息级安全性。

gRPC 会将安全网络留给基础 HTTP/2 协议，你可以使用 TLS 证书来保护这一点。

Web 浏览器坚持使用 HTTP/2 的 TLS 连接，但大多数编程客户端（包括）都是如此。网络的 `HttpClient`，可以通过未加密的连接使用 HTTP/2。 默认情况下，`HttpClient` 的确需要加密，但你可以通过使用 <xref:System.AppContext> 开关来替代它。

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

对于公共 Api，应始终使用 TLS 连接，并从适当的 SSL 机构为你的服务提供有效的证书。 [LetsEncrypt](https://letsencrypt.org)提供免费的自动 SSL 证书，并且目前大多数托管基础结构都支持具有通用插件或扩展的 LetsEncrypt 标准。

对于跨企业网络的内部服务，还应考虑使用 TLS 来保护进出 gRPC services 的网络流量。

如果需要在 Kubernetes 中运行的服务之间使用显式 TLS，请考虑使用群集内证书颁发机构和证书管理器控制器（如[cert 管理器](https://docs.cert-manager.io/en/latest/)）。 然后，你可以在部署时自动将证书分配给服务。

>[!div class="step-by-step"]
>[上一页](channel-credentials.md)
>[下一页](grpc-in-production.md)
