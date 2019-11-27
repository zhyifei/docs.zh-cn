---
title: 局部类型推理
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: f79ac70aecb5805a3a4a4fea8f7e7ccd3f8243fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351839"
---
# <a name="local-type-inference-visual-basic"></a>局部类型推理 (Visual Basic)

Visual Basic 编译器使用*类型推理*来确定不使用 `As` 子句声明的局部变量的数据类型。 编译器从初始化表达式的类型推断出变量的类型。 这样，便可以在不显式声明类型的情况下声明变量，如下面的示例中所示。 作为声明的结果，`num1` 和 `num2` 都作为整数强类型化。

[!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]

> [!NOTE]
> 如果您不希望在前一示例中将 `num2` 类型化为 `Integer`，则可以使用 `Dim num3 As Object = 3` 或 `Dim num4 As Double = 3`之类的声明来指定另一种类型。

> [!NOTE]
> 类型推理只能用于非静态局部变量;它不能用于确定类字段、属性或函数的类型。

局部类型推理适用于过程级别。 它不能用于在模块级别（在类、结构、模块或接口中，而不是在过程或块中）声明变量。 如果上一个示例中 `num2` 是某个类的一个字段，而不是过程中的局部变量，则该声明将导致与 `Option Strict` 出现错误，并将 `num2` 分类为 `Object` `Option Strict` off。 同样，局部类型推理不适用于声明为 `Static`的过程级变量。

## <a name="type-inference-vs-late-binding"></a>类型推理与后期绑定

使用类型推理的代码与依赖后期绑定的代码类似。 但是，类型推理强类型变量，而不是将其保留为 `Object`。 编译器在编译时使用变量的初始值设定项来确定变量的类型以生成早期绑定的代码。 在前面的示例中，`num2`（如 `num1`）被类型化为 `Integer`。

早期绑定变量的行为与后期绑定变量的行为不同，后者的类型仅在运行时已知。 事先知道类型使编译器能够在执行之前识别问题，精确分配内存并执行其他优化。 早期绑定还允许 Visual Basic 集成开发环境（IDE）为对象的成员提供 IntelliSense 帮助。 早期绑定也是性能的首选。 这是因为，后期绑定变量中存储的所有数据都必须包装为类型 `Object`，并且在运行时访问该类型的成员会使程序速度变慢。

## <a name="examples"></a>示例

如果在不使用 `As` 子句的情况下声明了本地变量并进行了初始化，则会发生类型推理。 编译器使用所赋的初始值的类型作为变量的类型。 例如，以下每行代码都声明一个 `String`类型的变量。

[!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]

下面的代码演示了两种创建整数数组的等效方法。

[!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]

使用类型推理来确定循环控制变量的类型是一种很方便的方法。 在下面的代码中，编译器将推断 `number` 是 `Integer`，因为上一示例中的 `someNumbers2` 是整数数组。

[!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]

可以在 `Using` 语句中使用局部类型推理来建立资源名称的类型，如下面的示例所示。

[!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]

还可以从函数的返回值推断变量的类型，如下例所示。 `pList1` 和 `pList2` 都是进程的数组，因为 `Process.GetProcesses` 返回进程的数组。

[!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]

## <a name="option-infer"></a>选项推断

`Option Infer` 使你可以指定是否允许在特定文件中执行局部类型推理。 若要启用或阻止该选项，请在文件开头键入以下语句之一。

`Option Infer On`

`Option Infer Off`

如果在代码中未指定 `Option Infer` 的值，则将 `Option Infer On`编译器默认值。

如果为文件中 `Option Infer` 设置的值与在 IDE 中或在命令行上设置的值冲突，则文件中的值优先。

有关详细信息，请参阅[选项推断语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)和[编译页，项目设计器（Visual Basic）](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)。

## <a name="see-also"></a>另请参阅

- [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [早期绑定和后期绑定](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [For Each...Next 语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [For...Next 语句](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [-optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
