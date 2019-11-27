---
title: 如何：创建新变量
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: 2a2b5b8bef3b66f9727f0e65b61882186c007e94
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353637"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a>如何：创建新变量 (Visual Basic)

使用[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)创建变量。

### <a name="to-create-a-new-variable"></a>创建新变量

1. 在 `Dim` 语句中声明变量。

    ```vb
    Dim newCustomer
    ```

2. 包含变量特征的规范，如[Private](../../../../visual-basic/language-reference/modifiers/private.md)、 [Static](../../../../visual-basic/language-reference/modifiers/static.md)、 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)或[WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md)。 有关详细信息，请参阅[声明的元素特征](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)。

    ```vb
    Public Static newCustomer
    ```

    如果在声明中使用其他关键字，则不需要 `Dim` 关键字。

3. 请按照该规范的名称进行操作，该变量的名称必须遵循 Visual Basic 规则和约定。 有关详细信息，请参阅已[声明的元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。

    ```vb
    Public Static newCustomer
    ```

4. 在名称后跟[As](../../../../visual-basic/language-reference/statements/as-clause.md)子句以指定变量的数据类型。

    ```vb
    Public Static newCustomer As Customer
    ```

    如果未指定数据类型，则将使用默认值： `Object`。

5. 将 `As` 子句跟一个等号（`=`），并在该变量的初始值后跟等号。

    每次运行 `Dim` 语句时，Visual Basic 都将指定的值分配给变量。 如果不指定初始值，则 Visual Basic 在第一次输入包含 `Dim` 语句的代码时，为变量的数据类型分配默认初始值。

    如果变量是引用类型，则可以通过在 `As` 子句中包含[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)关键字来创建其类的实例。 如果不使用 `New`，则变量的初始值为[Nothing](../../../../visual-basic/language-reference/nothing.md)。

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a>另请参阅

- [变量](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [已声明的元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [已声明元素的特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [语句](../../../../visual-basic/language-reference/statements/index.md)
- [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
