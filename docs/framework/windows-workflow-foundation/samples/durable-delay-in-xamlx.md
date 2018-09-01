---
title: XAMLX 中的持久延迟
ms.date: 03/30/2017
ms.assetid: efc38df4-2d34-453c-8e59-2c21d1307354
ms.openlocfilehash: 1eef9211c67d190ecb5f329c481fa2e3d1763353
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43389252"
---
# <a name="durable-delay-in-xamlx"></a>XAMLX 中的持久延迟
此示例演示如何使用持久延迟，在持久延迟过程中，将把工作流保留到持久性设备。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlx`  
  
## <a name="discussion"></a>讨论  
 示例工作流包含发往一个本地文件并由延迟分隔的两个消息。 触发延迟时，工作流会卸载，并在重新加载到内存中之前，在工作流实例存储中等待 5 秒。  
  
 .Xamlx 文件是 Visual Studio 中托管的工作流服务。 Visual Studio 使用 Cassini 使用工作流服务主机来承载工作流。  
  
 除了承载工作流之外，工作流服务主机还通过加载和卸载工作流实例来对其进行管理。 若要开始 （在工作流服务主机） 上的 Windows Workflow Foundation (WF) 定义的实例，设置发送到消息的客户端<xref:System.ServiceModel.Activities.Receive>在工作流活动。 此 <xref:System.ServiceModel.Activities.Receive> 将自己的 <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> 属性设置为 `true`，从而可以在接收到消息时创建工作流的新实例。  
  
 初始化过程中，会将一个卸载实例行为添加到配置文件，该行为应在该配置文件指定到的工作流服务主机下，将实例卸载到持久性存储区（数据库）。 对于此示例，它在工作流进入空闲状态后（触发了延迟时）立即卸载实例。  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。  
  
2.  导航到 DurableDelayXamlx\CS 文件夹。  
  
3.  运行 Setup.cmd。  
  
4.  以管理员身份运行 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。  
  
5.  打开 DurableDelayXamlx.sln 解决方案文件。  
  
6.  在中**解决方案资源管理器**，右键单击解决方案并选择**属性**。  
  
7.  选择**多个启动项目**并将这两个项目设置为**启动**。  
  
8.  要生成解决方案，按 Ctrl+Shift+B。  
  
9. 若要运行解决方案，请按 Ctrl+F5。  
  
#### <a name="to-uninstall-this-sample"></a>卸载此示例  
  
1.  打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。  
  
2.  导航到 DurableDelayXamlx\CS 文件夹。  
  
3.  运行 Cleanup.cmd。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelayXamlX`
