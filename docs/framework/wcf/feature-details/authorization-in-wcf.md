---
title: WCF 中的授权
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 26aa445f3136fcb16e2eb9cdce6b245476297dfd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650567"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="88d80-102">WCF 中的授权</span><span class="sxs-lookup"><span data-stu-id="88d80-102">Authorization in WCF</span></span>
<span data-ttu-id="88d80-103">授权是控制对资源（例如服务或文件）的访问和权限的过程。</span><span class="sxs-lookup"><span data-stu-id="88d80-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="88d80-104">在本部分中的主题说明如何在 Windows Communication Foundation (WCF) 在不同的方式执行此基本任务。</span><span class="sxs-lookup"><span data-stu-id="88d80-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="88d80-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="88d80-105">In This Section</span></span>  
 [<span data-ttu-id="88d80-106">访问控制机制</span><span class="sxs-lookup"><span data-stu-id="88d80-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="88d80-107">简要介绍了 WCF，并建议的使用的授权机制。</span><span class="sxs-lookup"><span data-stu-id="88d80-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="88d80-108">如何：使用 PrincipalPermissionAttribute 类限制访问</span><span class="sxs-lookup"><span data-stu-id="88d80-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="88d80-109">演示使用 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 限制对服务的访问的过程。</span><span class="sxs-lookup"><span data-stu-id="88d80-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="88d80-110">如何：与服务一起使用 ASP.NET 角色提供程序</span><span class="sxs-lookup"><span data-stu-id="88d80-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="88d80-111">演练对服务的配置，使其能够使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 的角色提供程序功能。</span><span class="sxs-lookup"><span data-stu-id="88d80-111">Walks through the configuration of a service to enable it to use the role provider feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span></span>  
  
 [<span data-ttu-id="88d80-112">如何：将用于服务 ASP.NET 授权管理器角色提供程序</span><span class="sxs-lookup"><span data-stu-id="88d80-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] <span data-ttu-id="88d80-113">可以使用授权管理器来管理网站的授权。</span><span class="sxs-lookup"><span data-stu-id="88d80-113">can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="88d80-114">WCF 同样可以利用[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization Manager 组合来进行授权的客户端。</span><span class="sxs-lookup"><span data-stu-id="88d80-114">WCF can similarly leverage the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="88d80-115">使用标识模型管理声明和授权</span><span class="sxs-lookup"><span data-stu-id="88d80-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="88d80-116">说明将标识模型基础结构用于基于声明的授权的基础知识。</span><span class="sxs-lookup"><span data-stu-id="88d80-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="88d80-117">委托和模拟</span><span class="sxs-lookup"><span data-stu-id="88d80-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="88d80-118">说明委托和模拟之间的区别。</span><span class="sxs-lookup"><span data-stu-id="88d80-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="88d80-119">参考</span><span class="sxs-lookup"><span data-stu-id="88d80-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="88d80-120">相关章节</span><span class="sxs-lookup"><span data-stu-id="88d80-120">Related Sections</span></span>  
 [<span data-ttu-id="88d80-121">身份验证</span><span class="sxs-lookup"><span data-stu-id="88d80-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="88d80-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="88d80-122">See also</span></span>

- [<span data-ttu-id="88d80-123">安全性概述</span><span class="sxs-lookup"><span data-stu-id="88d80-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="88d80-124">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="88d80-124">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
