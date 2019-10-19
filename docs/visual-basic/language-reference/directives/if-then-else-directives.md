---
title: '#If .。。Then ... #Else 指令（Visual Basic）'
ms.date: 04/11/2018
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
ms.openlocfilehash: aaf5e7dd82cebf734da59e9feb89174705468a4b
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72580090"
---
# <a name="ifthenelse-directives"></a>#If...Then...#Else 指令

有条件地编译选定的 Visual Basic 代码块。

## <a name="syntax"></a>语法

```vb
#If expression Then
   statements
[ #ElseIf expression Then
   [ statements ]
...
#ElseIf expression Then
   [ statements ] ]
[ #Else
   [ statements ] ]
#End If
```

## <a name="parts"></a>部件

`expression`  
@No__t_0 和 `#ElseIf` 语句需要，在其他位置为可选。 任何表达式（仅包含一个或多个条件编译器常量、文本和运算符），其计算结果为 `True` 或 `False`。

`statements`  
@No__t_0 语句块需要，在其他位置为可选。 如果关联的表达式的计算结果为 `True`，则 Visual Basic 编译的程序行或编译器指令。

`#End If`  
终止 `#If` 语句块。

## <a name="remarks"></a>备注

在表面上，`#If...Then...#Else` 指令的行为与 `If...Then...Else` 语句的行为相同。 但 `#If...Then...#Else` 指令计算编译器编译的内容，而 `If...Then...Else` 语句则在运行时计算条件。

条件编译通常用于针对不同平台编译相同的程序。 它还用于阻止调试代码出现在可执行文件中。 在条件编译期间排除的代码在最终可执行文件中被完全省略，因此它不会对大小或性能产生任何影响。

不管任何计算结果如何，都将使用 `Option Compare Binary` 来计算所有表达式。 @No__t_0 语句不会影响 `#If` 和 `#ElseIf` 语句中的表达式。

> [!NOTE]
> @No__t_0、`#Else`、`#ElseIf` 和 `#End If` 指令不存在单行形式。 任何其他代码都不能与任何指令出现在同一行上。

条件编译块内的语句必须是完整的逻辑语句。 例如，你无法有条件地仅编译函数的属性，但你可以有条件地声明函数及其属性：

```vb
#If DEBUG Then
<WebMethod()>
Public Function SomeFunction() As String
#Else
<WebMethod(CacheDuration:=86400)>
Public Function SomeFunction() As String
#End If
```

## <a name="example"></a>示例

此示例使用 `#If...Then...#Else` 构造来确定是否编译某些语句。

[!code-vb[VbVbalrConditionalComp#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#1)]

## <a name="see-also"></a>请参阅

- [#Const 指令](../../../visual-basic/language-reference/directives/const-directive.md)
- [If...Then...Else 语句](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [条件编译](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- <xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>
