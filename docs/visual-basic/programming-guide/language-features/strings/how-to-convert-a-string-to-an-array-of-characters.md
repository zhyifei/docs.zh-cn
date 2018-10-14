---
title: 如何：在 Visual Basic 中将字符串转换为字符数组
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: cc12b70cddcb93a72b4421a8ddd93542ef84f55b
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2018
ms.locfileid: "48845185"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>如何：在 Visual Basic 中将字符串转换为字符数组
有时是有关你的字符串和这些字符在字符串中，例如当需要分析字符串的位置中的字符的数据很有用。 此示例演示如何获取字符数组的字符串中通过调用字符串的<xref:System.String.ToCharArray%2A>方法。  
  
## <a name="example"></a>示例  
 此示例演示如何将字符串拆分`Char`数组，以及如何拆分字符串`String`其 Unicode 文本字符的数组。 这一区别的原因是 Unicode 文本字符可以由两个或多个组成`Char`字符 (例如，代理项对或组合字符序列)。 有关详细信息，请参阅<xref:System.Globalization.TextElementEnumerator>并[Unicode 标准](https://www.unicode.org/standard/standard.html)。  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## <a name="example"></a>示例  
 更难以将字符串拆分为其 Unicode 文本字符，但这是必需的如果需要有关字符串的可视表示形式的信息。 此示例使用<xref:System.Globalization.StringInfo.SubstringByTextElements%2A>方法以获取有关构成了一个字符串的 Unicode 文本字符的信息。  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.String.Chars%2A>  
 <xref:System.Globalization.StringInfo?displayProperty=nameWithType>  
 [如何：访问字符串中的字符](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)  
 [在 Visual Basic 中将字符串转换为其他数据类型](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [字符串](../../../../visual-basic/programming-guide/language-features/strings/index.md)
