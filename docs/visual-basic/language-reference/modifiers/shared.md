---
title: Shared (Visual Basic)
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
ms.openlocfilehash: b15dd08d69f372317b9140001e8072eeb66d44ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)
指定的一个或多个已声明的编程元素与类或结构在大型，而不使用的类或结构的特定实例关联。  
  
## <a name="remarks"></a>备注  
  
## <a name="when-to-use-shared"></a>何时使用共享  
 共享的类或结构成员使其可供每个实例，而不是*非共享*，其中每个实例都需要其自己的副本。 这很有用，例如，如果变量的值应用于整个应用程序。 如果将该变量声明`Shared`，那么所有实例会都访问同一存储位置，而如果一个实例更改变量的值，所有实例都会都都访问更新后的值。  
  
 共享不会更改成员的访问级别。 例如，可以共享类成员和私有 （仅可从访问类中），两种公共和非共享。 有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
## <a name="rules"></a>规则  
  
-   **声明上下文。** 只能在模块级别使用 `Shared`。 这意味着的声明上下文`Shared`元素必须是类或结构，并且不能是源文件、 命名空间或过程。  
  
-   **组合的修饰符。** 不能指定`Shared`连同[重写](../../../visual-basic/language-reference/modifiers/overrides.md)，[可重写](../../../visual-basic/language-reference/modifiers/overridable.md)， [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)， [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)，或[静态](../../../visual-basic/language-reference/modifiers/static.md)同一声明中。  
  
-   **访问。** 通过其类或结构名称而不是其类或结构的特定实例的变量名称限定它访问的共享的元素。 即使不需要创建的类或结构，用于访问它的共享的成员实例。  
  
     下面的示例调用共享的过程<xref:System.Double.IsNaN%2A>公开<xref:System.Double>结构。  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   **隐式共享。** 不能使用`Shared`修饰符在[Const 语句](../../../visual-basic/language-reference/statements/const-statement.md)，但隐式共享常量。 同样，不能声明为模块或接口的成员`Shared`，但它们会被隐式共享。  
  
## <a name="behavior"></a>行为  
  
-   **存储。** 仅一次，无论多少或少数几个实例你创建的类或结构，在内存中存储的共享的变量或事件。 同样，共享的过程或属性仅存储一组的本地变量。  
  
-   **通过实例变量访问。** 可通过用包含其类或结构的特定实例的变量的名称限定它访问的共享的元素。 虽然这通常按预期工作，编译器将生成一条警告消息，并使通过类或结构名称而不使用变量的访问权限。  
  
-   **通过实例表达式进行访问。** 如果通过一个表达式，返回其类或结构的实例访问共享的元素，则编译器会通过类或结构名称而不是计算表达式的访问权限。 如果你想要执行其他操作，以及返回实例的表达式，这会产生意外的结果。 下面的示例阐释了这一点。  
  
    ```  
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
  
     在前面的示例中，编译器将生成一条警告消息代码访问共享的变量两次`total`通过实例。 每种情况下它都使直接通过类访问`shareTotal`并不会进行的任何实例使用。 在预期调用的过程的情况下`returnClass`，这意味着它不甚至生成调用`returnClass`，因此不执行额外的操作显示"调用函数 returnClass()"。  
  
 `Shared` 修饰符可用于下面的上下文中：  
  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>请参阅  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Static](../../../visual-basic/language-reference/modifiers/static.md)  
 [在 Visual Basic 中的生存期](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [过程](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [结构](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [对象和类](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
