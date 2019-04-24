---
title: 如何：一次检索多个对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 18aff4d8-bde8-461b-9960-ccabb24e9d22
ms.openlocfilehash: dd53c2fd16a82ce0f69a33e0b7d7ffef7815b91b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220521"
---
# <a name="how-to-retrieve-many-objects-at-once"></a>如何：一次检索多个对象
通过使用 <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>，可以在一个查询中检索许多对象。  
  
## <a name="example"></a>示例  
 下面的代码使用 <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> 方法来同时检索 `Customer` 和 `Order` 对象。  
  
 [!code-csharp[DLinqQueryConcepts#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#9)]
 [!code-vb[DLinqQueryConcepts#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#9)]  
  
## <a name="see-also"></a>请参阅

- [查询概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
