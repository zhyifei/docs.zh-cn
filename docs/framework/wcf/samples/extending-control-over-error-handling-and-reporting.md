---
title: "扩展对错误处理和错误报告的控制"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45f996a7-fa00-45cb-9d6f-b368f5778aaa
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ab2e105c9055760bbeaeef5e56a8cb18c538306
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="extending-control-over-error-handling-and-reporting"></a><span data-ttu-id="33e47-102">扩展对错误处理和错误报告的控制</span><span class="sxs-lookup"><span data-stu-id="33e47-102">Extending Control Over Error Handling and Reporting</span></span>
<span data-ttu-id="33e47-103">此示例演示如何在 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务中使用 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 接口对错误处理和错误报告进行扩展控制。</span><span class="sxs-lookup"><span data-stu-id="33e47-103">This sample demonstrates how to extend control over error handling and error reporting in a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service using the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="33e47-104">示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)使用的一些其他代码添加到服务来处理错误。</span><span class="sxs-lookup"><span data-stu-id="33e47-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) with some additional code added to the service to handle errors.</span></span> <span data-ttu-id="33e47-105">客户端强制实施若干个错误条件。</span><span class="sxs-lookup"><span data-stu-id="33e47-105">The client forces several error conditions.</span></span> <span data-ttu-id="33e47-106">服务将截获这些错误并将其记录到某个文件中。</span><span class="sxs-lookup"><span data-stu-id="33e47-106">The service intercepts the errors and logs them in a file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33e47-107">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="33e47-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="33e47-108">服务可以截获错误、执行处理，并使用 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 接口影响错误报告的方式。</span><span class="sxs-lookup"><span data-stu-id="33e47-108">Services can intercept errors, perform processing, and affect how errors are reported using the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="33e47-109">该接口有两个可以实现的方法：<xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> 和 <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>。</span><span class="sxs-lookup"><span data-stu-id="33e47-109">The interface has two methods that can be implemented: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> and <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>.</span></span> <span data-ttu-id="33e47-110">通过 <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> 方法，您可以添加、修改或取消为响应异常而生成的错误消息。</span><span class="sxs-lookup"><span data-stu-id="33e47-110">The <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> method allows you to add, modify, or suppress a fault message that is generated in response to an exception.</span></span> <span data-ttu-id="33e47-111">通过 <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> 方法，您可以在发生错误时对错误进行处理，并控制是否可以运行其他错误处理。</span><span class="sxs-lookup"><span data-stu-id="33e47-111">The <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> method allows error processing to take place in the event of an error and controls whether additional error handling can run.</span></span>  
  
 <span data-ttu-id="33e47-112">在此示例中，`CalculatorErrorHandler` 类型实现 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 接口。</span><span class="sxs-lookup"><span data-stu-id="33e47-112">In this sample, the `CalculatorErrorHandler` type implements the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="33e47-113">在</span><span class="sxs-lookup"><span data-stu-id="33e47-113">In the</span></span>  
  
 <span data-ttu-id="33e47-114"><xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> 方法中，`CalculatorErrorHandler` 将错误日志写入 c:\logs 中的 Error.txt 文本文件中。</span><span class="sxs-lookup"><span data-stu-id="33e47-114"><xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> method, the `CalculatorErrorHandler` writes a log of the error to an Error.txt text file in c:\logs.</span></span> <span data-ttu-id="33e47-115">请注意，该示例记录错误而不会取消错误，并允许错误报告回客户端。</span><span class="sxs-lookup"><span data-stu-id="33e47-115">Note that the sample logs the fault and does not suppress it, allowing it to be reported back to the client.</span></span>  
  
```  
public class CalculatorErrorHandler : IErrorHandler  
{  
        // Provide a fault. The Message fault parameter can be replaced, or set to  
        // null to suppress reporting a fault.  
  
        public void ProvideFault(Exception error, MessageVersion version, ref Message fault)  
        {  
        }  
  
        // HandleError. Log an error, then allow the error to be handled as usual.  
        // Return true if the error is considered as already handled  
  
        public bool HandleError(Exception error)  
        {  
            using (TextWriter tw = File.AppendText(@"c:\logs\error.txt"))  
            {  
                if (error != null)  
                {  
                    tw.WriteLine("Exception: " + error.GetType().Name + " - " + error.Message);  
                }  
                tw.Close();  
            }  
            return true;  
        }  
    }  
```  
  
 <span data-ttu-id="33e47-116">`ErrorBehaviorAttribute` 作为一种向服务注册错误处理程序的机制存在。</span><span class="sxs-lookup"><span data-stu-id="33e47-116">The `ErrorBehaviorAttribute` exists as a mechanism to register an error handler with a service.</span></span> <span data-ttu-id="33e47-117">此属性采取单一的类型参数。</span><span class="sxs-lookup"><span data-stu-id="33e47-117">This attribute takes a single type parameter.</span></span> <span data-ttu-id="33e47-118">该类型应实现 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 接口，还应具有一个公用的空构造函数。</span><span class="sxs-lookup"><span data-stu-id="33e47-118">That type should implement the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface and should have a public, empty constructor.</span></span> <span data-ttu-id="33e47-119">该属性随后实例化该错误处理程序类型的实例，并将其安装到该服务中。</span><span class="sxs-lookup"><span data-stu-id="33e47-119">The attribute then instantiates an instance of that error handler type and installs it into the service.</span></span> <span data-ttu-id="33e47-120">实现此操作的方法是，实现 <xref:System.ServiceModel.Description.IServiceBehavior> 接口，然后使用 <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> 方法将错误处理程序的实例添加到该服务。</span><span class="sxs-lookup"><span data-stu-id="33e47-120">It does this by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface and then using the <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> method to add instances of the error handler to the service.</span></span>  
  
```  
// This attribute can be used to install a custom error handler for a service.  
public class ErrorBehaviorAttribute : Attribute, IServiceBehavior  
{  
    Type errorHandlerType;  
  
    public ErrorBehaviorAttribute(Type errorHandlerType)  
    {  
        this.errorHandlerType = errorHandlerType;  
    }  
  
    void IServiceBehavior.Validate(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
    }  
  
    void IServiceBehavior.AddBindingParameters(ServiceDescription description, ServiceHostBase serviceHostBase, System.Collections.ObjectModel.Collection<ServiceEndpoint> endpoints, BindingParameterCollection parameters)  
    {  
    }  
  
    void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
        IErrorHandler errorHandler;  
  
        try  
        {  
            errorHandler = (IErrorHandler)Activator.CreateInstance(errorHandlerType);  
        }  
        catch (MissingMethodException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must have a public empty constructor.", e);  
        }  
        catch (InvalidCastException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must implement System.ServiceModel.Dispatcher.IErrorHandler.", e);  
        }  
  
        foreach (ChannelDispatcherBase channelDispatcherBase in serviceHostBase.ChannelDispatchers)  
        {  
            ChannelDispatcher channelDispatcher = channelDispatcherBase as ChannelDispatcher;  
            channelDispatcher.ErrorHandlers.Add(errorHandler);  
        }                                                  
    }  
}  
```  
  
 <span data-ttu-id="33e47-121">该示例实现计算器服务。</span><span class="sxs-lookup"><span data-stu-id="33e47-121">The sample implements a calculator service.</span></span> <span data-ttu-id="33e47-122">客户端通过提供具有非法值的参数，使该服务故意出现两个错误。</span><span class="sxs-lookup"><span data-stu-id="33e47-122">The client deliberately causes two errors to occur on the service by providing parameters with illegal values.</span></span> <span data-ttu-id="33e47-123">`CalculatorErrorHandler` 使用 <xref:System.ServiceModel.Dispatcher.IErrorHandler> 接口将这些错误记录到某个本地文件，然后允许将这些错误报告回客户端。</span><span class="sxs-lookup"><span data-stu-id="33e47-123">The `CalculatorErrorHandler` uses the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface to log the errors to a local file and then allows them to be reported back to the client.</span></span> <span data-ttu-id="33e47-124">客户端强制执行除以零的除法运算和自变量超出范围的情况。</span><span class="sxs-lookup"><span data-stu-id="33e47-124">The client forces a divide by zero and an argument-out-of-range condition.</span></span>  
  
```  
try  
{  
    Console.WriteLine("Forcing an error in Divide");  
    // Call the Divide service operation - trigger a divide by 0 error.  
    value1 = 22;  
    value2 = 0;  
    result = proxy.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
}  
catch (FaultException e)  
{  
    Console.WriteLine("FaultException: " + e.GetType().Name + " - " + e.Message);  
}  
catch (Exception e)  
{  
    Console.WriteLine("Exception: " + e.GetType().Name + " - " + e.Message);  
}  
```  
  
 <span data-ttu-id="33e47-125">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="33e47-125">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="33e47-126">您将看到除以零的除法运算和参数超出范围的情况被报告为错误。</span><span class="sxs-lookup"><span data-stu-id="33e47-126">You see the division by zero and the argument-out-of-range conditions being reported as faults.</span></span> <span data-ttu-id="33e47-127">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="33e47-127">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Forcing an error in Divide  
FaultException: FaultException - Invalid Argument: The second argument must not be zero.  
Forcing an error in Factorial  
FaultException: FaultException - Invalid Argument: The argument must be greater than zero.  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="33e47-128">文件 c:\logs\errors.txt 包含服务记录的有关错误的信息。</span><span class="sxs-lookup"><span data-stu-id="33e47-128">The file c:\logs\errors.txt contains the information logged about the errors by the service.</span></span> <span data-ttu-id="33e47-129">请注意，为了使服务写入该目录，必须确保服务正在其下运行的进程（通常为 ASP.NET 或网络服务）具有写入目录的权限。</span><span class="sxs-lookup"><span data-stu-id="33e47-129">Note that for the service to write to the directory you must make sure that the process under which the service is running, (typically ASP.NET or Network Service), has the permission to write to the directory.</span></span>  
  
```  
Fault: Reason = Invalid Argument: The second argument must not be zero.  
Fault: Reason = Invalid Argument: The argument must be greater than zero.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="33e47-130">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="33e47-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="33e47-131">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="33e47-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="33e47-132">若要生成解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="33e47-132">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="33e47-133">确保您已经为 error.txt 文件创建了 c:\logs 目录，</span><span class="sxs-lookup"><span data-stu-id="33e47-133">Ensure you have created the c:\logs directory for the error.txt file.</span></span> <span data-ttu-id="33e47-134">或者修改 `CalculatorErrorHandler.HandleError` 中使用的文件名。</span><span class="sxs-lookup"><span data-stu-id="33e47-134">Or modify the file name used in `CalculatorErrorHandler.HandleError`.</span></span>  
  
4.  <span data-ttu-id="33e47-135">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="33e47-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33e47-136">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="33e47-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="33e47-137">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="33e47-137">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="33e47-138">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="33e47-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="33e47-139">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="33e47-139">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\ErrorHandling`  
  
## <a name="see-also"></a><span data-ttu-id="33e47-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="33e47-140">See Also</span></span>
