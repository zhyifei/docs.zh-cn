---
title: 分部方法 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
ms.openlocfilehash: a1708c1d953a60429c1bd87fd858da5c50a3e759
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="partial-methods-visual-basic"></a>分部方法 (Visual Basic)
分部方法允许开发人员将自定义逻辑插入到代码。 通常情况下，代码是类的设计器生成的一部分。 分部方法定义中创建的代码生成器中，分部类和它们通常用于提供的内容已更改的通知。 它们使开发人员在更改的响应中指定自定义行为。  
  
 代码生成器的设计器定义仅方法签名和对方法的一个或多个调用。 如果他们想要自定义生成代码的行为，开发人员然后可以提供的方法的实现。 如果没有实现，则对方法的调用将删除由编译器，导致产生其他性能开销。  
  
## <a name="declaration"></a>声明  
 生成的代码的分部方法的定义标记放置关键字`Partial`签名行的开头。  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 定义必须满足以下条件：  
  
-   该方法必须是`Sub`，而不`Function`。  
  
-   方法的主体必须保留为空。  
  
-   访问修饰符必须`Private`。  
  
## <a name="implementation"></a>实现  
 实现主要由于填写分部方法的正文。 实现通常是在定义中，单独的分部类中，并且由开发人员希望将扩展到生成的代码编写。  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 前面的示例重复中声明的签名完全匹配，但可以变体。 具体而言，其他可以添加修饰符，如`Overloads`或`Overrides`。 只有一个`Overrides`允许使用修饰符。 有关方法修饰符的详细信息，请参阅[Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)。  
  
## <a name="use"></a>使用  
 你调用分部方法，如将调用任何其他`Sub`过程。 如果尚未实施方法，计算自变量并在执行方法的正文。 但请记住，实现分部方法是可选的。 如果未实现方法，它调用具有不起作用，并且无法计算的表达式作为自变量传递给方法。  
  
## <a name="example"></a>示例  
 在文件中名，定义`Product`具有类`Quantity`属性。  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 在文件中名，提供一个实现`QuantityChanged`。  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 最后，在 Main 方法中一个项目中，声明`Product`实例并提供的初始值其`Quantity`属性。  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 应出现一个消息框，显示此消息：  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>请参阅  
 [Sub 语句](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Sub 过程](./sub-procedures.md)  
 [可选参数](./optional-parameters.md)  
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [LINQ to SQL 中的代码生成](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [通过使用分部方法添加业务逻辑](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
