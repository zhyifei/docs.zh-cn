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
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1271d7b287dacdae0dd46f084ba21d0dc901bd49
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a><span data-ttu-id="2e821-102">如何：通过保留数据库值解决冲突</span><span class="sxs-lookup"><span data-stu-id="2e821-102">How to: Resolve Conflicts by Retaining Database Values</span></span>
<span data-ttu-id="2e821-103">若要先协调预期数据库值与实际数据库值之间的差异，再尝试重新提交更改，则可以使用 <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> 保留在数据库中找到的值。</span><span class="sxs-lookup"><span data-stu-id="2e821-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> to retain the values found in the database.</span></span> <span data-ttu-id="2e821-104">然后会覆盖对象模型中的当前值。</span><span class="sxs-lookup"><span data-stu-id="2e821-104">The current values in the object model are then overwritten.</span></span> <span data-ttu-id="2e821-105">有关详细信息，请参阅[开放式并发： 概述](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2e821-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e821-106">在所有情况下，都会先通过从数据库中检索更新后的数据来刷新客户端上的记录。</span><span class="sxs-lookup"><span data-stu-id="2e821-106">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="2e821-107">此操作确保了下一次更新尝试将通过相同的并发检查。</span><span class="sxs-lookup"><span data-stu-id="2e821-107">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e821-108">示例</span><span class="sxs-lookup"><span data-stu-id="2e821-108">Example</span></span>  
 <span data-ttu-id="2e821-109">在本方案中，当 User1 尝试提交更改时将引发 <xref:System.Data.Linq.ChangeConflictException> 异常，原因是 User2 同时已更改了 Assistant 和 Department 列。</span><span class="sxs-lookup"><span data-stu-id="2e821-109">In this scenario, a <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="2e821-110">下表说明了这种情况。</span><span class="sxs-lookup"><span data-stu-id="2e821-110">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="2e821-111">Manager</span><span class="sxs-lookup"><span data-stu-id="2e821-111">Manager</span></span>|<span data-ttu-id="2e821-112">Assistant</span><span class="sxs-lookup"><span data-stu-id="2e821-112">Assistant</span></span>|<span data-ttu-id="2e821-113">Department</span><span class="sxs-lookup"><span data-stu-id="2e821-113">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="2e821-114">原始数据库在被 User1 和 User2 查询时的状态。</span><span class="sxs-lookup"><span data-stu-id="2e821-114">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="2e821-115">Alfreds</span><span class="sxs-lookup"><span data-stu-id="2e821-115">Alfreds</span></span>|<span data-ttu-id="2e821-116">Maria</span><span class="sxs-lookup"><span data-stu-id="2e821-116">Maria</span></span>|<span data-ttu-id="2e821-117">销售额</span><span class="sxs-lookup"><span data-stu-id="2e821-117">Sales</span></span>|  
|<span data-ttu-id="2e821-118">User1 准备提交这些更改。</span><span class="sxs-lookup"><span data-stu-id="2e821-118">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="2e821-119">Alfred</span><span class="sxs-lookup"><span data-stu-id="2e821-119">Alfred</span></span>||<span data-ttu-id="2e821-120">Marketing</span><span class="sxs-lookup"><span data-stu-id="2e821-120">Marketing</span></span>|  
|<span data-ttu-id="2e821-121">User2 已经提交了这些更改。</span><span class="sxs-lookup"><span data-stu-id="2e821-121">User2 has already submitted these changes.</span></span>||<span data-ttu-id="2e821-122">Mary</span><span class="sxs-lookup"><span data-stu-id="2e821-122">Mary</span></span>|<span data-ttu-id="2e821-123">服务</span><span class="sxs-lookup"><span data-stu-id="2e821-123">Service</span></span>|  
  
 <span data-ttu-id="2e821-124">User1 决定通过用更新的数据库值覆盖对象模型中的当前值来解决此冲突。</span><span class="sxs-lookup"><span data-stu-id="2e821-124">User1 decides to resolve this conflict by having the newer database values overwrite the current values in the object model.</span></span>  
  
 <span data-ttu-id="2e821-125">User1 通过使用 <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> 解决了此冲突后，数据库中的结果将如下表中所示：</span><span class="sxs-lookup"><span data-stu-id="2e821-125">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, the result in the database is as follows in the table:</span></span>  
  
||<span data-ttu-id="2e821-126">Manager</span><span class="sxs-lookup"><span data-stu-id="2e821-126">Manager</span></span>|<span data-ttu-id="2e821-127">Assistant</span><span class="sxs-lookup"><span data-stu-id="2e821-127">Assistant</span></span>|<span data-ttu-id="2e821-128">Department</span><span class="sxs-lookup"><span data-stu-id="2e821-128">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="2e821-129">解决冲突后的新状态。</span><span class="sxs-lookup"><span data-stu-id="2e821-129">New state after conflict resolution.</span></span>|<span data-ttu-id="2e821-130">Alfreds</span><span class="sxs-lookup"><span data-stu-id="2e821-130">Alfreds</span></span><br /><br /> <span data-ttu-id="2e821-131">（原始）</span><span class="sxs-lookup"><span data-stu-id="2e821-131">(original)</span></span>|<span data-ttu-id="2e821-132">Mary</span><span class="sxs-lookup"><span data-stu-id="2e821-132">Mary</span></span><br /><br /> <span data-ttu-id="2e821-133">（来自 User2）</span><span class="sxs-lookup"><span data-stu-id="2e821-133">(from User2)</span></span>|<span data-ttu-id="2e821-134">服务</span><span class="sxs-lookup"><span data-stu-id="2e821-134">Service</span></span><br /><br /> <span data-ttu-id="2e821-135">（来自 User2）</span><span class="sxs-lookup"><span data-stu-id="2e821-135">(from User2)</span></span>|  
  
 <span data-ttu-id="2e821-136">下面的示例代码演示了如何用数据库值覆盖对象模型中的当前值。</span><span class="sxs-lookup"><span data-stu-id="2e821-136">The following example code shows how to overwrite current values in the object model with the database values.</span></span> <span data-ttu-id="2e821-137">（未对各个成员冲突进行检查或自定义处理。）</span><span class="sxs-lookup"><span data-stu-id="2e821-137">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2e821-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e821-138">See Also</span></span>  
 [<span data-ttu-id="2e821-139">如何：管理更改冲突</span><span class="sxs-lookup"><span data-stu-id="2e821-139">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
