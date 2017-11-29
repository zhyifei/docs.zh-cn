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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c7611ce26c1a3b9150a60ced7b4931cc1282eecd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
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
