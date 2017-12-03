---
title: "如何：在服务上模拟客户端"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, impersonation
- impersonation
- WCF, security
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de7bfb7d926f9aa75ccfcfe8a550a0dbae4e12ef
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-impersonate-a-client-on-a-service"></a><span data-ttu-id="30137-102">如何：在服务上模拟客户端</span><span class="sxs-lookup"><span data-stu-id="30137-102">How to: Impersonate a Client on a Service</span></span>
<span data-ttu-id="30137-103">如果在 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 服务上模拟客户端，则该服务可以代表该客户端执行操作。</span><span class="sxs-lookup"><span data-stu-id="30137-103">Impersonating a client on a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service enables the service to perform actions on behalf of the client.</span></span> <span data-ttu-id="30137-104">对于受访问控制列表 (ACL) 检查的操作（例如，访问计算机上的目录和文件，或访问 SQL Server 数据库），ACL 检查针对的是客户端用户帐户。</span><span class="sxs-lookup"><span data-stu-id="30137-104">For actions subject to access control list (ACL) checks, such as access to directories and files on a machine or access to a SQL Server database, the ACL check is against the client user account.</span></span> <span data-ttu-id="30137-105">本主题演示一些基本步骤，通过这些步骤，Windows 域中的客户端可以设置客户端模拟级别。</span><span class="sxs-lookup"><span data-stu-id="30137-105">This topic shows the basic steps required to enable a client in a Windows domain to set a client impersonation level.</span></span> <span data-ttu-id="30137-106">有关此操作的可运行示例，请参阅 [Impersonating the Client](../../../docs/framework/wcf/samples/impersonating-the-client.md)。</span><span class="sxs-lookup"><span data-stu-id="30137-106">For a working example of this, see [Impersonating the Client](../../../docs/framework/wcf/samples/impersonating-the-client.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="30137-107">客户端模拟，请参阅[委托和模拟](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)。</span><span class="sxs-lookup"><span data-stu-id="30137-107"> client impersonation, see [Delegation and Impersonation](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30137-108">当客户端和服务运行在同一计算机上，客户端运行在系统帐户（即 `Local System` 或 `Network Service`）下时，如果安全会话是使用状态安全上下文令牌建立的，则不能模拟客户端。</span><span class="sxs-lookup"><span data-stu-id="30137-108">When the client and service are running on the same computer and the client is running under a system account (that is, `Local System` or `Network Service`), the client cannot be impersonated when a secure session is established with stateful Security Context tokens.</span></span> <span data-ttu-id="30137-109">WinForms 或控制台应用程序通常运行在当前登录的帐户下，因此，默认情况下可以模拟该帐户。</span><span class="sxs-lookup"><span data-stu-id="30137-109">A WinForms or console application typically is run under the currently logged in account, so that account can be impersonated by default.</span></span> <span data-ttu-id="30137-110">但是，如果客户端为 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 页并且该页承载在 [!INCLUDE[iis601](../../../includes/iis601-md.md)] 或 IIS 7.0 中，则默认情况下，客户端会在 `Network Service` 帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="30137-110">However, when the client is an [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] page and that page is hosted in [!INCLUDE[iis601](../../../includes/iis601-md.md)] or IIS 7.0, then the client does run under the `Network Service` account by default.</span></span> <span data-ttu-id="30137-111">默认情况下，系统提供的所有支持安全会话的绑定都使用无状态安全上下文令牌。</span><span class="sxs-lookup"><span data-stu-id="30137-111">All of the system-provided bindings that support secure sessions use a stateless Security Context token by default.</span></span> <span data-ttu-id="30137-112">但如果客户端是 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 页，并且使用了安全会话以及有状态的安全上下文令牌，则无法模拟该客户端。</span><span class="sxs-lookup"><span data-stu-id="30137-112">However, if the client is an [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] page and secure sessions with stateful Security Context tokens are used, the client cannot be impersonated.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="30137-113">安全会话中使用有状态安全上下文令牌，请参阅[如何： 为安全会话创建安全上下文令牌](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)。</span><span class="sxs-lookup"><span data-stu-id="30137-113"> using stateful Security Context tokens in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-enable-impersonation-of-a-client-from-a-cached-windows-token-on-a-service"></a><span data-ttu-id="30137-114">根据缓存的 Windows 令牌在服务上启用客户端模拟</span><span class="sxs-lookup"><span data-stu-id="30137-114">To enable impersonation of a client from a cached Windows token on a service</span></span>  
  
1.  <span data-ttu-id="30137-115">创建服务。</span><span class="sxs-lookup"><span data-stu-id="30137-115">Create the service.</span></span> <span data-ttu-id="30137-116">有关此基本过程的教程，请参阅 [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="30137-116">For a tutorial of this basic procedure, see [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
2.  <span data-ttu-id="30137-117">使用采用 Windows 身份验证并创建会话的绑定，例如 <xref:System.ServiceModel.NetTcpBinding> 或 <xref:System.ServiceModel.WSHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="30137-117">Use a binding that uses Windows authentication and creates a session, such as <xref:System.ServiceModel.NetTcpBinding> or <xref:System.ServiceModel.WSHttpBinding>.</span></span>  
  
3.  <span data-ttu-id="30137-118">在创建服务接口的实现时，将 <xref:System.ServiceModel.OperationBehaviorAttribute> 类应用于要求客户端模拟的方法。</span><span class="sxs-lookup"><span data-stu-id="30137-118">When creating the implementation of the service's interface, apply the <xref:System.ServiceModel.OperationBehaviorAttribute> class to the method that requires client impersonation.</span></span> <span data-ttu-id="30137-119">将 <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> 属性设置为 <xref:System.ServiceModel.ImpersonationOption.Required>。</span><span class="sxs-lookup"><span data-stu-id="30137-119">Set the <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> property to <xref:System.ServiceModel.ImpersonationOption.Required>.</span></span>  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### <a name="to-set-the-allowed-impersonation-level-on-the-client"></a><span data-ttu-id="30137-120">设置客户端允许的模拟级别</span><span class="sxs-lookup"><span data-stu-id="30137-120">To set the allowed impersonation level on the client</span></span>  
  
1.  <span data-ttu-id="30137-121">通过使用 [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)创建服务客户端代码。</span><span class="sxs-lookup"><span data-stu-id="30137-121">Create service client code by using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="30137-122">[使用 WCF 客户端访问服务](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md)。</span><span class="sxs-lookup"><span data-stu-id="30137-122"> [Accessing Services Using a WCF Client](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="30137-123">创建 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端后，将 <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> 类的 <xref:System.ServiceModel.Security.WindowsClientCredential> 属性设置为 <xref:System.Security.Principal.TokenImpersonationLevel> 枚举值之一。</span><span class="sxs-lookup"><span data-stu-id="30137-123">After creating the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client, set the <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> property of the <xref:System.ServiceModel.Security.WindowsClientCredential> class to one of the <xref:System.Security.Principal.TokenImpersonationLevel> enumeration values.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="30137-124">若要使用 <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>，则必须使用协商 Kerberos 身份验证（有时称为“多段”  或“多步”  Kerberos）。</span><span class="sxs-lookup"><span data-stu-id="30137-124">To use <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>, negotiated Kerberos authentication (sometimes called *multi-leg* or *multi-step* Kerberos) must be used.</span></span> <span data-ttu-id="30137-125">有关如何实现这一方案的说明，请参阅[安全性的最佳做法](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md)。</span><span class="sxs-lookup"><span data-stu-id="30137-125">For a description of how to implement this, see [Best Practices for Security](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).</span></span>  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="30137-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30137-126">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 [<span data-ttu-id="30137-127">模拟客户端</span><span class="sxs-lookup"><span data-stu-id="30137-127">Impersonating the Client</span></span>](../../../docs/framework/wcf/samples/impersonating-the-client.md)  
 [<span data-ttu-id="30137-128">委托和模拟</span><span class="sxs-lookup"><span data-stu-id="30137-128">Delegation and Impersonation</span></span>](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
