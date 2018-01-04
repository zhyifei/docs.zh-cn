---
title: "WMI 提供程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c1b1f923b6673ead42c7c702bd50d253ea06c765
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="wmi-provider"></a><span data-ttu-id="c9752-102">WMI 提供程序</span><span class="sxs-lookup"><span data-stu-id="c9752-102">WMI Provider</span></span>
<span data-ttu-id="c9752-103">此示例演示如何在运行时使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中内置的 Windows Management Instrumentation (WMI) 提供程序从 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务中收集数据。</span><span class="sxs-lookup"><span data-stu-id="c9752-103">This sample demonstrates how to gather data from [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services at runtime by using the Windows Management Instrumentation (WMI) provider that is built into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="c9752-104">另外，此示例还演示如何向服务添加用户定义的 WMI 对象。</span><span class="sxs-lookup"><span data-stu-id="c9752-104">Also, this sample demonstrates how to add a user-defined WMI object to a service.</span></span> <span data-ttu-id="c9752-105">示例激活的 WMI 提供程序[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)并演示了如何收集数据`ICalculator`服务在运行时。</span><span class="sxs-lookup"><span data-stu-id="c9752-105">The sample activates the WMI provider for the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and demonstrates how to gather data from the `ICalculator` service at runtime.</span></span>  
  
 <span data-ttu-id="c9752-106">WMI 是 Microsoft 基于 Web 的企业管理 (WBEM) 标准的实现。</span><span class="sxs-lookup"><span data-stu-id="c9752-106">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> <span data-ttu-id="c9752-107">有关 WMI SDK 的详细信息，请参阅[Windows Management Instrumentation](https://msdn.microsoft.com/library/aa394582.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c9752-107">For more information about the WMI SDK, see [Windows Management Instrumentation](https://msdn.microsoft.com/library/aa394582.aspx).</span></span> <span data-ttu-id="c9752-108">WBEM 是有关应用程序如何向外部管理工具公开管理规范的行业标准。</span><span class="sxs-lookup"><span data-stu-id="c9752-108">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c9752-109"> 实现 WMI 提供程序，该提供程序是一个在运行时通过 WBEM 兼容接口公开规范的组件。</span><span class="sxs-lookup"><span data-stu-id="c9752-109"> implements a WMI provider, a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="c9752-110">管理工具可以在运行时通过接口连接至服务。</span><span class="sxs-lookup"><span data-stu-id="c9752-110">Management tools can connect to the services through the interface at runtime.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c9752-111"> 公开服务的特性，如地址、绑定、行为和侦听器。</span><span class="sxs-lookup"><span data-stu-id="c9752-111"> exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="c9752-112">在应用程序的配置文件中激活内置 WMI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="c9752-112">The built-in WMI provider is activated in the configuration file of the application.</span></span> <span data-ttu-id="c9752-113">通过完成此操作`wmiProviderEnabled`属性[\<诊断 >](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)中[ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)部分，如下面的示例中所示配置：</span><span class="sxs-lookup"><span data-stu-id="c9752-113">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="c9752-114">此配置项公开 WMI 接口。</span><span class="sxs-lookup"><span data-stu-id="c9752-114">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="c9752-115">现在，您可以通过此接口连接管理应用程序并访问应用程序的管理规范。</span><span class="sxs-lookup"><span data-stu-id="c9752-115">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="custom-wmi-object"></a><span data-ttu-id="c9752-116">自定义 WMI 对象</span><span class="sxs-lookup"><span data-stu-id="c9752-116">Custom WMI Object</span></span>  
 <span data-ttu-id="c9752-117">将 WMI 对象添加到服务，可以显示用户定义的信息以及内置的 WMI 提供程序信息。</span><span class="sxs-lookup"><span data-stu-id="c9752-117">Adding WMI objects to a service makes it possible to reveal user-defined information along with the built-in WMI provider information.</span></span> <span data-ttu-id="c9752-118">这可以通过使用 Installutil.exe 应用程序将服务方案发布到 WMI 来实现。</span><span class="sxs-lookup"><span data-stu-id="c9752-118">This is accomplished by publishing the schema of the service to WMI by using the Installutil.exe application.</span></span> <span data-ttu-id="c9752-119">本主题末尾的安装说明介绍了如何实现上述操作的说明以及更详细的信息。</span><span class="sxs-lookup"><span data-stu-id="c9752-119">Instructions to accomplish this, along with more details can be found in the setup instructions at the end of the topic.</span></span>  
  
## <a name="accessing-wmi-information"></a><span data-ttu-id="c9752-120">访问 WMI 信息</span><span class="sxs-lookup"><span data-stu-id="c9752-120">Accessing WMI Information</span></span>  
 <span data-ttu-id="c9752-121">可以采用多种不同方式访问 WMI 数据。</span><span class="sxs-lookup"><span data-stu-id="c9752-121">WMI data can be accessed many different ways.</span></span> <span data-ttu-id="c9752-122">Microsoft 提供脚本、[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 应用程序、C++ 应用程序和 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 的 WMI API (http://msdn.microsoft.com/library/default.asp?url=/library/wmisdk/wmi/using_wmi.asp)。</span><span class="sxs-lookup"><span data-stu-id="c9752-122">Microsoft provides WMI APIs for scripts, [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] applications, C++ applications, and the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] (http://msdn.microsoft.com/library/default.asp?url=/library/wmisdk/wmi/using_wmi.asp).</span></span>  
  
 <span data-ttu-id="c9752-123">此示例使用两个 Java 脚本：一个脚本用于枚举在计算机上运行的服务及其某些属性，另一个脚本用于查看用户定义的 WMI 数据。</span><span class="sxs-lookup"><span data-stu-id="c9752-123">This sample uses two Java scripts: one to enumerate services running on the computer along with some of their properties and the second to view user-defined WMI data.</span></span> <span data-ttu-id="c9752-124">该脚本打开与 WMI 提供程序的连接、分析数据并显示所收集的数据。</span><span class="sxs-lookup"><span data-stu-id="c9752-124">The script opens a connection to the WMI provider, parses data, and displays the data gathered.</span></span>  
  
 <span data-ttu-id="c9752-125">启动该示例可以创建 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务的一个运行中实例。</span><span class="sxs-lookup"><span data-stu-id="c9752-125">Start the sample to create a running instance of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="c9752-126">在该服务运行的同时，在命令提示符处使用以下命令运行每个 Java 脚本：</span><span class="sxs-lookup"><span data-stu-id="c9752-126">While the service is running, run each Java script by using the following command at the command prompt:</span></span>  
  
```  
cscript EnumerateServices.js  
```  
  
 <span data-ttu-id="c9752-127">该脚本访问服务中包含的规范，并生成下面的输出：</span><span class="sxs-lookup"><span data-stu-id="c9752-127">The script accesses the instrumentation contained in the service and produces the following output:</span></span>  
  
```  
Microsoft (R) Windows Script Host Version 5.6  
Copyright © Microsoft Corporation 1996-2001. All rights reserved.  
  
1 service(s) found.  
|-PID:           5776  
|-DistinguishedName:  CalculatorService@http://localhost/ServiceModelSamples/service.svc  
|-Endpoints:     1 endpoints  
  |-CalculatorService.ICalculator@http://localhost/ServiceModelSamples/service.svc  
    |-Address:                        http://localhost/ServiceModelSamples/service.svc  
    |-CounterInstanceName:  
    |-AddressHeaders:                 0  
    |-ContractType:                   Contract.Name='ICalculator'  
    |-BindingElements:                4 bindings  
      |-BindingElements[0]  
        |-Type:                       TransactionFlowBindingElement  
      |-BindingElements[1]  
        |-Type:                       SymmetricSecurityBindingElement  
      |-BindingElements[2]  
        |-Type:                       TextMessageEncodingBindingElement  
        |-MaxReadPoolSize:            64  
        |-MaxWritePoolSize:           16  
      |-BindingElements[3]  
        |-Type:                       HttpTransportBindingElement  
        |-ManualAddressing:           false  
        |-MaxBufferSize:              65536  
        |-AllowCookies:               false  
        |-AuthenticationScheme:       Anonymous  
        |-BypassProxyOnLocal:         false  
        |-HostNameComparisonMode:     StrongWildcard  
        |-ProxyAddress:               null  
        |-ProxyAuthenticationScheme:  Anonymous  
        |-Realm:  
        |-TransferMode:               Buffered  
        |-UseDefaultWebProxy:         true  
|-Behaviors:     5 behaviors  
      |-Behavior[0]  
      |-Type:                       ServiceBehaviorAttribute  
        |-AddressFilterMode:               Exact  
        |-AutomaticSessionShutdown:        true  
        |-ConcurrencyMode:                 Single  
        |-IncludeExceptionDetailInFaults:  false  
        |-InstanceContextMode:             PerSession  
        |-TransactionIsolationLevel:       Unspecified  
        |-TransactionTimeout:              null  
        |-ValidateMustUnderstand:          true  
      |-Behavior[1]  
      |-Type:                       AspNetCompatibilityRequirementsAttribute  
      |-Behavior[2]  
      |-Type:                       ServiceDebugBehavior  
      |-Behavior[3]  
      |-Type:                       ServiceAuthorizationBehavior  
      |-Behavior[4]  
      |-Type:                       Behavior  
```  
  
 <span data-ttu-id="c9752-128">接下来，运行第二个 Java 脚本可以显示用户定义的 WMI 数据：</span><span class="sxs-lookup"><span data-stu-id="c9752-128">Next, run the second Java Script to display the user-defined WMI data:</span></span>  
  
```  
cscript EnumerateCustomObjects.js  
```  
  
 <span data-ttu-id="c9752-129">该脚本访问服务中包含的用户定义的规范，并生成下面的输出：</span><span class="sxs-lookup"><span data-stu-id="c9752-129">The script accesses the user-defined instrumentation contained in the services and produces the following output:</span></span>  
  
```  
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 <span data-ttu-id="c9752-130">该输出显示计算机上正在运行一个单一服务。</span><span class="sxs-lookup"><span data-stu-id="c9752-130">The output shows that there is a single service running on the computer.</span></span> <span data-ttu-id="c9752-131">该服务公开一个实现 `ICalculator` 协定的终结点。</span><span class="sxs-lookup"><span data-stu-id="c9752-131">The service exposes one endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="c9752-132">该终结点实现的行为和绑定的设置列作消息堆栈的各个元素的总和。</span><span class="sxs-lookup"><span data-stu-id="c9752-132">The settings of the behavior and binding that are implemented by the endpoint are listed as the sum of individual elements of the messaging stack.</span></span>  
  
 <span data-ttu-id="c9752-133">WMI 不仅限于公开 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 基础结构的管理规范。</span><span class="sxs-lookup"><span data-stu-id="c9752-133">WMI is not limited to exposing the management instrumentation of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure.</span></span> <span data-ttu-id="c9752-134">该应用程序可以通过相同机制公开它自己的特定域数据项。</span><span class="sxs-lookup"><span data-stu-id="c9752-134">The application can expose its own domain-specific data items through the same mechanism.</span></span> <span data-ttu-id="c9752-135">WMI 是用于检查和控制 Web 服务的统一机制。</span><span class="sxs-lookup"><span data-stu-id="c9752-135">WMI is a unified mechanism for inspection and control of a Web service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c9752-136">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="c9752-136">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="c9752-137">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="c9752-137">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="c9752-138">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="c9752-138">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="c9752-139">通过在宿主目录中的 service.dll 文件上运行 InstallUtil.exe（InstallUtil.exe 的默认位置是“%WINDIR%\Microsoft.NET\Framework\v4.0.30319”），可以将服务方案发布到 WMI。</span><span class="sxs-lookup"><span data-stu-id="c9752-139">Publish the services schema to WMI by running the InstallUtil.exe (the default locations for InstallUtil.exe is "%WINDIR%\Microsoft.NET\Framework\v4.0.30319") on the service.dll file in the hosting directory.</span></span> <span data-ttu-id="c9752-140">只有在对 service.dll 文件进行了更改的情况下才需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="c9752-140">This step only needs to be executed when changes have been made to the service.dll file.</span></span> <span data-ttu-id="c9752-141">有关详细信息，请参阅“如何：将方案发布到已检测的应用程序的 WMI”一节中位于 http://msdn2.microsoft.com/library/ms186147.aspx 的“通过检测应用程序提供管理信息”。</span><span class="sxs-lookup"><span data-stu-id="c9752-141">For more information, see Providing Management Information by Instrumenting Applications at: http://msdn2.microsoft.com/library/ms186147.aspx in the "How To: Publish the Scheme to WMI for an Instrumented Application" section.</span></span>  
  
4.  <span data-ttu-id="c9752-142">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="c9752-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c9752-143">如果您在安装 ASP.NET 之后安装了 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]，则可能需要运行 "%WINDIR%\ Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe " -r -x 以便为 ASPNET 帐户授予发布 WMI 对象的权限。</span><span class="sxs-lookup"><span data-stu-id="c9752-143">If you installed [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] after installing ASP.NET, you may need to run "%WINDIR%\ Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe " -r -x to give the ASPNET account permission to publish WMI objects.</span></span>  
  
5.  <span data-ttu-id="c9752-144">使用下面的命令可以查看通过 WMI 显示的示例：`cscript EnumerateServices.js` 或 `cscript EnumerateCustomObjects.js`。</span><span class="sxs-lookup"><span data-stu-id="c9752-144">View data from the sample surfaced through WMI by using the commands: `cscript EnumerateServices.js` or `cscript EnumerateCustomObjects.js`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9752-145">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="c9752-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c9752-146">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="c9752-146">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c9752-147">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="c9752-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c9752-148">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="c9752-148">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a><span data-ttu-id="c9752-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9752-149">See Also</span></span>  
 [<span data-ttu-id="c9752-150">AppFabric 监视示例</span><span class="sxs-lookup"><span data-stu-id="c9752-150">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
