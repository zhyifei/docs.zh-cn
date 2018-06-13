---
title: Transactions2
ms.date: 03/30/2017
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
ms.openlocfilehash: 361022851d971c0b9350899e1fee6a27c557d666
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514590"
---
# <a name="transactions"></a><span data-ttu-id="b735d-102">事务</span><span class="sxs-lookup"><span data-stu-id="b735d-102">Transactions</span></span>
<span data-ttu-id="b735d-103">本节包含演示工作流事务中 Windows Workflow Foundation (WF) 的示例。</span><span class="sxs-lookup"><span data-stu-id="b735d-103">This section contains samples that demonstrate workflow transactions in Windows Workflow Foundation (WF).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b735d-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="b735d-104">In This Section</span></span>  
 [<span data-ttu-id="b735d-105">基本 TransactionScope</span><span class="sxs-lookup"><span data-stu-id="b735d-105">Basic TransactionScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 <span data-ttu-id="b735d-106">包含四个演示如何嵌套 <xref:System.Activities.Statements.TransactionScope> 实例的方案。</span><span class="sxs-lookup"><span data-stu-id="b735d-106">Consists of four scenarios that show how to nest <xref:System.Activities.Statements.TransactionScope> instances.</span></span>  
  
 [<span data-ttu-id="b735d-107">使用 TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="b735d-107">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 <span data-ttu-id="b735d-108">演示如何使用 <xref:System.Activities.Statements.TransactionScope> 将事务从客户端流动到服务器，以在客户端上创建一个新的事务和一个 <xref:System.ServiceModel.Activities.TransactedReceiveScope>，从而接收具有流动的事务的消息，并确定事务在服务器上的生存期范围。</span><span class="sxs-lookup"><span data-stu-id="b735d-108">Demonstrates how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span>  
  
 [<span data-ttu-id="b735d-109">服务内的 TransactionScope 嵌套</span><span class="sxs-lookup"><span data-stu-id="b735d-109">Nesting of TransactionScope within a service</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 <span data-ttu-id="b735d-110">包含两个演示如何在服务中处理 <xref:System.Activities.Statements.TransactionScope> 活动实例的方案。</span><span class="sxs-lookup"><span data-stu-id="b735d-110">Consists of two scenarios that show how to handle <xref:System.Activities.Statements.TransactionScope> activity instances within a service.</span></span>
