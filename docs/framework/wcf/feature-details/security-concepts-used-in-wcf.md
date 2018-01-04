---
title: "WCF 中使用的安全概念"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 142de63c3d61ae2ff7f89b1d602f2a48c739f53a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="security-concepts-used-in-wcf"></a><span data-ttu-id="350e2-102">WCF 中使用的安全概念</span><span class="sxs-lookup"><span data-stu-id="350e2-102">Security Concepts Used in WCF</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="350e2-103"> 安全性建立在已在各种安全基础架构中使用并部署的概念之上。</span><span class="sxs-lookup"><span data-stu-id="350e2-103"> security is built upon concepts already in use and deployed in various security infrastructures.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="350e2-104"> 支持这些基础结构的其中一些，如 HTTP 上的安全套接字层 (SSL) (HTTPS)。</span><span class="sxs-lookup"><span data-stu-id="350e2-104"> supports some of those infrastructures, such as Secure Sockets Layer (SSL) over HTTP (HTTPS).</span></span> <span data-ttu-id="350e2-105">但是，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 实现了针对 SOAP 编码消息的更新的可互操作安全标准（如 WS-Security），因此已不再仅仅是支持现有安全基础结构。</span><span class="sxs-lookup"><span data-stu-id="350e2-105">However, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] goes beyond supporting existing security infrastructures by implementing newer interoperable security standards (such as WS-Security) over SOAP-encoded messages.</span></span> <span data-ttu-id="350e2-106">无论是使用现有机制还是新的可互操作标准，其背后的安全概念都是相同的。</span><span class="sxs-lookup"><span data-stu-id="350e2-106">Whether you are using existing mechanisms or new interoperable standards, the security concepts behind both are the same.</span></span> <span data-ttu-id="350e2-107">理解现有基础结构以及较新的标准背后的概念对于为应用程序实现最佳安全模型至关重要。</span><span class="sxs-lookup"><span data-stu-id="350e2-107">Understanding the concepts behind existing infrastructures and the newer standards is central to implementing the best security model for an application.</span></span>  
  
## <a name="introduction-to-security-for-wcf-web-services"></a><span data-ttu-id="350e2-108">WCF Web 服务安全简介</span><span class="sxs-lookup"><span data-stu-id="350e2-108">Introduction to Security for WCF Web Services</span></span>  
 <span data-ttu-id="350e2-109">Microsoft 模式和实践组编写 WCF 安全指南即可以从此处下载了深入白皮书： [WCF 安全指南](http://go.microsoft.com/fwlink/?LinkId=210210)。</span><span class="sxs-lookup"><span data-stu-id="350e2-109">The Microsoft Patterns and Practices group wrote an in-depth whitepaper on WCF security guidance which is available for download here: [WCF Security Guide](http://go.microsoft.com/fwlink/?LinkId=210210).</span></span> <span data-ttu-id="350e2-110">该白皮书介绍了与 Web 服务有关的基本安全概念、关键 WCF 安全概念、Intranet 应用程序方案和 Internet 应用程序方案。</span><span class="sxs-lookup"><span data-stu-id="350e2-110">This whitepaper describes the fundamental security concepts as they relate to web services, key WCF security concepts, intranet application scenarios, and internet application scenarios.</span></span>  
  
## <a name="industry-wide-security-specifications"></a><span data-ttu-id="350e2-111">业界级安全规范</span><span class="sxs-lookup"><span data-stu-id="350e2-111">Industry-Wide Security Specifications</span></span>  
  
### <a name="public-key-infrastructure"></a><span data-ttu-id="350e2-112">公钥基础结构</span><span class="sxs-lookup"><span data-stu-id="350e2-112">Public Key Infrastructure</span></span>  
 <span data-ttu-id="350e2-113">公钥基础结构 (PKI) 是一种由数字证书、证书颁发机构以及其他注册机构所组成的系统，旨在通过使用公钥加密对电子事务中所涉及的各方进行检验和身份验证。</span><span class="sxs-lookup"><span data-stu-id="350e2-113">Public Key Infrastructure (PKI) is a system of digital certificates, certification authorities, and other registration authorities that verify and authenticate each party involved in an electronic transaction through the use of public key cryptography.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="350e2-114">[Windows Server 2008 R2 证书服务](http://go.microsoft.com/fwlink/?LinkId=210211)。</span><span class="sxs-lookup"><span data-stu-id="350e2-114"> [Windows Server 2008 R2 Certificate Services](http://go.microsoft.com/fwlink/?LinkId=210211).</span></span>  
  
### <a name="kerberos-protocol"></a><span data-ttu-id="350e2-115">Kerberos 协议</span><span class="sxs-lookup"><span data-stu-id="350e2-115">Kerberos Protocol</span></span>  
 <span data-ttu-id="350e2-116">*Kerberos 协议*是一种规范，为创建一种安全机制，对 Windows 域上的用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="350e2-116">The *Kerberos protocol* is a specification for creating a security mechanism that authenticates users on a Windows domain.</span></span> <span data-ttu-id="350e2-117">它允许用户建立针对域中的其他实体的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="350e2-117">It allows a user to establish a secure context with other entities within a domain.</span></span> <span data-ttu-id="350e2-118">Windows 2000 及版本更高的平台默认情况下使用 Kerberos 协议。</span><span class="sxs-lookup"><span data-stu-id="350e2-118">Windows 2000 and later platforms use the Kerberos protocol by default.</span></span> <span data-ttu-id="350e2-119">在创建将与 intranet 客户端进行交互的服务时，理解系统的机制非常有用。</span><span class="sxs-lookup"><span data-stu-id="350e2-119">Understanding the mechanisms of the system is useful when creating a service that will interact with intranet clients.</span></span> <span data-ttu-id="350e2-120">此外，由于*Web 服务安全性 Kerberos 绑定*的广泛发布，你可以使用 Kerberos 协议与 Internet 客户端通信 （即 Kerberos 协议是可互操作）。</span><span class="sxs-lookup"><span data-stu-id="350e2-120">In addition, since the *Web Services Security Kerberos Binding* is widely published, you can use the Kerberos protocol to communicate with Internet clients (that is, the Kerberos protocol is interoperable).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="350e2-121">如何在 Windows 中实现 Kerberos 协议，请参阅[Microsoft Kerberos](http://go.microsoft.com/fwlink/?LinkId=210212)。</span><span class="sxs-lookup"><span data-stu-id="350e2-121"> how the Kerberos protocol is implemented in Windows, see  [Microsoft Kerberos](http://go.microsoft.com/fwlink/?LinkId=210212).</span></span>  
  
### <a name="x509-certificates"></a><span data-ttu-id="350e2-122">X.509 证书</span><span class="sxs-lookup"><span data-stu-id="350e2-122">X.509 Certificates</span></span>  
 <span data-ttu-id="350e2-123">X.509 证书是安全应用程序中使用的主要凭据形式。</span><span class="sxs-lookup"><span data-stu-id="350e2-123">X.509 certificates are a primary credential form used in security applications.</span></span> <span data-ttu-id="350e2-124">有关详细信息 X.509 证书，请查看[X.509 公钥证书](http://go.microsoft.com/fwlink/?LinkId=210213)。</span><span class="sxs-lookup"><span data-stu-id="350e2-124">For more information on X.509 certificates see [X.509 Public Key Certificates](http://go.microsoft.com/fwlink/?LinkId=210213).</span></span> <span data-ttu-id="350e2-125">X.509 证书存储在证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="350e2-125">X.509 certificates are stored within a certificate store.</span></span> <span data-ttu-id="350e2-126">运行 Windows 的计算机有多种证书存储区，每一种都针对不同的用途。</span><span class="sxs-lookup"><span data-stu-id="350e2-126">A computer running Windows has several kinds of certificate stores, each with a different purpose.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="350e2-127">不同存储区，请参阅[证书存储](http://go.microsoft.com/fwlink/?LinkID=87787)。</span><span class="sxs-lookup"><span data-stu-id="350e2-127"> the different stores, see [Certificate Stores](http://go.microsoft.com/fwlink/?LinkID=87787).</span></span>  
  
## <a name="web-services-security-specifications"></a><span data-ttu-id="350e2-128">Web 服务安全规范</span><span class="sxs-lookup"><span data-stu-id="350e2-128">Web Services Security Specifications</span></span>  
 <span data-ttu-id="350e2-129">系统定义的绑定支持许多常用 Web 服务安全规范。</span><span class="sxs-lookup"><span data-stu-id="350e2-129">The system-defined bindings support many commonly used web services security specifications.</span></span> <span data-ttu-id="350e2-130">它们支持，请参阅有关的系统提供的绑定和 web 服务规范的完整列表：[协议支持的 Web 服务系统提供的互操作性绑定](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)</span><span class="sxs-lookup"><span data-stu-id="350e2-130">For a complete list of system-provided bindings and the web services specifications they support see: [Web Services Protocols Supported by System-Provided Interoperability Bindings](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)</span></span>  
  
## <a name="access-control-mechanisms"></a><span data-ttu-id="350e2-131">访问控制机制</span><span class="sxs-lookup"><span data-stu-id="350e2-131">Access Control Mechanisms</span></span>  
 <span data-ttu-id="350e2-132">WCF 提供了多种服务或操作的访问控制方式。</span><span class="sxs-lookup"><span data-stu-id="350e2-132">WCF provides a number of ways to control access to a service or operation.</span></span> <span data-ttu-id="350e2-133">其中包括：</span><span class="sxs-lookup"><span data-stu-id="350e2-133">Among them are</span></span>  
  
1.  <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
2.  <span data-ttu-id="350e2-134">ASP.NET 成员身份提供程序</span><span class="sxs-lookup"><span data-stu-id="350e2-134">ASP.NET Membership Provider</span></span>  
  
3.  <span data-ttu-id="350e2-135">ASP.NET 角色提供程序</span><span class="sxs-lookup"><span data-stu-id="350e2-135">ASP.NET Role Provider</span></span>  
  
4.  <span data-ttu-id="350e2-136">授权管理器</span><span class="sxs-lookup"><span data-stu-id="350e2-136">Authorization Manager</span></span>  
  
5.  <span data-ttu-id="350e2-137">标识模型</span><span class="sxs-lookup"><span data-stu-id="350e2-137">Identity Model</span></span>  
  
 <span data-ttu-id="350e2-138">有关详细信息这些主题，请参阅[访问控制机制](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)</span><span class="sxs-lookup"><span data-stu-id="350e2-138">For more information on these topics see, [Access Control Mechanisms](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="350e2-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="350e2-139">See Also</span></span>  
 [<span data-ttu-id="350e2-140">安全性概述</span><span class="sxs-lookup"><span data-stu-id="350e2-140">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="350e2-141">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="350e2-141">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
