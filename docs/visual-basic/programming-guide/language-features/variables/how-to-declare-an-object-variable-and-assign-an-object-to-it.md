---
title: 'How to: Declare an Object Variable and Assign an Object to It'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 4cfad1d820b584d4610d24c392b14ac3958471b7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352909"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>如何：在 Visual Basic 中声明对象变量并为它分配对象

You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md). You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.

## <a name="example"></a>示例

The following example declares an `Object` variable and assigns the current instance to it.

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

You can combine the declaration and assignment by initializing the variable as part of its declaration. The following example is equivalent to the preceding example.

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compiling-the-code"></a>编译代码

此示例需要：

- 对 <xref:System> 命名空间的引用。

- A class, structure, or module in which to put the `Dim` statement.

- A procedure in which to put the assignment statement.

## <a name="see-also"></a>请参阅

- [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [对象变量声明](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
