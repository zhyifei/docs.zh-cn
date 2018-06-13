---
title: 如何：在 Visual Basic 中访问字符串中的字符
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 48507cade639660e6ce36697975d09fb29206c20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649147"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>如何：在 Visual Basic 中访问字符串中的字符
此示例演示如何使用<xref:System.String.Chars%2A>属性来访问位于字符串中的指定位置处的字符。  
  
## <a name="example"></a>示例  
 有时很有用具有了解你的字符串和这些字符在字符串中的位置中的字符的数据。 你可以将字符串的字符的数组视为 (`Char`实例); 你可以通过引用通过该字符的索引检索特定字符<xref:System.String.Chars%2A>属性。  
  
 [!code-vb[VbVbalrStrings#49](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-access-characters-in-strings_1.vb)]  
  
 `index`参数<xref:System.String.Chars%2A>属性是从零开始。  
  
## <a name="robust-programming"></a>可靠编程  
 <xref:System.String.Chars%2A>属性返回位于指定位置处的字符。 但是，可以由多个字符表示某些 Unicode 字符。 有关如何使用 Unicode 字符的详细信息，请参阅[如何： 将字符串转换为字符数组](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)。  
  
 <xref:System.String.Chars%2A>属性将引发<xref:System.IndexOutOfRangeException>异常如果`index`参数为大于或等于的长度的字符串，或如果它小于零  
  
## <a name="see-also"></a>请参阅  
 <xref:System.String.Chars%2A>  
 [如何：将字符串转换为字符数组](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)  
 [在 Visual Basic 中将字符串转换为其他数据类型](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [字符串](../../../../visual-basic/programming-guide/language-features/strings/index.md)
