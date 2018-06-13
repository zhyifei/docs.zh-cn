---
title: 异常、事务和补偿
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: 346b07cd89c4071088676235d457930637b71549
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512205"
---
# <a name="exceptions-transactions-and-compensation"></a>异常、事务和补偿
[!INCLUDE[wf1](../../../includes/wf1-md.md)] 为在工作流中处理运行时错误条件提供了多个不同机制。 工作流可以结合使用异常处理程序、事务、取消以及补偿来妥善处理错误条件并从中恢复。  
  
## <a name="in-this-section"></a>本节内容  
 [异常](../../../docs/framework/windows-workflow-foundation/exceptions.md)  
 演示如何使用 <xref:System.Activities.Statements.TryCatch> 活动在工作流中处理异常。  
  
 [事务](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)  
 演示如何使用 <xref:System.Activities.Statements.TransactionScope> 活动在工作流中使用事务。  
  
 [补偿](../../../docs/framework/windows-workflow-foundation/compensation.md)  
 介绍工作流中的补偿并演示如何使用补偿活动，如 <xref:System.Activities.Statements.CompensableActivity>、<xref:System.Activities.Statements.Compensate> 和 <xref:System.Activities.Statements.Confirm>。  
  
 [取消](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)  
 介绍如何使用内置活动以及自定义活动来在工作流中执行取消处理。  
  
 [调试工作流](../../../docs/framework/windows-workflow-foundation/debugging-workflows.md)  
 介绍如何调试工作流。
