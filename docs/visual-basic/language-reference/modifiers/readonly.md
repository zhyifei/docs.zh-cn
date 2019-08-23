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
ms.openlocfilehash: 01c441576cb4247933c053f2043296733f99fdeb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965422"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
指定可以读取但不能写入变量或属性。  
  
## <a name="remarks"></a>备注  
  
## <a name="rules"></a>规则  
  
- **声明上下文。** 只能在模块级别使用 `ReadOnly`。 这意味着`ReadOnly`元素的声明上下文必须是类、结构或模块, 不能是源文件、命名空间或过程。  
  
- **组合修饰符。** 不能在`ReadOnly`同一声明`Static`中同时指定和。  
  
- **赋值。** 使用`ReadOnly`属性的代码不能设置其值。 但有权访问基础存储的代码可以随时分配或更改值。  
  
     只能在其声明中或在`ReadOnly`定义它的类或结构的构造函数中为变量赋值。  
  
## <a name="when-to-use-a-readonly-variable"></a>何时使用 ReadOnly 变量  
 在某些情况下, 不能使用[Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)来声明和分配常量值。 例如, `Const`语句可能不接受您要分配的数据类型, 或者您可能无法在编译时使用常量表达式来计算值。 在编译时, 您甚至不知道值。 在这些情况下, 可以使用`ReadOnly`变量来保存常量值。  
  
> [!IMPORTANT]
> 如果该变量的数据类型是引用类型 (如数组或类实例), 则即使该变量本身为`ReadOnly`, 也可以更改其成员。 下面的示例阐释了这一点。  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 初始化后, 由指向的`characterArray()`数组包含 "x"、"y" 和 "z"。 由于变量`characterArray`为`ReadOnly`, 因此在初始化后无法更改其值; 也就是说, 您不能为其分配新数组。 但是, 您可以更改一个或多个数组成员的值。 调用过程`changeArrayElement`后, 由`characterArray()`指向的数组包含 "x"、"M" 和 "z"。  
  
 请注意, 这类似于将过程参数声明为[ByVal](../../../visual-basic/language-reference/modifiers/byval.md), 这会阻止过程更改调用自变量本身, 但允许该过程更改其成员。  
  
## <a name="example"></a>示例  
 下面的示例定义`ReadOnly`了雇员雇用日期的属性。 类在内部将属性值存储为`Private`变量, 并且只有类中的代码可以更改该值。 但是, 属性为`Public`, 并且任何可以访问类的代码都可以读取属性。  
  
 [!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]  
  
 `ReadOnly` 修饰符可用于下面的上下文中：  
  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>请参阅

- [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)
- [关键字](../../../visual-basic/language-reference/keywords/index.md)
