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
ms.workload: dotnet
ms.openlocfilehash: 79970ad1220e3aab393a18cf52f94487702f37d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="transactions"></a><span data-ttu-id="2c654-102">事务</span><span class="sxs-lookup"><span data-stu-id="2c654-102">Transactions</span></span>
<span data-ttu-id="2c654-103">本节包含用于演示 [!INCLUDE[wf](../../../../includes/wf-md.md)] 中的工作流事务的示例。</span><span class="sxs-lookup"><span data-stu-id="2c654-103">This section contains samples that demonstrate workflow transactions in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2c654-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="2c654-104">In This Section</span></span>  
 [<span data-ttu-id="2c654-105">基本 TransactionScope</span><span class="sxs-lookup"><span data-stu-id="2c654-105">Basic TransactionScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 <span data-ttu-id="2c654-106">包含四个演示如何嵌套 <xref:System.Activities.Statements.TransactionScope> 实例的方案。</span><span class="sxs-lookup"><span data-stu-id="2c654-106">Consists of four scenarios that show how to nest <xref:System.Activities.Statements.TransactionScope> instances.</span></span>  
  
 [<span data-ttu-id="2c654-107">使用 TransactedReceiveScope</span><span class="sxs-lookup"><span data-stu-id="2c654-107">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 <span data-ttu-id="2c654-108">演示如何使用 <xref:System.Activities.Statements.TransactionScope> 将事务从客户端流动到服务器，以在客户端上创建一个新的事务和一个 <xref:System.ServiceModel.Activities.TransactedReceiveScope>，从而接收具有流动的事务的消息，并确定事务在服务器上的生存期范围。</span><span class="sxs-lookup"><span data-stu-id="2c654-108">Demonstrates how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span>  
  
 [<span data-ttu-id="2c654-109">服务内的 TransactionScope 嵌套</span><span class="sxs-lookup"><span data-stu-id="2c654-109">Nesting of TransactionScope within a service</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 <span data-ttu-id="2c654-110">包含两个演示如何在服务中处理 <xref:System.Activities.Statements.TransactionScope> 活动实例的方案。</span><span class="sxs-lookup"><span data-stu-id="2c654-110">Consists of two scenarios that show how to handle <xref:System.Activities.Statements.TransactionScope> activity instances within a service.</span></span>
