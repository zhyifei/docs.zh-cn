---
title: 异常、事务和补偿
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], error handling
ms.assetid: 694db4f9-7387-4b13-8f9f-b923b18c7490
ms.openlocfilehash: c4d66e252561ad7b896ff8092e80013c51bd463c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774005"
---
# <a name="exceptions-transactions-and-compensation"></a><span data-ttu-id="ebaee-102">异常、事务和补偿</span><span class="sxs-lookup"><span data-stu-id="ebaee-102">Exceptions, Transactions, and Compensation</span></span>
[!INCLUDE[wf1](../../../includes/wf1-md.md)] <span data-ttu-id="ebaee-103">为在工作流中处理运行时错误条件提供了多个不同机制。</span><span class="sxs-lookup"><span data-stu-id="ebaee-103">provides several different mechanisms for handling run-time error conditions in workflows.</span></span> <span data-ttu-id="ebaee-104">工作流可以结合使用异常处理程序、事务、取消以及补偿来妥善处理错误条件并从中恢复。</span><span class="sxs-lookup"><span data-stu-id="ebaee-104">Workflows can use a combination of exception handlers, transactions, cancellation, and compensation to handle and recover gracefully from error conditions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ebaee-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="ebaee-105">In This Section</span></span>  
 [<span data-ttu-id="ebaee-106">异常</span><span class="sxs-lookup"><span data-stu-id="ebaee-106">Exceptions</span></span>](exceptions.md)  
 <span data-ttu-id="ebaee-107">演示如何使用 <xref:System.Activities.Statements.TryCatch> 活动在工作流中处理异常。</span><span class="sxs-lookup"><span data-stu-id="ebaee-107">Demonstrates how to use the <xref:System.Activities.Statements.TryCatch> activity to handle exceptions in a workflow.</span></span>  
  
 [<span data-ttu-id="ebaee-108">事务</span><span class="sxs-lookup"><span data-stu-id="ebaee-108">Transactions</span></span>](workflow-transactions.md)  
 <span data-ttu-id="ebaee-109">演示如何使用 <xref:System.Activities.Statements.TransactionScope> 活动在工作流中使用事务。</span><span class="sxs-lookup"><span data-stu-id="ebaee-109">Demonstrates how to use the <xref:System.Activities.Statements.TransactionScope> activity to use transactions in a workflow.</span></span>  
  
 [<span data-ttu-id="ebaee-110">补偿</span><span class="sxs-lookup"><span data-stu-id="ebaee-110">Compensation</span></span>](compensation.md)  
 <span data-ttu-id="ebaee-111">介绍工作流中的补偿并演示如何使用补偿活动，如 <xref:System.Activities.Statements.CompensableActivity>、<xref:System.Activities.Statements.Compensate> 和 <xref:System.Activities.Statements.Confirm>。</span><span class="sxs-lookup"><span data-stu-id="ebaee-111">Describes compensation in workflows and demonstrates how to use compensation activities such as <xref:System.Activities.Statements.CompensableActivity>, <xref:System.Activities.Statements.Compensate>, and <xref:System.Activities.Statements.Confirm>.</span></span>  
  
 [<span data-ttu-id="ebaee-112">取消</span><span class="sxs-lookup"><span data-stu-id="ebaee-112">Cancellation</span></span>](modeling-cancellation-behavior-in-workflows.md)  
 <span data-ttu-id="ebaee-113">介绍如何使用内置活动以及自定义活动来在工作流中执行取消处理。</span><span class="sxs-lookup"><span data-stu-id="ebaee-113">Describes how to perform cancellation handling in workflows using built-in activities as well as custom activities.</span></span>  
  
 [<span data-ttu-id="ebaee-114">调试工作流</span><span class="sxs-lookup"><span data-stu-id="ebaee-114">Debugging Workflows</span></span>](debugging-workflows.md)  
 <span data-ttu-id="ebaee-115">介绍如何调试工作流。</span><span class="sxs-lookup"><span data-stu-id="ebaee-115">Describes how to debug workflows.</span></span>
