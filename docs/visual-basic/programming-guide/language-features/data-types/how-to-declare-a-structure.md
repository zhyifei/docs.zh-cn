---
title: 如何：声明结构 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: 6128addd60609bfc88a1409648fb320bc7089974
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-a-structure-visual-basic"></a>如何：声明结构 (Visual Basic)
开始具有的结构声明[Structure 语句](../../../../visual-basic/language-reference/statements/structure-statement.md)，并与结尾`End``Structure`语句。 这两个语句之间必须声明至少一个*元素*。 元素可以是任何数据类型，但至少一个必须为非共享的变量或非共享、 非自定义事件。  
  
 无法初始化任何结构声明中的结构元素。 在声明为结构类型的变量时，你将值分配给元素变量通过访问它们。  
  
 结构和类之间的差异的讨论，请参阅[结构和类](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)。  
  
 出于演示目的，请考虑你想要跟踪的员工的名称、 电话分机和薪金的情况。 一个结构，可在单个变量执行此操作。  
  
### <a name="to-declare-a-structure"></a>若要声明结构  
  
1.  创建的开始和结束结构的语句。  
  
     你可以指定结构使用的访问级别[公共](../../../../visual-basic/language-reference/modifiers/public.md)，[受保护](../../../../visual-basic/language-reference/modifiers/protected.md)，[友元](../../../../visual-basic/language-reference/modifiers/friend.md)，或[私有](../../../../visual-basic/language-reference/modifiers/private.md)关键字，也可以让它默认为`Public`。  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  将元素添加到结构的正文。  
  
     结构必须具有至少一个元素。 必须声明的每个元素，并为其指定访问级别。 如果你使用[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)不含任何关键字，可访问性默认为`Public`。  
  
    ```  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     `salary`字段在前面的示例是`Private`，这意味着它是外部表的结构，甚至从包含类不能访问。 但是，`giveRaise`过程是`Public`，因此它可以从调用，在结构之外。 同样，你可以将提升`salaryReviewTime`从在结构之外的事件。  
  
     除了变量，还`Sub`过程和事件，你还可以定义常量、`Function`过程和结构中的属性。 你可以指定最多一个属性作为*默认属性*、 提供它采用至少一个自变量。 你可以处理的事件[共享](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub`过程。 有关详细信息，请参阅[如何： 声明和调用默认属性在 Visual Basic 中](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)。  
  
## <a name="see-also"></a>请参阅  
 [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [基本数据类型](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [复合数据类型](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [值类型和引用类型](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [结构](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [数据类型疑难解答](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [结构变量](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 [结构和其他编程元素](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [结构和类](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [用户定义的数据类型](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
