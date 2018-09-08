---
title: 基于配置的激活
ms.date: 03/30/2017
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
ms.openlocfilehash: e016dffdaf93b222c1fd2380bfa175256b009068
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44188301"
---
# <a name="configuration-based-activation"></a>基于配置的激活
此示例演示如何在不需要.svc 文件的情况下激活 Windows Communication Foundation (WCF) 服务。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## <a name="sample-details"></a>示例详细信息  
 在此示例中，客户端 WCF 测试客户端，并且服务承载在 IIS 中。  
  
> [!NOTE]
>  本主题的最后提供了此示例的设置和生成说明。  
  
### <a name="activation-of-services-without-requiring-a-svc-file"></a>在不需要 .svc 文件的情况下激活服务  
 在 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] 中，激活服务需要一个 .svc 文件。 这会导致额外的管理开销，因为需要与该应用程序一起部署和维护一个附加文件。 [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] 发布后，可使用应用程序配置文件来配置激活组件。  
  
 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] 在应用程序配置文件的 <xref:System.ServiceModel.Configuration.ServiceActivationElement> 中引入了一个新的配置元素 (<xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>)。 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> 集合接受要激活的服务集合，如下面的代码示例所示。  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
```  
  
 观察发现，该配置看上去非常类似于 .svc 文件的配置。 引入的一个附加特性是 `relativeAddress`，它可以提供服务的地址。 相对地址也是该服务的虚拟路径。 主机从 `virtualPath` 位置检索该文件的 Web.config 文件（如果存在），否则主机以递归方式搜索其父文件夹。  
  
> [!NOTE]
>  此示例需要在 IIS 中承载才能正常工作。  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 Service.csproj 文件。  
  
2.  要生成解决方案，按 Ctrl+Shift+B。  
  
3.  通过运行 WCFTestClient.exe 测试该服务。  
  
4.  使用 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]，导航到 %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE 文件夹。  
  
5.  运行 WcfTestClient.exe。  
  
6.  设置该服务的 MEX 地址。  
  
7.  按 Ctrl+Shift+A 设置服务地址。  
  
8.  将该地址设置 http://localhost/ServiceModelSamples/Calculator.svc 。  
  
9. 执行 `Add` 操作。 将 `n1` 参数上的值设置为 10，并将 `n2` 参数上的值设置为 15。  
  
10. 按**调用**。  
  
     预期结果为 25。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  确保您已执行了[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2.  若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。  
  
3.  生成解决方案后，运行 Setup.bat 以在 IIS 中设置 ServiceModelSamples 应用程序。 现在，ServiceModelSamples 目录应显示为 IIS 应用程序。  
  
4.  若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。  
  
## <a name="see-also"></a>请参阅  
 [AppFabric 承载和持久性示例](https://go.microsoft.com/fwlink/?LinkId=193961)
