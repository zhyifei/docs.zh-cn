---
title: 模拟客户端
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, impersonation sample
- Impersonating the Client Sample [Windows Communication Foundation]
- impersonation, Windows Communication Foundation sample
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
ms.openlocfilehash: 10a8d243b3f053879f183864e955d9260c07865b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183615"
---
# <a name="impersonating-the-client"></a>模拟客户端
此模拟示例演示如何在服务中模拟调用方应用程序，以便服务可以代表调用方访问系统资源。  
  
 此示例基于[自主机](../../../../docs/framework/wcf/samples/self-host.md)示例。 服务和客户端配置文件与[自主机](../../../../docs/framework/wcf/samples/self-host.md)示例相同。  
  
> [!NOTE]
> 本主题的最后介绍了此示例的设置过程和生成说明。  
  
 对于服务代码已经进行了修改，以便服务上的 `Add` 方法使用 <xref:System.ServiceModel.OperationBehaviorAttribute> 来模拟调用方，如下面的示例代码中所示。  
  
```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    Console.WriteLine("Received Add({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 因此，执行线程的安全上下文将在进入 `Add` 方法之前进行切换以模拟调用方，并在退出该方法时恢复。  
  
 以下示例代码中所示的 `DisplayIdentityInformation` 方法是一个用来显示调用方标识的实用工具函数。  
  
```csharp
static void DisplayIdentityInformation()  
{  
    Console.WriteLine("\t\tThread Identity            :{0}",  
         WindowsIdentity.GetCurrent().Name);  
    Console.WriteLine("\t\tThread Identity level  :{0}",
         WindowsIdentity.GetCurrent().ImpersonationLevel);  
    Console.WriteLine("\t\thToken                     :{0}",  
         WindowsIdentity.GetCurrent().Token.ToString());  
    return;  
}  
```  
  
 服务上的 `Subtract` 方法使用命令性调用来模拟调用方，如下面的示例代码中所示。  
  
```csharp
public double Subtract(double n1, double n2)  
{  
    double result = n1 - n2;  
    Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    Console.WriteLine("Before impersonating");  
    DisplayIdentityInformation();  
  
    if (ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Impersonation ||  
        ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Delegation)  
    {  
        // Impersonate.  
        using (ServiceSecurityContext.Current.WindowsIdentity.Impersonate())  
        {  
            // Make a system call in the caller's context and ACLs
            // on the system resource are enforced in the caller's context.
            Console.WriteLine("Impersonating the caller imperatively");  
            DisplayIdentityInformation();  
        }  
    }  
    else  
    {  
        Console.WriteLine("ImpersonationLevel is not high enough to perform this operation.");  
    }  
  
    Console.WriteLine("After reverting");  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 请注意，在本例中，并未针对整个调用模拟调用方，而只是针对调用的一部分来模拟调用方。 通常，针对最小范围进行模拟比针对整个操作进行模拟更可取。  
  
 其他方法不能模拟调用方。  
  
 已经对客户端代码进行了修改，以便将模拟级别设置为 <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>。 客户端通过使用 <xref:System.Security.Principal.TokenImpersonationLevel> 枚举来指定要由服务使用的模拟级别。 枚举支持下列值：<xref:System.Security.Principal.TokenImpersonationLevel.None>、<xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>、<xref:System.Security.Principal.TokenImpersonationLevel.Identification>、<xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> 和 <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>。 如果要在访问使用 Windows ACL 保护的本地计算机上的系统资源时执行访问检查，则必须将模拟级别设置为 <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>，如下面的示例代码中所示。  
  
```csharp
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 运行示例时，操作请求和响应将显示在服务和客户端控制台窗口中。 在每个控制台窗口中按 Enter 可以关闭服务和客户端。  
  
> [!NOTE]
> 服务必须在管理帐户下运行，或者必须授予其运行的帐户向 HTTP 层注册`http://localhost:8000/ServiceModelSamples`URI 的权限。 可以使用[Httpcfg.exe 工具](/windows/win32/http/httpcfg-exe)设置[命名空间保留](/windows/win32/http/namespace-reservations-registrations-and-routing)来授予此类权限。  
  
> [!NOTE]
> 在运行 Windows Server 2003 的计算机上，仅当 Host.exe 应用程序具有模拟权限时，才支持模拟。 （默认情况下，只有管理员具有此权限。要将此权限添加到服务运行的帐户，请转到**管理工具**、打开**本地安全策略**、打开**本地策略**、单击 **"用户权限分配**"，然后选择 **"身份验证后模拟客户端**"和"双击**属性**"以添加用户或组。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1. 确保已为 Windows[通信基础示例执行一次性设置过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2. 若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。  
  
3. 要在单机或跨计算机配置中运行示例，请按照[运行 Windows 通信基础示例中的](../../../../docs/framework/wcf/samples/running-the-samples.md)说明操作。  
  
4. 若要演示服务对调用方的模拟，请在与运行服务时所用帐户不同的其他帐户下运行客户端。 为此，请在命令提示符下键入：  
  
    ```console  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     系统随后将提示您输入一个密码。 请输入您以前为帐户指定的密码。  
  
5. 运行客户端时，请注意它在用不同的凭据运行前后的标识。  
