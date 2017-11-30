---
title: "用户定义的数据类型"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e1876d61a2ce89b04c6e5061b868f0be365639f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="user-defined-data-type"></a>用户定义的数据类型
在您定义的格式中包含数据。 `Structure`语句定义的格式。  
  
 以前版本的 Visual Basic 支持用户定义类型 (UDT)。 当前版本则将扩展到 UDT*结构*。 结构是一个或多个串联*成员*的各种数据类型。 虽然你也可以单独访问其成员，Visual Basic 将视为单个单元，一种结构。  
  
## <a name="remarks"></a>备注  
 定义和使用结构数据类型，当你需要将各种数据类型组合到单个单元，或者当没有一个基本数据类型满足您的需要。  
  
 结构数据类型的默认值由其每个成员的默认值的组合组成。  
  
## <a name="declaration-format"></a>声明格式  
 结构声明开头[Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)和结束的`End``Structure`语句。 `Structure`语句提供结构，它也是在定义结构的数据类型的标识符的名称。 代码的其他部分可以使用此标识符声明变量、 参数和函数的返回值是此结构的数据类型。  
  
 之间的声明`Structure`和`End``Structure`语句定义结构的成员。  
  
## <a name="member-access-levels"></a>成员访问级别  
 必须声明使用每个成员[Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)或指定访问级别，例如语句[公共](../../../visual-basic/language-reference/modifiers/public.md)，[友元](../../../visual-basic/language-reference/modifiers/friend.md)，或[私有](../../../visual-basic/language-reference/modifiers/private.md). 如果你使用`Dim`语句，为公共的访问级别默认值。  
  
## <a name="programming-tips"></a>编程提示  
  
-   **内存消耗。** 与所有复合数据类型，不能安全地通过同时添加其成员的名义存储分配计算结构的总内存消耗。 此外，不能安全地假设存储在内存中的顺序是声明的顺序相同。 如果你需要控制结构的存储布局，则可以应用<xref:System.Runtime.InteropServices.StructLayoutAttribute>属性设为`Structure`语句。  
  
-   **互操作注意事项。** 如果你与不是为.NET Framework 编写的组件交互，例如自动化或 COM 对象，请记住在其他环境中的用户定义的类型不兼容使用 Visual Basic 的结构类型。  
  
-   **扩大转换。** 没有自动转换到或从任何结构数据类型。 你可以定义转换运算符对你结构使用[Operator 语句](../../../visual-basic/language-reference/statements/operator-statement.md)，你可以声明为每个转换运算符`Widening`或`Narrowing`。  
  
-   **类型字符。** 结构数据类型的任何文本类型字符或标识符类型字符。  
  
-   **Framework 类型。** .NET Framework 中不存在相应的类型。 从.NET Framework 类继承的所有结构<xref:System.ValueType?displayProperty=nameWithType>，但没有单独的结构对应<xref:System.ValueType?displayProperty=nameWithType>。  
  
## <a name="example"></a>示例  
 下面的示例演示了结构声明的轮廓。  
  
```  
[Public | Protected | Friend | Protected Friend | Private] Structure structname  
    {Dim | Public | Friend | Private} member1 As datatype1  
    ' ...  
    {Dim | Public | Friend | Private} memberN As datatypeN  
End Structure  
```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ValueType>  
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>  
 [数据类型](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [转换摘要](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Structure 语句](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [有效使用数据类型](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
