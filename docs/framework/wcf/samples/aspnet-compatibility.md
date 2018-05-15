---
title: ASP.NET 兼容性
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: f621a3f13fafee67a015d463898a10aaf9104008
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="aspnet-compatibility"></a><span data-ttu-id="96b73-102">ASP.NET 兼容性</span><span class="sxs-lookup"><span data-stu-id="96b73-102">ASP.NET Compatibility</span></span>
<span data-ttu-id="96b73-103">此示例演示如何启用[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]兼容模式中 Windows Communication Foundation (WCF)。</span><span class="sxs-lookup"><span data-stu-id="96b73-103">This sample demonstrates how to enable [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Compatibility mode in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="96b73-104">在 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 兼容性模式中运行的服务可完全参与 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 应用程序管道并可利用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 功能，如文件/URL 授权、会话状态和 <xref:System.Web.HttpContext> 类。</span><span class="sxs-lookup"><span data-stu-id="96b73-104">Services running in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Compatibility mode participate fully in the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] application pipeline and can make use of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] features such as file/URL authorization, session state, and the <xref:System.Web.HttpContext> class.</span></span> <span data-ttu-id="96b73-105">使用 <xref:System.Web.HttpContext> 类可以访问 Cookie、会话和其他 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 功能。</span><span class="sxs-lookup"><span data-stu-id="96b73-105">The <xref:System.Web.HttpContext> class allows access to cookies, sessions, and other [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] features.</span></span> <span data-ttu-id="96b73-106">此模式要求绑定使用 HTTP 传输，且服务本身必须承载于 IIS 中。</span><span class="sxs-lookup"><span data-stu-id="96b73-106">This mode requires that the bindings use the HTTP transport and the service itself must be hosted in IIS.</span></span>  
  
 <span data-ttu-id="96b73-107">在此示例中，客户端是一个控制台应用程序（一个可执行文件），服务由 Internet 信息服务 (IIS) 承载。</span><span class="sxs-lookup"><span data-stu-id="96b73-107">In this sample, the client is a console application (an executable) and the service is hosted in Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96b73-108">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="96b73-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96b73-109">此示例需要 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 应用程序池才能运行。</span><span class="sxs-lookup"><span data-stu-id="96b73-109">This sample requires a [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] application pool in order to run.</span></span> <span data-ttu-id="96b73-110">若要创建新的应用程序池或修改默认应用程序池，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="96b73-110">To create a new application pool, or to modify the default application pool, follow these steps.</span></span>  
>   
>  1.  <span data-ttu-id="96b73-111">打开“控制面板” 。</span><span class="sxs-lookup"><span data-stu-id="96b73-111">Open **Control Panel**.</span></span>  <span data-ttu-id="96b73-112">打开**管理工具**下的小程序**系统和安全**标题。</span><span class="sxs-lookup"><span data-stu-id="96b73-112">Open the **Administrative Tools** applet under the **System and Security** heading.</span></span> <span data-ttu-id="96b73-113">打开**Internet Information Services (IIS) Manager**小程序。</span><span class="sxs-lookup"><span data-stu-id="96b73-113">Open the **Internet Information Services (IIS) Manager** applet.</span></span>  
> 2.  <span data-ttu-id="96b73-114">展开中的树视图**连接**窗格。</span><span class="sxs-lookup"><span data-stu-id="96b73-114">Expand the treeview in the **Connections** pane.</span></span> <span data-ttu-id="96b73-115">选择**应用程序池**节点。</span><span class="sxs-lookup"><span data-stu-id="96b73-115">Select the **Application Pools** node.</span></span>  
> 3.  <span data-ttu-id="96b73-116">若要设置要使用的默认应用程序池[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]（它可能会导致与现有站点的不兼容问题），右键单击**DefaultAppPool**列表项，然后选择**基本设置...**.</span><span class="sxs-lookup"><span data-stu-id="96b73-116">To set the default application pool to use [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (which may cause incompatibility problems with existing sites), right-click the **DefaultAppPool** list item and select **Basic Settings…**.</span></span> <span data-ttu-id="96b73-117">设置 **.Net Framework 版本**到 **.Net Framework v4.0.30128** （或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="96b73-117">Set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span>  
> 4.  <span data-ttu-id="96b73-118">若要创建新的应用程序池使用[!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]（以保持与其他应用程序兼容性），右键单击**应用程序池**节点，然后选择**添加应用程序池...**.</span><span class="sxs-lookup"><span data-stu-id="96b73-118">To create a new application pool that uses [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (to preserve compatibility for other applications), right-click the **Application Pools** node and select **Add Application Pool…**.</span></span> <span data-ttu-id="96b73-119">命名新的应用程序池，并设置 **.Net Framework 版本**到 **.Net Framework v4.0.30128** （或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="96b73-119">Name the new application pool, and set the **.Net Framework Version** pull-down to **.Net Framework v4.0.30128** (or later).</span></span> <span data-ttu-id="96b73-120">运行安装程序下面的步骤后，右键单击**ServiceModelSamples**应用程序并选择**管理应用程序**，**高级设置...**.</span><span class="sxs-lookup"><span data-stu-id="96b73-120">After running the setup steps below, right-click the **ServiceModelSamples** application and select **Manage Application**, **Advanced Settings…**.</span></span> <span data-ttu-id="96b73-121">设置**应用程序池**到新的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="96b73-121">Set the **Application Pool** to the new application pool.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="96b73-122">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="96b73-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="96b73-123">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="96b73-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="96b73-124">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="96b73-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="96b73-125">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="96b73-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 <span data-ttu-id="96b73-126">此示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)，该类可实现计算器服务。</span><span class="sxs-lookup"><span data-stu-id="96b73-126">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements a calculator service.</span></span> <span data-ttu-id="96b73-127">`ICalculator` 协定已根据 `ICalculatorSession` 协定进行修改，允许在保持运行结果的同时执行一组运算。</span><span class="sxs-lookup"><span data-stu-id="96b73-127">The `ICalculator` contract has been modified as the `ICalculatorSession` contract to allow a set of operations to be performed, while keeping a running result.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculatorSession  
{  
    [OperationContract]  
    void Clear();  
    [OperationContract]  
    void AddTo(double n);  
    [OperationContract]  
    void SubtractFrom(double n);  
    [OperationContract]  
    void MultiplyBy(double n);  
    [OperationContract]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 <span data-ttu-id="96b73-128">在调用多个服务操作来执行计算时，服务将使用该功能保持每个客户端的状态。</span><span class="sxs-lookup"><span data-stu-id="96b73-128">The service maintains state, using the feature, for each client as multiple service operations are called to perform a calculation.</span></span> <span data-ttu-id="96b73-129">客户端可以通过调用 `Result` 来检索当前结果，通过调用 `Clear` 将结果清零。</span><span class="sxs-lookup"><span data-stu-id="96b73-129">The client can retrieve the current result by calling `Result` and can clear the result to zero by calling `Clear`.</span></span>  
  
 <span data-ttu-id="96b73-130">服务使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 会话来存储每个客户端会话的结果。</span><span class="sxs-lookup"><span data-stu-id="96b73-130">The service uses the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] session to store the result for each client session.</span></span> <span data-ttu-id="96b73-131">这使服务可以为跨多个服务调用的每个客户端保持运行结果。</span><span class="sxs-lookup"><span data-stu-id="96b73-131">This allows the service to maintain the running result for each client across multiple calls to the service.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="96b73-132"> 会话状态和 WCF 会话是截然不同的事物。</span><span class="sxs-lookup"><span data-stu-id="96b73-132"> session state and WCF sessions are very different things.</span></span>  <span data-ttu-id="96b73-133">请参阅[会话](../../../../docs/framework/wcf/samples/session.md)有关 WCF 会话的详细信息。</span><span class="sxs-lookup"><span data-stu-id="96b73-133">See the [Session](../../../../docs/framework/wcf/samples/session.md) for details on WCF sessions.</span></span>  
  
 <span data-ttu-id="96b73-134">服务直接依赖于 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 会话状态，并需要 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 兼容性模式才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="96b73-134">The service has an intimate dependency on [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] session state and requires [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] compatibility mode to function correctly.</span></span> <span data-ttu-id="96b73-135">这些要求是通过应用 `AspNetCompatibilityRequirements` 属性以声明性方式表示的。</span><span class="sxs-lookup"><span data-stu-id="96b73-135">These requirements are expressed declaratively by applying the `AspNetCompatibilityRequirements` attribute.</span></span>  
  
```  
[AspNetCompatibilityRequirements(RequirementsMode =  
                       AspNetCompatibilityRequirementsMode.Required)]  
public class CalculatorService : ICalculatorSession  
{  
    double Result  
    {  // store result in AspNet Session  
       get {  
          if (HttpContext.Current.Session["Result"] != null)  
             return (double)HttpContext.Current.Session["Result"];  
          return 0.0D;  
       }  
       set  
       {  
          HttpContext.Current.Session["Result"] = value;  
       }  
    }  
    public void Clear()  
    {  
        Result = 0.0D;  
    }  
    public void AddTo(double n)  
    {  
        Result += n;  
    }  
    public void SubtractFrom(double n)  
    {  
        Result -= n;  
    }  
    public void MultiplyBy(double n)  
    {  
        Result *= n;  
    }  
    public void DivideBy(double n)  
    {  
        Result /= n;  
    }  
    public double Result()  
    {  
        return Result;  
    }  
}  
```  
  
 <span data-ttu-id="96b73-136">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="96b73-136">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="96b73-137">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="96b73-137">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="96b73-138">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="96b73-138">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="96b73-139">请确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="96b73-139">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="96b73-140">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="96b73-140">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="96b73-141">生成解决方案后，运行 Setup.bat 在 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 中设置 ServiceModelSamples 应用程序。</span><span class="sxs-lookup"><span data-stu-id="96b73-141">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span></span> <span data-ttu-id="96b73-142">现在，ServiceModelSamples 目录应显示为 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 应用程序。</span><span class="sxs-lookup"><span data-stu-id="96b73-142">The ServiceModelSamples directory should now appear as an [!INCLUDE[iisver](../../../../includes/iisver-md.md)] Application.</span></span>  
  
4.  <span data-ttu-id="96b73-143">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="96b73-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b73-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="96b73-144">See Also</span></span>  
 [<span data-ttu-id="96b73-145">AppFabric 承载和持久性示例</span><span class="sxs-lookup"><span data-stu-id="96b73-145">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
