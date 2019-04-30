---
title: 如何：通过重写数据库值解决冲突
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd6db0b8-c29c-48ff-b768-31d28e7a148c
ms.openlocfilehash: 7b8d7cf8ab2335c064062ed3ab4072d81e8042fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033652"
---
# <a name="how-to-resolve-conflicts-by-overwriting-database-values"></a><span data-ttu-id="0f84c-102">如何：通过重写数据库值解决冲突</span><span class="sxs-lookup"><span data-stu-id="0f84c-102">How to: Resolve Conflicts by Overwriting Database Values</span></span>
<span data-ttu-id="0f84c-103">若要先协调预期数据库值与实际数据库值之间的差异，再尝试重新提交更改，则可以使用 <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> 覆盖数据库值。</span><span class="sxs-lookup"><span data-stu-id="0f84c-103">To reconcile differences between expected and actual database values before you try to resubmit your changes, you can use <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> to overwrite database values.</span></span> <span data-ttu-id="0f84c-104">有关详细信息，请参阅[开放式并发：概述](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="0f84c-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f84c-105">在所有情况下，都会先通过从数据库中检索更新后的数据来刷新客户端上的记录。</span><span class="sxs-lookup"><span data-stu-id="0f84c-105">In all cases, the record on the client is first refreshed by retrieving the updated data from the database.</span></span> <span data-ttu-id="0f84c-106">此操作确保了下一次更新尝试将通过相同的并发检查。</span><span class="sxs-lookup"><span data-stu-id="0f84c-106">This action makes sure that the next update try will not fail on the same concurrency checks.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f84c-107">示例</span><span class="sxs-lookup"><span data-stu-id="0f84c-107">Example</span></span>  
 <span data-ttu-id="0f84c-108">在本方案中，当 User1 尝试提交更改时将引发 <xref:System.Data.Linq.ChangeConflictException> 异常，原因是 User2 同时已更改了 Assistant 和 Department 列。</span><span class="sxs-lookup"><span data-stu-id="0f84c-108">In this scenario, an <xref:System.Data.Linq.ChangeConflictException> exception is thrown when User1 tries to submit changes, because User2 has in the meantime changed the Assistant and Department columns.</span></span> <span data-ttu-id="0f84c-109">下表说明了这种情况。</span><span class="sxs-lookup"><span data-stu-id="0f84c-109">The following table shows the situation.</span></span>  
  
||<span data-ttu-id="0f84c-110">经理</span><span class="sxs-lookup"><span data-stu-id="0f84c-110">Manager</span></span>|<span data-ttu-id="0f84c-111">Assistant</span><span class="sxs-lookup"><span data-stu-id="0f84c-111">Assistant</span></span>|<span data-ttu-id="0f84c-112">Department</span><span class="sxs-lookup"><span data-stu-id="0f84c-112">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="0f84c-113">原始数据库在被 User1 和 User2 查询时的状态。</span><span class="sxs-lookup"><span data-stu-id="0f84c-113">Original database state when queried by User1 and User2.</span></span>|<span data-ttu-id="0f84c-114">Alfreds</span><span class="sxs-lookup"><span data-stu-id="0f84c-114">Alfreds</span></span>|<span data-ttu-id="0f84c-115">Maria</span><span class="sxs-lookup"><span data-stu-id="0f84c-115">Maria</span></span>|<span data-ttu-id="0f84c-116">销售额</span><span class="sxs-lookup"><span data-stu-id="0f84c-116">Sales</span></span>|  
|<span data-ttu-id="0f84c-117">User1 准备提交这些更改。</span><span class="sxs-lookup"><span data-stu-id="0f84c-117">User1 prepares to submit these changes.</span></span>|<span data-ttu-id="0f84c-118">Alfred</span><span class="sxs-lookup"><span data-stu-id="0f84c-118">Alfred</span></span>||<span data-ttu-id="0f84c-119">“营销”</span><span class="sxs-lookup"><span data-stu-id="0f84c-119">Marketing</span></span>|  
|<span data-ttu-id="0f84c-120">User2 已经提交了这些更改。</span><span class="sxs-lookup"><span data-stu-id="0f84c-120">User2 has already submitted these changes.</span></span>||<span data-ttu-id="0f84c-121">Mary</span><span class="sxs-lookup"><span data-stu-id="0f84c-121">Mary</span></span>|<span data-ttu-id="0f84c-122">服务</span><span class="sxs-lookup"><span data-stu-id="0f84c-122">Service</span></span>|  
  
 <span data-ttu-id="0f84c-123">User1 决定通过用当前客户端成员值覆盖数据库值来解决此冲突。</span><span class="sxs-lookup"><span data-stu-id="0f84c-123">User1 decides to resolve this conflict by overwriting database values with the current client member values.</span></span>  
  
 <span data-ttu-id="0f84c-124">User1 通过使用 <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> 解决了此冲突后，数据库中的结果将如下表中所示：</span><span class="sxs-lookup"><span data-stu-id="0f84c-124">When User1 resolves the conflict by using <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, the result in the database is as in following table:</span></span>  
  
||<span data-ttu-id="0f84c-125">经理</span><span class="sxs-lookup"><span data-stu-id="0f84c-125">Manager</span></span>|<span data-ttu-id="0f84c-126">Assistant</span><span class="sxs-lookup"><span data-stu-id="0f84c-126">Assistant</span></span>|<span data-ttu-id="0f84c-127">Department</span><span class="sxs-lookup"><span data-stu-id="0f84c-127">Department</span></span>|  
|------|-------------|---------------|----------------|  
|<span data-ttu-id="0f84c-128">解决冲突后的新状态。</span><span class="sxs-lookup"><span data-stu-id="0f84c-128">New state after conflict resolution.</span></span>|<span data-ttu-id="0f84c-129">Alfred</span><span class="sxs-lookup"><span data-stu-id="0f84c-129">Alfred</span></span><br /><br /> <span data-ttu-id="0f84c-130">（来自 User1）</span><span class="sxs-lookup"><span data-stu-id="0f84c-130">(from User1)</span></span>|<span data-ttu-id="0f84c-131">Maria</span><span class="sxs-lookup"><span data-stu-id="0f84c-131">Maria</span></span><br /><br /> <span data-ttu-id="0f84c-132">（原始）</span><span class="sxs-lookup"><span data-stu-id="0f84c-132">(original)</span></span>|<span data-ttu-id="0f84c-133">“营销”</span><span class="sxs-lookup"><span data-stu-id="0f84c-133">Marketing</span></span><br /><br /> <span data-ttu-id="0f84c-134">（来自 User1）</span><span class="sxs-lookup"><span data-stu-id="0f84c-134">(from User1)</span></span>|  
  
 <span data-ttu-id="0f84c-135">下面的示例代码演示了如何用当前客户端成员值覆盖数据库值。</span><span class="sxs-lookup"><span data-stu-id="0f84c-135">The following example code shows how to overwrite database values with the current client member values.</span></span> <span data-ttu-id="0f84c-136">（未对各个成员冲突进行检查或自定义处理。）</span><span class="sxs-lookup"><span data-stu-id="0f84c-136">(No inspection or custom handling of individual member conflicts occurs.)</span></span>  
  
 [!code-csharp[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0f84c-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f84c-137">See also</span></span>

- [<span data-ttu-id="0f84c-138">如何：管理更改冲突</span><span class="sxs-lookup"><span data-stu-id="0f84c-138">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
