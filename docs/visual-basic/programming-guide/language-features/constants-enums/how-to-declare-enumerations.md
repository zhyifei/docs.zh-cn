---
title: 如何：声明枚举 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: e2dbdbbf6bf7fe3e4b71cbe7edc7a19b18f96ef2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650798"
---
# <a name="how-to-declare-enumerations-visual-basic"></a>如何：声明枚举 (Visual Basic)
创建一个包含枚举`Enum`声明部分中的类或模块的语句。 不能声明枚举的方法内。 若要指定适当的访问级别，使用`Private`， `Protected`， `Friend`，或`Public`。  
  
 `Enum`类型都有名称、 一个基础类型和一组字段，各表示常量。 该名称必须是有效的 Visual Basic.NET 限定符。 基础类型必须是整数类型之一-`Byte`， `Short`，`Long`或`Integer`。 默认为 `Integer`。 枚举始终强类型和不可互换与整数类型。  
  
 枚举不能具有浮点值。 如果枚举分配具有的浮点值`Option Strict On`，将导致编译器错误。 如果`Option Strict`是`Off`，值自动转换为`Enum`类型。  
  
 有关如何使用和名称，信息`Imports`语句使名称限定不必要的请参阅[枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)。  
  
### <a name="to-declare-an-enumeration"></a>若要声明枚举  
  
1.  编写包含代码访问级别，声明`Enum`关键字和有效的名称，如下面的示例，其中每个声明不同`Enum`。  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  枚举中定义常量。 默认情况下，枚举中的第一个常数初始化为`0`，而后续常量将初始化为一个多个前面的常数的值。 例如，下面的枚举， `Days`，包含名为常量`Sunday`值`0`，名为常量`Monday`值`1`，名为常量`Tuesday`的值与`2`，依次类推。  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  显式可以通过使用赋值语句将值分配给枚举中的常量。 你可以分配任何整数值，包括负数。 例如，你可能想常量值小于零表示错误条件。 在下面的枚举常量`Invalid`显式分配的值`–1`，和常量`Sunday`分配的值`0`。 因为它是在枚举中，第一个常量`Saturday`还初始化为值`0`。 值`Monday`是`1`(一的值大于`Sunday`); 的值`Tuesday`是`2`，依次类推。  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a>若要声明为显式类型枚举  
  
-   通过使用指定的枚举类型`As`子句，如下面的示例中所示。  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a>请参阅  
 [枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [如何：引用枚举成员](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [如何： 循环访问 Visual Basic 中的一个枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [如何：确定与枚举值关联的字符串](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [何时使用枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [常量概述](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [常量和文本数据类型](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)
