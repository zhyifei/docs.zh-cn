---
title: 有效使用数据类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- performance, data type efficiency
- data types [Visual Basic], weak typing
- AscW function [Visual Basic], preferred to Asc
- data types [Visual Basic], using efficiently
- optimization [Visual Basic], data types
- data types [Visual Basic], strong typing
- strong typing
- typing, strong
- data types [Visual Basic], optimizing
- ChrW function [Visual Basic], preferred to Chr
ms.assetid: 28f5e4ba-ec24-4f37-b90a-e8ee822f778a
ms.openlocfilehash: 68371a9f8d4dcc5d0a2b67955d5e88943a83b085
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68631102"
---
# <a name="efficient-use-of-data-types-visual-basic"></a>有效使用数据类型 (Visual Basic)
为未声明的变量和声明的变量分配`Object`了数据类型。 这样就可以轻松地快速编写程序, 但这可能会导致其执行速度更慢。

## <a name="strong-typing"></a>强类型化
 为所有变量指定数据类型称为*强*类型。 使用强类型具有以下优点:

- 它为你的变量启用 IntelliSense 支持。 这使您可以在代码中键入时查看它们的属性和其他成员。

- 它利用编译器的类型检查。 这将捕获在运行时可能会因错误 (如溢出) 而失败的语句。 它还会捕获对不支持这些对象的方法的调用。

- 这会使代码的执行速度更快。

## <a name="most-efficient-data-types"></a>最有效的数据类型
 对于从不包含小数的变量, 整型数据类型比非整型数据类型更有效。 在 Visual Basic 中`Integer` , `UInteger`和是最有效的数值类型。

 对于小数值, `Double`是最有效的数据类型, 因为当前平台上的处理器以双精度执行浮点运算。 但是, 与整数`Double`类型`Integer`(例如) 相比, 具有的操作的速度并不像。

## <a name="specifying-data-type"></a>指定数据类型
 使用[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)声明特定类型的变量。 可以使用[Public](../../../../visual-basic/language-reference/modifiers/public.md)、 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)、 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)或[Private](../../../../visual-basic/language-reference/modifiers/private.md)关键字同时指定其访问级别, 如以下示例中所示。

```vb
Private x As Double
Protected s As String
```

## <a name="character-conversion"></a>字符转换
 `AscW` 和`ChrW`函数以 Unicode 的方式运行。 应优先使用和`Asc` `Chr`, 以使它们必须转换为 Unicode 和 Unicode。

## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [数值数据类型](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [使用 IntelliSense](/visualstudio/ide/using-intellisense)
