---
title: New 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 0fe511b2c16681d7bab7eeda7c121fcbbaa2f5dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="new-operator-visual-basic"></a>New 运算符 (Visual Basic)
引入了`New`子句创建一个新的对象实例，指定类型参数的构造函数约束或标识`Sub`作为类构造函数的过程。  
  
## <a name="remarks"></a>备注  
 声明或赋值语句中`New`子句必须指定可从中创建实例定义的类。 这意味着类必须公开一个或多个构造函数调用的代码可访问。  
  
 你可以使用`New`声明语句或赋值语句中的子句。 当该语句在运行时，它将调用适当的构造函数指定的类，并传递你提供任何参数。 下面的示例演示这通过创建的实例`Customer`具有两个构造函数的类、 一个不带任何参数，另一个采用字符串参数。  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 由于数组是类，`New`可以创建新的数组实例，如下面的示例中所示。  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 公共语言运行时 (CLR) 引发<xref:System.OutOfMemoryException>错误是否存在内存不足，无法创建新实例。  
  
> [!NOTE]
>  `New`关键字还用于在类型参数列表中指定所提供的类型必须公开可访问的无参数构造函数。 有关类型参数和约束的详细信息，请参阅[类型列表](../../../visual-basic/language-reference/statements/type-list.md)。  
  
 若要创建一个类的构造函数过程，设置的名称`Sub`过程`New`关键字。 有关详细信息，请参阅[对象生存期： 对象的创建和破坏的方式](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)。  
  
 `New` 关键字可用于以下上下文中：  
  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>请参阅  
 <xref:System.OutOfMemoryException>  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)  
 [类型列表](../../../visual-basic/language-reference/statements/type-list.md)  
 [Visual Basic 中的泛型类型](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [对象生存期：如何创建和销毁对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
