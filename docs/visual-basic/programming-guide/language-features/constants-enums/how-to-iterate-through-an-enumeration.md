---
title: 如何：在 Visual Basic 中循环访问枚举
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 06609d38c805e5f073a2f3a299ecc3aa7cf7be01
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>如何：在 Visual Basic 中循环访问枚举
枚举提供了使用相关常量集以及将常量值与名称相关联的一个便捷方法。 若要循环枚举，你可以将其移到数组使用<xref:System.Enum.GetValues%2A>方法。 你还可以循环访问枚举使用`For...Each`语句中，使用<xref:System.Enum.GetNames%2A>或<xref:System.Enum.GetValues%2A>方法以提取的字符串或数值的值。  
  
### <a name="to-iterate-through-an-enumeration"></a>若要循环访问枚举  
  
-   声明数组并将在枚举转换为其与<xref:System.Enum.GetValues%2A>然后再将数组传递作为你的方法将任何其他变量。 下面的示例显示在枚举每个成员<xref:Microsoft.VisualBasic.FirstDayOfWeek>如该示例循环访问枚举。  
  
     [!code-vb[VbEnumsTask#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-iterate-through-an-enumeration_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [枚举概述](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [如何： 声明枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [何时使用枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [如何：确定与枚举值关联的字符串](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [如何：引用枚举成员](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
