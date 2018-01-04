---
title: "WCF 中的身份验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 432ed9debeffad82125b567508ed46b46d4b8821
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="03146-102">WCF 中的身份验证</span><span class="sxs-lookup"><span data-stu-id="03146-102">Authentication in WCF</span></span>
<span data-ttu-id="03146-103">下面的主题演示 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中用于提供身份验证的多个不同机制，例如 Windows 身份验证、X.509 证书以及用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="03146-103">The following topics show a number of different mechanisms in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="03146-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="03146-104">In This Section</span></span>  
 [<span data-ttu-id="03146-105">如何：使用 ASP.NET 成员资格提供程序</span><span class="sxs-lookup"><span data-stu-id="03146-105">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="03146-106">ASP.NET 功能包括成员资格和角色提供程序、用于存储用户名/密码对以供进行身份验证的数据库，以及用于身份验证的用户角色。</span><span class="sxs-lookup"><span data-stu-id="03146-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="03146-107">本主题说明 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务如何使用同一数据库对用户进行身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="03146-107">This topic explains how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="03146-108">如何：使用自定义用户名和密码验证程序</span><span class="sxs-lookup"><span data-stu-id="03146-108">How to: Use a Custom User Name and Password Validator</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="03146-109">演示如何集成自定义用户名/密码验证程序。</span><span class="sxs-lookup"><span data-stu-id="03146-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="03146-110">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="03146-110">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 <span data-ttu-id="03146-111">作为额外的保护措施，客户端可以通过指定期望验证服务*标识*的服务。</span><span class="sxs-lookup"><span data-stu-id="03146-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="03146-112">如果期望的标识与服务返回的标识不匹配，则身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="03146-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="03146-113">安全性协商和超时</span><span class="sxs-lookup"><span data-stu-id="03146-113">Security Negotiation and Timeouts</span></span>](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <span data-ttu-id="03146-114">说明如何使用 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> 类的 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> 属性。</span><span class="sxs-lookup"><span data-stu-id="03146-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="03146-115">调试 Windows 身份验证错误</span><span class="sxs-lookup"><span data-stu-id="03146-115">Debugging Windows Authentication Errors</span></span>](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 <span data-ttu-id="03146-116">重点说明使用 Windows 身份验证时所遇到的常见问题。</span><span class="sxs-lookup"><span data-stu-id="03146-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="03146-117">参考</span><span class="sxs-lookup"><span data-stu-id="03146-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="03146-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="03146-118">Related Sections</span></span>  
 [<span data-ttu-id="03146-119">常用安全方案</span><span class="sxs-lookup"><span data-stu-id="03146-119">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="03146-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="03146-120">See Also</span></span>  
 [<span data-ttu-id="03146-121">安全性概述</span><span class="sxs-lookup"><span data-stu-id="03146-121">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="03146-122">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="03146-122">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
