---
title: 如何：循环访问枚举
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: 6e8fd6760565a73d9d3b3d1d02fc872992eea354
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354027"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a>如何：在 Visual Basic 中循环访问枚举
枚举提供了使用相关常量集以及将常量值与名称相关联的一个便捷方法。 若要循环访问枚举，可以使用 <xref:System.Enum.GetValues%2A> 方法将其移到数组中。 还可以使用 `For...Each` 语句来循环访问枚举，方法是使用 <xref:System.Enum.GetNames%2A> 或 <xref:System.Enum.GetValues%2A> 方法提取字符串或数字值。  
  
### <a name="to-iterate-through-an-enumeration"></a>循环访问枚举  
  
- 声明数组，并使用 <xref:System.Enum.GetValues%2A> 方法将枚举转换为它，然后再传递数组，就像传递任何其他变量一样。 下面的示例在循环访问枚举时显示枚举 <xref:Microsoft.VisualBasic.FirstDayOfWeek> 的每个成员。  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a>另请参阅

- [枚举概述](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [如何：声明枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [何时使用枚举](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
- [如何：确定与枚举值关联的字符串](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [如何：引用枚举成员](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)
- [枚举和名称限定](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [数组](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
