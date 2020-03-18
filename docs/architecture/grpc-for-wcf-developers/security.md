---
title: gRPC 应用中的安全性 - 适用于 WCF 开发人员的 gRPC
description: gRPC 中的呼叫和通道身份验证和授权的概述。
ms.date: 09/02/2019
ms.openlocfilehash: 70cbf441bbc1b299b997f7d1f02bcd2bf7fde60c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147810"
---
# <a name="security-in-grpc-applications"></a>gRPC 应用程序中的安全性

在任何实际场景中，保护应用程序和服务都至关重要。 安全涵盖三个关键领域：

* 加密网络流量，防止恶意黑客拦截网络流量。
* 验证客户端和服务器以建立身份和信任。
* 授权客户端控制对系统的访问，并根据标识应用权限。

> [!NOTE]
> *身份验证*与建立客户端或服务器的标识有关。 *授权*涉及确定客户端是否具有访问资源或发出命令的权限。

本章将介绍 gRPC 中用于ASP.NET核心的身份验证和授权功能。 它还将讨论通过 TLS 加密连接的网络安全。

## <a name="wcf-authentication-and-authorization"></a>WCF 身份验证和授权

在 Windows 通信基础 （WCF） 中，身份验证和授权的处理方式不同，具体取决于所使用的传输和绑定。 WCF 支持各种\*WS-安全标准。 它还支持对在 IIS 中运行的 HTTP 服务或 Windows 系统之间的 NetTCP 服务进行 Windows 身份验证。

## <a name="grpc-authentication-and-authorization"></a>gRPC 身份验证和授权

gRPC 身份验证和授权在两个级别上工作：

* 调用级别的身份验证/授权通常通过在进行调用时在元数据中应用的令牌进行处理。
* 通道级身份验证使用在连接级别应用的客户端证书。 它还可以包括呼叫级身份验证/授权凭据，以便自动应用于通道上的每个呼叫。

您可以使用以下任一机制或两种机制来帮助保护服务。

gRPC ASP.NET核心实现通过大多数标准ASP.NET核心机制支持身份验证和授权：

- 呼叫身份验证
  - Azure Active Directory
  - 标识服务器
  - JWT 持票代币
  - OAuth 2.0
  - OpenID Connect
  - WS 联合身份验证
- 通道身份验证
  - 客户端证书

调用身份验证方法都基于*令牌*。 唯一的真正区别是令牌的生成方式以及用于验证 ASP.NET Core 服务中的令牌的库。

有关详细信息，请参阅[身份验证和授权](/aspnet/core/grpc/authn-and-authz)一文。

> [!NOTE]
> 当您通过 TLS 加密的 HTTP/2 连接使用 gRPC 时，客户端和服务器之间的所有流量都加密，即使您不使用通道级身份验证也是如此。

本章将演示如何将呼叫凭据和通道凭据应用于 gRPC 服务。 它还将演示如何使用 .NET Core gRPC 客户端的凭据对服务进行身份验证。

>[!div class="step-by-step"]
>[上一个](client-libraries.md)
>[下一个](call-credentials.md)
