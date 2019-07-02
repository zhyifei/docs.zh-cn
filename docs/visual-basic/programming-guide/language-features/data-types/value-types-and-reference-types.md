---
title: Value Types and Reference Types
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: f25caec43b7118b7b64db1b14516b0c5ea80f4f6
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504877"
---
# <a name="value-types-and-reference-types"></a>Value Types and Reference Types
有两种类型的 Visual Basic 中的类型： 引用类型和值类型。 引用类型的变量存储对其数据（对象）的引用，而值类型的变量直接包含其数据。 对于引用类型，两种变量可引用同一对象；因此，对一个变量执行的操作会影响另一个变量所引用的对象。 对于值类型，每个变量都具有其自己数据副本，并且不可能会影响另一个变量上的操作 (的情况下除外[ByRef 参数修饰符](../../../language-reference/modifiers/byref.md))。
  
## <a name="value-types"></a>值类型  
 数据类型是*值类型*如果它保存在其自己的内存分配中的数据。 值类型包括：  
  
- 所有数值数据类型  
  
- `Boolean`、 `Char`和 `Date`  
  
- 所有的结构，即使其成员是引用类型  
  
- 枚举，因为它们的基础类型始终`SByte`， `Short`， `Integer`， `Long`， `Byte`， `UShort`， `UInteger`，或 `ULong`  
  
 每个结构是值类型，即使它包含引用类型成员。 出于此原因，值类型，如`Char`和`Integer`由.NET Framework 结构实现。  
  
 可以通过使用保留的关键字，例如，声明值类型`Decimal`。 此外可以使用`New`关键字初始化值类型。 这是特别有用，如果该类型具有带参数的构造函数。 这就<xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>构造函数，将生成新`Decimal`从提供的部分的值。  
  
## <a name="reference-types"></a>引用类型  
 一个*引用类型*存储对其数据的引用。 引用类型包括：  
  
- `String`  
  
- 所有数组，即使其元素是值类型  
  
- 类类型如 <xref:System.Windows.Forms.Form>  
  
- 委托  
  
 类是*引用类型*。 请注意，每个数组是引用类型，即使其成员是值类型。  
  
 由于每个引用类型表示的基础的.NET Framework 类，因此必须使用[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)关键字时对其进行初始化。 下面的语句初始化数组。  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>不是类型的元素  
 以下的编程元素不适合作为类型，因为您不能指定其中任何一个已声明元素的数据类型为：  
  
- 命名空间  
  
- 模块  
  
- 事件  
  
- 属性和过程  
  
- 变量、 常量和字段  
  
## <a name="working-with-the-object-data-type"></a>使用对象数据类型  
 可以将引用类型或值类型分配给的变量`Object`数据类型。 `Object`变量始终保留到数据，永远不会数据本身的引用。 但是，如果将分配到值类型`Object`变量，其行为就像它保留其自己的数据。 有关详细信息，请参阅[Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)。  
  
 您可以确定是否`Object`变量充当引用类型或值类型将其传递到<xref:Microsoft.VisualBasic.Information.IsReference%2A>中的方法<xref:Microsoft.VisualBasic.Information>的类<xref:Microsoft.VisualBasic?displayProperty=nameWithType>命名空间。 <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> 返回`True`如果内容的`Object`变量表示引用类型。  
  
## <a name="see-also"></a>请参阅

- [可以为 null 的值类型](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [有效使用数据类型](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
