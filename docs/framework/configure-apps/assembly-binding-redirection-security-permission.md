---
title: 程序集绑定重定向安全权限
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
ms.openlocfilehash: b59689e78f901637674c0a1df28ed74411e8e7c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921376"
---
# <a name="assembly-binding-redirection-security-permission"></a>程序集绑定重定向安全权限
应用程序配置文件中的显式程序集绑定重定向需要安全权限。 这适用于对 .NET Framework 程序集和来自第三方的程序集的重定向。 通过在<xref:System.Security.Permissions.SecurityPermissionFlag> <xref:System.Security.Permissions.SecurityPermission>上设置标志来授予权限。 默认情况下, 托管程序集没有权限。  
  
 此安全权限将授予受信任区域 (本地计算机) 和 Intranet 区域中运行的应用程序。 严格禁止在 Internet 区域中运行的应用程序执行程序集绑定重定向。  
  
 如果程序集重定向是在由组件发行者控制的发行者策略文件中执行, 或者在管理员控制的计算机配置文件中执行, 则不需要该权限。 但是, 应用程序需要权限才能使用应用程序配置文件中的[ \<publisherpolicy apply apply = "no"/>](./file-schema/runtime/publisherpolicy-element.md)元素显式忽略发布服务器策略。  
  
 下表显示了**BindingRedirects**标志的默认安全设置。  
  
|区域|BindingRedirects 标志设置|  
|----------|-----------------------------------|  
|受信任区域 (本地计算机)|**基于**|  
|Intranet 区域|**基于**|  
|Internet 区域|**OFF**|  
|不受信任区域|**OFF**|  
  
 管理员可以更改这些安全设置, 以支持或限制给定计算机上的特定方案。 没有用于更改**BindingRedirects**标志设置的默认值的工具;管理员必须手动编辑用户计算机上的安全配置文件。  
  
## <a name="see-also"></a>请参阅

- [发行者策略文件和并行执行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/06d2bae3(v=vs.100))
- [如何：启用和禁用自动绑定重定向](how-to-enable-and-disable-automatic-binding-redirection.md)
- [并行执行](../deployment/side-by-side-execution.md)
