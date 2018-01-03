---
title: "如何：检测到并解决冲突的提交"
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
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 28dba94262002f863a750a83493ba98b3714fabd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-detect-and-resolve-conflicting-submissions"></a><span data-ttu-id="a2dd0-102">如何：检测到并解决冲突的提交</span><span class="sxs-lookup"><span data-stu-id="a2dd0-102">How to: Detect and Resolve Conflicting Submissions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="a2dd0-103"> 提供了许多资源，用于检测和解决因多个用户更改数据库而产生的冲突。</span><span class="sxs-lookup"><span data-stu-id="a2dd0-103"> provides many resources for detecting and resolving conflicts that stem from multi-user changes to the database.</span></span> <span data-ttu-id="a2dd0-104">有关详细信息，请参阅[如何： 管理更改冲突](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)。</span><span class="sxs-lookup"><span data-stu-id="a2dd0-104">For more information, see [How to: Manage Change Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2dd0-105">示例</span><span class="sxs-lookup"><span data-stu-id="a2dd0-105">Example</span></span>  
 <span data-ttu-id="a2dd0-106">下面的示例演示`try` / `catch`捕获的块<xref:System.Data.Linq.ChangeConflictException>异常。</span><span class="sxs-lookup"><span data-stu-id="a2dd0-106">The following example shows a `try`/`catch` block that catches a <xref:System.Data.Linq.ChangeConflictException> exception.</span></span> <span data-ttu-id="a2dd0-107">每个冲突的实体和成员信息会显示在控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="a2dd0-107">Entity and member information for each conflict is displayed in the console window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2dd0-108">您必须将 `using System.Reflection` 指令（在 Visual Basic 中为 `Imports System.Reflection`）包含在内，以支持信息检索。</span><span class="sxs-lookup"><span data-stu-id="a2dd0-108">You must include the `using System.Reflection` directive (`Imports System.Reflection` in Visual Basic) to support the information retrieval.</span></span> <span data-ttu-id="a2dd0-109">有关详细信息，请参阅<xref:System.Reflection>。</span><span class="sxs-lookup"><span data-stu-id="a2dd0-109">For more information, see <xref:System.Reflection>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="a2dd0-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2dd0-110">See Also</span></span>  
 [<span data-ttu-id="a2dd0-111">进行和提交数据更改</span><span class="sxs-lookup"><span data-stu-id="a2dd0-111">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="a2dd0-112">如何：管理更改冲突</span><span class="sxs-lookup"><span data-stu-id="a2dd0-112">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
