---
title: "服务说明"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7034b5d6-d608-45f3-b57d-ec135f83ff24
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1d3251d960b00d34c08826957e0db9c30bd5aae3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="service-description"></a><span data-ttu-id="2299a-102">服务说明</span><span class="sxs-lookup"><span data-stu-id="2299a-102">Service Description</span></span>
<span data-ttu-id="2299a-103">服务说明示例演示服务如何在运行时检索其服务说明信息。</span><span class="sxs-lookup"><span data-stu-id="2299a-103">The Service Description sample demonstrates how a service can retrieve its service description information at runtime.</span></span> <span data-ttu-id="2299a-104">示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)，与其他服务操作定义为返回有关服务的描述性信息。</span><span class="sxs-lookup"><span data-stu-id="2299a-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), with an additional service operation defined to return descriptive information about the service.</span></span> <span data-ttu-id="2299a-105">返回的信息列出了服务的基址和终结点。</span><span class="sxs-lookup"><span data-stu-id="2299a-105">The information that is returned lists the base addresses and endpoints for the service.</span></span> <span data-ttu-id="2299a-106">服务使用 <xref:System.ServiceModel.OperationContext>、<xref:System.ServiceModel.ServiceHost> 和 <xref:System.ServiceModel.Description.ServiceDescription> 类提供此信息。</span><span class="sxs-lookup"><span data-stu-id="2299a-106">The service provides this information using the <xref:System.ServiceModel.OperationContext>, <xref:System.ServiceModel.ServiceHost>, and <xref:System.ServiceModel.Description.ServiceDescription> classes.</span></span>  
  
 <span data-ttu-id="2299a-107">在此示例中，客户端是一个控制台应用程序 (.exe)，服务是由 Internet 信息服务 (IIS) 承载的。</span><span class="sxs-lookup"><span data-stu-id="2299a-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2299a-108">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="2299a-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="2299a-109">本示例有名为 `IServiceDescriptionCalculator` 的计算器协定修改版本。</span><span class="sxs-lookup"><span data-stu-id="2299a-109">This sample has a modified version of the calculator contract called `IServiceDescriptionCalculator`.</span></span> <span data-ttu-id="2299a-110">此协定定义一个名为 `GetServiceDescriptionInfo` 的附加服务操作，它向客户端返回多行描述服务的基址或地址和服务终结点的字符串。</span><span class="sxs-lookup"><span data-stu-id="2299a-110">The contract defines an additional service operation named `GetServiceDescriptionInfo` that returns a multi-line string to the client that describes the base address or addresses and service endpoint or endpoints for the service.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IServiceDescriptionCalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    int Divide(int n1, int n2);  
    [OperationContract]  
    string GetServiceDescriptionInfo();  
}  
```  
  
 <span data-ttu-id="2299a-111">`GetServiceDescriptionInfo` 的实现代码使用 <xref:System.ServiceModel.Description.ServiceDescription> 列出服务终结点。</span><span class="sxs-lookup"><span data-stu-id="2299a-111">The implementation code for `GetServiceDescriptionInfo` uses the <xref:System.ServiceModel.Description.ServiceDescription> to list the service endpoints.</span></span> <span data-ttu-id="2299a-112">服务终结点可以具有相关地址，因此它首先列出服务的基址。</span><span class="sxs-lookup"><span data-stu-id="2299a-112">Because service endpoints can have relative addresses, it first lists the base addresses for the service.</span></span> <span data-ttu-id="2299a-113">若要获取所有这些信息，代码将使用 <xref:System.ServiceModel.OperationContext.Current%2A> 获取服务操作上下文。</span><span class="sxs-lookup"><span data-stu-id="2299a-113">To get all of this information, the code obtains its operation context using <xref:System.ServiceModel.OperationContext.Current%2A>.</span></span> <span data-ttu-id="2299a-114"><xref:System.ServiceModel.ServiceHost> 及其 <xref:System.ServiceModel.Description.ServiceDescription> 对象是从操作上下文中检索的。</span><span class="sxs-lookup"><span data-stu-id="2299a-114">The <xref:System.ServiceModel.ServiceHost> and its <xref:System.ServiceModel.Description.ServiceDescription> object are retrieved from the operation context.</span></span> <span data-ttu-id="2299a-115">若要列出服务的基本终结点，代码需循环访问服务主机的 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> 集合。</span><span class="sxs-lookup"><span data-stu-id="2299a-115">To list the base endpoints for the service, the code iterates through the service host's <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A> collection.</span></span> <span data-ttu-id="2299a-116">若要列出服务的服务终结点，代码需循环访问服务说明终结点集合。</span><span class="sxs-lookup"><span data-stu-id="2299a-116">To list the service endpoints for the service, the code iterates through the service description's endpoints collection.</span></span>  
  
```  
public string GetServiceDescriptionInfo()  
{  
    string info = "";  
    OperationContext operationContext = OperationContext.Current;  
    ServiceHost host = (ServiceHost)operationContext.Host;  
    ServiceDescription desc = host.Description;  
    // Enumerate the base addresses in the service host.  
    info += "Base addresses:\n";  
    foreach (Uri uri in host.BaseAddresses)  
    {  
        info += "    " + uri + "\n";  
    }  
    // Enumerate the service endpoints in the service description.  
    info += "Service endpoints:\n";  
    foreach (ServiceEndpoint endpoint in desc.Endpoints)  
    {  
        info += "    Address:  " + endpoint.Address + "\n";  
        info += "    Binding:  " + endpoint.Binding.Name + "\n";  
        info += "    Contract: " + endpoint.Contract.Name + "\n";  
    }  
     return info;  
}  
```  
  
 <span data-ttu-id="2299a-117">运行示例时，将显示计算器操作，接着显示 `GetServiceDescriptionInfo` 操作返回的服务信息。</span><span class="sxs-lookup"><span data-stu-id="2299a-117">When you run the sample, you see the calculator operations and then the service information returned by the `GetServiceDescriptionInfo` operation.</span></span> <span data-ttu-id="2299a-118">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="2299a-118">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Divide(22,7) = 3  
GetServiceDescriptionInfo  
Base addresses:  
    http://<machine-name>/ServiceModelSamples/service.svc  
    https://<machine-name>/ServiceModelSamples/service.svc  
Service endpoints:  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc  
    Binding:  WSHttpBinding  
    Contract: IServiceDescriptionCalculator  
    Address:  http://<machine-name>/ServiceModelSamples/service.svc/mex  
    Binding:  MetadataExchangeHttpBinding  
    Contract: IMetadataExchange  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2299a-119">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="2299a-119">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2299a-120">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="2299a-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="2299a-121">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="2299a-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="2299a-122">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="2299a-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2299a-123">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="2299a-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2299a-124">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="2299a-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2299a-125">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="2299a-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2299a-126">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="2299a-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ServiceDescription`  
  
## <a name="see-also"></a><span data-ttu-id="2299a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2299a-127">See Also</span></span>
