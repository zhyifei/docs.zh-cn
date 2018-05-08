---
title: 名称&#39;&lt;名称&gt;&#39;未声明
ms.date: 07/20/2015
f1_keywords:
- bc30451
- vbc30451
helpviewer_keywords:
- BC30451
ms.assetid: 765f099b-e21e-47c6-a906-a065444e56b3
ms.openlocfilehash: e17017e84720a2581abc5115338352aacc02d473
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="name-39ltnamegt39-is-not-declared"></a>名称&#39;&lt;名称&gt;&#39;未声明
语句引用一个编程元素，但编译器找不到具有相同名称的元素。  
  
 **错误 ID:** BC30451  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  检查引用语句中名称的拼写。 Visual Basic 不区分大小写，但拼写中的任何其他变体都会被视为完全不同的名称。 请注意，下划线 (`_`) 是名称的一部分，因此也是拼写的一部分。  
  
2.  检查你具有成员访问运算符 (`.`) 对象和其成员之间。 例如，如果你拥有名为 <xref:System.Windows.Forms.TextBox> 的 `TextBox1`控件，则要键入 <xref:System.Windows.Forms.TextBoxBase.Text%2A> 才可访问其 `TextBox1.Text`。 如果你转而键入 `TextBox1Text`，则会创建不同的名称。  
  
3.  如果拼写正确，以及任何对象成员访问的语法正确，请验证已声明元素。 有关详细信息，请参阅[声明元素](../../../visual-basic/programming-guide/language-features/declared-elements/index.md)。  
  
4.  如果已声明的编程元素，请检查它是否在作用域。 如果引用语句位于声明编程元素的区域外，你可能需要限定元素名称。 有关详细信息，请参阅[在 Visual Basic 中的作用域](../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)。  
  
## <a name="see-also"></a>请参阅  
 [声明和常量摘要](../../../visual-basic/language-reference/keywords/declarations-and-constants-summary.md)  
 [Visual Basic 命名约定](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [已声明的元素名称](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [对已声明元素的引用](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
