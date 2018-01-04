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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac43b2185048287d0edd4cb20561a936bce2f58b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="authorization-in-wcf"></a>WCF 中的授权
授权是控制对资源（例如服务或文件）的访问和权限的过程。 本节中的主题演示如何在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中以多种方式执行此基本任务。  
  
## <a name="in-this-section"></a>本节内容  
 [访问控制机制](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 概述 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中的授权机制，并给出了建议用法。  
  
 [如何：使用 PrincipalPermissionAttribute 类限制访问](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 演示使用 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 限制对服务的访问的过程。  
  
 [如何：将 ASP.NET 角色提供程序与服务一起使用](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 演练对服务的配置，使其能够使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 的角色提供程序功能。  
  
 [如何：将 ASP.NET 授权管理器角色提供程序与服务一起使用](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 可以使用授权管理器来管理网站的授权。 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 同样可以利用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/授权管理器组合来对客户端进行授权。  
  
 [使用标识模型管理声明和授权](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 说明将标识模型基础结构用于基于声明的授权的基础知识。  
  
 [委托和模拟](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 说明委托和模拟之间的区别。  
  
## <a name="reference"></a>参考  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a>相关章节  
 [身份验证](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a>请参阅  
 [安全性概述](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Windows Server App Fabric 的安全模型](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
