---
title: GRPC 应用程序中的安全性-WCF 开发人员 gRPC
description: GRPC 中的呼叫和通道身份验证和授权的概述。
ms.date: 09/02/2019
ms.openlocfilehash: d5804ad5de4a834eb81b90fa1ea7a61969a0b42f
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503420"
---
# <a name="security-in-grpc-applications"></a><span data-ttu-id="baef7-103">gRPC 应用程序中的安全性</span><span class="sxs-lookup"><span data-stu-id="baef7-103">Security in gRPC applications</span></span>

<span data-ttu-id="baef7-104">在任何实际情况下，确保应用程序和服务的安全至关重要。</span><span class="sxs-lookup"><span data-stu-id="baef7-104">In any real-world scenario, securing applications and services is essential.</span></span> <span data-ttu-id="baef7-105">安全性涵盖三个关键领域：</span><span class="sxs-lookup"><span data-stu-id="baef7-105">Security covers three key areas:</span></span> 

* <span data-ttu-id="baef7-106">加密网络流量可防止恶意黑客拦截该流量。</span><span class="sxs-lookup"><span data-stu-id="baef7-106">Encrypting network traffic to prevent malicious hackers from intercepting it.</span></span>
* <span data-ttu-id="baef7-107">对客户端和服务器进行身份验证，以建立标识和信任。</span><span class="sxs-lookup"><span data-stu-id="baef7-107">Authenticating clients and servers to establish identity and trust.</span></span>
* <span data-ttu-id="baef7-108">授权客户端控制对系统的访问并根据标识应用权限。</span><span class="sxs-lookup"><span data-stu-id="baef7-108">Authorizing clients to control access to systems and apply permissions based on identity.</span></span>

> [!NOTE]
> <span data-ttu-id="baef7-109">*身份验证*涉及建立客户端或服务器的标识。</span><span class="sxs-lookup"><span data-stu-id="baef7-109">*Authentication* is concerned with establishing the identity of a client or server.</span></span> <span data-ttu-id="baef7-110">*授权*与确定客户端是否有权访问资源或发出命令相关。</span><span class="sxs-lookup"><span data-stu-id="baef7-110">*Authorization* is concerned with determining whether a client has permission to access a resource or issue a command.</span></span>

<span data-ttu-id="baef7-111">本章将介绍在 gRPC 中用于 ASP.NET Core 的身份验证和授权功能。</span><span class="sxs-lookup"><span data-stu-id="baef7-111">This chapter will cover the facilities for authentication and authorization in gRPC for ASP.NET Core.</span></span> <span data-ttu-id="baef7-112">它还将通过 TLS 加密连接讨论网络安全。</span><span class="sxs-lookup"><span data-stu-id="baef7-112">It will also discuss network security through TLS encrypted connections.</span></span>

## <a name="wcf-authentication-and-authorization"></a><span data-ttu-id="baef7-113">WCF 身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="baef7-113">WCF authentication and authorization</span></span>

<span data-ttu-id="baef7-114">在 Windows Communication Foundation （WCF）中，身份验证和授权的处理方式不同，具体取决于所使用的传输和绑定。</span><span class="sxs-lookup"><span data-stu-id="baef7-114">In Windows Communication Foundation (WCF), authentication and authorization were handled in different ways, depending on the transports and bindings being used.</span></span> <span data-ttu-id="baef7-115">WCF 支持多种\* 安全标准。</span><span class="sxs-lookup"><span data-stu-id="baef7-115">WCF supported various WS-\* security standards.</span></span> <span data-ttu-id="baef7-116">它还支持 windows 身份验证，适用于在 IIS 中运行的 HTTP 服务或 Windows 系统之间 Wcf-nettcp 的服务。</span><span class="sxs-lookup"><span data-stu-id="baef7-116">It also supported Windows authentication for HTTP services running in IIS or NetTCP services between Windows systems.</span></span>

## <a name="grpc-authentication-and-authorization"></a><span data-ttu-id="baef7-117">gRPC 身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="baef7-117">gRPC authentication and authorization</span></span>

<span data-ttu-id="baef7-118">gRPC 身份验证和授权适用于两个级别：</span><span class="sxs-lookup"><span data-stu-id="baef7-118">gRPC authentication and authorization works on two levels:</span></span>

* <span data-ttu-id="baef7-119">调用级身份验证/授权通常通过在调用时应用于元数据的令牌进行处理。</span><span class="sxs-lookup"><span data-stu-id="baef7-119">Call-level authentication/authorization is usually handled through tokens that are applied in metadata when the call is made.</span></span> 
* <span data-ttu-id="baef7-120">通道级身份验证使用在连接级别应用的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="baef7-120">Channel-level authentication uses a client certificate that's applied at the connection level.</span></span> <span data-ttu-id="baef7-121">它还可以包含调用级别的身份验证/授权凭据，以自动将其应用到通道上的每个调用。</span><span class="sxs-lookup"><span data-stu-id="baef7-121">It can also include call-level authentication/authorization credentials to be applied to every call on the channel automatically.</span></span> 

<span data-ttu-id="baef7-122">你可以使用其中一个或两个机制来帮助保护你的服务。</span><span class="sxs-lookup"><span data-stu-id="baef7-122">You can use either or both of these mechanisms to help secure your service.</span></span>

<span data-ttu-id="baef7-123">GRPC 的 ASP.NET Core 实现通过大多数标准 ASP.NET Core 机制支持身份验证和授权：</span><span class="sxs-lookup"><span data-stu-id="baef7-123">The ASP.NET Core implementation of gRPC supports authentication and authorization through most of the standard ASP.NET Core mechanisms:</span></span>

- <span data-ttu-id="baef7-124">调用身份验证</span><span class="sxs-lookup"><span data-stu-id="baef7-124">Call authentication</span></span>
  - <span data-ttu-id="baef7-125">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="baef7-125">Azure Active Directory</span></span>
  - <span data-ttu-id="baef7-126">IdentityServer</span><span class="sxs-lookup"><span data-stu-id="baef7-126">IdentityServer</span></span>
  - <span data-ttu-id="baef7-127">JWT 持有者令牌</span><span class="sxs-lookup"><span data-stu-id="baef7-127">JWT Bearer Token</span></span>
  - <span data-ttu-id="baef7-128">OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="baef7-128">OAuth 2.0</span></span>
  - <span data-ttu-id="baef7-129">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="baef7-129">OpenID Connect</span></span>
  - <span data-ttu-id="baef7-130">WS 联合身份验证</span><span class="sxs-lookup"><span data-stu-id="baef7-130">WS-Federation</span></span>
- <span data-ttu-id="baef7-131">通道身份验证</span><span class="sxs-lookup"><span data-stu-id="baef7-131">Channel authentication</span></span>
  - <span data-ttu-id="baef7-132">客户端证书</span><span class="sxs-lookup"><span data-stu-id="baef7-132">Client certificate</span></span>

<span data-ttu-id="baef7-133">呼叫身份验证方法都是基于*令牌*的。</span><span class="sxs-lookup"><span data-stu-id="baef7-133">The call authentication methods are all based on *tokens*.</span></span> <span data-ttu-id="baef7-134">唯一的区别在于如何生成令牌和用于验证 ASP.NET Core 服务中的令牌的库。</span><span class="sxs-lookup"><span data-stu-id="baef7-134">The only real difference is how the tokens are generated and the libraries that are used to validate the tokens in the ASP.NET Core service.</span></span>

<span data-ttu-id="baef7-135">有关详细信息，请参阅[身份验证和授权](/aspnet/core/grpc/authn-and-authz)一文。</span><span class="sxs-lookup"><span data-stu-id="baef7-135">For more information, see the [Authentication and authorization](/aspnet/core/grpc/authn-and-authz) article.</span></span>

> [!NOTE]
> <span data-ttu-id="baef7-136">当你在 TLS 加密的 HTTP/2 连接上使用 gRPC 时，客户端和服务器之间的所有流量都将加密，即使你不使用通道级身份验证。</span><span class="sxs-lookup"><span data-stu-id="baef7-136">When you're using gRPC over a TLS-encrypted HTTP/2 connection, all traffic between clients and servers is encrypted, even if you don't use channel-level authentication.</span></span>

<span data-ttu-id="baef7-137">本章介绍如何将调用凭据和通道凭据应用于 gRPC 服务。</span><span class="sxs-lookup"><span data-stu-id="baef7-137">This chapter will show how to apply call credentials and channel credentials to a gRPC service.</span></span> <span data-ttu-id="baef7-138">它还将演示如何使用 .NET Core gRPC 客户端提供的凭据对服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="baef7-138">It will also show how to use credentials from a .NET Core gRPC client to authenticate with the service.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="baef7-139">[上一页](client-libraries.md)
>[下一页](call-credentials.md)</span><span class="sxs-lookup"><span data-stu-id="baef7-139">[Previous](client-libraries.md)
[Next](call-credentials.md)</span></span>
