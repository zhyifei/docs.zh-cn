---
title: Join 子句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: b5211d0ed3f618013dc9fe764a6d7b2db8177c26
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582296"
---
# <a name="join-clause-visual-basic"></a>Join 子句 (Visual Basic)

将两个集合合并为单个集合。 联接运算基于匹配键，并使用 `Equals` 运算符。

## <a name="syntax"></a>语法

```vb
Join element In collection _
  [ joinClause _ ]
  [ groupJoinClause ... _ ]
On key1 Equals key2 [ And key3 Equals key4 [... ]
```

## <a name="parts"></a>部件

`element`（必需）。 要联接的集合的控件变量。

`collection`  
必须的。 要与 `Join` 运算符左侧标识的集合进行组合的集合。 @No__t_0 子句可以嵌套在另一个 `Join` 子句中，也可以嵌套在 `Group Join` 子句中。

`joinClause`  
可选。 用于进一步优化查询的一个或多个附加 `Join` 子句。

`groupJoinClause`  
可选。 用于进一步优化查询的一个或多个附加 `Group Join` 子句。

`key1` `Equals` `key2`  
必须的。 标识要联接的集合的键。 必须使用 `Equals` 运算符来比较要联接的集合中的键。 可以通过使用 `And` 运算符来标识多个键，从而组合联接条件。 `key1` 必须来自 `Join` 运算符左侧的集合。 `key2` 必须来自 `Join` 运算符右侧的集合。

联接条件中使用的键可以是包含集合中多个项的表达式。 但是，每个键表达式只能包含其各自集合中的项。

## <a name="remarks"></a>备注

@No__t_0 子句基于要联接的集合中的匹配键值合并两个集合。 生成的集合可以包含从 `Join` 运算符左侧标识的集合中的任何值组合和 `Join` 子句中标识的集合。 查询将只返回满足 `Equals` 运算符指定的条件的结果。 这等效于 SQL 中的 `INNER JOIN`。

您可以使用查询中的多个 `Join` 子句将两个或多个集合联接到一个集合中。

您可以执行隐式联接以组合集合，而不使用 `Join` 子句。 为此，请在 `From` 子句中包含多个 `In` 子句，并指定一个 `Where` 子句，用于标识要用于联接的键。

您可以使用 `Group Join` 子句将集合合并为单个分层集合。 这类似于 SQL 中的 `LEFT OUTER JOIN`。

## <a name="example"></a>示例

下面的代码示例将执行隐式联接，以将客户列表与订单组合在一起。

[!code-vb[VbSimpleQuerySamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#13)]

## <a name="example"></a>示例

下面的代码示例使用 `Join` 子句联接两个集合。

[!code-vb[VbSimpleQuerySamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples2.vb#12)]

此示例将生成与下面类似的输出：

`winlogon (968), Windows Logon`

`explorer (2424), File Explorer`

`cmd (5136), Command Window`

## <a name="example"></a>示例

下面的代码示例通过使用包含两个键列的 `Join` 子句来联接两个集合。

[!code-vb[VbSimpleQuerySamples#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples3.vb#17)]

该示例将生成类似于以下内容的输出：

`winlogon (968), Windows Logon, Priority = 13`

`cmd (700), Command Window, Priority = 8`

`explorer (2424), File Explorer, Priority = 8`

## <a name="see-also"></a>请参阅

- [Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [查询](../../../visual-basic/language-reference/queries/index.md)
- [Select 子句](../../../visual-basic/language-reference/queries/select-clause.md)
- [From 子句](../../../visual-basic/language-reference/queries/from-clause.md)
- [Group Join 子句](../../../visual-basic/language-reference/queries/group-join-clause.md)
- [Where 子句](../../../visual-basic/language-reference/queries/where-clause.md)
