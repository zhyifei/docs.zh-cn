---
title: GRPC 应用程序中的安全性-WCF 开发人员 gRPC
description: GRPC 中的呼叫和通道身份验证和授权的概述。
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: d0b7ff5bef755c5eeb9b3c419dcda1cb75ac4031
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841371"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="6c442-103">gRPC 应用程序中的安全性</span><span class="sxs-lookup"><span data-stu-id="6c442-103">Security in gRPC applications</span></span>

<span data-ttu-id="6c442-104">在任何实际情况下，确保应用程序和服务的安全至关重要。</span><span class="sxs-lookup"><span data-stu-id="6c442-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="6c442-105">安全性涵盖三个关键领域：加密网络流量以防止其被错误的执行组件截获;对客户端和服务器进行身份验证，以建立标识和信任;并授权客户端控制对系统的访问，并根据标识应用权限。</span><span class="sxs-lookup"><span data-stu-id="6c442-105">Security covers three key areas: encrypting network traffic to prevent it from being intercepted by bad actors; authenticating clients and servers to establish identity and trust; and authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="6c442-106">**身份验证**涉及建立客户端或服务器的标识。</span><span class="sxs-lookup"><span data-stu-id="6c442-106">**Authentication** is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="6c442-107">**授权**与确定客户端是否有权访问资源或发出命令相关。</span><span class="sxs-lookup"><span data-stu-id="6c442-107">**Authorization** is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="6c442-108">本章介绍了用于在 ASP.NET Core gRPC 中进行身份验证和授权的功能，并介绍了使用 TLS 加密连接的网络安全性。</span><span class="sxs-lookup"><span data-stu-id="6c442-108">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core, and discuss network security using TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="6c442-109">WCF 身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="6c442-109">WCF authentication and authorization</span></span>

<span data-ttu-id="6c442-110">在 WCF 中，身份验证和授权的处理方式不同，具体取决于所使用的传输和绑定。</span><span class="sxs-lookup"><span data-stu-id="6c442-110">In WCF, authentication and authorization were handled in different ways depending on the transports and bindings being used.</span></span> <span data-ttu-id="6c442-111">WCF 支持各种 WS\* 安全标准，以及 windows 系统之间 IIS 或 Wcf-nettcp 服务中运行的 HTTP 服务的 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6c442-111">WCF supported various WS-\* security standards, as well as Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="6c442-112">gRPC 身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="6c442-112">gRPC authentication and authorization</span></span>

<span data-ttu-id="6c442-113">gRPC 身份验证和授权适用于两个级别。</span><span class="sxs-lookup"><span data-stu-id="6c442-113">gRPC authentication and authorization works on two levels.</span></span> <span data-ttu-id="6c442-114">调用级身份验证/授权通常使用在调用时应用于元数据中的令牌进行处理。</span><span class="sxs-lookup"><span data-stu-id="6c442-114">Call-level authentication/authorization is usually handled using tokens that are applied in metadata when the call is made.</span></span> <span data-ttu-id="6c442-115">通道级身份验证使用在连接级别应用的客户端证书，还可以包含要对通道上的每个调用自动应用的调用级身份验证/授权凭据。</span><span class="sxs-lookup"><span data-stu-id="6c442-115">Channel-level authentication uses a client certificate that is applied at the connection level, and can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span> <span data-ttu-id="6c442-116">您可以使用这两种机制或其中一种机制来保护您的服务。</span><span class="sxs-lookup"><span data-stu-id="6c442-116">You can use either or both of these mechanisms to secure your service.</span></span>

<span data-ttu-id="6c442-117">GRPC 的 ASP.NET Core 实现使用大多数标准 ASP.NET Core 机制支持身份验证和授权：</span><span class="sxs-lookup"><span data-stu-id="6c442-117">The ASP.NET Core implementation of gRPC supports authentication and authorization using most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="6c442-118">调用身份验证</span><span class="sxs-lookup"><span data-stu-id="6c442-118">Call authentication</span></span>
  - <span data-ttu-id="6c442-119">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6c442-119">Azure Active Directory</span></span>
  - <span data-ttu-id="6c442-120">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="6c442-120">IdentityServer</span></span>
  - <span data-ttu-id="6c442-121">JWT 持有者令牌</span><span class="sxs-lookup"><span data-stu-id="6c442-121">JWT Bearer Token</span></span>
  - <span data-ttu-id="6c442-122">OAuth 2。0</span><span class="sxs-lookup"><span data-stu-id="6c442-122">OAuth 2.0</span></span>
  - <span data-ttu-id="6c442-123">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="6c442-123">OpenID Connect</span></span>
  - <span data-ttu-id="6c442-124">WS-Federation</span><span class="sxs-lookup"><span data-stu-id="6c442-124">WS-Federation</span></span>
- <span data-ttu-id="6c442-125">通道身份验证</span><span class="sxs-lookup"><span data-stu-id="6c442-125">Channel authentication</span></span>
  - <span data-ttu-id="6c442-126">客户端证书</span><span class="sxs-lookup"><span data-stu-id="6c442-126">Client Certificate</span></span>

<span data-ttu-id="6c442-127">呼叫身份验证方法都是基于*令牌*的。</span><span class="sxs-lookup"><span data-stu-id="6c442-127">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="6c442-128">唯一的区别在于如何生成令牌和用于验证 ASP.NET Core 服务中的令牌的库。</span><span class="sxs-lookup"><span data-stu-id="6c442-128">The only real difference is how the token is generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="6c442-129">有关详细信息，请参阅[Microsoft Docs 上的身份验证和授权文档](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0)。</span><span class="sxs-lookup"><span data-stu-id="6c442-129">For more information, see the [Authentication and authorization documentation on Microsoft Docs](https://docs.microsoft.com/aspnet/core/grpc/authn-and-authz?view=aspnetcore-3.0).</span></span>

> [!NOTE]
> <span data-ttu-id="6c442-130">在通过 TLS 加密的 HTTP/2 连接上使用 gRPC 时，客户端与服务器之间的所有流量都将加密，即使您不使用通道级身份验证也是如此。</span><span class="sxs-lookup"><span data-stu-id="6c442-130">When using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="6c442-131">本章介绍如何将调用凭据和通道凭据应用于 gRPC 服务，以及如何使用 .NET Core gRPC 客户端提供的凭据对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="6c442-131">This chapter will show how to apply call credentials and channel credentials to a gRPC service, and how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6c442-132">[上一页](client-libraries.md)
>[下一页](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="6c442-132">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
