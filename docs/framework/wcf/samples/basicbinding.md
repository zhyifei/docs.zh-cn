---
title: BasicBinding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86fbeb87-4d89-4b61-9577-867e0ac12945
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8a84959e082919431f4ff3db98e70b3a51988aba
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="basicbinding"></a><span data-ttu-id="3c93a-102">BasicBinding</span><span class="sxs-lookup"><span data-stu-id="3c93a-102">BasicBinding</span></span>
<span data-ttu-id="3c93a-103">此示例演示如何使用 `basicHttpBinding` 来提供 HTTP 通信以及与第一代和第二代 Web 服务的最大互操作性。</span><span class="sxs-lookup"><span data-stu-id="3c93a-103">This sample demonstrates the use of `basicHttpBinding` that provides HTTP communication and maximum interoperability with first- and second-generation Web services.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c93a-104">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="3c93a-104">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c93a-105">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="3c93a-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="3c93a-106">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="3c93a-106">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="3c93a-107">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="3c93a-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3c93a-108">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="3c93a-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\Http`  
  
## <a name="sample-details"></a><span data-ttu-id="3c93a-109">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="3c93a-109">Sample Details</span></span>  
 <span data-ttu-id="3c93a-110">此示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)实现计算器服务。</span><span class="sxs-lookup"><span data-stu-id="3c93a-110">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
 <span data-ttu-id="3c93a-111">若要将基本绑定与默认行为一起使用，只需要使用绑定节的名称。</span><span class="sxs-lookup"><span data-stu-id="3c93a-111">To use the basic binding with default behavior, only the binding section name is required.</span></span> <span data-ttu-id="3c93a-112">如果要配置基本绑定并更改它的某些设置，则必须定义一个绑定配置。</span><span class="sxs-lookup"><span data-stu-id="3c93a-112">If you want to configure the basic binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="3c93a-113">终结点必须通过按名称引用绑定配置`bindingConfiguration`属性 <`endpoint`> 元素，如下面的示例代码中所示。</span><span class="sxs-lookup"><span data-stu-id="3c93a-113">The endpoint must reference the binding configuration by name by using the `bindingConfiguration` attribute of the <`endpoint`> element, as shown in the following sample code.</span></span>  
  
```xml  
<services>  
    <service   
        type="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
       <endpoint address=""  
             binding="basicHttpBinding"  
             bindingConfiguration="Binding1"   
             contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </service>  
</services>  
```  
  
 <span data-ttu-id="3c93a-114">在此示例中，定义了绑定配置并将其命名为 `"Binding1"`，如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="3c93a-114">In this sample, the binding configuration is named `"Binding1"` and is defined as shown in the following code example.</span></span>  
  
```xml  
<bindings>  
   <basicHttpBinding>  
      <binding name="Binding1"   
               hostNameComparisonMode="StrongWildcard"   
               receiveTimeout="00:10:00"  
               sendTimeout="00:10:00"  
               openTimeout="00:10:00"  
               closeTimeout="00:10:00"  
               maxMessageSize="65536"   
               maxBufferSize="65536"   
               maxBufferPoolSize="524288"   
               transferMode="Buffered"   
               messageEncoding="Text"   
               textEncoding="utf-8"  
               bypassProxyOnLocal="false"  
               useDefaultWebProxy="true" >  
         <security mode="None" />  
      </binding>  
   </basicHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="3c93a-115">绑定元素提供用来设置如下内容的属性：主机名比较模式、最大消息大小、代理选项、超时、消息编码和其他选项。</span><span class="sxs-lookup"><span data-stu-id="3c93a-115">The binding element provides attributes for setting the host name comparison mode, maximum message size, proxy options, timeouts, message encoding, and other options.</span></span>  
  
 <span data-ttu-id="3c93a-116">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="3c93a-116">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="3c93a-117">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="3c93a-117">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3c93a-118">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="3c93a-118">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="3c93a-119">使用以下命令安装 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0。</span><span class="sxs-lookup"><span data-stu-id="3c93a-119">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="3c93a-120">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="3c93a-120">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="3c93a-121">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="3c93a-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="3c93a-122">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="3c93a-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c93a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c93a-123">See Also</span></span>
