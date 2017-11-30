---
title: "类型提升 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3a55c023afe7afe96f862f0b3cbbdb03a15b902
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="type-promotion-visual-basic"></a>类型提升 (Visual Basic)
当你声明一个模块中的编程元素时[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]提升其作用域限制为包含该模块的命名空间。 这称为*类型提升*。  
  
 下面的示例演示了模块的主干定义而且该模块的两个成员。  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 在`projModule`、 编程在模块级别声明的元素将被提升到`projNamespace`。 在前面的示例中，`basicEnum`和`innerClass`提升，但`numberSub`无效，因为不能在模块级别声明。  
  
## <a name="effect-of-type-promotion"></a>类型提升的结果  
 类型提升的效果是限定字符串不需要包含模块名称。 下面的示例调用两个过程在前面的示例。  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 在前面的示例中，第一次调用使用完全限定字符串。 但是，这是不必要由于类型提升。 第二个调用也访问模块成员而不包括`projModule`限定字符串中。  
  
## <a name="defeat-of-type-promotion"></a>类型提升失效  
 如果命名空间已具有相同的名称作为模块成员的成员，使该模块成员的类型提升无效。 下面的示例演示一个枚举和相同的命名空间内的模块的主干定义。  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 在前面的示例中，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]无法提升类`abc`到`thisNameSpace`原因是已经存在具有相同名称在命名空间级别的枚举。 访问`abcSub`，必须使用完全限定字符串`thisNamespace.thisModule.abc.abcSub`。 但是，类`xyz`仍会提升，并且可以访问`xyzSub`与使用较短的限定字符串`thisNamespace.xyz.xyzSub`。  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>分部类型的类型提升的失效  
 如果类或结构在模块内的使用[部分](../../../../visual-basic/language-reference/modifiers/partial.md)关键字，类型提升会自动失效该类或结构，无论该命名空间具有具有相同名称的成员。 该模块中的其他元素都仍可进行类型提升。  
  
 **后果。** 意外的结果，甚至编译器错误，则可能会导致的部分定义的类型提升的失效。 下面的示例演示其中之一是在模块内的类的主干分部定义。  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 在前面的示例中，开发人员可能希望合并的两个分部定义编译器`sampleClass`。 但是，编译器不会考虑的分部定义内的升级`sampleModule`。 因此，它将尝试编译两个单独的且不同类、 命名`sampleClass`但具有不同限定路径。  
  
 仅当其完全限定的路径相同时，编译器才将合并分部定义。  
  
## <a name="recommendations"></a>建议  
 下面的建议提供良好编程习惯。  
  
-   **唯一的名称。** 如果必须对编程元素的命名的完全控制，并总是最好无处不在使用唯一的名称。 相同的名称需要额外的限定，并且可以使代码难以阅读。 此外，它们还可能导致细微的错误和意外的结果。  
  
-   **完全限定。** 当你使用模块和相同的命名空间中的其他元素时，最安全的方法是始终对所有的编程元素中使用完全限定。 如果使某个模块成员的类型提升并不完全限定该成员，你无意中无法访问不同的编程元素。  
  
## <a name="see-also"></a>另请参阅  
 [Module 语句](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [Namespace 语句](../../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [如何：控制变量的范围](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [对已声明元素的引用](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
