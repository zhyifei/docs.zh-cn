---
title: 从零开始的 vs。在 Visual Basic 中的基于 1 的字符串访问
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: a0a42f72d94adf1c10865374017fa61e833df40f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649095"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a>从零开始的 vs。在 Visual Basic 中的基于 1 的字符串访问
本主题将比较如何 Visual Basic 和[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]提供对字符串中字符的访问。 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]始终提供对在字符串中，字符的从零开始访问，而 Visual Basic 提供从零开始的和基于 1 的访问权限，具体取决于该函数。  
  
## <a name="one-based"></a>基于 1 的  
 对于基于 1 的 Visual Basic 函数的示例，请考虑`Mid`函数。 它采用了参数，该值指示子字符串将开始，从位置 1 开始的字符位置。 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType>方法采用的字符索引处的子字符串将启动的字符串中从位置 0 开始。 因此，如果你有一个字符串"ABCDE"，每个字符进行编号用于 1,2,3,4,5`Mid`函数，但用于 0,1,2,3,4<xref:System.String.Substring%2A?displayProperty=nameWithType>方法。  
  
## <a name="zero-based"></a>从零开始  
 从零开始的 Visual Basic 函数的示例，请考虑`Split`函数。 它将一个字符串拆分，并返回包含子字符串的数组。 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType>方法还将字符串拆分，并返回包含子字符串的数组。 因为`Split`函数和<xref:System.String.Split%2A>方法返回[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]的数组，它们必须是从零开始。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:System.String.Substring%2A>  
 <xref:System.String.Split%2A>  
 [Visual Basic 中的字符串简介](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
