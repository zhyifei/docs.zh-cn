---
title: 如何：创建过程（Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
ms.openlocfilehash: 2cf4c788ec421c1e74ef7198496a92149e049752
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216720"
---
# <a name="how-to-create-a-procedure-visual-basic"></a>如何：创建过程（Visual Basic）

在开始声明语句`Sub` （或`Function`）和结束声明语句（`End Sub`或`End Function`）之间包含过程。 过程的所有代码都位于这些语句之间。

 一个过程不能包含另一个过程，所以其开始和结束语句必须在其他任何过程之外。

 如果你的代码在不同的位置执行相同的任务，则可以将该任务作为过程写入一次，然后从代码中的不同位置调用它。

### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>创建不返回值的过程

1. 在`Sub`任何其他过程之外，使用语句，然后`End Sub`使用语句。

2. 在语句中，在`Sub`关键字后面跟过程的名称，然后是括号中的参数列表。 `Sub`

3. 将过程的代码语句放置在`Sub`和`End Sub`语句之间。

### <a name="to-create-a-procedure-that-returns-a-value"></a>创建返回值的过程

1. 在`Function`任何其他过程之外，使用语句，然后`End Function`使用语句。

2. 在语句中，在`Function`关键字后面跟过程的名称，然后是括号中的参数列表，然后是`As`指定返回值的数据类型的子句。 `Function`

3. 将过程的代码语句放置在`Function`和`End Function`语句之间。

4. `Return`使用语句将值返回到调用代码。

### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>将新过程与旧的、重复的代码块连接起来

1. 请确保在旧代码有权访问的位置定义新过程。

2. 在旧的、重复的代码块中，使用调用`Sub`或`Function`过程的单个语句替换执行重复任务的语句。

3. 如果你`Function`的过程是返回值的，请确保调用语句使用返回值执行操作（例如，将其存储在变量中），否则值将丢失。

## <a name="example"></a>示例

 以下`Function`过程将计算直角三角形的最长边（或斜边），并给出另两个边的值：

 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

## <a name="see-also"></a>请参阅

- [过程](index.md)
- [Sub 过程](sub-procedures.md)
- [Function 过程](function-procedures.md)
- [属性过程](property-procedures.md)
- [运算符过程](operator-procedures.md)
- [过程参数和自变量](procedure-parameters-and-arguments.md)
- [递归过程](recursive-procedures.md)
- [过程重载](procedure-overloading.md)
- [对象和类](../objects-and-classes/index.md)
- [面向对象的编程 (Visual Basic)](../../concepts/object-oriented-programming.md)
