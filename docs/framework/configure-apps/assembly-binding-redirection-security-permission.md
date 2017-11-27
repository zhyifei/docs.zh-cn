---
title: "程序集绑定重定向安全权限"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: ddaf9965a3b3b5d6171a643b198db93309afad48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-binding-redirection-security-permission"></a>程序集绑定重定向安全权限
应用程序配置文件中的显式程序集绑定重定向需要安全权限。 这适用于对 .NET Framework 程序集和来自第三方的程序集的重定向。 通过设置授予此权限<xref:System.Security.Permissions.SecurityPermissionFlag>标志<xref:System.Security.Permissions.SecurityPermission>。 默认情况下，托管程序集具有任何权限。  
  
 安全权限授予的受信任的区域 （本地计算机） 和 Intranet 区域中运行应用程序。 在 Internet 区域中运行的应用程序严格禁止执行程序集绑定重定向。  
  
 如果控制由组件的发布者，发布服务器策略文件中或由管理员控制的计算机配置文件中执行程序集重定向，则不需要的权限。 但是，权限是若要显式忽略发行者策略使用的应用需要[ \<publisherPolicy 适用 ="no"/ >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)应用程序配置文件中的元素。  
  
 下表显示的默认安全设置**可**标志。  
  
|区域|可标志设置|  
|----------|-----------------------------------|  
|受信任的区域 （本地计算机）|**ON**|  
|Intranet 区域|**ON**|  
|Internet 区域|**关闭**|  
|不受信任的区域|**关闭**|  
  
 管理员可以更改这些安全设置以支持或限制由给定计算机上的特定方案。 没有用于更改工具**可**标志设置从默认设置; 管理员必须手动编辑用户的计算机上的 Security.config 文件。  
  
## <a name="see-also"></a>另请参阅  
 [发布服务器策略文件，并通过并行执行](http://msdn.microsoft.com/en-us/97a042be-4d72-40c3-91c0-76fd36bdf133)  
 [如何：启用和禁用自动绑定重定向](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [通过并行执行](../../../docs/framework/deployment/side-by-side-execution.md)
