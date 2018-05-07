---
title: From 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: 1f113444efae83de7d299db330593937c7800bb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="from-clause-visual-basic"></a>From 子句 (Visual Basic)
指定一个或多个范围变量和查询的集合。  
  
## <a name="syntax"></a>语法  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`element`|必须的。 A*范围变量*用于循环访问集合的元素。 范围变量用于引用的每个成员`collection`如查询循环访问`collection`。 必须是可枚举类型。|  
|`type`|可选。 `element` 的类型。 如果没有`type`指定的一种`element`从推断`collection`。|  
|`collection`|必须的。 是指要查询的集合。 必须是可枚举类型。|  
  
## <a name="remarks"></a>备注  
 `From`子句用于标识查询和用于在源集合中引用元素的变量的源数据。 这些变量称为*范围变量*。 `From`子句是必需的对于查询，除非`Aggregate`子句用于确定某个查询仅返回聚合结果。 有关详细信息，请参阅[Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md)。  
  
 你可以指定多个`From`查询来标识要联接的多个集合中的子句。 如果指定多个集合，它们独立，循环访问，或如果它们相关可以将其联接。 你可以通过使用隐式联接集合`Select`子句，或通过使用显式`Join`或`Group Join`子句。 作为替代方法，你可以指定多个范围变量和集合在一次`From`子句，使用每个相关的范围变量和与其他用逗号分隔的集合。 下面的代码示例演示两个语法选项`From`子句。  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 `From`子句定义查询，这是相似的作用域范围`For`循环。 因此，每个`element`查询的作用域中的范围变量必须具有唯一的名称。 因为你可以指定多个`From`对于查询，后续的子句`From`子句可以引用中的范围变量`From`子句，或它们在以前的范围变量可以引用`From`子句。 例如，下面的示例演示一个嵌套`From`子句，第二个子句中的集合基于第一个子句中的范围变量的属性。  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 每个`From`子句后面可以跟其他查询子句以优化查询的任意组合。 你可以通过以下方式来优化查询：  
  
-   通过使用隐式组合多个集合`From`和`Select`子句，或通过使用显式`Join`或`Group Join`子句。  
  
-   使用`Where`子句来筛选查询结果。  
  
-   对结果进行排序通过使用`Order By`子句。  
  
-   通过将类似的结果组合在一起`Group By`子句。  
  
-   使用`Aggregate`子句标识要针对整个查询结果计算的聚合函数。  
  
-   使用`Let`子句引入其值由表达式而非一个集合的迭代变量。  
  
-   使用`Distinct`子句，以忽略重复的查询结果。  
  
-   识别要使用返回的结果的部分`Skip`， `Take`， `Skip While`，和`Take While`子句。  
  
## <a name="example"></a>示例  
 下面的查询表达式使用`From`子句来声明范围变量`cust`每个`Customer`对象在`customers`集合。 `Where`子句使用的范围变量以将输出限制为客户，从指定的区域。 `For Each`循环显示查询结果中的每个客户的公司名称。  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a>请参阅  
 [查询](../../../visual-basic/language-reference/queries/queries.md)  
 [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [For Each...Next 语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [Distinct 子句](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 [Join 子句](../../../visual-basic/language-reference/queries/join-clause.md)  
 [Group Join 子句](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Let 子句](../../../visual-basic/language-reference/queries/let-clause.md)  
 [Skip 子句](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Take 子句](../../../visual-basic/language-reference/queries/take-clause.md)  
 [Skip While 子句](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Take While 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)
