---
title: 服务调试行为
ms.date: 03/30/2017
ms.assetid: 9d8fd3fb-dc39-427a-8235-336a7e7162ba
ms.openlocfilehash: bfed164093e10c070b24832cf5a3be362ad3bc56
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772045"
---
# <a name="service-debug-behavior"></a><span data-ttu-id="50b84-102">服务调试行为</span><span class="sxs-lookup"><span data-stu-id="50b84-102">Service Debug Behavior</span></span>
<span data-ttu-id="50b84-103">本示例演示如何配置服务调试行为设置。</span><span class="sxs-lookup"><span data-stu-id="50b84-103">This sample demonstrates how service debug behavior settings can be configured.</span></span> <span data-ttu-id="50b84-104">该示例基于[Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)，它可以实现`ICalculator`服务协定。</span><span class="sxs-lookup"><span data-stu-id="50b84-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="50b84-105">本示例在配置文件中显式定义服务调试行为。</span><span class="sxs-lookup"><span data-stu-id="50b84-105">This sample explicitly defines service debug behavior in the configuration file.</span></span> <span data-ttu-id="50b84-106">也可以在代码中强制完成此操作。</span><span class="sxs-lookup"><span data-stu-id="50b84-106">It can also be done imperatively in code.</span></span>  
  
 <span data-ttu-id="50b84-107">在此示例中，客户端是一个控制台应用程序 (.exe)，服务是由 Internet 信息服务 (IIS) 承载的。</span><span class="sxs-lookup"><span data-stu-id="50b84-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50b84-108">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="50b84-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="50b84-109">服务器的 Web.config 文件定义服务调试行为以启用帮助页和异常处理，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="50b84-109">The Web.config file for the server defines the service debug behavior to enable the help page and exception handling as shown in the following sample.</span></span>  
  
```xml  
<behaviors>  
     <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
         <!-- WARNING: Setting includeExceptionDetailInFaults = "True" could result in leaking secured server information to the client.-->  
         <!-- Please set this to false when deploying -->  
             <serviceDebug includeExceptionDetailInFaults="True" httpHelpPageEnabled="True"/>  
         </behavior>  
     </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="50b84-110">[\<serviceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)是允许更改服务调试行为属性的配置元素。</span><span class="sxs-lookup"><span data-stu-id="50b84-110">[\<serviceDebug>](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) is the configuration element that allows changing the service debug behavior properties.</span></span> <span data-ttu-id="50b84-111">用户可以修改此行为以实现以下目标：</span><span class="sxs-lookup"><span data-stu-id="50b84-111">The user can modify this behavior to achieve the following:</span></span>  
  
-   <span data-ttu-id="50b84-112">这使服务可以返回应用程序代码引发的任何异常，即使未使用 <xref:System.ServiceModel.FaultContractAttribute> 声明该异常。</span><span class="sxs-lookup"><span data-stu-id="50b84-112">This allows the service to return any exception that is thrown by the application code even if the exception is not declared using the <xref:System.ServiceModel.FaultContractAttribute>.</span></span> <span data-ttu-id="50b84-113">为此，需要将 `includeExceptionDetailInFaults` 设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="50b84-113">It is done by setting `includeExceptionDetailInFaults` to `true`.</span></span> <span data-ttu-id="50b84-114">此设置在调试服务器引发意外异常的事例时很有用。</span><span class="sxs-lookup"><span data-stu-id="50b84-114">This setting is useful when debugging cases where the server is throwing an unexpected exception.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="50b84-115">在生产环境中打开此设置会不安全。</span><span class="sxs-lookup"><span data-stu-id="50b84-115">It is not secure to turn this setting on in a production environment.</span></span> <span data-ttu-id="50b84-116">由于意外服务器异常可能具有某些不适用于客户端的信息，因此将 `includeExceptionDetailsInFaults` 设置为 `true` 可能导致信息泄露。</span><span class="sxs-lookup"><span data-stu-id="50b84-116">An unexpected server exception may have some information that is not intended for the client and so setting `includeExceptionDetailsInFaults` to `true` might result in an information leak.</span></span>  
  
-   <span data-ttu-id="50b84-117">[ \<ServiceDebug >](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)还允许用户启用或禁用帮助页。</span><span class="sxs-lookup"><span data-stu-id="50b84-117">The [\<serviceDebug>](../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md) also allows a user to enable or disable the help page.</span></span> <span data-ttu-id="50b84-118">每个服务可以选择公开一个帮助页，该帮助页包含有关服务的信息，其中包括要获取服务的 WSDL 的终结点。</span><span class="sxs-lookup"><span data-stu-id="50b84-118">Each service can optionally expose a help page that contains information about the service including the endpoint to get WSDL for the service.</span></span> <span data-ttu-id="50b84-119">通过将 `httpHelpPageEnabled` 设置为 `true` 可以启用该帮助页。</span><span class="sxs-lookup"><span data-stu-id="50b84-119">This can be enabled by setting `httpHelpPageEnabled` to `true`.</span></span> <span data-ttu-id="50b84-120">这将使帮助页返回到对服务基址的 GET 请求。</span><span class="sxs-lookup"><span data-stu-id="50b84-120">This enables the help page to be returned to a GET request to the base address of the service.</span></span> <span data-ttu-id="50b84-121">通过设置另一个属性 `httpHelpPageUrl`，可以更改此地址。</span><span class="sxs-lookup"><span data-stu-id="50b84-121">You can change this address by setting another attribute `httpHelpPageUrl`.</span></span> <span data-ttu-id="50b84-122">通过使用 HTTPS（而不是 HTTP）可以使其安全。</span><span class="sxs-lookup"><span data-stu-id="50b84-122">You can make this secure by using HTTPS instead of HTTP.</span></span> <span data-ttu-id="50b84-123">这可以通过设置 `httpsHelpPageEnabled` 和 `httpsHelpPageUrl` 来完成。</span><span class="sxs-lookup"><span data-stu-id="50b84-123">This can be done by setting `httpsHelpPageEnabled` and `httpsHelpPageUrl`.</span></span>  
  
 <span data-ttu-id="50b84-124">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="50b84-124">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="50b84-125">前三个操作（加、减和乘）都会成功。</span><span class="sxs-lookup"><span data-stu-id="50b84-125">The first three operations (Add, Subtract and Multiply) must succeed.</span></span> <span data-ttu-id="50b84-126">最后一个操作（“除”）由于除数为零异常而失败。</span><span class="sxs-lookup"><span data-stu-id="50b84-126">The last operation ("divide") fails with a division by zero exception.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="50b84-127">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="50b84-127">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="50b84-128">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="50b84-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="50b84-129">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="50b84-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="50b84-130">若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="50b84-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="50b84-131">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="50b84-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="50b84-132">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="50b84-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="50b84-133">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="50b84-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="50b84-134">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="50b84-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\ServiceDebug`  
