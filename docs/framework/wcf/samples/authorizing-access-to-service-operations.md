---
title: 授予对服务操作的访问权限
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, authorizing access sample
- Authorizing Access To Service Operations Sample [Windows Communication Foundation]
- authorization, Windows Communication Foundation sample
ms.assetid: ddcfdaa5-8b2e-4e13-bd85-887209dc6328
ms.openlocfilehash: c2ad6977674666ef65df1ea4cfe58cfd4bff8b69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183926"
---
# <a name="authorizing-access-to-service-operations"></a>授予对服务操作的访问权限
此示例演示如何使用[\<服务授权>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)启用使用属性<xref:System.Security.Permissions.PrincipalPermissionAttribute>来授权访问服务操作。 此示例基于["入门"](../../../../docs/framework/wcf/samples/getting-started-sample.md)示例。 服务和客户端使用[\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)配置。 `mode``Message``clientCredentialType`[安全\<>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)的属性已设置为 ，并已设置为`Windows`。 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 应用到每个服务方法并用于限制对每个操作的访问。 调用方必须是 Windows 管理员才能访问每项操作。  
  
 在此示例中，客户端是一个控制台应用程序 (.exe)，服务是由 Internet 信息服务 (IIS) 承载的。  
  
> [!NOTE]
> 本主题的最后介绍了此示例的设置过程和生成说明。  
  
 服务配置文件使用[\<服务授权>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)来设置属性`principalPermissionMode`：  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior>
      <!-- The serviceAuthorization behavior sets the  
           principalPermissionMode to UseWindowsGroups.  
           This puts a WindowsPrincipal on the current thread when a   
           service is invoked. -->  
      <serviceAuthorization principalPermissionMode="UseWindowsGroups" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 将 `principalPermissionMode` 设置为 `UseWindowsGroups` 可使用基于 Windows 组名的 <xref:System.Security.Permissions.PrincipalPermissionAttribute>。  
  
 将 <xref:System.Security.Permissions.PrincipalPermissionAttribute> 应用于每个操作以要求调用方是 Windows 管理员组的成员，如下面的示例代码所示。  
  
```csharp
[PrincipalPermission(SecurityAction.Demand,
                             Role = "Builtin\\Administrators")]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    return result;  
}  
```  
  
 运行示例时，操作请求和响应将显示在客户端控制台窗口中。 如果客户端在管理员组成员的账户下运行，客户端可与每个操作成功通信；否则访问被拒绝。 若要体验授权失败，请在不是管理员组成员的账户下运行客户端。 在控制台窗口中按 Enter 可以关闭客户端。  
  
 通过实现 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 可以通知服务授权失败。 有关实现`IErrorHandler`的信息[，请参阅扩展对错误处理和报告的控制](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md)。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1. 确保已为 Windows[通信基础示例执行一次性设置过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2. 若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。  
  
3. 要在单计算机或跨计算机配置中运行示例，请按照[运行 Windows 通信基础示例中的](../../../../docs/framework/wcf/samples/running-the-samples.md)说明操作。  
