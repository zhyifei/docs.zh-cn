---
title: "启用了 ReceiveContext 的 WCF 通道"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 765efb43efc0ea60ebb71bc8cdb5bd8edf973c2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="receivecontext-enabled-wcf-channels"></a>启用了 ReceiveContext 的 WCF 通道
本示例演示启用了 <xref:System.ServiceModel.Channels.ReceiveContext> 的 WCF 通道的用处。 本示例实现一个服务，以使用 NetMSMQ 通道查找两个数字的乘积。  
  
 应用程序使用 <xref:System.ServiceModel.Channels.ReceiveContext> 类可以决定是访问消息还是将其留在队列中供将来进行处理，即便是在已检查了消息内容后也可如此。 在本示例中，客户端向事务性队列发送随机整数。 `ProductCalculator` 服务接收消息，检查消息内容（为整数）以确定是否可以计算乘积。 如果服务操作不计算乘积，则消息会放回队列，可由侦听队列的服务再次接收。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  确保安装了 Microsoft 消息队列 (MSMQ)。  
  
    1.  在 [!INCLUDE[lserver](../../../../includes/lserver-md.md)] 上安装 MSMQ：  
  
        1.  在**服务器管理器**，单击**功能**。  
  
        2.  在右窗格中下**功能摘要**，单击**添加功能**。  
  
        3.  在生成的窗口中，展开**消息队列**。  
  
        4.  展开**消息队列服务**。  
  
        5.  单击**目录服务集成**（用于计算机加入到域的），然后单击**HTTP 支持**。  
  
        6.  单击**下一步**，然后单击**安装**。  
  
    2.  在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 上安装 MSMQ：  
  
        1.  打开“控制面板” 。  
  
        2.  单击**程序**，然后在**程序和功能**，单击**打开或关闭 Windows 功能**。  
  
        3.  展开**Microsoft Message Queue (MSMQ) 服务器**，展开**Microsoft 消息队列 (MSMQ) 服务器核心**，然后选择以下的消息队列功能，以安装对应的复选框：  
  
            -   消息队列服务器  
  
            -   MSMQ Active Directory 域服务集成（用于加入域的计算机）  
  
            -   MSMQ HTTP 支持  
  
        4.  单击 **“确定”**。  
  
        5.  如果系统提示您重新启动计算机时，请单击**确定**以完成安装。  
  
2.  确保计算机上安装了 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]。  
  
3.  使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 ReceiveContextProductGenerator.sln 解决方案文件。  
  
4.  要生成解决方案，按 Ctrl+Shift+B。  
  
5.  若要运行解决方案，请按 Ctrl+F5。
