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
ms.openlocfilehash: 9456316f71a213905bcb50336533c4e618f5174a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="value-types-and-reference-types"></a>Value Types and Reference Types
在 Visual Basic 中，数据类型是基于其分类来实现的。 Visual Basic 数据类型可以根据特定类型的变量存储其自己的数据或指向的数据进行分类。 如果它存储其自己的数据则*值类型*; 如果它保留一个指向它的内存中其他位置的数据*引用类型*。  
  
## <a name="value-types"></a>值类型  
 数据类型是*值类型*如果它包含在其自己的内存分配数据。 值类型包括：  
  
-   所有数值数据类型  
  
-   `Boolean`、`Char` 和 `Date`  
  
-   所有的结构，即使其成员是引用类型  
  
-   枚举，因为其基础类型始终是`SByte`， `Short`， `Integer`， `Long`， `Byte`， `UShort`， `UInteger`，或 `ULong`  
  
 每个结构是值类型，即使它包含引用类型成员。 为此，值类型，如`Char`和`Integer`由.NET Framework 结构实现。  
  
 你可以使用保留的关键字，例如，声明值类型`Decimal`。 你还可以使用`New`关键字初始化值类型。 这是特别有用，如果该类型具有的构造函数的参数。 此示例是<xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29>构造函数，它将生成新`Decimal`从提供的部分的值。  
  
## <a name="reference-types"></a>引用类型  
 A*引用类型*包含保存的数据的另一个内存位置的指针。 引用类型包括：  
  
-   `String`  
  
-   所有数组，即使其元素为值类型  
  
-   类类型如 <xref:System.Windows.Forms.Form>  
  
-   委托  
  
 类是*引用类型*。 为此，引用类型如`Object`和`String`支持[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]类。 请注意，每个数组是引用类型，即使其成员是值类型。  
  
 由于每个引用类型表示的基础的.NET Framework 类，你必须使用[New 运算符](../../../../visual-basic/language-reference/operators/new-operator.md)关键字时对其进行初始化。 下面的语句初始化数组。  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a>不支持类型的元素  
 以下编程元素不适合作为类型，因为不能指定其中任何为声明的元素的数据类型：  
  
-   命名空间  
  
-   模块  
  
-   事件  
  
-   属性和过程  
  
-   变量、 常量和字段  
  
## <a name="working-with-the-object-data-type"></a>使用对象数据类型  
 可以将引用类型或值类型分配给变量的`Object`数据类型。 `Object`变量始终保留一个指向的数据，永远不会数据本身。 但是，如果将分配到的值类型`Object`变量，其行为就像它包含其自己的数据。 有关详细信息，请参阅[Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)。  
  
 你可以找出是否`Object`变量作为引用类型或值类型将其传递到<xref:Microsoft.VisualBasic.Information.IsReference%2A>中的方法<xref:Microsoft.VisualBasic.Information>类<xref:Microsoft.VisualBasic?displayProperty=nameWithType>命名空间。 <xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> 返回`True`如果的内容`Object`变量表示引用类型。  
  
## <a name="see-also"></a>请参阅  
 [可以为 null 的值类型](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [在 Visual Basic 中的类型转换](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [有效使用数据类型](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Object 数据类型](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
