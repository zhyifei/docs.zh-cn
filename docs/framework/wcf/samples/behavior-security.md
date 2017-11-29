---
title: "行为安全"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19710ae3-f197-4d28-ba9d-52e465006819
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9182c95b9770cac94b2a747e277fcd0cc02b387f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="behavior-security"></a><span data-ttu-id="5f9dc-102">行为安全</span><span class="sxs-lookup"><span data-stu-id="5f9dc-102">Behavior Security</span></span>
<span data-ttu-id="5f9dc-103">本节包含演示服务行为的配置安全的示例。</span><span class="sxs-lookup"><span data-stu-id="5f9dc-103">This section includes samples that demonstrate configuring security for service behaviors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f9dc-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="5f9dc-104">In This Section</span></span>  
 [<span data-ttu-id="5f9dc-105">服务审核行为</span><span class="sxs-lookup"><span data-stu-id="5f9dc-105">Service Auditing Behavior</span></span>](../../../../docs/framework/wcf/samples/service-auditing-behavior.md)  
 <span data-ttu-id="5f9dc-106">此示例演示如何在服务操作过程中使用 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> 来启用对安全事件的审核。</span><span class="sxs-lookup"><span data-stu-id="5f9dc-106">This sample demonstrates how to use the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to enable auditing of security events during service operations.</span></span>  
  
 [<span data-ttu-id="5f9dc-107">成员资格和角色提供程序</span><span class="sxs-lookup"><span data-stu-id="5f9dc-107">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 <span data-ttu-id="5f9dc-108">此示例演示服务如何使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 成员资格和角色提供程序来对客户端进行身份验证和授权。</span><span class="sxs-lookup"><span data-stu-id="5f9dc-108">This sample demonstrates how a service can use the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership and role providers to authenticate and authorize clients.</span></span>  
  
 [<span data-ttu-id="5f9dc-109">授予对服务操作访问权限</span><span class="sxs-lookup"><span data-stu-id="5f9dc-109">Authorizing Access to Service Operations</span></span>](../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 <span data-ttu-id="5f9dc-110">此示例演示如何使用[ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)地使用<xref:System.Security.Permissions.PrincipalPermissionAttribute>特性以授予服务操作访问权限。</span><span class="sxs-lookup"><span data-stu-id="5f9dc-110">This sample demonstrates how to use the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to enable use of the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to authorize access to service operations.</span></span>  
  
 [<span data-ttu-id="5f9dc-111">模拟客户端</span><span class="sxs-lookup"><span data-stu-id="5f9dc-111">Impersonating the Client</span></span>](../../../../docs/framework/wcf/samples/impersonating-the-client.md)  
 <span data-ttu-id="5f9dc-112">此示例演示如何在服务中模拟调用方应用程序，以便服务可以代表调用方访问系统资源。</span><span class="sxs-lookup"><span data-stu-id="5f9dc-112">This sample demonstrates how to impersonate the caller application at the service so that the service can access system resources on behalf of the caller.</span></span>
