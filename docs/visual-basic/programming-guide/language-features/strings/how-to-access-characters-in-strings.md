---
title: 如何：访问字符串中的字符
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], accessing characters
- characters [Visual Basic], accessing in strings
ms.assetid: 02c5206c-ffab-494d-b648-3b2ea358dc34
ms.openlocfilehash: 44a021ed3ce1d10613cf6ab7c959c62feec6046c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352464"
---
# <a name="how-to-access-characters-in-strings-in-visual-basic"></a>如何：在 Visual Basic 中访问字符串中的字符
此示例演示如何使用 <xref:System.String.Chars%2A> 属性访问字符串中指定位置处的字符。  
  
## <a name="example"></a>示例  
 有时，请在字符串中包含有关字符串中的字符和这些字符的位置的数据。 可以将字符串视为字符数组（`Char` 实例）;您可以通过使用 <xref:System.String.Chars%2A> 属性引用该字符的索引来检索特定字符。  
  
 [!code-vb[VbVbalrStrings#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#49)]  
  
 <xref:System.String.Chars%2A> 属性的 `index` 参数是从零开始的。  
  
## <a name="robust-programming"></a>可靠的编程  
 <xref:System.String.Chars%2A> 属性返回指定位置处的字符。 但是，某些 Unicode 字符可以由多个字符表示。 有关如何使用 Unicode 字符的详细信息，请参阅[如何：将字符串转换为字符数组](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)。  
  
 如果 `index` 参数大于或等于字符串的长度，或小于零，则 <xref:System.String.Chars%2A> 属性将引发 <xref:System.IndexOutOfRangeException> 异常  
  
## <a name="see-also"></a>另请参阅

- <xref:System.String.Chars%2A>
- [如何：将字符串转换为字符数组](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-a-string-to-an-array-of-characters.md)
- [在 Visual Basic 中将字符串转换为其他数据类型](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [字符串](../../../../visual-basic/programming-guide/language-features/strings/index.md)
