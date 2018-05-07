---
title: Visual Basic 中的变量声明
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables [Visual Basic], declarations
- Dim statement [Visual Basic], variable declaration
- declaring variables [Visual Basic]
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime [Visual Basic], variables
- variables [Visual Basic], lifetime
- access levels [Visual Basic], variables
- scope [Visual Basic], declaration statements
- variables [Visual Basic], access level
- local variables [Visual Basic], declarations
- scope [Visual Basic], variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
ms.openlocfilehash: 6890ddfd8b463cd731ab3d8f39565b50a31a1192
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="variable-declaration-in-visual-basic"></a>Visual Basic 中的变量声明
声明一个变量以指定其名称和特性。 变量的声明语句是[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)。 其位置和内容确定变量的特征。  
  
 变量命名规则和注意事项，请参阅[声明元素名称](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)。  
  
## <a name="declaration-levels"></a>声明级别  
  
### <a name="local-and-member-variables"></a>本地和成员变量  
 A*局部变量*是指在过程内声明。 A*成员变量*是 Visual Basic 类型; 的成员在模块级别，在类、 结构或模块，但不是能在该类、 结构或模块的内部任何过程声明。  
  
### <a name="shared-and-instance-variables"></a>共享和实例变量  
 在类或结构中，成员变量的类别取决于共享。 如果它用声明[共享](../../../../visual-basic/language-reference/modifiers/shared.md)关键字，它是*共享的变量*，并且它在类或结构的所有实例间共享的单个副本中存在。  
  
 否则它是*实例变量*，并且为每个实例的类或结构创建的单独副本。 仅适用于类或结构在其中创建的实例的给定的实例变量的副本。 它是独立的类或结构的任何其他实例中的实例变量的副本。  
  
## <a name="declaring-data-type"></a>声明数据类型  
 [作为](../../../../visual-basic/language-reference/statements/as-clause.md)声明语句中的子句允许你定义的数据类型或正在声明的变量的对象类型。 你可以指定任何以下类型的变量：  
  
-   基本数据类型，如`Boolean`， `Long`，或 `Decimal`  
  
-   复合数据类型，如数组或结构  
  
-   对象类型或在你的应用程序或其他应用程序中定义的类  
  
-   A[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]类，如<xref:System.Windows.Forms.Label>或 <xref:System.Windows.Forms.TextBox>  
  
-   接口类型，如<xref:System.IComparable>或 <xref:System.IDisposable>  
  
 您可以声明在一个语句中的多个变量，而无需重复的数据类型。 在下面的语句中，变量`i`， `j`，和`k`声明为类型`Integer`，`l`和`m`作为`Long`，和`x`和`y`作为`Single`:  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 数据类型的详细信息，请参阅[数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)。 对象的详细信息，请参阅[对象和类](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)和[使用组件编程](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)。  
  
## <a name="local-type-inference"></a>局部类型推理  
 *类型推理*用于确定未声明的本地变量的数据类型`As`子句。 编译器推断出从初始化表达式的类型变量的类型。 这使您可以声明变量，而无需显式声明类型。 在下面的示例中，同时`num1`和`num2`强类型为整数。  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]  
  
 如果你想要使用局部类型推理`Option Infer`必须设置为`On`。 有关详细信息，请参阅[本地类型推断](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)和 [Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)。  
  
## <a name="characteristics-of-declared-variables"></a>声明变量的特征  
 *生存期*的变量是的时间段期间它是可供使用。 一般情况下，只要声明 （如过程或类） 的元素将继续存在，将存在的变量。 如果该变量并不需要继续现有其包含元素的生存期结束后，你不需要执行任何特殊操作在声明中。 如果变量需要继续超过其包含元素存在，则可以包括`Static`或`Shared`中的关键字其`Dim`语句。 有关详细信息，请参阅[Visual Basic 中的生存期](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)。  
  
 *作用域*的变量是一组的所有代码都可以引用它而无须限定其名称。 变量的作用域由声明它的位置决定。 位于给定区域的代码可以使用而无需限定其名称在该区域中定义的变量。 有关详细信息，请参阅[在 Visual Basic 中的作用域](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)。  
  
 变量的*访问级别*是有权访问它的代码的范围。 这由访问修饰符 (如[公共](../../../../visual-basic/language-reference/modifiers/public.md)或[私有](../../../../visual-basic/language-reference/modifiers/private.md)) 在中使用`Dim`语句。 有关详细信息，请参阅[访问 Visual Basic 中的级别](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何：创建新变量](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)  
 [如何：将数据移入和移出变量](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)  
 [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)  
 [已声明元素的特性](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [局部类型推理](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Infer 语句](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
