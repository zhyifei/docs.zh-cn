---
title: 如何：检索实体冲突信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
ms.openlocfilehash: 766ede90b14f07e2799c2715daf62aaeeeaa83f4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782235"
---
# <a name="how-to-retrieve-entity-conflict-information"></a><span data-ttu-id="d41c2-102">如何：检索实体冲突信息</span><span class="sxs-lookup"><span data-stu-id="d41c2-102">How to: Retrieve Entity Conflict Information</span></span>
<span data-ttu-id="d41c2-103">您可以使用 <xref:System.Data.Linq.ObjectChangeConflict> 类的对象来提供有关 <xref:System.Data.Linq.ChangeConflictException> 异常指出的冲突的信息。</span><span class="sxs-lookup"><span data-stu-id="d41c2-103">You can use objects of the <xref:System.Data.Linq.ObjectChangeConflict> class to provide information about conflicts revealed by <xref:System.Data.Linq.ChangeConflictException> exceptions.</span></span> <span data-ttu-id="d41c2-104">有关详细信息，请[参阅乐观并发：概述](optimistic-concurrency-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d41c2-104">For more information, see [Optimistic Concurrency: Overview](optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d41c2-105">示例</span><span class="sxs-lookup"><span data-stu-id="d41c2-105">Example</span></span>  
 <span data-ttu-id="d41c2-106">下面的示例循环访问累积冲突的列表。</span><span class="sxs-lookup"><span data-stu-id="d41c2-106">The following example iterates through a list of accumulated conflicts.</span></span>  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d41c2-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="d41c2-107">See also</span></span>

- [<span data-ttu-id="d41c2-108">如何：管理更改冲突</span><span class="sxs-lookup"><span data-stu-id="d41c2-108">How to: Manage Change Conflicts</span></span>](how-to-manage-change-conflicts.md)
