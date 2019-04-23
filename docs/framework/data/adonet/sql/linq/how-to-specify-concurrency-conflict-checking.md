---
title: 如何：指定并发冲突检查
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
ms.openlocfilehash: 53d3ba6969705940c403795d3764c021f0829c64
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098970"
---
# <a name="how-to-specify-concurrency-conflict-checking"></a><span data-ttu-id="f87a2-102">如何：指定并发冲突检查</span><span class="sxs-lookup"><span data-stu-id="f87a2-102">How to: Specify Concurrency-Conflict Checking</span></span>
<span data-ttu-id="f87a2-103">您可以指定在您调用 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 时要检查数据库的哪些列是否发生并发冲突。</span><span class="sxs-lookup"><span data-stu-id="f87a2-103">You can specify which columns of the database are to be checked for concurrency conflicts when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="f87a2-104">有关详细信息，请参阅[如何：指定针对并发冲突对哪些成员进行测试](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)。</span><span class="sxs-lookup"><span data-stu-id="f87a2-104">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f87a2-105">示例</span><span class="sxs-lookup"><span data-stu-id="f87a2-105">Example</span></span>  
 <span data-ttu-id="f87a2-106">下面的代码指定在更新检查期间永远都不应该测试 `HomePage` 成员。</span><span class="sxs-lookup"><span data-stu-id="f87a2-106">The following code specifies that the `HomePage` member should never be tested during update checks.</span></span> <span data-ttu-id="f87a2-107">有关详细信息，请参阅 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>。</span><span class="sxs-lookup"><span data-stu-id="f87a2-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f87a2-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="f87a2-108">See also</span></span>

- [<span data-ttu-id="f87a2-109">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="f87a2-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="f87a2-110">如何：通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="f87a2-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
