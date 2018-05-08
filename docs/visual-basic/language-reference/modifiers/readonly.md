---
title: ReadOnly (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: e2957bf49292dfcafab8e78f4b997247c34ad279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
指定，可以读取而不是写入的变量或属性。  
  
## <a name="remarks"></a>备注  
  
## <a name="rules"></a>规则  
  
-   **声明上下文。** 只能在模块级别使用 `ReadOnly`。 这意味着的声明上下文`ReadOnly`元素必须是类、 结构或模块，并且不能是源文件、 命名空间或过程。  
  
-   **组合的修饰符。** 不能指定`ReadOnly`连同`Static`同一声明中。  
  
-   **将分配一个值。** 代码使用`ReadOnly`属性不能将其值设置。 但有权访问基础存储区的代码可以分配或随时更改的值。  
  
     你可以将值赋给`ReadOnly`变量仅在其声明或在类或结构定义它的构造函数。  
  
## <a name="when-to-use-a-readonly-variable"></a>何时使用 ReadOnly 变量  
 在一些情况下，你不能在其中使用[Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)声明和分配常量值。 例如，`Const`语句不可能接受的数据类型，你想要分配，或你可能不能在编译时常量表达式计算的值。 您可能不知道值在编译时。 在这些情况下，你可以使用`ReadOnly`变量以保存常量值。  
  
> [!IMPORTANT]
>  即使变量本身是，如果变量的数据类型是引用类型，如数组或类实例，可以更改其成员`ReadOnly`。 下面的示例阐释了这一点。  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 在初始化时，该数组的指向`characterArray()`保存"x"、"y"和"z"。 因为变量`characterArray`是`ReadOnly`，只要该函数将初始化; 即，不能更改其值，不能向其分配一个新数组。 但是，你可以更改的一个或多个数组成员的值。 在过程调用`changeArrayElement`，指向的数组`characterArray()`保存"x"、"M"和"z"。  
  
 请注意，这是类似于声明过程参数是[ByVal](../../../visual-basic/language-reference/modifiers/byval.md)，它防止过程更改调用自变量本身，但这样一来更改其成员。  
  
## <a name="example"></a>示例  
 下面的示例定义`ReadOnly`员工受雇在其的日期属性。 属性值作为在内部的类存储`Private`变量，并且只在类中的代码可以更改该值。 但是，该属性是`Public`，和可以访问类任何代码都可以读取该属性。  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 `ReadOnly` 修饰符可用于下面的上下文中：  
  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>请参阅  
 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)
