---
title: "模拟客户端"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, impersonation sample
- Impersonating the Client Sample [Windows Communication Foundation]
- impersonation, Windows Communication Foundation sample
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15f0b0427dcbf12f476470369945044815cb3269
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="impersonating-the-client"></a><span data-ttu-id="88727-102">模拟客户端</span><span class="sxs-lookup"><span data-stu-id="88727-102">Impersonating the Client</span></span>
<span data-ttu-id="88727-103">此模拟示例演示如何在服务中模拟调用方应用程序，以便服务可以代表调用方访问系统资源。</span><span class="sxs-lookup"><span data-stu-id="88727-103">The Impersonation sample demonstrates how to impersonate the caller application at the service so that the service can access system resources on behalf of the caller.</span></span>  
  
 <span data-ttu-id="88727-104">此示例基于[自承载](../../../../docs/framework/wcf/samples/self-host.md)示例。</span><span class="sxs-lookup"><span data-stu-id="88727-104">This sample is based on the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md) sample.</span></span> <span data-ttu-id="88727-105">服务和客户端配置文件是相同的[自承载](../../../../docs/framework/wcf/samples/self-host.md)示例。</span><span class="sxs-lookup"><span data-stu-id="88727-105">The service and client configuration files are the same as that of the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md) sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88727-106">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="88727-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="88727-107">对于服务代码已经进行了修改，以便服务上的 `Add` 方法使用 <xref:System.ServiceModel.OperationBehaviorAttribute> 来模拟调用方，如下面的示例代码中所示。</span><span class="sxs-lookup"><span data-stu-id="88727-107">The service code has been modified such that the `Add` method on the service impersonates the caller using the <xref:System.ServiceModel.OperationBehaviorAttribute> as shown in the following sample code.</span></span>  
  
```  
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
  
 <span data-ttu-id="88727-108">因此，执行线程的安全上下文将在进入 `Add` 方法之前进行切换以模拟调用方，并在退出该方法时恢复。</span><span class="sxs-lookup"><span data-stu-id="88727-108">As a result, the security context of the executing thread is switched to impersonate the caller before entering the `Add` method and reverted on exiting the method.</span></span>  
  
 <span data-ttu-id="88727-109">以下示例代码中所示的 `DisplayIdentityInformation` 方法是一个用来显示调用方标识的实用工具函数。</span><span class="sxs-lookup"><span data-stu-id="88727-109">The `DisplayIdentityInformation` method shown in the following sample code is a utility function that displays the caller's identity.</span></span>  
  
```  
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
  
 <span data-ttu-id="88727-110">服务上的 `Subtract` 方法使用命令性调用来模拟调用方，如下面的示例代码中所示。</span><span class="sxs-lookup"><span data-stu-id="88727-110">The `Subtract` method on the service impersonates the caller using imperative calls as shown in the following sample code.</span></span>  
  
```  
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
  
 <span data-ttu-id="88727-111">请注意，在本例中，并未针对整个调用模拟调用方，而只是针对调用的一部分来模拟调用方。</span><span class="sxs-lookup"><span data-stu-id="88727-111">Note that in this case the caller is not impersonated for the entire call but is only impersonated for a portion of the call.</span></span> <span data-ttu-id="88727-112">通常，针对最小范围进行模拟比针对整个操作进行模拟更可取。</span><span class="sxs-lookup"><span data-stu-id="88727-112">In general, impersonating for the smallest scope is preferable to impersonating for the entire operation.</span></span>  
  
 <span data-ttu-id="88727-113">其他方法不能模拟调用方。</span><span class="sxs-lookup"><span data-stu-id="88727-113">The other methods do not impersonate the caller.</span></span>  
  
 <span data-ttu-id="88727-114">已经对客户端代码进行了修改，以便将模拟级别设置为 <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>。</span><span class="sxs-lookup"><span data-stu-id="88727-114">The client code has been modified to set the impersonation level to <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>.</span></span> <span data-ttu-id="88727-115">客户端通过使用 <xref:System.Security.Principal.TokenImpersonationLevel> 枚举来指定要由服务使用的模拟级别。</span><span class="sxs-lookup"><span data-stu-id="88727-115">The client specifies the impersonation level to be used by the service, by using the <xref:System.Security.Principal.TokenImpersonationLevel> enumeration.</span></span> <span data-ttu-id="88727-116">枚举支持下列值：<xref:System.Security.Principal.TokenImpersonationLevel.None>、<xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>、<xref:System.Security.Principal.TokenImpersonationLevel.Identification>、<xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> 和 <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>。</span><span class="sxs-lookup"><span data-stu-id="88727-116">The enumeration supports the following values: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> and <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>.</span></span> <span data-ttu-id="88727-117">如果要在访问使用 Windows ACL 保护的本地计算机上的系统资源时执行访问检查，则必须将模拟级别设置为 <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>，如下面的示例代码中所示。</span><span class="sxs-lookup"><span data-stu-id="88727-117">To perform an access check when accessing a system resource on the local machine that is protected using Windows ACLs, the impersonation level must be set to <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, as shown in the following sample code.</span></span>  
  
```  
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 <span data-ttu-id="88727-118">运行示例时，操作请求和响应将显示在服务和客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="88727-118">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="88727-119">在每个控制台窗口中按 Enter 可以关闭服务和客户端。</span><span class="sxs-lookup"><span data-stu-id="88727-119">Press ENTER in each console window to shut down the service and client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88727-120">服务必须在管理帐户下运行，或者运行服务时所使用的帐户必须被授予向 HTTP 层注册 http://localhost:8000/ServiceModelSamples URI 的权限。</span><span class="sxs-lookup"><span data-stu-id="88727-120">The service must either run under an administrative account or the account it runs under must be granted rights to register the http://localhost:8000/ServiceModelSamples URI with the HTTP layer.</span></span> <span data-ttu-id="88727-121">此类权限可以通过设置授予[Namespace 保留](http://go.microsoft.com/fwlink/?LinkId=95012)使用[Httpcfg.exe 工具](http://go.microsoft.com/fwlink/?LinkId=95010)。</span><span class="sxs-lookup"><span data-stu-id="88727-121">Such rights can be granted by setting up a [Namespace Reservation](http://go.microsoft.com/fwlink/?LinkId=95012) using the [Httpcfg.exe tool](http://go.microsoft.com/fwlink/?LinkId=95010).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="88727-122">在运行 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 的计算机上，只有当 Host.exe 应用程序具有“模拟”特权时，才支持进行模拟。</span><span class="sxs-lookup"><span data-stu-id="88727-122">On computers running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], impersonation is supported only if the Host.exe application has the Impersonation privilege.</span></span> <span data-ttu-id="88727-123">（默认情况下，只有管理员才具有此权限。）若要将此权限添加到服务所运行的帐户，请转到**管理工具**，打开**本地安全策略**，打开**本地策略**，单击**用户权限分配**，然后选择**身份验证后模拟客户端**双击**属性**以添加用户或组。</span><span class="sxs-lookup"><span data-stu-id="88727-123">(By default, only administrators have this permission.) To add this privilege to an account the service is running as, go to **Administrative Tools**, open **Local Security Policy**, open **Local Policies**, click **User Rights Assignment**, and select **Impersonate a Client after Authentication** and double-click **Properties** to add a user or group.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="88727-124">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="88727-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="88727-125">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="88727-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="88727-126">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="88727-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="88727-127">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="88727-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="88727-128">若要演示服务对调用方的模拟，请在与运行服务时所用帐户不同的其他帐户下运行客户端。</span><span class="sxs-lookup"><span data-stu-id="88727-128">To demonstrate that the service impersonates the caller, run the client under a different account than the one the service is running under.</span></span> <span data-ttu-id="88727-129">为此，请在命令提示符下键入：</span><span class="sxs-lookup"><span data-stu-id="88727-129">To do so, at the command prompt, type:</span></span>  
  
    ```  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     <span data-ttu-id="88727-130">系统随后将提示您输入一个密码。</span><span class="sxs-lookup"><span data-stu-id="88727-130">You are then prompted for a password.</span></span> <span data-ttu-id="88727-131">请输入您以前为帐户指定的密码。</span><span class="sxs-lookup"><span data-stu-id="88727-131">Enter the password for the account you previously specified.</span></span>  
  
5.  <span data-ttu-id="88727-132">运行客户端时，请注意它在用不同的凭据运行前后的标识。</span><span class="sxs-lookup"><span data-stu-id="88727-132">When you run the client, note the identity before and after running it with different credentials.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88727-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88727-133">See Also</span></span>
