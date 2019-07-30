---
title: 如何：确定对象变量引用的类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 935623dd4b6edca188f932aca0e560130199e8f6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626569"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a>如何：确定对象变量引用的类型 (Visual Basic)

对象变量包含指向存储在其他位置的数据的指针。 该数据的类型在运行时可能会更改。 随时都可以使用<xref:System.Type.GetTypeCode%2A>方法确定当前运行时类型, 或使用[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)来找出当前运行时类型是否与指定的类型兼容。

### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a>确定对象变量当前所引用的确切类型

1. 在对象变量上, 调用<xref:System.Object.GetType%2A>方法来<xref:System.Type?displayProperty=nameWithType>检索对象。

    ```vb
    Dim myObject As Object
    myObject.GetType()
    ```

2. 在类上, 调用共享方法<xref:System.Type.GetTypeCode%2A>以检索<xref:System.TypeCode>该对象的类型的枚举值。 <xref:System.Type?displayProperty=nameWithType>

    ```vb
    Dim myObject As Object
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())
    MsgBox("myObject currently has type code " & CStr(datTyp))
    ```

    您可以根据任何<xref:System.TypeCode>所需的枚举成员 ( `Double`例如) 测试枚举值。

### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a>确定对象变量的类型是否与指定的类型兼容

- 将运算符与[Is 运算符](../../../../visual-basic/language-reference/operators/is-operator.md)结合使用, 以`TypeOf`使用 ... `TypeOf``Is`表达式。

    ```vb
    If TypeOf objA Is System.Windows.Forms.Control Then
        MsgBox("objA is compatible with the Control class")
    End If
    ```

    `TypeOf`.。。如果对象的运行时类型与指定的类型兼容, 则表达式返回`True`。 `Is`

    兼容性的条件取决于指定的类型是类、结构还是接口。 通常, 如果对象的类型与、继承自或实现指定的类型, 则类型是兼容的。 有关详细信息, 请参阅[TypeOf 运算符](../../../../visual-basic/language-reference/operators/typeof-operator.md)。

## <a name="compiling-the-code"></a>编译代码

请注意, 指定的类型不能为变量或表达式。 它必须是已定义类型的名称, 如类、结构或接口。 这包括内部类型`Integer` , 例如和。 `String`

## <a name="see-also"></a>请参阅

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [对象变量](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [对象变量值](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)
