---
title: "并发"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, concurency sample
- Concurrency Sample [Windows Communication Foundation]
ms.assetid: f8dbdfb3-6858-4f95-abe3-3a1db7878926
caps.latest.revision: "32"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c63882055718bd54d1983ea0aa10d208bd70793f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="concurrency"></a><span data-ttu-id="daeaf-102">并发</span><span class="sxs-lookup"><span data-stu-id="daeaf-102">Concurrency</span></span>
<span data-ttu-id="daeaf-103">“并发”示例演示如何使用具有 <xref:System.ServiceModel.ServiceBehaviorAttribute> 枚举的 <xref:System.ServiceModel.ConcurrencyMode>，该枚举控制服务的实例是依次还是同时处理消息。</span><span class="sxs-lookup"><span data-stu-id="daeaf-103">The Concurrency sample demonstrates using the <xref:System.ServiceModel.ServiceBehaviorAttribute> with the <xref:System.ServiceModel.ConcurrencyMode> enumeration, which controls whether an instance of a service processes messages sequentially or concurrently.</span></span> <span data-ttu-id="daeaf-104">示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)，该类实现`ICalculator`服务协定。</span><span class="sxs-lookup"><span data-stu-id="daeaf-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="daeaf-105">本示例定义从 `ICalculatorConcurrency` 中继承的新协定 `ICalculator`，该协定提供两个用于检查服务并发状态的附加操作。</span><span class="sxs-lookup"><span data-stu-id="daeaf-105">This sample defines a new contract, `ICalculatorConcurrency`, which inherits from `ICalculator`, providing two additional operations for inspecting the state of the service concurrency.</span></span> <span data-ttu-id="daeaf-106">通过更改并发设置，可以在运行客户端时观察到行为发生的变化。</span><span class="sxs-lookup"><span data-stu-id="daeaf-106">By altering the concurrency setting, you can observe the change in behavior by running the client.</span></span>  
  
 <span data-ttu-id="daeaf-107">在此示例中，客户端是一个控制台应用程序 (.exe)，服务是由 Internet 信息服务 (IIS) 承载的。</span><span class="sxs-lookup"><span data-stu-id="daeaf-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="daeaf-108">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="daeaf-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="daeaf-109">有三种可用的并发模式：</span><span class="sxs-lookup"><span data-stu-id="daeaf-109">There are three concurrency modes available:</span></span>  
  
-   <span data-ttu-id="daeaf-110">`Single`：每个服务实例一次处理一个消息。</span><span class="sxs-lookup"><span data-stu-id="daeaf-110">`Single`: Each service instance processes one message at a time.</span></span> <span data-ttu-id="daeaf-111">这是默认的并发模式。</span><span class="sxs-lookup"><span data-stu-id="daeaf-111">This is the default concurrency mode.</span></span>  
  
-   <span data-ttu-id="daeaf-112">`Multiple`：每个服务实例同时处理多个消息。</span><span class="sxs-lookup"><span data-stu-id="daeaf-112">`Multiple`: Each service instance processes multiple messages concurrently.</span></span> <span data-ttu-id="daeaf-113">若要使用此并发模式，服务实现必须是线程安全的。</span><span class="sxs-lookup"><span data-stu-id="daeaf-113">The service implementation must be thread-safe to use this concurrency mode.</span></span>  
  
-   <span data-ttu-id="daeaf-114">`Reentrant`：每个服务实例一次处理一个消息，但接受可重入调用。</span><span class="sxs-lookup"><span data-stu-id="daeaf-114">`Reentrant`: Each service instance processes one message at a time, but accepts reentrant calls.</span></span> <span data-ttu-id="daeaf-115">仅当服务对外调用时才会接受这些调用。在演示重入[ConcurrencyMode.Reentrant](../../../../docs/framework/wcf/samples/concurrencymode-reentrant.md)示例。</span><span class="sxs-lookup"><span data-stu-id="daeaf-115">The service only accepts these calls when it is calling out. Reentrant is demonstrated in the [ConcurrencyMode.Reentrant](../../../../docs/framework/wcf/samples/concurrencymode-reentrant.md) sample.</span></span>  
  
 <span data-ttu-id="daeaf-116">并发的使用与实例化模式有关。</span><span class="sxs-lookup"><span data-stu-id="daeaf-116">The use of concurrency is related to the instancing mode.</span></span> <span data-ttu-id="daeaf-117">在 <xref:System.ServiceModel.InstanceContextMode.PerCall> 实例化过程中，与并发没有关系，因为每个消息都由一个新服务实例处理。</span><span class="sxs-lookup"><span data-stu-id="daeaf-117">In <xref:System.ServiceModel.InstanceContextMode.PerCall> instancing, concurrency is not relevant, because each message is processed by a new service instance.</span></span> <span data-ttu-id="daeaf-118">在 <xref:System.ServiceModel.InstanceContextMode.Single> 实例化过程中，与 <xref:System.ServiceModel.ConcurrencyMode.Single> 或 <xref:System.ServiceModel.ConcurrencyMode.Multiple> 并发有关，具体取决于单个实例是依次还是同时处理消息。</span><span class="sxs-lookup"><span data-stu-id="daeaf-118">In <xref:System.ServiceModel.InstanceContextMode.Single> instancing, either <xref:System.ServiceModel.ConcurrencyMode.Single> or <xref:System.ServiceModel.ConcurrencyMode.Multiple> concurrency is relevant, depending on whether the single instance processes messages sequentially or concurrently.</span></span> <span data-ttu-id="daeaf-119">在 <xref:System.ServiceModel.InstanceContextMode.PerSession> 实例化过程中，可能与任何并发模式有关。</span><span class="sxs-lookup"><span data-stu-id="daeaf-119">In <xref:System.ServiceModel.InstanceContextMode.PerSession> instancing, any of the concurrency modes may be relevant.</span></span>  
  
 <span data-ttu-id="daeaf-120">服务类使用 `[ServiceBehavior(ConcurrencyMode=<setting>)]` 属性来指定并发行为，如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="daeaf-120">The service class specifies concurrency behavior with the `[ServiceBehavior(ConcurrencyMode=<setting>)]` attribute as shown in the code sample that follows.</span></span> <span data-ttu-id="daeaf-121">通过更换注释掉的行，您可以体验 `Single` 和 `Multiple` 并发模式。</span><span class="sxs-lookup"><span data-stu-id="daeaf-121">By changing which lines are commented out, you can experiment with the `Single` and `Multiple` concurrency modes.</span></span> <span data-ttu-id="daeaf-122">请记住，更改并发模式之后重新生成服务。</span><span class="sxs-lookup"><span data-stu-id="daeaf-122">Remember to rebuild the service after changing the concurrency mode.</span></span>  
  
```  
// Single allows a single message to be processed sequentially by each service instance.  
//[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, InstanceContextMode = InstanceContextMode.Single)]  
  
// Multiple allows concurrent processing of multiple messages by a service instance.  
// The service implementation should be thread-safe. This can be used to increase throughput.  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]  
  
// Uses Thread.Sleep to vary the execution time of each operation.  
public class CalculatorService : ICalculatorConcurrency  
{  
    int operationCount;  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(180);  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(100);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(150);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(120);  
        return n1 / n2;  
    }  
  
    public string GetConcurrencyMode()  
    {     
        // Return the ConcurrencyMode of the service.  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.ConcurrencyMode.ToString();  
    }  
  
    public int GetOperationCount()  
    {     
        // Return the number of operations.  
        return operationCount;  
    }  
}  
```  
  
 <span data-ttu-id="daeaf-123">默认情况下，此示例使用通过 <xref:System.ServiceModel.ConcurrencyMode.Multiple> 实例化的 <xref:System.ServiceModel.InstanceContextMode.Single> 并发。</span><span class="sxs-lookup"><span data-stu-id="daeaf-123">The sample uses <xref:System.ServiceModel.ConcurrencyMode.Multiple> concurrency with <xref:System.ServiceModel.InstanceContextMode.Single> instancing by default.</span></span> <span data-ttu-id="daeaf-124">已经对客户端代码进行了修改，以便使用异步代理。</span><span class="sxs-lookup"><span data-stu-id="daeaf-124">The client code has been modified to use an asynchronous proxy.</span></span> <span data-ttu-id="daeaf-125">这允许客户端对服务进行多个调用，而不必在每个调用之间的等待响应。</span><span class="sxs-lookup"><span data-stu-id="daeaf-125">This allows the client to make multiple calls to the service without waiting for a response between each call.</span></span> <span data-ttu-id="daeaf-126">您可以观察到服务并发模式的行为中的差异。</span><span class="sxs-lookup"><span data-stu-id="daeaf-126">You can observe the difference in behavior of the service concurrency mode.</span></span>  
  
 <span data-ttu-id="daeaf-127">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="daeaf-127">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="daeaf-128">显示运行服务所用的并发模式、调用每个操作，然后显示操作计数。</span><span class="sxs-lookup"><span data-stu-id="daeaf-128">The concurrency mode that the service is running under is displayed, each operation is called, and then the operation count is displayed.</span></span> <span data-ttu-id="daeaf-129">请注意，并发模式为 `Multiple` 时，返回结果的顺序与调用的顺序不同，因为服务同时处理多个消息。</span><span class="sxs-lookup"><span data-stu-id="daeaf-129">Notice that when the concurrency mode is `Multiple`, the results are returned in a different order than how they were called, because the service processes multiple messages concurrently.</span></span> <span data-ttu-id="daeaf-130">通过将并发模式更改为 `Single`，可以按调用顺序返回结果，因为服务按顺序处理每个消息。</span><span class="sxs-lookup"><span data-stu-id="daeaf-130">By changing the concurrency mode to `Single`, the results are returned in the order they were called, because the service processes each message sequentially.</span></span> <span data-ttu-id="daeaf-131">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="daeaf-131">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="daeaf-132">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="daeaf-132">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="daeaf-133">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="daeaf-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="daeaf-134">如果使用 Svcutil.exe 来生成客户端代理，确保包括`/async`选项。</span><span class="sxs-lookup"><span data-stu-id="daeaf-134">If you use Svcutil.exe to generate the proxy client, ensure that you include the `/async` option.</span></span>  
  
3.  <span data-ttu-id="daeaf-135">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="daeaf-135">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="daeaf-136">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="daeaf-136">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="daeaf-137">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="daeaf-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="daeaf-138">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="daeaf-138">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="daeaf-139">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="daeaf-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="daeaf-140">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="daeaf-140">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Concurrency`  
  
## <a name="see-also"></a><span data-ttu-id="daeaf-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="daeaf-141">See Also</span></span>
