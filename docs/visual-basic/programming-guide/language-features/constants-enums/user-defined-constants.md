---
title: 用户定义的常量 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: b4a7e2b63b930b98ee082c0104c24f6857b5b35b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="user-defined-constants-visual-basic"></a>用户定义的常量 (Visual Basic)
常量是有意义的名称发生的数字或字符串不会更改。 顾名思义，常量存储在应用程序的执行过程中保持不变的值。 你可以使用由控件或你使用的组件定义的常量或可以创建你自己。 你自己创建的常量被描述为*用户定义*。  
  
 声明具有的常数`Const`语句，用于创建变量的名称使用相同的规则。 如果`Option Strict`是`On`，您必须显式声明的常量的类型。  
  
## <a name="const-statement-usage"></a>Const 语句使用情况  
 A`Const`语句可以表示数学或日期/时间数量：  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 它还可以定义`String`常量：  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 右侧表达式的等号 ( `=` ) 通常是数字或文本字符串，但它还会导致数字或字符串 （尽管该表达式不能包含对函数的调用） 的表达式。 您甚至可以定义根据以前定义的常量的常量：  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a>作用域的用户定义的常量  
 A`Const`语句的作用域是相同的同一位置中声明的变量。 您可以在任何通过以下方式指定作用域：  
  
-   若要创建过程中仅存在一个常数，它在该过程中进行声明。  
  
-   若要创建一个类中的所有过程但不是属于该模块以外的任何代码都可用的常数，请将其声明类的声明部分中。  
  
-   若要创建一个常数，用于所有成员的程序集，但不是属于的程序集外部客户端可用，将使用其声明`Friend`类的声明部分中的关键字。  
  
-   若要创建在整个应用程序都可用的常数，将使用其声明`Public`在声明中的关键字部分类。  
  
 有关详细信息，请参阅[如何： 声明常量](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)。  
  
### <a name="avoiding-circular-references"></a>避免循环引用  
 因为可以根据其他常量定义常量，所以有可能无意中创建*周期*，或两个或多个常量之间的循环引用。 具有两个或多个公共常量，其中每个根据另一个，如以下示例所示定义时发生循环：  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 如果发生循环，Visual Basic 会生成一个编译器错误。  
  
## <a name="see-also"></a>请参阅  
 [Const 语句](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [常量和文本数据类型](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [常量和枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [枚举概述](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [常量概述](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [如何： 声明枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
