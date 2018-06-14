---
title: 如何：控制变量的范围 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 6e8d1178398711226b88fee7e6defd5162b91fcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649186"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>如何：控制变量的范围 (Visual Basic)
通常情况下，变量位于*作用域*，或作为参考，整个声明它的区域可见。 在某些情况下，该变量的*访问级别*可影响其范围。  
  
 有关详细信息，请参阅[在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)。  
  
## <a name="scope-at-block-or-procedure-level"></a>在块或过程级别的作用域  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>若要使变量仅在块内可见  
  
-   位置[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)变量之间的起始和终止声明语句的该块中，例如之间`For`和`Next`的语句`For`循环。  
  
     你可以引用该变量只能在块中。  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>若要使变量仅在过程内可见  
  
-   位置`Dim`变量过程中但在任何块外部语句 (如`With`...`End With`块)。  
  
     你可以引用只能从在过程中，包括在该过程中包含任何块内的变量。  
  
## <a name="scope-at-module-or-namespace-level"></a>在模块或 Namespace 级别的作用域  
 为方便起见，单个字词*模块级别*同样适用于模块、 类和结构。 模块级变量的访问级别确定其作用域。 包含模块、 类或结构的命名空间也会影响范围。  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>若要使变量在整个模块、 类或结构可见  
  
1.  位置`Dim`内部模块、 类或结构，但在任何过程外部变量的语句。  
  
2.  包括[私有](../../../../visual-basic/language-reference/modifiers/private.md)中的关键字`Dim`语句。  
  
3.  您可以参考内任意位置模块、 类或结构，但不是能从变量之外。  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>若要使变量在一个命名空间整个可见  
  
1.  位置`Dim`内部模块、 类或结构，但在任何过程外部变量的语句。  
  
2.  包括[友元](../../../../visual-basic/language-reference/modifiers/friend.md)或[公共](../../../../visual-basic/language-reference/modifiers/public.md)中的关键字`Dim`语句。  
  
3.  你可以引用的变量从任意位置包含模块、 类或结构的命名空间中。  
  
## <a name="example"></a>示例  
 下面的示例声明了一个在模块级别的变量，并限制到模块中的代码其可见性。  
  
```  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 在前面的示例中，在模块中定义的所有过程`demonstrateScope`可以指`String`变量`strMsg`。 当`usePrivateVariable`调用过程时，它将显示的字符串变量的内容`strMsg`在对话框中。  
  
 与前面的示例中，字符串变量到以下内容有变更`strMsg`可以通过其声明的命名空间中的任意位置的代码引用。  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>可靠编程  
 变量中，你有针对意外引用它来替换另一个变量具有相同名称的可能性更小的范围越窄。 你还可以尽量减少引用匹配的问题。  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 变量的范围越窄，它的使用变量越小的恶意代码可以不正确的机会。  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [在 Visual Basic 中的生存期](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [在 Visual Basic 中的访问级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [变量](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [变量声明](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)
