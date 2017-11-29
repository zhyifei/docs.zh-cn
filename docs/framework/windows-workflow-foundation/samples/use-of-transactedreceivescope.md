---
title: "使用 TransactedReceiveScope"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d455f1dc-bfc5-43d6-8ae9-bc3b3a3ea08a
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b01352910c52d117d7ab0adcd94320ff9cf6931d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="use-of-transactedreceivescope"></a>使用 TransactedReceiveScope
此示例演示如何使用 <xref:System.Activities.Statements.TransactionScope> 将事务从客户端流动到服务器，以在客户端上创建一个新的事务和一个 <xref:System.ServiceModel.Activities.TransactedReceiveScope>，从而接收具有流动的事务的消息，并确定事务在服务器上的生存期范围。 此示例由充当客户端和服务器角色的两个项目组成。  
  
## <a name="client-application"></a>客户端应用程序  
 客户端应用程序运行一个工作流，该工作流输出分布式事务 ID，向服务器发送消息，流动事务，接收回复，再次输出分布式事务 ID 并完成操作。 最初输出分布式事务 ID 时，它是一个空 GUID，因为事务仍然仅为本地事务。  
  
## <a name="server-application"></a>服务器应用程序  
 服务器项目与客户端项目相似，不过，工作流承载于 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 中，因为它必须在一个终结点上侦听来自客户端的消息。 工作流位于 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 的中心，后者从客户端接收流动的事务，输出已发送的消息，输出分布式事务 ID 并向客户端发送回复。 分布式事务 ID 现在为非空 GUID，如果已在 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 的主体中添加了一个识别事务的活动，则它将在流动的事务下执行。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 TransactedReceiveScope.sln 解决方案。  
  
2.  若要生成解决方案，按 CTRL + SHIFT + B 或选择**生成解决方案**从**生成**菜单。  
  
3.  成功生成之后，右键单击解决方案并选择**设置启动项目**。 在对话框中，选择**多启动项目**并确保这两个项目的操作是**启动**。  
  
4.  按 F5，或选择**启动调试**从**调试**菜单。 或者，你可以按 CTRL + F5，或选择**启动但不调试**从**调试**菜单运行而不调试。  
  
    > [!NOTE]
    >  在启动客户端之前，服务器必须正在运行。 承载服务的控制台窗口的输出将指示它启动的时间。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TransactedReceiveScope`  
  
## <a name="see-also"></a>另请参阅
