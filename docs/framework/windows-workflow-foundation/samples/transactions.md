---
title: Transactions2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 73bfef97de5c6622a6dda4edb2e4ff0b829df7e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="transactions"></a>事务
本节包含用于演示 [!INCLUDE[wf](../../../../includes/wf-md.md)] 中的工作流事务的示例。  
  
## <a name="in-this-section"></a>本节内容  
 [基本 TransactionScope](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 包含四个演示如何嵌套 <xref:System.Activities.Statements.TransactionScope> 实例的方案。  
  
 [使用 TransactedReceiveScope](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 演示如何使用 <xref:System.Activities.Statements.TransactionScope> 将事务从客户端流动到服务器，以在客户端上创建一个新的事务和一个 <xref:System.ServiceModel.Activities.TransactedReceiveScope>，从而接收具有流动的事务的消息，并确定事务在服务器上的生存期范围。  
  
 [服务内的 TransactionScope 嵌套](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 包含两个演示如何在服务中处理 <xref:System.Activities.Statements.TransactionScope> 活动实例的方案。
