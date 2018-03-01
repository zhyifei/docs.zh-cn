---
title: "迭代器 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd6c0b1fa422dc4ab659d8c59472e5c098c729bc
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="iterator-visual-basic"></a>迭代器 (Visual Basic)
指定函数或`Get`访问器是迭代器。  
  
## <a name="remarks"></a>备注  
 *迭代器*对集合执行自定义迭代。 迭代器使用[产生](../../../visual-basic/language-reference/statements/yield-statement.md)语句以返回一次的一个集合中的每个元素。 当`Yield`达到语句，保留当前代码中的位置。 下次调用迭代器函数时，将从该位置重新开始执行。  
  
 迭代器可以为函数或作为实现`Get`的属性定义访问器。 `Iterator`修饰符出现在声明中的迭代器函数或`Get`访问器。  
  
 通过使用，从客户端代码调用迭代器[每个...下一条语句](../../../visual-basic/language-reference/statements/for-each-next-statement.md)。  
  
 迭代器函数的返回类型或`Get`访问器可以是<xref:System.Collections.IEnumerable>， <xref:System.Collections.Generic.IEnumerable%601>， <xref:System.Collections.IEnumerator>，或<xref:System.Collections.Generic.IEnumerator%601>。  
  
 迭代器不能含有任何`ByRef`参数。  
  
 不能在事件、实例构造函数、静态构造函数或静态析构函数中使用迭代器。  
  
 迭代器可以是一个匿名函数。 有关更多信息，请参见 [迭代器](../../programming-guide/concepts/iterators.md)。  
  
## <a name="usage"></a>用法  
 `Iterator` 修饰符可用于下面的上下文中：  
  
-   [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property 语句](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>示例  
 下面的示例演示一个迭代器函数。 迭代器函数具有`Yield`语句内[为...下一步](../../../visual-basic/language-reference/statements/for-next-statement.md)循环。 每次迭代[每个](../../../visual-basic/language-reference/statements/for-each-next-statement.md)语句体中的`Main`创建调用`Power`迭代器函数。 对迭代器函数的每个调用将继续到 `Yield` 语句的下一次执行（在 `For…Next` 循环的下一次迭代期间发生）。  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## <a name="example"></a>示例  
 下面的示例演示一个作为迭代器的 `Get` 访问器。 `Iterator`修饰符为属性声明中。  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 有关其他示例，请参阅[迭代器](../../programming-guide/concepts/iterators.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>  
 [迭代器](../../programming-guide/concepts/iterators.md)  
 [Yield 语句](../../../visual-basic/language-reference/statements/yield-statement.md)
