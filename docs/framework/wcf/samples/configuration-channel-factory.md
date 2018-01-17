---
title: "配置通道工厂"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13001ff291c1d2874e5c9ce6e427afe09067432a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="configuration-channel-factory"></a>配置通道工厂
此示例介绍 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 的用法。 通过 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>，可以集中管理 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端配置。 这可能在应用程序域加载时间之后选择或更改配置的方案中也非常有用。  
  
## <a name="demonstrates"></a>演示  
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>  
  
## <a name="discussion"></a>讨论  
 此示例演示如何使用 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 将特定配置文件添加到客户端应用程序，而不必使用默认的应用程序文件。  
  
 此示例由两个项目组成。 第一个项目是一个简单服务，运行该服务可答复来自客户端的消息。 第二个项目是一个客户端应用程序，它使用 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 为 Test.config 配置文件生成两个 <xref:System.Configuration.ExeConfigurationFileMap> 对象，然后使用这两个对象与服务通信。 两个客户端都使用 Test.config 中指定的配置与服务通信。  
  
 以下代码可将自定义配置文件添加到客户端应用程序。  
  
```  
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();  
fileMap.ExeConfigFilename = "Test.config";  
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);  
  
ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));  
ICalculatorChannel client1 = factory1.CreateChannel();  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  使用管理员权限打开 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。  
  
2.  右击击 ConfigurationChannelFactory 解决方案 （2 个项目），然后选择**属性**。  
  
3.  在**通用属性**，选择**启动项目**，然后单击**多启动项目**。  
  
4.  移动**服务**与项目的列表中，开始到**操作开始**，，然后移动**客户端**项目后**服务**项目，还使用**操作开始**，因此**客户端**项目执行后**服务**项目。  
  
5.  单击**确定**，然后按 F5 （或 CTRL + F5） 来运行该示例。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
