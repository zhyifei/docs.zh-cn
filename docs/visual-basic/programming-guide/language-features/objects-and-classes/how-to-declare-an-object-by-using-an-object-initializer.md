---
title: "如何：使用对象初始值设定项声明对象 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 87c818765cbeac7a3080ee666d464052493e5bde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>如何：使用对象初始值设定项声明对象 (Visual Basic)
对象初始值设定项，可以声明并实例化单个语句中的类的实例。 此外，可以但不调用参数化构造函数一次初始化实例的一个或多个的成员。  
  
 当使用对象初始值设定项来创建命名类型的实例时，被调用跟你指定的顺序中的指定成员的初始化的类的默认构造函数。  
  
 下面的过程演示如何创建的实例`Student`三个不同的方式的类。 此类具有名字、 姓氏和类年属性，以及其他。 每三个声明创建的新实例`Student`，与属性`First`设置为"Michael"，属性`Last`设置为"Tucker"，并且所有其他成员设置为其默认值。 在过程中每个声明的结果等效于以下示例中，这个过程未使用的对象初始值设定项。  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_1.vb)]  
  
 实现的`Student`类，请参阅[如何： 创建项列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)。 您可以从该主题可以将设置类创建的列表中复制代码`Student`要使用的对象。  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>若要使用对象初始值设定项中创建命名类的对象  
  
1.  就像你计划使用构造函数，请开始声明。  
  
     `Dim student1 As New Student`  
  
2.  键入关键字`With`后, 跟一个大括号内的初始化列表。  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  在初始化列表中，包括每个你想要初始化，并为其分配的初始值的属性。 属性的名称以句点开头。  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_2.vb)]  
  
     你可以初始化类的一个或多个成员。  
  
4.  或者，你可以声明类的新实例，然后将值分配给它。 首先，声明的实例`Student`:  
  
     `Dim student2 As Student`  
  
5.  开始创建的实例`Student`以正常方式。  
  
     `Dim student2 As Student = New Student`  
  
6.  类型`With`，然后对象初始值设定项的新实例的一个或多个成员进行初始化。  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_3.vb)]  
  
7.  你可以通过省略简化上一步中的定义`As Student`。 如果执行此操作时，编译器确定`student3`是的一个实例`Student`使用局部类型推理。  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_4.vb)]  
  
     有关详细信息，请参阅[本地类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)。  
  
## <a name="see-also"></a>另请参阅  
 [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [如何：创建项列表](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)  
 [对象初始值设定项：命名类型和匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [匿名类型](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
