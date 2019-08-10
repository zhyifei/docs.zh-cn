---
title: Throw 语句 (Visual Basic)
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
ms.openlocfilehash: 9680700267f17c8e316de351fead61f1dc4aded0
ms.sourcegitcommit: 9ee6cd851b6e176a5811ea28ed0d5935c71950f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/09/2019
ms.locfileid: "68869024"
---
# <a name="throw-statement-visual-basic"></a>Throw 语句 (Visual Basic)

在过程中引发异常。

## <a name="syntax"></a>语法

```vb
Throw [ expression ]
```

## <a name="part"></a>部件

`expression`\
提供有关要引发的异常的信息。 如果位于`Catch`语句中, 则为可选; 否则为必需。

## <a name="remarks"></a>备注

语句引发异常, 你可以使用结构化异常处理代码 (`Try`... `Throw``Catch`...) 或非结构化异常处理代码`On Error GoTo`()。 `Finally` 您可以使用`Throw`语句来捕获代码中的错误, 因为 Visual Basic 在调用堆栈中向上移动, 直到找到相应的异常处理代码。

不带 expression 的`Catch` `Catch`语句只能用在语句中, 在这种情况下, 该语句重新引发语句当前正在处理的异常。 `Throw`

语句重置`expression`异常的调用堆栈。 `Throw` 如果`expression`未提供, 则调用堆栈保持不变。 您可以通过<xref:System.Exception.StackTrace%2A>属性访问异常的调用堆栈。

## <a name="example"></a>示例

下面的代码使用`Throw`语句引发异常:

[!code-vb[VbVbalrStatements#84](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#84)]

## <a name="see-also"></a>请参阅

- [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [On Error 语句](../../../visual-basic/language-reference/statements/on-error-statement.md)
