---
title: "事务支持"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 79cd52f137347ec24e7cc9a646d0306d95fe53d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="transaction-support"></a><span data-ttu-id="aa55e-102">事务支持</span><span class="sxs-lookup"><span data-stu-id="aa55e-102">Transaction Support</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="aa55e-103">支持三种不同的事务模型。</span><span class="sxs-lookup"><span data-stu-id="aa55e-103"> supports three distinct transaction models.</span></span> <span data-ttu-id="aa55e-104">下文按执行检查的顺序列出了这些模型。</span><span class="sxs-lookup"><span data-stu-id="aa55e-104">The following lists these models in the order of checks performed.</span></span>  
  
## <a name="explicit-local-transaction"></a><span data-ttu-id="aa55e-105">显式本地事务</span><span class="sxs-lookup"><span data-stu-id="aa55e-105">Explicit Local Transaction</span></span>  
 <span data-ttu-id="aa55e-106">调用 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 时，如果 <xref:System.Data.Linq.DataContext.Transaction%2A> 属性设置为 (`IDbTransaction`) 事务，则在同一事务的上下文中执行 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 调用。</span><span class="sxs-lookup"><span data-stu-id="aa55e-106">When <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called, if the <xref:System.Data.Linq.DataContext.Transaction%2A> property is set to a (`IDbTransaction`) transaction, the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> call is executed in the context of the same transaction.</span></span>  
  
 <span data-ttu-id="aa55e-107">成功执行事务后，要由您来提交或回滚事务。</span><span class="sxs-lookup"><span data-stu-id="aa55e-107">It is your responsibility to commit or rollback the transaction after successful execution of the transaction.</span></span> <span data-ttu-id="aa55e-108">与事务对应的连接必须与用于构造 <xref:System.Data.Linq.DataContext> 的连接匹配。</span><span class="sxs-lookup"><span data-stu-id="aa55e-108">The connection corresponding to the transaction must match the connection used for constructing the <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="aa55e-109">如果使用其他连接，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="aa55e-109">An exception is thrown if a different connection is used.</span></span>  
  
## <a name="explicit-distributable-transaction"></a><span data-ttu-id="aa55e-110">显式可分发事务</span><span class="sxs-lookup"><span data-stu-id="aa55e-110">Explicit Distributable Transaction</span></span>  
 <span data-ttu-id="aa55e-111">可以在活动 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的作用域中调用 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> API（包括但不限于 <xref:System.Transactions.Transaction>）。</span><span class="sxs-lookup"><span data-stu-id="aa55e-111">You can call [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] APIs (including but not limited to <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) in the scope of an active <xref:System.Transactions.Transaction>.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="aa55e-112">检测到调用是在事务范围中并不会创建一个新的事务。</span><span class="sxs-lookup"><span data-stu-id="aa55e-112"> detects that the call is in the scope of a transaction and does not create a new transaction.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="aa55e-113">此外可以避免这种情况下关闭连接。</span><span class="sxs-lookup"><span data-stu-id="aa55e-113"> also avoids closing the connection in this case.</span></span> <span data-ttu-id="aa55e-114">您可以在此类事务的上下文中执行查询和 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 操作。</span><span class="sxs-lookup"><span data-stu-id="aa55e-114">You can perform query and <xref:System.Data.Linq.DataContext.SubmitChanges%2A> executions in the context of such a transaction.</span></span>  
  
## <a name="implicit-transaction"></a><span data-ttu-id="aa55e-115">隐式事务</span><span class="sxs-lookup"><span data-stu-id="aa55e-115">Implicit Transaction</span></span>  
 <span data-ttu-id="aa55e-116">当您调用 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会检查此调用是否在 <xref:System.Transactions.Transaction> 的作用域内或者 `Transaction` 属性 (`IDbTransaction`) 是否设置为由用户启动的本地事务。</span><span class="sxs-lookup"><span data-stu-id="aa55e-116">When you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] checks to see whether the call is in the scope of a <xref:System.Transactions.Transaction> or if the `Transaction` property (`IDbTransaction`) is set to a user-started local transaction.</span></span> <span data-ttu-id="aa55e-117">如果这两个事务均未找到，则 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 启动本地事务 (`IDbTransaction`)，并使用此事务执行所生成的 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="aa55e-117">If it finds neither transaction, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] starts a local transaction (`IDbTransaction`) and uses it to execute the generated SQL commands.</span></span> <span data-ttu-id="aa55e-118">当所有 SQL 命令均已成功执行完毕时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 提交本地事务并返回。</span><span class="sxs-lookup"><span data-stu-id="aa55e-118">When all SQL commands have been successfully completed, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] commits the local transaction and returns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa55e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa55e-119">See Also</span></span>  
 [<span data-ttu-id="aa55e-120">背景信息</span><span class="sxs-lookup"><span data-stu-id="aa55e-120">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="aa55e-121">如何：通过使用事务对数据提交进行分类</span><span class="sxs-lookup"><span data-stu-id="aa55e-121">How to: Bracket Data Submissions by Using Transactions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)
