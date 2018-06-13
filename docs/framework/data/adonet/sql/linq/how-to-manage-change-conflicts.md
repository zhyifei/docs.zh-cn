---
title: 如何：管理更改冲突
ms.date: 03/30/2017
ms.assetid: cd292c51-a3d1-4c6f-8d8e-04323c36054e
ms.openlocfilehash: 7858dc304d281dfb99755d83eec19b421f63d2ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361661"
---
# <a name="how-to-manage-change-conflicts"></a><span data-ttu-id="9c4a2-102">如何：管理更改冲突</span><span class="sxs-lookup"><span data-stu-id="9c4a2-102">How to: Manage Change Conflicts</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="9c4a2-103"> 提供的 Api 以帮助你发现、 评估和解决并发冲突的集合。</span><span class="sxs-lookup"><span data-stu-id="9c4a2-103"> provides a collection of APIs to help you discover, evaluate, and resolve concurrency conflicts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9c4a2-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="9c4a2-104">In This Section</span></span>  
 [<span data-ttu-id="9c4a2-105">如何：检测到并解决冲突的提交</span><span class="sxs-lookup"><span data-stu-id="9c4a2-105">How to: Detect and Resolve Conflicting Submissions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)  
 <span data-ttu-id="9c4a2-106">介绍如何检测和解决并发冲突。</span><span class="sxs-lookup"><span data-stu-id="9c4a2-106">Describes how to detect and resolve concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="9c4a2-107">如何：指定何时引发并发异常</span><span class="sxs-lookup"><span data-stu-id="9c4a2-107">How to: Specify When Concurrency Exceptions are Thrown</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md)  
 <span data-ttu-id="9c4a2-108">介绍如何指定应何时通知您出现并发冲突。</span><span class="sxs-lookup"><span data-stu-id="9c4a2-108">Describes how to specify when you should be informed of concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="9c4a2-109">如何：指定针对并发冲突对哪些成员进行测试</span><span class="sxs-lookup"><span data-stu-id="9c4a2-109">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 <span data-ttu-id="9c4a2-110">介绍如何通过设置成员的属性来指定是否检查其有无并发冲突。</span><span class="sxs-lookup"><span data-stu-id="9c4a2-110">Describes how to attribute members to specify whether they are checked for concurrency conflicts.</span></span>  
  
 [<span data-ttu-id="9c4a2-111">如何：检索实体冲突信息</span><span class="sxs-lookup"><span data-stu-id="9c4a2-111">How to: Retrieve Entity Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-entity-conflict-information.md)  
 <span data-ttu-id="9c4a2-112">介绍如何收集有关实体冲突的信息。</span><span class="sxs-lookup"><span data-stu-id="9c4a2-112">Describes how to gather information about entity conflicts.</span></span>  
  
 [<span data-ttu-id="9c4a2-113">如何：检索成员冲突信息</span><span class="sxs-lookup"><span data-stu-id="9c4a2-113">How to: Retrieve Member Conflict Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-member-conflict-information.md)  
 <span data-ttu-id="9c4a2-114">介绍如何收集有关成员冲突的信息。</span><span class="sxs-lookup"><span data-stu-id="9c4a2-114">Describes how to gather information about member conflicts.</span></span>  
  
 [<span data-ttu-id="9c4a2-115">如何：通过保留数据库值解决冲突</span><span class="sxs-lookup"><span data-stu-id="9c4a2-115">How to: Resolve Conflicts by Retaining Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)  
 <span data-ttu-id="9c4a2-116">介绍如何用数据库值覆盖当前值。</span><span class="sxs-lookup"><span data-stu-id="9c4a2-116">Describes how to overwrite current values with database values.</span></span>  
  
 [<span data-ttu-id="9c4a2-117">如何：通过重写数据库值解决冲突</span><span class="sxs-lookup"><span data-stu-id="9c4a2-117">How to: Resolve Conflicts by Overwriting Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)  
 <span data-ttu-id="9c4a2-118">介绍如何通过覆盖数据库值保留当前值。</span><span class="sxs-lookup"><span data-stu-id="9c4a2-118">Describes how to keep current values by overwriting database values.</span></span>  
  
 [<span data-ttu-id="9c4a2-119">如何：通过与数据库值合并解决冲突</span><span class="sxs-lookup"><span data-stu-id="9c4a2-119">How to: Resolve Conflicts by Merging with Database Values</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-merging-with-database-values.md)  
 <span data-ttu-id="9c4a2-120">介绍如何通过将数据库值与当前值合并来解决冲突。</span><span class="sxs-lookup"><span data-stu-id="9c4a2-120">Describes how to resolve a conflict by merging database and current values.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9c4a2-121">相关章节</span><span class="sxs-lookup"><span data-stu-id="9c4a2-121">Related Sections</span></span>  
 [<span data-ttu-id="9c4a2-122">开放式并发：概述</span><span class="sxs-lookup"><span data-stu-id="9c4a2-122">Optimistic Concurrency: Overview</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)  
 <span data-ttu-id="9c4a2-123">解释与 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中的开放式并发有关的一些术语。</span><span class="sxs-lookup"><span data-stu-id="9c4a2-123">Explains the terms that apply to optimistic concurrency in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>
