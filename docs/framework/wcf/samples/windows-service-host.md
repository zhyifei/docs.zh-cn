---
title: Windows 服务主机
ms.date: 03/30/2017
helpviewer_keywords:
- NT Service
- NT Service Host Sample [Windows Communication Foundation]
ms.assetid: 1b2f45c5-2bed-4979-b0ee-8f9efcfec028
ms.openlocfilehash: 83b40f467af933b5da69b859d990fbe4ba005928
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143520"
---
# <a name="windows-service-host"></a>Windows 服务主机
此示例演示托管 Windows 服务中托管的 Windows 通信基础 （WCF） 服务。 Windows 服务使用 **"控制面板**"中的服务小程序进行控制，并可配置为在系统重新启动后自动启动。 此示例包含一个客户端程序和一个 Windows 服务程序。 服务作为一个 .exe 程序实现，并包含其自己的主机代码。 在其他承载环境（如 Windows 进程激活服务 (WAS) 或 Internet Information Services (IIS)）中，你没有必要编写承载代码。

> [!NOTE]
> 本主题的最后介绍了此示例的设置过程和生成说明。

> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WindowsService`  
  
 生成此服务之后，必须像任何其他 Windows 服务一样使用 Installutil.exe 实用工具安装此服务。 如果要对此服务进行更改，必须首先使用 `installutil /u` 将其卸载。 此示例中随附的 Setup.bat 和 Cleanup.bat 文件是用于安装和启动 Windows 服务的命令，还可用于关闭和卸载 Windows 服务。 仅当 Windows 服务正在运行时，WCF 服务才能响应客户端。 如果使用 **"控制面板**"中的服务小程序停止 Windows 服务并运行客户端，则客户端尝试<xref:System.ServiceModel.EndpointNotFoundException>访问该服务时将发生异常。 如果重新启动 Windows 服务并重新运行客户端，通信将成功。  
  
 服务代码包括安装程序类、实现 I计算器协定的 WCF 服务实现类以及充当运行时主机的 Windows 服务类。 安装程序类继承自 <xref:System.Configuration.Install.Installer>，允许通过 Installutil.exe 工具将程序安装为 NT 服务。 服务实现类`WcfCalculatorService`是实现基本服务协定的 WCF 服务。 此 WCF 服务托管在称为`WindowsCalculatorService`的 Windows 服务类中。 为了符合作为 Windows 服务的要求，该类从 <xref:System.ServiceProcess.ServiceBase> 继承并实现 <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> 和 <xref:System.ServiceProcess.ServiceBase.OnStop> 方法。 在 <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> 中，为 <xref:System.ServiceModel.ServiceHost> 类型创建并打开了 `WcfCalculatorService` 对象。 在 <xref:System.ServiceProcess.ServiceBase.OnStop> 中，通过调用 <xref:System.ServiceModel.Channels.CommunicationObject.Close%28System.TimeSpan%29> 对象的 <xref:System.ServiceModel.ServiceHost> 方法关闭了 ServiceHost。 主机的基本地址使用[\<add>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)元素进行配置，该元素是[\<基地址>](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)的子元素，它是[\<主机>](../../../../docs/framework/configure-apps/file-schema/wcf/host.md)元素的子项，该元素是[\<服务>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md)元素的子元素。  
  
 定义的终结点使用基本地址和[\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)。 下面的示例演示了基本地址的配置以及公开 CalculatorService 的终结点。  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.WcfCalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <host>  
      <baseAddresses>  
        <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
      </baseAddresses>  
    </host>  
    <!-- This endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service.  -->  
    <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    ...  
  </service>  
</services>  
```  
  
 运行示例时，操作请求和响应将显示在服务和客户端控制台窗口中。 在每个控制台窗口中按 Enter 可以关闭服务和客户端。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1. 确保已为 Windows[通信基础示例执行一次性设置过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2. 若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。  
  
3. 构建解决方案后，从提升的 Visual Studio 2012 命令提示符运行安装程序.bat，使用 Installutil.exe 工具安装 Windows 服务。 该服务应出现在“服务”中。  
  
4. 要在单计算机或跨计算机配置中运行示例，请按照[运行 Windows 通信基础示例中的](../../../../docs/framework/wcf/samples/running-the-samples.md)说明操作。  
  
## <a name="see-also"></a>另请参阅

- [AppFabric 承载和持久性示例](https://docs.microsoft.com/previous-versions/appfabric/ff383418(v=azure.10))
