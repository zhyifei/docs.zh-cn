---
title: "Internet 身份验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authentication [.NET Framework], classes
- IAuthenticationModule interface
- ICredentialLookup interface
- CredentialCache class, about CredentialCache class
- receiving data, authentication
- AuthenticationManager class, about AuthenticationManager class
- Internet, authentication
- sending data, authentication
- network resources, authentication
- user authentication, classes for authentication
- NetworkCredential class, about NetworkCredential class
- client authentication, classes for authentication
ms.assetid: d342e87c-f672-4660-a513-41a2f2b80c4a
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: fbf25ae866b338d2f1ac0ea11570e0d535e9137c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="internet-authentication"></a><span data-ttu-id="f1cfd-102">Internet 身份验证</span><span class="sxs-lookup"><span data-stu-id="f1cfd-102">Internet Authentication</span></span>
<span data-ttu-id="f1cfd-103"><xref:System.Net> 类支持多种客户端身份验证机制，包括标准 Internet 身份验证方法、基本、摘要式、协商、NTLM 和 Kerberos 身份验证，以及可以创建的自定义方法。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-103">The <xref:System.Net> classes support a variety of client authentication mechanisms, including the standard Internet authentication methods basic, digest, negotiate, NTLM, and Kerberos authentication, as well as custom methods that you can create.</span></span>  
  
 <span data-ttu-id="f1cfd-104">身份验证凭据存储在实现 <xref:System.Net.ICredentials> 接口的 <xref:System.Net.NetworkCredential> 和 <xref:System.Net.CredentialCache> 类中。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-104">Authentication credentials are stored in the <xref:System.Net.NetworkCredential> and <xref:System.Net.CredentialCache> classes, which implement the <xref:System.Net.ICredentials> interface.</span></span> <span data-ttu-id="f1cfd-105">在查询其中一个类以获取凭据时，它会返回 NetworkCredential 类的实例。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-105">When one of these classes is queried for credentials, it returns an instance of the **NetworkCredential** class.</span></span> <span data-ttu-id="f1cfd-106">身份验证过程由 <xref:System.Net.AuthenticationManager> 类管理，而实际的身份验证过程由实现 <xref:System.Net.IAuthenticationModule> 接口的身份验证模块类执行。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-106">The authentication process is managed by the <xref:System.Net.AuthenticationManager> class, and the actual authentication process is performed by an authentication module class that implements the <xref:System.Net.IAuthenticationModule> interface.</span></span> <span data-ttu-id="f1cfd-107">必须首先向 AuthenticationManager 注册自定义身份验证模块才能使用此模块；基本、摘要式、协商、NTLM 和 Kerberos 身份验证方法的模块是默认注册的。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-107">You must register a custom authentication module with the **AuthenticationManager** before it can be used; modules for the basic, digest, negotiate, NTLM, and Kerberos authentication methods are registered by default.</span></span>  
  
 <span data-ttu-id="f1cfd-108">NetworkCredential 存储与由 URI 标识的单个 Internet 资源相关联的凭据集，并返回它们以响应任何对 <xref:System.Net.NetworkCredential.GetCredential%2A> 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-108">**NetworkCredential** stores a set of credentials associated with a single Internet resource identified by a URI and returns them in response to any call to the <xref:System.Net.NetworkCredential.GetCredential%2A> method.</span></span> <span data-ttu-id="f1cfd-109">NetworkCredential 类通常由访有限数量的 Internet 资源的应用程序使用，或者由在所有情况下使用同一凭据集的应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-109">The **NetworkCredential** class is typically used by applications that access a limited number of Internet resources or by applications that use the same set of credentials in all cases.</span></span>  
  
 <span data-ttu-id="f1cfd-110">CredentialCache 类存储各种 Web 资源的凭据集合。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-110">The **CredentialCache** class stores a collection of credentials for various Web resources.</span></span> <span data-ttu-id="f1cfd-111">调用 <xref:System.Net.CredentialCache.GetCredential%2A> 方法时，CredentialCache 会返回适合的凭据集，由 Web 资源的 URI 以及请求的身份验证方案来确定。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-111">When the <xref:System.Net.CredentialCache.GetCredential%2A> method is called, **CredentialCache** returns the proper set of credentials, as determined by the URI of the Web resource and the requested authentication scheme.</span></span> <span data-ttu-id="f1cfd-112">通过不同的身份验证方案使用各种 Internet 资源的应用程序可从使用 CredentialCache 中受益，因为此类可以存储所有凭据，并按照请求提供这些凭据。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-112">Applications that use a variety of Internet resources with different authentication schemes benefit from using the **CredentialCache** class, since it stores all the credentials and provides them as requested.</span></span>  
  
 <span data-ttu-id="f1cfd-113">Internet 资源请求身份验证时，<xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType> 方法将 <xref:System.Net.WebRequest> 发送给 AuthenticationManager，同时会发送对凭据的请求。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-113">When an Internet resource requests authentication, the <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType> method sends the <xref:System.Net.WebRequest> to the **AuthenticationManager** along with the request for credentials.</span></span> <span data-ttu-id="f1cfd-114">之后会根据以下过程对请求进行身份验证：</span><span class="sxs-lookup"><span data-stu-id="f1cfd-114">The request is then authenticated according to the following process:</span></span>  
  
1.  <span data-ttu-id="f1cfd-115">AuthenticationManager 按照注册的顺序在每个已注册的身份验证模块上调用 <xref:System.Net.IAuthenticationModule.Authenticate%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-115">The **AuthenticationManager** calls the <xref:System.Net.IAuthenticationModule.Authenticate%2A> method on each of the registered authentication modules in the order they were registered.</span></span> <span data-ttu-id="f1cfd-116">AuthenticationManager 使用第一个不返回 null 的模块来执行身份验证过程。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-116">The **AuthenticationManager** uses the first module that does not return **null** to carry out the authentication process.</span></span> <span data-ttu-id="f1cfd-117">此过程的详细信息根据所涉及到的身份验证模块类型而异。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-117">The details of the process vary depending on the type of authentication module involved.</span></span>  
  
2.  <span data-ttu-id="f1cfd-118">完成身份验证过程后，此身份验证模块向包含访问 Internet 资源所需的信息的 WebRequest 返回 <xref:System.Net.Authorization>。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-118">When the authentication process is complete, the authentication module returns an <xref:System.Net.Authorization> to the **WebRequest** that contains the information needed to access the Internet resource.</span></span>  
  
 <span data-ttu-id="f1cfd-119">某些身份验证方案可以对用户进行身份验证，而无需首先对资源发出请求。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-119">Some authentication schemes can authenticate a user without first making a request for a resource.</span></span> <span data-ttu-id="f1cfd-120">应用程序可以使用资源预先对用户进行身份验证以节省时间，这样可以减少至少到服务器的一个往返。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-120">An application can save time by preauthenticating the user with the resource, thus eliminating at least one round trip to the server.</span></span> <span data-ttu-id="f1cfd-121">或者，它也可以在程序启动期间执行身份验证，便于稍后更好地响应用户。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-121">Or, it can perform authentication during program startup in order to be more responsive to the user later.</span></span> <span data-ttu-id="f1cfd-122">可以使用预身份验证的身份验证方案将 <xref:System.Net.IAuthenticationModule.PreAuthenticate%2A> 属性设置为“true”。</span><span class="sxs-lookup"><span data-stu-id="f1cfd-122">Authentication schemes that can use preauthentication set the <xref:System.Net.IAuthenticationModule.PreAuthenticate%2A> property to **true**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1cfd-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1cfd-123">See Also</span></span>  
 [<span data-ttu-id="f1cfd-124">基本和摘要式身份验证</span><span class="sxs-lookup"><span data-stu-id="f1cfd-124">Basic and Digest Authentication</span></span>](../../../docs/framework/network-programming/basic-and-digest-authentication.md)  
 [<span data-ttu-id="f1cfd-125">NTLM 和 Kerberos 身份验证</span><span class="sxs-lookup"><span data-stu-id="f1cfd-125">NTLM and Kerberos Authentication</span></span>](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)  
 [<span data-ttu-id="f1cfd-126">网络编程中的安全性</span><span class="sxs-lookup"><span data-stu-id="f1cfd-126">Security in Network Programming</span></span>](../../../docs/framework/network-programming/security-in-network-programming.md)
