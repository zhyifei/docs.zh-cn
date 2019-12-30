---
title: GRPC 应用程序中的安全性-WCF 开发人员 gRPC
description: GRPC 中的呼叫和通道身份验证和授权的概述。
ms.date: 09/02/2019
ms.openlocfilehash: b88ed0c01d1ca4432c7e4fe7115246f4227159df
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967252"
---
# <a name="security-in-grpc-applications"></a>gRPC 应用程序中的安全性

在任何实际情况下，确保应用程序和服务的安全至关重要。 安全性涵盖三个关键领域：加密网络流量以防止其被错误的执行组件截获;对客户端和服务器进行身份验证，以建立标识和信任;并授权客户端控制对系统的访问，并根据标识应用权限。

> [!NOTE]
> **身份验证**涉及建立客户端或服务器的标识。 **授权**与确定客户端是否有权访问资源或发出命令相关。

本章介绍了用于在 ASP.NET Core gRPC 中进行身份验证和授权的功能，并介绍了使用 TLS 加密连接的网络安全性。

## <a name="wcf-authentication-and-authorization"></a>WCF 身份验证和授权

在 WCF 中，身份验证和授权的处理方式不同，具体取决于所使用的传输和绑定。 WCF 支持各种 WS\* 安全标准，以及 windows 系统之间 IIS 或 Wcf-nettcp 服务中运行的 HTTP 服务的 Windows 身份验证。

## <a name="grpc-authentication-and-authorization"></a>gRPC 身份验证和授权

gRPC 身份验证和授权适用于两个级别。 调用级身份验证/授权通常使用在调用时应用于元数据中的令牌进行处理。 通道级身份验证使用在连接级别应用的客户端证书，还可以包含要对通道上的每个调用自动应用的调用级身份验证/授权凭据。 您可以使用这两种机制或其中一种机制来保护您的服务。

GRPC 的 ASP.NET Core 实现使用大多数标准 ASP.NET Core 机制支持身份验证和授权：

- 调用身份验证
  - Azure Active Directory
  - IdentityServer
  - JWT 持有者令牌
  - OAuth 2.0
  - OpenID Connect
  - WS-Federation
- 通道身份验证
  - 客户端证书

呼叫身份验证方法都是基于*令牌*的。 唯一的区别在于如何生成令牌和用于验证 ASP.NET Core 服务中的令牌的库。

有关详细信息，请参阅[Microsoft Docs 上的身份验证和授权文档](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0)。

> [!NOTE]
> 在通过 TLS 加密的 HTTP/2 连接上使用 gRPC 时，客户端与服务器之间的所有流量都将加密，即使您不使用通道级身份验证也是如此。

本章介绍如何将调用凭据和通道凭据应用于 gRPC 服务，以及如何使用 .NET Core gRPC 客户端提供的凭据对服务进行身份验证。

>[!div class="step-by-step"]
>[上一页](client-libraries.md)
>[下一页](call-credentials.md)
