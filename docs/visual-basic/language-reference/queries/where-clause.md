---
title: Where 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: 404dd848058f7e5c9bc8a74b6d89df18c6c55fad
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005001"
---
# <a name="where-clause-visual-basic"></a>Where 子句 (Visual Basic)
指定查询的筛选条件。  
  
## <a name="syntax"></a>语法  
  
```vb  
Where condition  
```  
  
## <a name="parts"></a>部件  
 `condition`  
 必需。 确定集合中当前项的值是否包含在输出集合中的表达式。 表达式的计算结果必须为 `Boolean` 值或等效于 @no__t 1 值。 如果条件的计算结果为 `True`，则查询结果中将包含元素;否则，元素会从查询结果中排除。  
  
## <a name="remarks"></a>备注  
 使用 `Where` 子句可以通过仅选择符合特定条件的元素来筛选查询数据。 如果元素的值导致 `Where` 子句的计算结果为 `True`，则包含在查询结果中;排除其他元素。 在 `Where` 子句中使用的表达式的计算结果必须为 @no__t 1 或等效的 `Boolean`，例如，当其值为零时，计算结果为 `False` 的整数。 可以通过使用逻辑运算符（如 `And`、`Or`、`AndAlso`、`OrElse`、`Is` 和 `IsNot`）在 `Where` 子句中组合多个表达式。  
  
 默认情况下，在访问查询表达式之前，不会对其进行计算（例如，当它们在 `For` 循环中进行数据绑定或循环访问时）。 因此，在访问查询之前，不会计算 `Where` 子句。 如果在 `Where` 子句中使用的查询外部存在值，请确保在执行查询时在 `Where` 子句中使用适当的值。 有关查询执行的详细信息，请参阅[编写第一个 LINQ 查询](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)。  
  
 可以在 `Where` 子句中调用函数，以对集合中的当前元素中的值执行计算或运算。 调用 `Where` 子句中的函数可能会导致在定义查询时（而不是在访问时）立即执行查询。 有关查询执行的详细信息，请参阅[编写第一个 LINQ 查询](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)。  
  
## <a name="example"></a>示例  
 下面的查询表达式使用 `From` 子句为 @no__t 集合中的每个 `Customer` 对象声明一个范围变量 `cust`。 @No__t-0 子句使用范围变量将输出限制为指定区域的客户。 @No__t-0 循环显示查询结果中每个客户的公司名称。  
  
 [!code-vb[VbSimpleQuerySamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#23)]  
  
## <a name="example"></a>示例  
 下面的示例使用了 `Where` 子句中的 @no__t 0 和 @no__t 逻辑运算符。  
  
 [!code-vb[VbSimpleQuerySamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#31)]  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [查询](../../../visual-basic/language-reference/queries/index.md)
- [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
- [For Each...Next 语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
