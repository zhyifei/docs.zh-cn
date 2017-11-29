---
title: "异常、事务和补偿"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: be803580a4d8ed195222e5960cfa6e26804d91c5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="9dd13-102">异常、事务和补偿</span><span class="sxs-lookup"><span data-stu-id="9dd13-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)]<span data-ttu-id="9dd13-103"> 为在工作流中处理运行时错误条件提供了多个不同机制。</span><span class="sxs-lookup"><span data-stu-id="9dd13-103"> provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="9dd13-104">工作流可以结合使用异常处理程序、事务、取消以及补偿来妥善处理错误条件并从中恢复。</span><span class="sxs-lookup"><span data-stu-id="9dd13-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9dd13-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="9dd13-105">In This Section</span></span>  
 [<span data-ttu-id="9dd13-106">异常</span><span class="sxs-lookup"><span data-stu-id="9dd13-106">Exceptions</span></span>](../../../docs/framework/windows-workflow-foundation/exceptions.md)  
 <span data-ttu-id="9dd13-107">演示如何使用 <xref:System.Activities.Statements.TryCatch> 活动在工作流中处理异常。</span><span class="sxs-lookup"><span data-stu-id="9dd13-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="9dd13-108">事务</span><span class="sxs-lookup"><span data-stu-id="9dd13-108">Transactions</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-transactions.md)  
 <span data-ttu-id="9dd13-109">演示如何使用 <xref:System.Activities.Statements.TransactionScope> 活动在工作流中使用事务。</span><span class="sxs-lookup"><span data-stu-id="9dd13-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="9dd13-110">补偿</span><span class="sxs-lookup"><span data-stu-id="9dd13-110">Compensation</span></span>](../../../docs/framework/windows-workflow-foundation/compensation.md)  
 <span data-ttu-id="9dd13-111">介绍工作流中的补偿并演示如何使用补偿活动，如 <xref:System.Activities.Statements.CompensableActivity>、<xref:System.Activities.Statements.Compensate> 和 <xref:System.Activities.Statements.Confirm>。</span><span class="sxs-lookup"><span data-stu-id="9dd13-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="9dd13-112">取消</span><span class="sxs-lookup"><span data-stu-id="9dd13-112">Cancellation</span></span>](../../../docs/framework/windows-workflow-foundation/modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="9dd13-113">介绍如何使用内置活动以及自定义活动来在工作流中执行取消处理。</span><span class="sxs-lookup"><span data-stu-id="9dd13-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="9dd13-114">调试工作流</span><span class="sxs-lookup"><span data-stu-id="9dd13-114">Debugging Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/debugging-workflows.md)  
 <span data-ttu-id="9dd13-115">介绍如何调试工作流。</span><span class="sxs-lookup"><span data-stu-id="9dd13-115">Describes how to debug workflows.</span></span>
