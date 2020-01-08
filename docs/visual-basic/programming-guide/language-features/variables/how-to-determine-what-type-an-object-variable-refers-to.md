---
title: 如何：确定对象变量引用的类型
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: b3778a170759f685db78e7dcde219138196f9eca
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344199"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>如何：确定对象变量引用的类型 (Visual Basic)

对象变量包含指向存储在其他位置的数据的指针。 该数据的类型在运行时可能会更改。 随时都可以使用 <xref:System.Type.GetTypeCode%2A> 方法来确定当前运行时类型，或使用[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)来确定当前运行时类型是否与指定的类型兼容。

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>确定对象变量当前所引用的确切类型

1. 在对象变量上，调用 <xref:System.Object.GetType%2A> 方法检索 <xref:System.Type?displayProperty=nameWithType> 对象。

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. 在 <xref:System.Type?displayProperty=nameWithType> 类上，调用共享方法 <xref:System.Type.GetTypeCode%2A> 以检索该对象的类型的 <xref:System.TypeCode> 枚举值。

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    您可以根据所需的任何枚举成员（如 `Double`）测试 <xref:System.TypeCode> 枚举值。

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>确定对象变量的类型是否与指定的类型兼容

- 结合使用 `TypeOf` 运算符和[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)来测试具有 `TypeOf`...`Is` 表达式的对象。

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    `TypeOf`...如果对象的运行时类型与指定的类型兼容, 则表达式返回`True`。 `Is`

    兼容性的条件取决于指定的类型是类、结构还是接口。 通常，如果对象的类型与、继承自或实现指定的类型，则类型是兼容的。 有关详细信息，请参阅[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)。

## <a name="compile-the-code"></a>编译代码

请注意，指定的类型不能为变量或表达式。 它必须是已定义类型的名称，如类、结构或接口。 这包括内部类型（如 `Integer` 和 `String`）。

## <a name="see-also"></a>另请参阅

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [对象变量值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)
