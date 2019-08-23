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
ms.openlocfilehash: 36cf71529b1f81c27881638d788117222c37171d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955884"
---
# <a name="new-operator-visual-basic"></a>New 运算符 (Visual Basic)
引入一个`New`子句, 用于创建新的对象实例, 指定类型参数上的构造函数约束, 或将`Sub`过程标识为类构造函数。  
  
## <a name="remarks"></a>备注  
 在声明或赋值语句中, `New`子句必须指定一个已定义的类, 可从中创建实例。 这意味着, 该类必须公开调用代码可以访问的一个或多个构造函数。  
  
 可在声明语句`New`或赋值语句中使用子句。 当语句运行时, 它将调用指定类的适当构造函数, 同时传递您提供的任何自变量。 下面的示例通过创建一个`Customer`具有两个构造函数的类的实例进行演示, 其中一个构造函数不采用任何参数, 另一个采用字符串参数。  
  
 [!code-vb[VbVbalrKeywords#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#11)]  
  
 由于数组是类, `New`因此可以创建新的数组实例, 如下面的示例中所示。  
  
 [!code-vb[VbVbalrKeywords#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class6.vb#12)]  
  
 如果没有足够的内存来创建新的<xref:System.OutOfMemoryException>实例, 则公共语言运行时 (CLR) 会引发错误。  
  
> [!NOTE]
> `New`关键字还用于类型参数列表, 用于指定提供的类型必须公开可访问的无参数构造函数。 有关类型参数和约束的详细信息, 请参阅[Type List](../../../visual-basic/language-reference/statements/type-list.md)。  
  
 若要为类创建构造函数过程, 请将`Sub`过程的名称设置`New`为关键字。 有关详细信息, 请[参阅对象生存期:如何创建和销毁](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)对象。  
  
 `New` 关键字可用于以下上下文中：  
  
 [Dim 语句](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>请参阅

- <xref:System.OutOfMemoryException>
- [关键字](../../../visual-basic/language-reference/keywords/index.md)
- [类型列表](../../../visual-basic/language-reference/statements/type-list.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [对象生存期:如何创建和销毁对象](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
