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
# <a name="security-in-grpc-applications"></a><span data-ttu-id="91e55-103">gRPC 应用程序中的安全性</span><span class="sxs-lookup"><span data-stu-id="91e55-103">Security in gRPC applications</span></span>

<span data-ttu-id="91e55-104">在任何实际场景中，保护应用程序和服务都至关重要。</span><span class="sxs-lookup"><span data-stu-id="91e55-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="91e55-105">安全涵盖三个关键领域：</span><span class="sxs-lookup"><span data-stu-id="91e55-105">Security covers three key areas:</span></span>

* <span data-ttu-id="91e55-106">加密网络流量，防止恶意黑客拦截网络流量。</span><span class="sxs-lookup"><span data-stu-id="91e55-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="91e55-107">验证客户端和服务器以建立身份和信任。</span><span class="sxs-lookup"><span data-stu-id="91e55-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="91e55-108">授权客户端控制对系统的访问，并根据标识应用权限。</span><span class="sxs-lookup"><span data-stu-id="91e55-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="91e55-109">*身份验证*与建立客户端或服务器的标识有关。</span><span class="sxs-lookup"><span data-stu-id="91e55-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="91e55-110">*授权*涉及确定客户端是否具有访问资源或发出命令的权限。</span><span class="sxs-lookup"><span data-stu-id="91e55-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="91e55-111">本章将介绍 gRPC 中用于ASP.NET核心的身份验证和授权功能。</span><span class="sxs-lookup"><span data-stu-id="91e55-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="91e55-112">它还将讨论通过 TLS 加密连接的网络安全。</span><span class="sxs-lookup"><span data-stu-id="91e55-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="91e55-113">WCF 身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="91e55-113">WCF authentication and authorization</span></span>

<span data-ttu-id="91e55-114">在 Windows 通信基础 （WCF） 中，身份验证和授权的处理方式不同，具体取决于所使用的传输和绑定。</span><span class="sxs-lookup"><span data-stu-id="91e55-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="91e55-115">WCF 支持各种\*WS-安全标准。</span><span class="sxs-lookup"><span data-stu-id="91e55-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="91e55-116">它还支持对在 IIS 中运行的 HTTP 服务或 Windows 系统之间的 NetTCP 服务进行 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="91e55-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="91e55-117">gRPC 身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="91e55-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="91e55-118">gRPC 身份验证和授权在两个级别上工作：</span><span class="sxs-lookup"><span data-stu-id="91e55-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="91e55-119">调用级别的身份验证/授权通常通过在进行调用时在元数据中应用的令牌进行处理。</span><span class="sxs-lookup"><span data-stu-id="91e55-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span>
* <span data-ttu-id="91e55-120">通道级身份验证使用在连接级别应用的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="91e55-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="91e55-121">它还可以包括呼叫级身份验证/授权凭据，以便自动应用于通道上的每个呼叫。</span><span class="sxs-lookup"><span data-stu-id="91e55-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span>

<span data-ttu-id="91e55-122">您可以使用以下任一机制或两种机制来帮助保护服务。</span><span class="sxs-lookup"><span data-stu-id="91e55-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="91e55-123">gRPC ASP.NET核心实现通过大多数标准ASP.NET核心机制支持身份验证和授权：</span><span class="sxs-lookup"><span data-stu-id="91e55-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="91e55-124">呼叫身份验证</span><span class="sxs-lookup"><span data-stu-id="91e55-124">Call authentication</span></span>
  - <span data-ttu-id="91e55-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="91e55-125">Azure Active Directory</span></span>
  - <span data-ttu-id="91e55-126">标识服务器</span><span class="sxs-lookup"><span data-stu-id="91e55-126">IdentityServer</span></span>
  - <span data-ttu-id="91e55-127">JWT 持票代币</span><span class="sxs-lookup"><span data-stu-id="91e55-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="91e55-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="91e55-128">OAuth 2.0</span></span>
  - <span data-ttu-id="91e55-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="91e55-129">OpenID Connect</span></span>
  - <span data-ttu-id="91e55-130">WS 联合身份验证</span><span class="sxs-lookup"><span data-stu-id="91e55-130">WS-Federation</span></span>
- <span data-ttu-id="91e55-131">通道身份验证</span><span class="sxs-lookup"><span data-stu-id="91e55-131">Channel authentication</span></span>
  - <span data-ttu-id="91e55-132">客户端证书</span><span class="sxs-lookup"><span data-stu-id="91e55-132">Client certificate</span></span>

<span data-ttu-id="91e55-133">调用身份验证方法都基于*令牌*。</span><span class="sxs-lookup"><span data-stu-id="91e55-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="91e55-134">唯一的真正区别是令牌的生成方式以及用于验证 ASP.NET Core 服务中的令牌的库。</span><span class="sxs-lookup"><span data-stu-id="91e55-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="91e55-135">有关详细信息，请参阅[身份验证和授权](/aspnet/core/grpc/authn-and-authz)一文。</span><span class="sxs-lookup"><span data-stu-id="91e55-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="91e55-136">当您通过 TLS 加密的 HTTP/2 连接使用 gRPC 时，客户端和服务器之间的所有流量都加密，即使您不使用通道级身份验证也是如此。</span><span class="sxs-lookup"><span data-stu-id="91e55-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="91e55-137">本章将演示如何将呼叫凭据和通道凭据应用于 gRPC 服务。</span><span class="sxs-lookup"><span data-stu-id="91e55-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="91e55-138">它还将演示如何使用 .NET Core gRPC 客户端的凭据对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="91e55-138">It will also show how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="91e55-139">[上一个](client-libraries.md)
>[下一个](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="91e55-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
