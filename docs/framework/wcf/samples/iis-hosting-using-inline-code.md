---
title: 使用内联代码的 IIS 承载
ms.date: 03/30/2017
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
ms.openlocfilehash: 30e50d39b0edb34bcda1bec6d1848a09eabd34fa
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524932"
---
# <a name="iis-hosting-using-inline-code"></a><span data-ttu-id="8ef8c-102">使用内联代码的 IIS 承载</span><span class="sxs-lookup"><span data-stu-id="8ef8c-102">IIS Hosting Using Inline Code</span></span>
<span data-ttu-id="8ef8c-103">此示例演示如何实现由 Internet 信息服务 (IIS) 承载的服务，该服务的服务代码以内联方式包含在一个 .svc 文件中，并且可以按需编译。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-103">This sample demonstrates how to implement a service hosted by Internet Information Services (IIS), where the service code is contained in-line in a .svc file and is compiled on demand.</span></span> <span data-ttu-id="8ef8c-104">服务代码还可以直接在源代码文件（位于应用程序的 \App_Code 目录中）中实现，也可以编译为 \bin 中所部署的程序集。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-104">Service code can also be implemented directly in source code files located in the application's \App_Code directory, or compiled into assembly deployed in \bin.</span></span> <span data-ttu-id="8ef8c-105">此示例不演示这些技术。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-105">This sample does not demonstrate these techniques.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8ef8c-106">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-106">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8ef8c-107">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-107">The samples may already be installed on your computer.</span></span> <span data-ttu-id="8ef8c-108">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="8ef8c-108">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8ef8c-109">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-109">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8ef8c-110">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="8ef8c-110">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`  
  
 <span data-ttu-id="8ef8c-111">本示例演示一个典型的服务，该服务实现定义“请求-答复”通信模式的协定。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-111">The sample demonstrates a typical service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="8ef8c-112">该服务由 IIS 承载，服务代码完全包含在 Service.svc 文件中。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-112">The service is hosted in IIS and the service code is entirely contained in the Service.svc file.</span></span> <span data-ttu-id="8ef8c-113">该服务由主机激活，并由发送给它的第一条消息按需编译。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-113">The service is host-activated and compiled on-demand by the first message sent to the service.</span></span> <span data-ttu-id="8ef8c-114">没有必要进行预先编译。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-114">There is no pre-compilation necessary.</span></span> <span data-ttu-id="8ef8c-115">该服务实现一个 `ICalculator` 协定，下面的代码对该协定进行了定义：</span><span class="sxs-lookup"><span data-stu-id="8ef8c-115">The service implements an `ICalculator` contract as defined in the following code:</span></span>  
  
```  
// Define a service contract.  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
    public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="8ef8c-116">服务实现计算并返回相应的结果。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-116">The service implementation calculates and returns the appropriate result.</span></span>  
  
```  
<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>   
…  
// Service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public double Add(double n1, double n2)  
    {  
        return n1 + n2;  
    }  
    public double Subtract(double n1, double n2)  
    {  
        return n1 - n2;  
    }  
    public double Multiply(double n1, double n2)  
    {  
        return n1 * n2;  
    }  
    public double Divide(double n1, double n2)  
    {  
        return n1 / n2;  
    }  
}  
```  
  
 <span data-ttu-id="8ef8c-117">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-117">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="8ef8c-118">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-118">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8ef8c-119">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="8ef8c-119">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8ef8c-120">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8ef8c-121">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8ef8c-122">生成解决方案后，请运行 setup.bat 以在 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 中设置 ServiceModelSamples 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-122">After the solution has been built, run setup.bat to set up the ServiceModelSamples Application in [!INCLUDE[iisver](../../../../includes/iisver-md.md)].</span></span> <span data-ttu-id="8ef8c-123">现在，ServiceModelSamples 目录应显示为 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-123">The ServiceModelSamples directory should now appear as an [!INCLUDE[iisver](../../../../includes/iisver-md.md)] Application.</span></span>  
  
4.  <span data-ttu-id="8ef8c-124">若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-124">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="8ef8c-125">有关如何创建可调用此服务的客户端应用程序的示例，请参阅[如何： 创建客户端](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)。</span><span class="sxs-lookup"><span data-stu-id="8ef8c-125">For an example on how to create a client application that can call this service, see [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ef8c-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ef8c-126">See Also</span></span>  
 [<span data-ttu-id="8ef8c-127">AppFabric 承载和持久性示例</span><span class="sxs-lookup"><span data-stu-id="8ef8c-127">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
