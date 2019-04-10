---
title: 通道工厂
ms.date: 03/30/2017
ms.assetid: 09b53aa1-b13c-476c-a461-e82fcacd2a8b
ms.openlocfilehash: 0bcaa739a51d168e18c809804b7da6948ab61e9d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59315525"
---
# <a name="channel-factory"></a><span data-ttu-id="c1cb8-102">通道工厂</span><span class="sxs-lookup"><span data-stu-id="c1cb8-102">Channel Factory</span></span>
<span data-ttu-id="c1cb8-103">此示例演示客户端应用程序如何使用 <xref:System.ServiceModel.ChannelFactory> 类而不是生成的客户端创建通道。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-103">This sample demonstrates how a client application can create a channel with the <xref:System.ServiceModel.ChannelFactory> class instead of a generated client.</span></span> <span data-ttu-id="c1cb8-104">此示例基于[Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)实现计算器服务。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1cb8-105">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="c1cb8-106">此示例使用 <xref:System.ServiceModel.ChannelFactory%601> 类来创建到服务终结点的通道。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-106">This sample uses the <xref:System.ServiceModel.ChannelFactory%601> class to create a channel to a service endpoint.</span></span> <span data-ttu-id="c1cb8-107">通常情况下，若要创建的服务终结点的通道生成的客户端类型[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)并创建生成的类型的实例。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-107">Typically, to create a channel to a service endpoint you generate a client type with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) and create an instance of the generated type.</span></span> <span data-ttu-id="c1cb8-108">还可以通过使用 <xref:System.ServiceModel.ChannelFactory%601> 类创建通道，如该示例所示。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-108">You can also create a channel by using the <xref:System.ServiceModel.ChannelFactory%601> class, as demonstrated in this sample.</span></span> <span data-ttu-id="c1cb8-109">下面的示例代码所创建的服务是中的服务相同[Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-109">The service created by the following sample code is identical to the service in the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
```csharp  
EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
WSHttpBinding binding = new WSHttpBinding();  
ChannelFactory<ICalculator> factory = new   
                    ChannelFactory<ICalculator>(binding, address);  
ICalculator channel = factory.CreateChannel();  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="c1cb8-110">如果你在跨计算机方案中运行该示例，则必须将前面代码中的“localhost”替换为运行服务的计算机的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-110">If you are running this sample in a cross-machine scenario, you must replace "localhost" in the preceding code with the fully-qualified name of the machine that is running the service.</span></span> <span data-ttu-id="c1cb8-111">此示例不使用配置来设置终结点地址，因此这必须通过代码完成。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-111">This sample does not use configuration to set the endpoint address, so this must be done in code.</span></span>  
  
 <span data-ttu-id="c1cb8-112">一旦创建了通道，便可以像调用生成的客户端那样调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-112">Once the channel is created, service operations can be invoked just as with a generated client.</span></span>  
  
```csharp  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = channel.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
```  
  
 <span data-ttu-id="c1cb8-113">若要关闭通道，必须将其强制转换为 <xref:System.ServiceModel.IClientChannel> 接口。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-113">To close the channel, it must first be cast to an <xref:System.ServiceModel.IClientChannel> interface.</span></span> <span data-ttu-id="c1cb8-114">这是因为生成的通道是在使用 `ICalculator` 接口的客户端应用程序中声明的，该应用程序具有 `Add` 和 `Subtract` 等方法，但没有 `Close` 方法。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-114">This is because the channel as generated is declared in the client application using the `ICalculator` interface, which has methods like `Add` and `Subtract` but not `Close`.</span></span> <span data-ttu-id="c1cb8-115">`Close` 方法在 <xref:System.ServiceModel.ICommunicationObject> 接口上产生。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-115">The `Close` method originates on the <xref:System.ServiceModel.ICommunicationObject> interface.</span></span>  
  
```csharp  
// Close the channel.  
 ((IClientChannel)client).Close();  
```  
  
 <span data-ttu-id="c1cb8-116">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-116">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="c1cb8-117">在客户端窗口中按 Enter 可以关闭客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-117">Press ENTER in the client window to shut down the client application.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c1cb8-118">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="c1cb8-118">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c1cb8-119">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="c1cb8-120">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span> <span data-ttu-id="c1cb8-121">请注意，该示例不会启用元数据发布。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-121">Note that this sample does not enable metadata publishing.</span></span> <span data-ttu-id="c1cb8-122">必须先对该示例启用元数据发布才能重新生成客户端类型。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-122">You must first enable metadata publishing for this sample to regenerate the client type.</span></span>  
  
3. <span data-ttu-id="c1cb8-123">若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-cross-machine"></a><span data-ttu-id="c1cb8-124">跨计算机运行示例</span><span class="sxs-lookup"><span data-stu-id="c1cb8-124">To run the sample cross machine</span></span>  
  
1. <span data-ttu-id="c1cb8-125">将下面代码中的“localhost”替换为运行服务的计算机的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-125">Replace "localhost" in the following code with the fully-qualified name of the machine that is running the service.</span></span>  
  
    ```csharp  
    EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
    ```  
  
> [!IMPORTANT]
>  <span data-ttu-id="c1cb8-126">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c1cb8-127">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="c1cb8-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c1cb8-128">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="c1cb8-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c1cb8-129">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="c1cb8-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ChannelFactory`  
