---
title: 按正文路由
ms.date: 03/30/2017
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
ms.openlocfilehash: fe201161ebed66b8444c23229a6907be329d3641
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835123"
---
# <a name="route-by-body"></a><span data-ttu-id="8f8d7-102">按正文路由</span><span class="sxs-lookup"><span data-stu-id="8f8d7-102">Route by Body</span></span>
<span data-ttu-id="8f8d7-103">此示例演示如何实现一种使用任何 SOAP 操作接受消息对象的服务。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-103">This sample demonstrates how to implement a service that accepts message objects with any SOAP action.</span></span> <span data-ttu-id="8f8d7-104">此示例基于[Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)实现计算器服务。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="8f8d7-105">该服务实现一个 `Calculate` 操作，此操作接受一个 <xref:System.ServiceModel.Channels.Message> 请求参数并返回一个 <xref:System.ServiceModel.Channels.Message> 响应。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-105">The service implements a single `Calculate` operation that accepts a <xref:System.ServiceModel.Channels.Message> request parameter and returns a <xref:System.ServiceModel.Channels.Message> response.</span></span>  
  
 <span data-ttu-id="8f8d7-106">在此示例中，客户端是一个控制台应用程序 (.exe)，并且服务承载在 IIS 中。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-106">In this sample, the client is a console application (.exe) and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f8d7-107">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8f8d7-108">此示例演示基于正文内容的消息调度。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-108">The sample demonstrates message dispatch based on the body content.</span></span> <span data-ttu-id="8f8d7-109">内置的 Windows Communication Foundation (WCF) 服务模型消息调度机制基于消息的操作。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-109">The built-in Windows Communication Foundation (WCF) service model message dispatch mechanism is based on message Actions.</span></span> <span data-ttu-id="8f8d7-110">不过，有许多现有的 Web 服务使用 Action="" 来定义其所有操作。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-110">However, there are many existing Web services that define all of their operations with Action="".</span></span> <span data-ttu-id="8f8d7-111">不可能基于 WSDL 生成基于 Action 信息调度请求消息的服务。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-111">It is impossible to build a service based on WSDL that keeps dispatching request messages based on Action information.</span></span> <span data-ttu-id="8f8d7-112">此示例演示一个基于 WSDL 的服务协定，此 WSDL 包含在该示例包括的 Service.wsdl 中。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-112">This sample demonstrates a service contract that is based on WSDL (the WSDL is contained in Service.wsdl that is included with the sample).</span></span> <span data-ttu-id="8f8d7-113">服务协定为计算器，与在中使用类似[Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-113">The service contract is Calculator, similar to the one used in [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="8f8d7-114">但是，`[OperationContract]` 指定所有操作的 `Action=""`。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-114">However the `[OperationContract]` specifies `Action=""` for all operations.</span></span>  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples"),    
                 XmlSerializerFormat, DispatchByBodyBehavior]  
    public interface ICalculator  
    {  
        [OperationContract(Action="")]  
        double Add(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Subtract(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Multiply(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Divide(double n1, double n2);  
    }  
```  
  
 <span data-ttu-id="8f8d7-115">给定协定之后，服务需要自定义调度行为 `DispatchByBodyBehavior` 以便允许在操作之间调度消息。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-115">Given a contract, a service requires custom dispatch behavior `DispatchByBodyBehavior` to allow messages to be dispatched between operations.</span></span> <span data-ttu-id="8f8d7-116">该调度行为初始化`DispatchByBodyElementOperationSelector`具有由各自的包装器元素的 QName 进行键控的操作名称的表的自定义操作选择器。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-116">This dispatch behavior initializes the `DispatchByBodyElementOperationSelector` custom operation selector with a table of the operation names keyed by QName of respective wrapper elements.</span></span> <span data-ttu-id="8f8d7-117">`DispatchByBodyElementOperationSelector` 在正文第一个子级的开始标记中查找，并使用前面提到的表选择操作。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-117">`DispatchByBodyElementOperationSelector` looks at the start tag of the first child of the Body and selects the operation using the table previously mentioned.</span></span>  
  
 <span data-ttu-id="8f8d7-118">客户端使用从服务使用导出的 WSDL 自动生成的代理[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-118">The client uses a proxy auto-generated from the WSDL exported by the service using [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
```  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 <span data-ttu-id="8f8d7-119">所有操作的此 Action 均为空，这一事实对客户端节点没有影响，但自动生成的代理中的 Action 参数除外。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-119">The fact that actions of all operations are empty has no impact on the client code, except for the Action parameters in the auto-generated proxy.</span></span>  
  
 <span data-ttu-id="8f8d7-120">客户端代码执行若干计算。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-120">The client code performs several calculations.</span></span> <span data-ttu-id="8f8d7-121">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="8f8d7-122">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8f8d7-123">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="8f8d7-123">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8f8d7-124">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8f8d7-125">若要生成解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-125">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8f8d7-126">若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8f8d7-127">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-127">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8f8d7-128">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="8f8d7-128">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8f8d7-129">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="8f8d7-129">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8f8d7-130">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="8f8d7-130">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
  
