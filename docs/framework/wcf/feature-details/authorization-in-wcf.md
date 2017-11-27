---
title: "WCF 中的授权"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0c2afafa1d645ec0e95b7b41ff8389873969c89
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="8f48a-102">WCF 中的授权</span><span class="sxs-lookup"><span data-stu-id="8f48a-102">Authorization in WCF</span></span>
<span data-ttu-id="8f48a-103">授权是控制对资源（例如服务或文件）的访问和权限的过程。</span><span class="sxs-lookup"><span data-stu-id="8f48a-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="8f48a-104">本节中的主题演示如何在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中以多种方式执行此基本任务。</span><span class="sxs-lookup"><span data-stu-id="8f48a-104">The topics in this section show you how to perform this basic task in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f48a-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="8f48a-105">In This Section</span></span>  
 [<span data-ttu-id="8f48a-106">访问控制机制</span><span class="sxs-lookup"><span data-stu-id="8f48a-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="8f48a-107">概述 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中的授权机制，并给出了建议用法。</span><span class="sxs-lookup"><span data-stu-id="8f48a-107">Provides a brief outline of the authorization mechanisms in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], and suggested uses.</span></span>  
  
 [<span data-ttu-id="8f48a-108">如何：使用 PrincipalPermissionAttribute 类限制访问</span><span class="sxs-lookup"><span data-stu-id="8f48a-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="8f48a-109">演示使用 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 限制对服务的访问的过程。</span><span class="sxs-lookup"><span data-stu-id="8f48a-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="8f48a-110">如何： 与服务一起使用 ASP.NET 角色提供程序</span><span class="sxs-lookup"><span data-stu-id="8f48a-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="8f48a-111">演练对服务的配置，使其能够使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 的角色提供程序功能。</span><span class="sxs-lookup"><span data-stu-id="8f48a-111">Walks through the configuration of a service to enable it to use the role provider feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span></span>  
  
 [<span data-ttu-id="8f48a-112">如何： 将 ASP.NET 授权管理器角色提供程序用于服务</span><span class="sxs-lookup"><span data-stu-id="8f48a-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="8f48a-113"> 可以使用授权管理器来管理网站的授权。</span><span class="sxs-lookup"><span data-stu-id="8f48a-113"> can use the Authorization Manager to manage authorization for a Web site.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8f48a-114"> 同样可以利用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/授权管理器组合来对客户端进行授权。</span><span class="sxs-lookup"><span data-stu-id="8f48a-114"> can similarly leverage the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="8f48a-115">管理声明和使用标识模型的授权</span><span class="sxs-lookup"><span data-stu-id="8f48a-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="8f48a-116">说明将标识模型基础结构用于基于声明的授权的基础知识。</span><span class="sxs-lookup"><span data-stu-id="8f48a-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="8f48a-117">委托和模拟</span><span class="sxs-lookup"><span data-stu-id="8f48a-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="8f48a-118">说明委托和模拟之间的区别。</span><span class="sxs-lookup"><span data-stu-id="8f48a-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8f48a-119">参考</span><span class="sxs-lookup"><span data-stu-id="8f48a-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="8f48a-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="8f48a-120">Related Sections</span></span>  
 [<span data-ttu-id="8f48a-121">身份验证</span><span class="sxs-lookup"><span data-stu-id="8f48a-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="8f48a-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f48a-122">See Also</span></span>  
 [<span data-ttu-id="8f48a-123">安全性概述</span><span class="sxs-lookup"><span data-stu-id="8f48a-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="8f48a-124">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="8f48a-124">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
