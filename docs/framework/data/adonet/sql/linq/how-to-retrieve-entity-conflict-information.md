---
title: 如何：检索实体冲突信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
ms.openlocfilehash: cabfae568396fa34e6090027032f310cdc05c507
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353190"
---
# <a name="how-to-retrieve-entity-conflict-information"></a><span data-ttu-id="31da1-102">如何：检索实体冲突信息</span><span class="sxs-lookup"><span data-stu-id="31da1-102">How to: Retrieve Entity Conflict Information</span></span>
<span data-ttu-id="31da1-103">您可以使用 <xref:System.Data.Linq.ObjectChangeConflict> 类的对象来提供有关 <xref:System.Data.Linq.ChangeConflictException> 异常指出的冲突的信息。</span><span class="sxs-lookup"><span data-stu-id="31da1-103">You can use objects of the <xref:System.Data.Linq.ObjectChangeConflict> class to provide information about conflicts revealed by <xref:System.Data.Linq.ChangeConflictException> exceptions.</span></span> <span data-ttu-id="31da1-104">有关详细信息，请参阅[开放式并发： 概述](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="31da1-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="31da1-105">示例</span><span class="sxs-lookup"><span data-stu-id="31da1-105">Example</span></span>  
 <span data-ttu-id="31da1-106">下面的示例循环访问累积冲突的列表。</span><span class="sxs-lookup"><span data-stu-id="31da1-106">The following example iterates through a list of accumulated conflicts.</span></span>  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="31da1-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="31da1-107">See Also</span></span>  
 [<span data-ttu-id="31da1-108">如何：管理更改冲突</span><span class="sxs-lookup"><span data-stu-id="31da1-108">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
