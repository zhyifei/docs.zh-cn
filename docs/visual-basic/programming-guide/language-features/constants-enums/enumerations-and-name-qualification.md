---
title: 枚举和名称限定 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- Imports statement [Visual Basic], namespace declarations
- declaring namespaces [Visual Basic], enumerations
- name collisions
- ambiguous names [Visual Basic], enumerations
- enumerations [Visual Basic], name qualification
- names [Visual Basic], avoiding conflicts
- namespaces [Visual Basic], declaring
- naming conflicts, enumerations
- naming conflicts, qualifying names
- declaring enumerations
- references [Visual Basic], enumeration members
- naming conventions [Visual Basic], naming conflicts
- declarations [Visual Basic], namespaces
ms.assetid: 08ba2738-df52-4140-bc55-f57c871c9b73
ms.openlocfilehash: eb1f5653d968e81168833cd57813219e8f049b70
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648575"
---
# <a name="enumerations-and-name-qualification-visual-basic"></a>枚举和名称限定 (Visual Basic)
通常情况下，当引用时枚举的成员，你必须限定枚举名称的成员名称。 例如，若要引用`Sunday`的成员你`Days`枚举，你将使用以下语法：  
  
 [!code-vb[VbEnumsTask#18](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_1.vb)]  
  
## <a name="using-the-imports-statement"></a>使用导入语句  
 你可以避免使用完全限定的名加上`Imports`语句与你的代码，如以下示例所示的命名空间声明部分：  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 `Imports`语句导入命名空间名称，从被引用的项目和程序集和与语句出现在其中的模块相同的项目。 此语句添加后，您可以参考你的枚举成员，而无需限定，如以下示例所示：  
  
 [!code-vb[VbEnumsTask#24](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_3.vb)]  
  
 通过几组相关常数在枚举中的组织，你可以使用相同的常数名在不同上下文中。 例如，可以使用相同的名称中对工作日常数`Days`和`WorkDays`枚举。 如果你使用`Imports`与枚举一起语句，必须注意以避免不明确的引用。 请看下面的示例：  
  
 [!code-vb[VbEnumsTask#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_2.vb)]  
  
 [!code-vb[VbEnumsTask#25](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_4.vb)]  
  
 假设`Monday`是的成员`Days`枚举和`Workdays`枚举，此代码生成一个编译器错误。 若要在单个常数引用时，请避免不明确的引用，限定其枚举常量的名称。 下面的代码是指`Saturday`中的常量`Days`和`WorkDays`枚举。  
  
 [!code-vb[VbEnumsTask#32](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/enumerations-and-name-qualification_5.vb)]  
  
## <a name="see-also"></a>请参阅  
 [常量和枚举](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [如何： 声明枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [如何：引用枚举成员](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [如何： 循环访问 Visual Basic 中的一个枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [如何：确定与枚举值关联的字符串](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [何时使用枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [常量和文本数据类型](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [Enum 语句](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Imports 语句（.NET 命名空间和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [数据类型](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
