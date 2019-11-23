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
ms.openlocfilehash: 781902f1bf28bd029c8d9825aee155a6691cbae9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004778"
---
# <a name="from-clause-visual-basic"></a>From 子句 (Visual Basic)
指定一个或多个范围变量以及要查询的集合。  
  
## <a name="syntax"></a>语法  
  
```vb  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>部件  
  
|术语|Definition|  
|---|---|  
|`element`|必需。 用于循环访问集合中的元素的*范围变量*。 当查询循环访问 `collection`时，范围变量用于引用 `collection` 的每个成员。 必须为可枚举类型。|  
|`type`|可选。 `element` 的类型。 如果未指定 `type`，则 `element` 的类型将从 `collection`推断。|  
|`collection`|必需。 引用要查询的集合。 必须为可枚举类型。|  
  
## <a name="remarks"></a>备注  
 `From` 子句用于标识查询的源数据和用于引用源集合中的元素的变量。 这些变量称为*范围变量*。 查询需要 `From` 子句，除非使用 `Aggregate` 子句标识仅返回聚合结果的查询。 有关详细信息，请参阅[Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md)。  
  
 您可以在查询中指定多个 `From` 子句来识别要联接的多个集合。 指定多个集合时，它们将被单独循环访问，如果相关，可以联接它们。 您可以使用 `Select` 子句隐式联接集合，或者使用 `Join` 或 `Group Join` 子句显式联接集合。 作为替代方法，您可以在单个 `From` 子句中指定多个范围变量和集合，其中每个相关范围变量和集合用逗号分隔开。 下面的代码示例演示了 `From` 子句的两种语法选项。  
  
 [!code-vb[VbSimpleQuerySamples#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#21)]  
  
 `From` 子句定义查询的作用域，该作用域类似于 `For` 循环的作用域。 因此，查询范围内的每个 `element` 范围变量都必须具有唯一的名称。 由于您可以为查询指定多个 `From` 子句，因此后续 `From` 子句可以引用 `From` 子句中的范围变量，或者它们可以引用上一个 `From` 子句中的范围变量。 例如，下面的示例显示一个嵌套的 `From` 子句，其中第二个子句中的集合基于第一个子句中范围变量的属性。  
  
 [!code-vb[VbSimpleQuerySamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#22)]  
  
 每个 `From` 子句可以后跟其他查询子句的任意组合，以优化查询。 可以通过以下方式优化查询：  
  
- 使用 `From` 和 `Select` 子句隐式组合多个集合，或使用 `Join` 或 `Group Join` 子句显式组合多个集合。  
  
- 使用 `Where` 子句来筛选查询结果。  
  
- 使用 `Order By` 子句对结果进行排序。  
  
- 使用 `Group By` 子句将相似结果组合在一起。  
  
- 使用 `Aggregate` 子句标识要为整个查询结果计算的聚合函数。  
  
- 使用 `Let` 子句引入一个迭代变量，该变量的值由表达式而不是集合确定。  
  
- 使用 `Distinct` 子句忽略重复的查询结果。  
  
- 使用 `Skip`、`Take`、`Skip While`和 `Take While` 子句标识要返回的结果的各部分。  
  
## <a name="example"></a>示例  
 下面的查询表达式使用 `From` 子句为 `customers` 集合中的每个 `Customer` 对象声明一个范围变量 `cust`。 `Where` 子句使用范围变量将输出限制为指定区域的客户。 `For Each` 循环将在查询结果中显示每个客户的公司名称。  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="see-also"></a>另请参阅

- [查询](../../../visual-basic/language-reference/queries/index.md)
- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [For Each...Next 语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [For...Next 语句](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
- [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
- [Aggregate 子句](../../../visual-basic/language-reference/queries/aggregate-clause.md)
- [Distinct 子句](../../../visual-basic/language-reference/queries/distinct-clause.md)
- [Join 子句](../../../visual-basic/language-reference/queries/join-clause.md)
- [Group Join 子句](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Let 子句](../../../visual-basic/language-reference/queries/let-clause.md)
- [Skip 子句](../../../visual-basic/language-reference/queries/skip-clause.md)
- [Take 子句](../../../visual-basic/language-reference/queries/take-clause.md)
- [Skip While 子句](../../../visual-basic/language-reference/queries/skip-while-clause.md)
- [Take While 子句](../../../visual-basic/language-reference/queries/take-while-clause.md)
