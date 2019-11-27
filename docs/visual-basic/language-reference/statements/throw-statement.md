---
title: Throw 语句
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: 147345990b625e034e651e69b322bc098d0bd8de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352784"
---
# <a name="throw-statement-visual-basic"></a>Throw 语句 (Visual Basic)

在过程中引发异常。

## <a name="syntax"></a>语法

```vb
Throw [ expression ]
```

## <a name="part"></a>部件

`expression`\
提供有关要引发的异常的信息。 如果位于 `Catch` 语句中，则为可选; 否则为必需。

## <a name="remarks"></a>备注

`Throw` 语句引发异常，你可以使用结构化异常处理代码（`Try`...`Catch`...`Finally`）或非结构化异常处理代码（`On Error GoTo`）处理该异常。 您可以使用 `Throw` 语句来捕获代码中的错误，因为 Visual Basic 会在调用堆栈中向上移动，直到找到相应的异常处理代码。

不带 expression 的 `Throw` 语句只能在 `Catch` 语句中使用，在这种情况下，该语句再次引发 `Catch` 语句正在处理的异常。

`Throw` 语句重置 `expression` 异常的调用堆栈。 如果未提供 `expression`，则调用堆栈保持不变。 可以通过 <xref:System.Exception.StackTrace%2A> 属性访问异常的调用堆栈。

## <a name="example"></a>示例

下面的代码使用 `Throw` 语句来引发异常：

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a>另请参阅

- [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [On Error 语句](../../../visual-basic/language-reference/statements/on-error-statement.md)
