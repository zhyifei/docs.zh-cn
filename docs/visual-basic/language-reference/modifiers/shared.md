---
title: Shared
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: 98fa25d2283408dfb80e82fbc620a1b284e5c530
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349119"
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)
指定一个或多个已声明的编程元素与较大的类或结构关联，而不是与类或结构的特定实例相关联。  
  
## <a name="remarks"></a>备注  
  
## <a name="when-to-use-shared"></a>何时使用共享  
 共享类或结构的成员使其可用于每个实例，而不是*共享，其中*每个实例都保留其自己的副本。 例如，如果将变量的值应用于整个应用程序，则此方法很有用。 如果声明要 `Shared`的变量，则所有实例都将访问相同的存储位置，并且如果一个实例更改该变量的值，则所有实例都将访问更新的值。  
  
 共享不会更改成员的访问级别。 例如，类成员可以是共享的，也可以是专用的（只能从类中访问），也可以是非共享和公共的。 有关详细信息，请参阅[Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
## <a name="rules"></a>规则  
  
- **声明上下文。** 只能在模块级别使用 `Shared`。 这意味着 `Shared` 元素的声明上下文必须是类或结构，不能是源文件、命名空间或过程。  
  
- **组合修饰符。** 不能在同一声明中同时指定 `Shared` 和[重写](../../../visual-basic/language-reference/modifiers/overrides.md)、可[重写](../../../visual-basic/language-reference/modifiers/overridable.md)、 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)、 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)或[静态](../../../visual-basic/language-reference/modifiers/static.md)。  
  
- **访问.** 使用共享元素的类或结构名称（而不是其类或结构的特定实例的变量名称）来限定共享元素。 甚至不必创建类或结构的实例即可访问其共享成员。  
  
     下面的示例调用 <xref:System.Double.IsNaN%2A> <xref:System.Double> 结构公开的共享过程。  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
- **隐式共享。** 不能在[Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)中使用 `Shared` 修饰符，而是隐式共享常量。 同样，你不能声明要 `Shared`的模块或接口的成员，但它们是隐式共享的。  
  
## <a name="behavior"></a>行为  
  
- **储存.** 共享的变量或事件只存储在内存中，无论您创建的是多少或几个实例的类或结构。 同样，共享过程或属性仅保存一组局部变量。  
  
- **通过实例变量访问。** 可以通过使用包含其类或结构的特定实例的变量的名称来限定共享元素，从而访问该共享元素。 虽然这通常按预期方式工作，但编译器会生成一条警告消息，并通过类或结构名称而不是变量来进行访问。  
  
- **通过实例表达式访问。** 如果通过返回类或结构的实例的表达式访问共享元素，编译器将通过类或结构名称进行访问，而不是计算表达式。 如果你希望表达式执行其他操作以及返回实例，则会产生意外的结果。 下面的示例阐释了这一点。  
  
    ```vb
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     在前面的示例中，编译器会在代码通过实例访问共享变量 `total` 时生成一条警告消息。 在每种情况下，它会通过类 `shareTotal` 直接访问，而不会使用任何实例。 如果对过程的预期调用 `returnClass`，这意味着它甚至不会生成对 `returnClass`的调用，因此不会执行显示 "Function returnClass （）" 的其他操作。  
  
 `Shared` 修饰符可用于下面的上下文中：  
  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>另请参阅

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Static](../../../visual-basic/language-reference/modifiers/static.md)
- [生存期（Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
