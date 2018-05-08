---
title: 如何：创建固定值变量 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d63c254abe6d12c094e0d1252c9721f668947f09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>如何：创建固定值变量 (Visual Basic)
不会更改其值的变量的概念可能看起来有点矛盾。 在一些情况下不可行常量时，但它可用于具有固定值的变量。 在这种情况下，你可以定义具有的成员变量[ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)关键字。  
  
 不能使用[Const 语句](../../../../visual-basic/language-reference/statements/const-statement.md)声明和分配常量值在以下情况下：  
  
-   `Const`语句不接受你想要使用的数据类型  
  
-   在编译时不知道值  
  
-   无法在编译时计算的常量值  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a>若要在值中创建一个变量，不会更改  
  
1.  在模块级别声明的成员变量[Dim 语句](../../../../visual-basic/language-reference/statements/dim-statement.md)，并且包括[ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md)关键字。  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     你可以指定`ReadOnly`仅在成员变量上。 这意味着你必须定义在模块级别，在任何过程之外的变量。  
  
2.  如果可以计算在编译时的单个语句中的值，使用中的初始化子句`Dim`语句。 请按照[作为](../../../../visual-basic/language-reference/statements/as-clause.md)子句以等号 (`=`) 后, 跟表达式。 请确保编译器可以计算此表达式与一个常数值。  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     你可以将值赋给`ReadOnly`变量一次。 这么做后，没有代码可以更改其值。  
  
     如果你在编译时，不知道值或不能在单个语句中的编译时计算，可以仍将其分配在构造函数中的运行时。 若要执行此操作，您必须声明`ReadOnly`变量在类或结构的级别。 在该类或结构的构造函数，计算变量的固定的值，并在返回从构造函数之前将其分配给变量。  
  
## <a name="see-also"></a>请参阅  
 [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [Const 语句](../../../../visual-basic/language-reference/statements/const-statement.md)
