---
title: 服务内的 TransactionScope 嵌套
ms.date: 03/30/2017
ms.assetid: e7e1ba64-1384-4eba-add8-415636e2d6d0
ms.openlocfilehash: cf73c0c2d061f1c997a8ade5d7b2bf61887915ca
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266412"
---
# <a name="nesting-of-transactionscope-within-a-service"></a>服务内的 TransactionScope 嵌套
此示例包含两个演示如何在一个服务中处理 <xref:System.Activities.Statements.TransactionScope> 活动实例的方案。 首先使用 <xref:System.Activities.Statements.TransactionScope> 活动发起事务，以在客户端上创建一个新的事务和要接收的 <xref:System.ServiceModel.Activities.TransactedReceiveScope>，并确定事务在服务器上的生存期范围。 该服务内的第一个方案运行一个辅助 <xref:System.Activities.Statements.TransactionScope> 活动，以演示服务中的 <xref:System.Activities.Statements.TransactionScope> 活动的嵌套。 第二个方案演示如何在嵌套的 <xref:System.Activities.Statements.TransactionScope> 活动中遵循超时限制。  
  
## <a name="client-application"></a>客户端应用程序  
 客户端应用程序运行一个工作流，该工作流启动一个 <xref:System.Activities.Statements.TransactionScope> 活动，输出分布式事务 ID，向服务器发送消息，流动事务，接收回复，再次输出分布式事务 ID 并完成操作。 它对每个服务方案执行一次这样的操作。  
  
## <a name="server-application"></a>服务器应用程序  
 服务器项目承载于 <xref:System.ServiceModel.Activities.WorkflowServiceHost> 中，后者可创建用于侦听来自客户端的消息的终结点。 工作流位于 <xref:System.ServiceModel.Activities.TransactedReceiveScope> 的中心，后者从客户端接收流动的事务，输出分布式事务 ID，然后再次执行 <xref:System.Activities.Statements.TransactionScope> 活动。 在第一个方案中，事务成功完成。 在第二个方案中，<xref:System.Activities.Statements.TransactionScope> 活动的主体是 5 秒延迟，事务的超时设置为 2 秒。 当事务超时时，事务将会中止。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 TransactionServiceExample.sln 解决方案。  
  
2.  若要生成解决方案，请按 CTRL + SHIFT + B 或选择**生成解决方案**从**生成**菜单。  
  
3.  成功生成之后，右键单击解决方案并选择**设置启动项目**。 从对话框中，选择**多个启动项目**，并确保这两个项目的操作是**启动**。  
  
4.  按 F5 或选择**开始调试**从**调试**菜单。 或者，可以按 CTRL + F5 或选择**启动但不调试**从**调试**菜单运行而不进行调试。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TRSComposability`
