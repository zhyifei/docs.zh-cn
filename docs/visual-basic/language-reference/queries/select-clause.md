---
title: Select 子句 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9d8cabcbd8554ca2aee639eaac8a52f0485a266
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="select-clause-visual-basic"></a>Select 子句 (Visual Basic)
定义查询的结果。  
  
## <a name="syntax"></a>语法  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>部件  
 `var1`  
 可选。 可以用于引用列表达式的结果的别名。  
  
 `fieldName1`  
 必需。 要返回查询结果中的字段的名称。  
  
## <a name="remarks"></a>备注  
 你可以使用`Select`子句定义要从查询返回的结果。 这使你可以定义通过查询创建新的匿名类型的成员或目标的命名查询返回的类型的成员。 `Select`子句不需要查询。 如果没有`Select`指定子句，则查询将返回基于标识为当前作用域的范围变量的所有成员的类型。 有关详细信息，请参阅[匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)。 当查询创建命名的类型时，它将返回的结果类型<xref:System.Collections.Generic.IEnumerable%601>其中`T`是创建的类型。  
  
 `Select`子句可引用当前作用域中的任何变量。 这包括在中标识的范围变量`From`子句 (或`From`子句)。 它还包括任何新的变量，以通过别名创建`Aggregate`， `Let`， `Group By`，或`Group Join`子句或从以前的变量`Select`在查询表达式的子句。 `Select`子句还可以包含静态值。 例如，下面的代码示例中演示了一个查询表达式`Select`子句定义为具有四个成员的新的匿名类型的查询结果： `ProductName`， `Price`， `Discount`，和`DiscountedPrice`。 `ProductName`和`Price`成员值，将从中定义的产品范围变量`From`子句。 `DiscountedPrice`中计算成员值`Let`子句。 `Discount`成员是静态值。  
  
 [!code-vb[VbSimpleQuerySamples#27](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_1.vb)]  
  
 `Select`子句引入了一组新的后续查询子句的范围变量和之前的范围变量将不再在作用域中。 最后一个`Select`子句在查询表达式确定查询的返回值。 例如，以下查询将返回公司总数超过 500 的每个客户订单的名称和顺序 ID。 第一个`Select`子句标识的范围变量`Where`子句和第二个`Select`子句。 第二个`Select`子句标识作为新的匿名类型的查询返回的值。  
  
 [!code-vb[VbSimpleQuerySamples#28](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_2.vb)]  
  
 如果`Select`子句标识要返回的单个项，查询表达式将返回该单个项的类型的集合。 如果`Select`子句标识要返回的多个项，查询表达式将返回新的匿名类型，基于所选项目的集合。 例如，以下两个查询返回基于两个不同类型的集合`Select`子句。 第一个查询返回公司名称作为字符串的的集合。 第二个查询返回的集合`Customer`填充有的公司名称和地址信息的对象。  
  
 [!code-vb[VbSimpleQuerySamples#29](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_3.vb)]  
  
## <a name="example"></a>示例  
 下面的查询表达式使用`From`子句来声明范围变量`cust`为`customers`集合。 `Select`子句选择的客户名称和 ID 值并填充`CompanyName`和`CustomerID`新的范围变量的列。 `For Each`语句循环访问每个返回的对象，并显示`CompanyName`和`CustomerID`为每个记录的列。  
  
 [!code-vb[VbSimpleQuerySamples#30](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_4.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [查询](../../../visual-basic/language-reference/queries/queries.md)  
 [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Order By 子句](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [匿名类型](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
