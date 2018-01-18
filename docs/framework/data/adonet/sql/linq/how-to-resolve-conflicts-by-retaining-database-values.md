---
title: "如何：通过保留数据库值解决冲突"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0747a4318fdab76c5fbd920f7291346d4d8ff58d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a><span data-ttu-id="e8dd5-102">如何：通过保留数据库值解决冲突</span><span class="sxs-lookup"><span data-stu-id="e8dd5-102">How to: Resolve Conflicts by Retaining Database Values</span></span>
<span data-ttu-id="e8dd5-103">若要先协调预期数据库值与实际数据库值之间的差异，再尝试重新提交更改，则可以使用 <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> 保留在数据库中找到的值。</span><span class="sxs-lookup"><span data-stu-id="e8dd5-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> to retain the values found in the database.</span></span> <span data-ttu-id="e8dd5-104">然后会覆盖对象模型中的当前值。</span><span class="sxs-lookup"><span data-stu-id="e8dd5-104">The current values in the object model are then overwritten.</span></span> <span data-ttu-id="e8dd5-105">有关详细信息，请参阅[开放式并发： 概述](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e8dd5-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8dd5-106">在所有情况下，都会先通过从数据库中检索更新后的数据来刷新客户端上的记录。</span><span class="sxs-lookup"><span data-stu-id="e8dd5-106">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="e8dd5-107">此操作确保了下一次更新尝试将通过相同的并发检查。</span><span class="sxs-lookup"><span data-stu-id="e8dd5-107">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8dd5-108">示例</span><span class="sxs-lookup"><span data-stu-id="e8dd5-108">Example</span></span>  
 <span data-ttu-id="e8dd5-109">在本方案中，当 User1 尝试提交更改时将引发 <xref:System.Data.Linq.ChangeConflictException> 异常，原因是 User2 同时已更改了 Assistant 和 Department 列。</span><span class="sxs-lookup"><span data-stu-id="e8dd5-109">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="e8dd5-110">下表说明了这种情况。</span><span class="sxs-lookup"><span data-stu-id="e8dd5-110">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="e8dd5-111">Manager</span><span class="sxs-lookup"><span data-stu-id="e8dd5-111">Manager</span></span>|<span data-ttu-id="e8dd5-112">Assistant</span><span class="sxs-lookup"><span data-stu-id="e8dd5-112">Assistant</span></span>|<span data-ttu-id="e8dd5-113">Department</span><span class="sxs-lookup"><span data-stu-id="e8dd5-113">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="e8dd5-114">原始数据库在被 User1 和 User2 查询时的状态。</span><span class="sxs-lookup"><span data-stu-id="e8dd5-114">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="e8dd5-115">Alfreds</span><span class="sxs-lookup"><span data-stu-id="e8dd5-115">Alfreds</span></span>|<span data-ttu-id="e8dd5-116">Maria</span><span class="sxs-lookup"><span data-stu-id="e8dd5-116">Maria</span></span>|<span data-ttu-id="e8dd5-117">销售额</span><span class="sxs-lookup"><span data-stu-id="e8dd5-117">Sales</span></span>|  
|<span data-ttu-id="e8dd5-118">User1 准备提交这些更改。</span><span class="sxs-lookup"><span data-stu-id="e8dd5-118">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="e8dd5-119">Alfred</span><span class="sxs-lookup"><span data-stu-id="e8dd5-119">Alfred</span></span>||<span data-ttu-id="e8dd5-120">Marketing</span><span class="sxs-lookup"><span data-stu-id="e8dd5-120">Marketing</span></span>|  
|<span data-ttu-id="e8dd5-121">User2 已经提交了这些更改。</span><span class="sxs-lookup"><span data-stu-id="e8dd5-121">User2 has already submitted these changes.</span></span>||<span data-ttu-id="e8dd5-122">Mary</span><span class="sxs-lookup"><span data-stu-id="e8dd5-122">Mary</span></span>|<span data-ttu-id="e8dd5-123">服务</span><span class="sxs-lookup"><span data-stu-id="e8dd5-123">Service</span></span>|  
  
 <span data-ttu-id="e8dd5-124">User1 决定通过用更新的数据库值覆盖对象模型中的当前值来解决此冲突。</span><span class="sxs-lookup"><span data-stu-id="e8dd5-124">User1 decides to resolve this conflict by having the newer database values overwrite the current values in the object model.</span></span>  
  
 <span data-ttu-id="e8dd5-125">User1 通过使用 <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> 解决了此冲突后，数据库中的结果将如下表中所示：</span><span class="sxs-lookup"><span data-stu-id="e8dd5-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, the result in the database is as follows in the table:</span></span>  
  
||<span data-ttu-id="e8dd5-126">Manager</span><span class="sxs-lookup"><span data-stu-id="e8dd5-126">Manager</span></span>|<span data-ttu-id="e8dd5-127">Assistant</span><span class="sxs-lookup"><span data-stu-id="e8dd5-127">Assistant</span></span>|<span data-ttu-id="e8dd5-128">Department</span><span class="sxs-lookup"><span data-stu-id="e8dd5-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="e8dd5-129">解决冲突后的新状态。</span><span class="sxs-lookup"><span data-stu-id="e8dd5-129">New state after conflict resolution.</span></span>|<span data-ttu-id="e8dd5-130">Alfreds</span><span class="sxs-lookup"><span data-stu-id="e8dd5-130">Alfreds</span></span><br /><br /> <span data-ttu-id="e8dd5-131">（原始）</span><span class="sxs-lookup"><span data-stu-id="e8dd5-131">(original)</span></span>|<span data-ttu-id="e8dd5-132">Mary</span><span class="sxs-lookup"><span data-stu-id="e8dd5-132">Mary</span></span><br /><br /> <span data-ttu-id="e8dd5-133">（来自 User2）</span><span class="sxs-lookup"><span data-stu-id="e8dd5-133">(from User2)</span></span>|<span data-ttu-id="e8dd5-134">服务</span><span class="sxs-lookup"><span data-stu-id="e8dd5-134">Service</span></span><br /><br /> <span data-ttu-id="e8dd5-135">（来自 User2）</span><span class="sxs-lookup"><span data-stu-id="e8dd5-135">(from User2)</span></span>|  
  
 <span data-ttu-id="e8dd5-136">下面的示例代码演示了如何用数据库值覆盖对象模型中的当前值。</span><span class="sxs-lookup"><span data-stu-id="e8dd5-136">The following example code shows how to overwrite current values in the object model with the database values.</span></span> <span data-ttu-id="e8dd5-137">（未对各个成员冲突进行检查或自定义处理。）</span><span class="sxs-lookup"><span data-stu-id="e8dd5-137">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e8dd5-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="e8dd5-138">See Also</span></span>  
 [<span data-ttu-id="e8dd5-139">如何：管理更改冲突</span><span class="sxs-lookup"><span data-stu-id="e8dd5-139">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
