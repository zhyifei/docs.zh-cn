---
title: "如何：指定并发冲突检查"
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
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: e9c3839f4b70bfec759617d875095d9ce8eecf54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-concurrency-conflict-checking"></a><span data-ttu-id="becd6-102">如何：指定并发冲突检查</span><span class="sxs-lookup"><span data-stu-id="becd6-102">How to: Specify Concurrency-Conflict Checking</span></span>
<span data-ttu-id="becd6-103">您可以指定在您调用 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 时要检查数据库的哪些列是否发生并发冲突。</span><span class="sxs-lookup"><span data-stu-id="becd6-103">You can specify which columns of the database are to be checked for concurrency conflicts when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="becd6-104">有关详细信息，请参阅[如何： 指定该成员进行测试并发冲突](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)。</span><span class="sxs-lookup"><span data-stu-id="becd6-104">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="becd6-105">示例</span><span class="sxs-lookup"><span data-stu-id="becd6-105">Example</span></span>  
 <span data-ttu-id="becd6-106">下面的代码指定在更新检查期间永远都不应该测试 `HomePage` 成员。</span><span class="sxs-lookup"><span data-stu-id="becd6-106">The following code specifies that the `HomePage` member should never be tested during update checks.</span></span> <span data-ttu-id="becd6-107">有关更多信息，请参见<xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>。</span><span class="sxs-lookup"><span data-stu-id="becd6-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="becd6-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="becd6-108">See Also</span></span>  
 [<span data-ttu-id="becd6-109">LINQ to SQL 对象模型</span><span class="sxs-lookup"><span data-stu-id="becd6-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="becd6-110">如何： 通过使用代码编辑器自定义实体类</span><span class="sxs-lookup"><span data-stu-id="becd6-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
