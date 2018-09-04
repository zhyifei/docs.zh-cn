---
title: 持久延迟
ms.date: 03/30/2017
ms.assetid: 220ec240-b958-430c-81ff-b734a6aa97ae
ms.openlocfilehash: 2a7692e28d60232913ae5d11a90025e59664c0e5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43507628"
---
# <a name="durable-delay"></a>持久延迟
此示例演示如何使用持久延迟，在持久延迟过程中，将把工作流保留到持久性设备。 示例工作流包含发送到控制台并由延迟分隔的两个消息。 触发延迟时，工作流会卸载，并在重新加载到内存中之前，在工作流实例存储中等待 5 秒。  
  
## <a name="workflow-details"></a>工作流详细信息  
 工作流服务主机承载工作流，并通过加载和卸载工作流实例来对其进行管理。 为了启动工作流定义的实例，此示例设置了一个代理，用于向工作流中的 <xref:System.ServiceModel.Activities.Receive> 活动发送消息。 <xref:System.ServiceModel.Activities.Receive.CanCreateInstance%2A> 属性设置为 `true`，从而可以在接收到消息时创建工作流的新实例。  
  
 下面的列表详细介绍初始化过程中工作流服务主机进行的设置。  
  
1.  创建服务主机的地址 (http://localhost:8080/Client)。  
  
2.  在该服务主机中创建一个终结点，以便与工作流内的 <xref:System.ServiceModel.Activities.Receive> 活动进行通信。  
  
3.  设置 SQL 实例存储区。  
  
4.  添加一个卸载实例行为，指定工作流服务主机在什么条件下应将工作流实例卸载到 SQL 持久性存储区。 对于此示例，它在工作流进入空闲状态后（触发了延迟时）立即卸载实例。  
  
5.  创建向工作流中的 <xref:System.ServiceModel.Activities.Receive> 活动发送消息的代理。  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  设置持久性数据库。  
  
    1.  打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。  
  
    2.  导航到[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]目录 (C:\Windows\Microsoft.NET\Framework\v4。X\\)。  
  
    3.  编辑 WorkflowManagementService.exe.config 文件，将以下连接字符串添加到 <`database`> 元素内。  
  
        ```xml  
        <database connectionString="Data Source=localhost\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True;Asynchronous Processing=True" />  
        ```  
  
    4.  导航到 DurableDelay\CS 目录。  
  
    5.  运行 Setup.cmd。  
  
2.  运行[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]通过右键单击使用提升的权限[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]图标，然后选择**以管理员身份运行**。  
  
3.  打开 Delay.sln 解决方案文件。  
  
4.  按 Ctrl+Shift+B 生成解决方案。  
  
5.  若要运行解决方案，请按 Ctrl+F5。  
  
#### <a name="to-uninstall-this-sample"></a>卸载此示例  
  
1.  打开一个 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符。  
  
2.  导航到 DurableDelay\CS 目录。  
  
3.  运行 Cleanup.cmd。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDelay`