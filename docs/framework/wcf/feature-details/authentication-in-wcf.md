---
title: WCF 中的身份验证
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: a4f9b719024db1334b599f0f02fe01bc083bf3c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="e96df-102">WCF 中的身份验证</span><span class="sxs-lookup"><span data-stu-id="e96df-102">Authentication in WCF</span></span>
<span data-ttu-id="e96df-103">以下主题中 Windows Communication Foundation (WCF) 提供身份验证，例如、 Windows 身份验证、 X.509 证书和用户名和密码显示多种不同的机制。</span><span class="sxs-lookup"><span data-stu-id="e96df-103">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e96df-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="e96df-104">In This Section</span></span>  
 [<span data-ttu-id="e96df-105">如何：使用 ASP.NET 成员资格提供程序</span><span class="sxs-lookup"><span data-stu-id="e96df-105">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="e96df-106">ASP.NET 功能包括成员资格和角色提供程序、用于存储用户名/密码对以供进行身份验证的数据库，以及用于身份验证的用户角色。</span><span class="sxs-lookup"><span data-stu-id="e96df-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="e96df-107">本主题介绍 WCF 服务如何使用相同的数据库用户进行身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="e96df-107">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="e96df-108">如何：使用自定义用户名和密码验证程序</span><span class="sxs-lookup"><span data-stu-id="e96df-108">How to: Use a Custom User Name and Password Validator</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="e96df-109">演示如何集成自定义用户名/密码验证程序。</span><span class="sxs-lookup"><span data-stu-id="e96df-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="e96df-110">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="e96df-110">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 <span data-ttu-id="e96df-111">作为额外的保护措施，客户端可以通过指定期望验证服务*标识*的服务。</span><span class="sxs-lookup"><span data-stu-id="e96df-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="e96df-112">如果期望的标识与服务返回的标识不匹配，则身份验证失败。</span><span class="sxs-lookup"><span data-stu-id="e96df-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="e96df-113">安全性协商和超时</span><span class="sxs-lookup"><span data-stu-id="e96df-113">Security Negotiation and Timeouts</span></span>](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <span data-ttu-id="e96df-114">说明如何使用 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> 类的 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> 属性。</span><span class="sxs-lookup"><span data-stu-id="e96df-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="e96df-115">调试 Windows 身份验证错误</span><span class="sxs-lookup"><span data-stu-id="e96df-115">Debugging Windows Authentication Errors</span></span>](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 <span data-ttu-id="e96df-116">重点说明使用 Windows 身份验证时所遇到的常见问题。</span><span class="sxs-lookup"><span data-stu-id="e96df-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e96df-117">参考</span><span class="sxs-lookup"><span data-stu-id="e96df-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="e96df-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="e96df-118">Related Sections</span></span>  
 [<span data-ttu-id="e96df-119">常用安全方案</span><span class="sxs-lookup"><span data-stu-id="e96df-119">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="e96df-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="e96df-120">See Also</span></span>  
 [<span data-ttu-id="e96df-121">安全性概述</span><span class="sxs-lookup"><span data-stu-id="e96df-121">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="e96df-122">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="e96df-122">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
