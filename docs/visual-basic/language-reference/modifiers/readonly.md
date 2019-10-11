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
ms.openlocfilehash: 748c38835cec83cefe54535f90d40ec3a030e4f4
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2019
ms.locfileid: "72250379"
---
# <a name="readonly-visual-basic"></a>ReadOnly (Visual Basic)
指定可以读取但不能写入变量或属性。  
  
## <a name="remarks"></a>备注  
  
## <a name="rules"></a>规则  
  
- **声明上下文。** 只能在模块级别使用 `ReadOnly`。 这意味着 `ReadOnly` 元素的声明上下文必须是类、结构或模块，不能是源文件、命名空间或过程。  
  
- **组合修饰符。** 不能在同一声明中同时指定 `ReadOnly` 和 @no__t。  
  
- **赋值。** 使用 `ReadOnly` 属性的代码不能设置其值。 但有权访问基础存储的代码可以随时分配或更改值。  
  
     只能在其声明中或在定义它的类或结构的构造函数中为 @no__t 0 变量赋值。  
  
## <a name="when-to-use-a-readonly-variable"></a>何时使用 ReadOnly 变量  
 在某些情况下，不能使用[Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)来声明和分配常量值。 例如，`Const` 语句可能不接受您要分配的数据类型，或者您可能无法在编译时使用常量表达式来计算值。 在编译时，您甚至不知道值。 在这些情况下，可以使用 `ReadOnly` 变量来保存常量值。  
  
> [!IMPORTANT]
> 如果该变量的数据类型是引用类型（如数组或类实例），则即使该变量本身 @no__t 为0，也可以更改其成员。 下面的示例阐释了这一点。  
  
 ```vb
 ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}
 Sub ChangeArrayElement()
     characterArray(1) = "M"c
 End Sub
 ```
  
 初始化后，@no__t 为的数组包含 "x"、"y" 和 "z"。 由于变量 `characterArray` @no__t 为-1，因此在初始化后，不能更改其值;也就是说，不能向其分配新数组。 但是，您可以更改一个或多个数组成员的值。 调用过程后 `ChangeArrayElement`，`characterArray()` 指向的数组包含 "x"、"M" 和 "z"。
  
 请注意，这类似于将过程参数声明为[ByVal](byval.md)，这会阻止过程更改调用自变量本身，但允许该过程更改其成员。  
  
## <a name="example"></a>示例

下面的示例为雇用员工的日期定义 `ReadOnly` 属性。 类将属性值作为 `Private` 变量在内部存储，并且只有类中的代码可以更改该值。 但是，属性为 `Public`，任何可访问类的代码都可以读取属性。
  
[!code-vb[VbVbalrKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#4)]
  
`ReadOnly` 修饰符可用于下面的上下文中：
  
- [Dim 语句](../statements/dim-statement.md) 
- [Property 语句](../statements/property-statement.md)  
  
## <a name="see-also"></a>请参阅

- [WriteOnly](writeonly.md)
- [关键字](../keywords/index.md)
