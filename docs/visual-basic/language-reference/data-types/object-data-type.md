---
title: Object 数据类型 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 1ac906494c49810e3d389591b1044f412e7320bc
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513048"
---
# <a name="object-data-type"></a>Object Data Type

保存引用对象的地址。 可以将任何引用类型 (字符串、数组、类或接口) 分配给`Object`变量。 变量还可以引用任意值类型的数据 ( `Char`数值、 `Boolean`、、 `Date`、结构或枚举)。 `Object`

## <a name="remarks"></a>备注

`Object`数据类型可以指向任何数据类型的数据, 包括应用程序识别的任何对象实例。 在`Object`编译时不知道变量可能指向的数据类型时, 请使用。

的默认值`Object`为`Nothing` (空引用)。

## <a name="data-types"></a>数据类型

可以将任何数据类型的变量、常量或表达式分配给`Object`变量。 若要确定`Object`变量当前引用的数据类型, 可以<xref:System.Type.GetTypeCode%2A>使用<xref:System.Type?displayProperty=nameWithType>类的方法。 下面的示例阐释了这一点。

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

`Object`数据类型为引用类型。 但是, 当`Object`变量引用值类型的数据时, Visual Basic 将变量视为值类型。

## <a name="storage"></a>存储

无论它引用哪种数据类型, `Object`变量都不包含数据值本身, 而是指向值的指针。 它在计算机内存中始终使用四个字节, 但这不包括表示变量值的数据的存储。 由于使用指针查找数据的代码, `Object`保存值类型的变量比显式类型化变量略慢。

## <a name="programming-tips"></a>编程提示

- **互操作注意事项。** 如果与不是为 .NET Framework 编写的组件 (如自动化或 COM 对象) 交互, 请记住, 其他环境中的指针类型与 Visual Basic `Object`类型不兼容。

- **性能。** 用`Object`类型声明的变量的灵活性足以包含对任何对象的引用。 但是, 在此类变量上调用方法或属性时, 始终会产生*后期绑定*(在运行时)。 若要强制进行*早期绑定*(在编译时) 和更好的性能, 请使用特定类名称声明变量, 或将其转换为特定数据类型。

  声明对象变量时, 请尝试使用特定类类型, <xref:System.OperatingSystem>而不是通用`Object`类型。 还应使用最具体的类, 如<xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.Control>而不是, 以便您可以访问其属性和方法。 通常可以使用**对象浏览器**中的 "**类**" 列表来查找可用的类名。

- **扩大.** 所有数据类型和所有引用类型都扩大到`Object`数据类型。 这意味着, 可以将任何类型转换`Object`为, 而<xref:System.OverflowException?displayProperty=nameWithType>不会遇到错误。

  但是, 如果在值类型和`Object`之间进行转换, Visual Basic 将执行称为*装箱*和*取消装箱*的操作, 这会使执行速度变慢。

- **键入字符。** `Object`没有文本类型字符或标识符类型字符。

- **Framework 类型。** .NET Framework 中的相应类型是<xref:System.Object?displayProperty=nameWithType>类。

## <a name="example"></a>示例

下面的示例演示指向`Object`对象实例的变量。

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a>请参阅

- <xref:System.Object>
- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
- [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [如何：确定两个对象是否相关](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [如何：确定两个对象是否相同](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
