---
title: 联接运算
ms.date: 07/20/2015
ms.assetid: 39ab4854-ac84-4738-9d0b-3cb79be84db4
ms.openlocfilehash: b09574369185be13664276c2e84697fc4969c6f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353298"
---
# <a name="join-operations-visual-basic"></a>Join Operations (Visual Basic)
联接两个数据源就是将一个数据源中的对象与另一个数据源中具有相同公共属性的对象相关联。  
  
 当查询所面向的数据源相互之间具有无法直接领会的关系时，联接就成为一项重要的运算。 在面向对象的编程中，这可能意味着在未建模对象之间进行关联，例如对单向关系进行反向推理。 下面是单向关系的一个示例：Customer 类有一个类型为 City 的属性，但 City 类没有作为 Customer 对象集合的属性。 如果你具有一个 City 对象列表，并且要查找每个城市中的所有客户，则可以使用联接运算完成此项查找。  
  
 LINQ 框架中提供的 join 方法包括 <xref:System.Linq.Enumerable.Join%2A> 和 <xref:System.Linq.Enumerable.GroupJoin%2A>。 这些方法执行同等联接，即根据 2 个数据源的键是否相等来匹配这 2 个数据源的联接。 (For comparison, Transact-SQL supports join operators other than 'equals', for example the 'less than' operator.) In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join, a type of join in which only those objects that have a match in the other data set are returned. <xref:System.Linq.Enumerable.GroupJoin%2A> 方法在关系数据库术语中没有直接等效项，但实现了内部联接和左外部联接的超集。 左外部联接是指返回第一个（左侧）数据源的每个元素的联接，即使其他数据源中没有关联元素。  
  
 下图显示了一个概念性视图，其中包含两个集合以及这两个集合中的包含在内部联接或左外部联接中的元素。  
  
 ![显示内部/外部的两个重叠圆圈。](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a>方法  
  
|方法名|描述|Visual Basic Query Expression Syntax|详细信息|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|联接|根据键选择器函数联接两个序列并提取值对。|`From x In …, y In … Where x.a = y.a`<br /><br /> 或<br /><br /> `Join … [As …]In … On …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|根据键选择器函数联接两个序列，并对每个元素的结果匹配项进行分组。|`Group Join … In … On …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>请参阅

- <xref:System.Linq>
- [标准查询运算符概述 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [构建联接和叉积查询](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [Join 子句](../../../../visual-basic/language-reference/queries/join-clause.md)
- [How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)
- [How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)
