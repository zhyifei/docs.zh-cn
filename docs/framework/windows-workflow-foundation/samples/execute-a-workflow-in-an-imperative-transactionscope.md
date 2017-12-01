---
title: "在命令式 TransactionScope 中执行工作流"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd0e8686-c1d0-4400-a541-da94ed03afc7
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40a9e00659cad1dd2ab22b85f3ed15d958fd107b
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="execute-a-workflow-in-an-imperative-transactionscope"></a>在命令式 TransactionScope 中执行工作流
此示例演示如何利用命令性 C# 代码，在 <xref:System.Activities.WorkflowInvoker> 中使用 <xref:System.Transactions.Transaction> 来执行工作流。  
  
## <a name="sample-details"></a>示例详细信息  
 在命令性 C# 代码中，使用 <xref:System.Transactions.TransactionScope> 封装在同一个事务中执行的工作集。 <xref:System.Transactions.TransactionScope> 采用以下工作方式：创建一个环境事务并初始化 <xref:System.Transactions.Transaction.Current%2A> 属性，对该线程执行的任何工作然后可以访问该属性。  
  
 若要在工作流中实现等效行为，在执行各项活动之前，运行时必须完成初始化 <xref:System.Transactions.Transaction.Current%2A> 的额外工作，因为工作流在各活动之间不会维护线程关联。 利用此运行时支持，获得的行为是：当在 <xref:System.Activities.WorkflowInvoker> 内使用 <xref:System.Transactions.TransactionScope> 执行工作流时，必须确保所有活动在由 <xref:System.Transactions.TransactionScope> 创建的环境事务上下文下运行。  
  
 对于每个工作流实例，一个工作流只能有一个环境事务；不可使用嵌套事务。 即使工作流包含一个 <xref:System.Activities.Statements.TransactionScope> 活动，这也不会创建一个新的内部事务， 而是重用在工作流外部创建的环境事务。  
  
 此示例开始一个新的 <xref:System.Transactions.TransactionScope>，输出事务 ID 并使用 <xref:System.Activities.WorkflowInvoker> 开始一个工作流。 该工作流再次输出事务 ID 以表明这是同一个事务，然后运行一个 <xref:System.Activities.Statements.TransactionScope>，最后完成操作。 由于 <xref:System.Activities.WorkflowInvoker.Invoke%2A> 上的 <xref:System.Activities.WorkflowInvoker> 调用是同步的，因此，原始线程在工作流完成之前将一直阻塞。 在工作流完成之后，相应的事务也会随之完成并释放资源。  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 ImperativeTransactionSample.sln 解决方案文件。  
  
2.  要生成解决方案，按 Ctrl+Shift+B。  
  
3.  若要运行解决方案，请按 F5。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\ImperativeTransaction`