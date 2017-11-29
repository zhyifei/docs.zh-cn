---
title: "如何：在 Visual Basic 中将字符串转换为字符数组"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59d0da52c8f78b93c76325e6242156c106deeaf1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>如何：在 Visual Basic 中将字符串转换为字符数组
有时很有用具有了解你的字符串和这些字符在字符串中，如当你需要分析字符串的位置中的字符的数据。 此示例演示如何获取数组的字符字符串中通过调用字符串的<xref:System.String.ToCharArray%2A>方法。  
  
## <a name="example"></a>示例  
 此示例演示如何拆分字符串插入`Char`数组，以及如何拆分字符串插入`String`其 Unicode 文本字符的数组。 这一区别的原因是 Unicode 文本字符可以组成两个或多`Char`字符 (例如，代理项对或组合字符序列)。 有关详细信息，请参阅<xref:System.Globalization.TextElementEnumerator>和"Unicode Standard"http://www.unicode.org。  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## <a name="example"></a>示例  
 更难以将字符串拆分为其 Unicode 文本字符，但这是必需的如果你需要有关的可视表示形式的字符串的信息。 此示例使用<xref:System.Globalization.StringInfo.SubstringByTextElements%2A>方法以获取有关构成一个字符串的 Unicode 文本字符的信息。  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.String.Chars%2A>  
 <xref:System.Globalization.StringInfo?displayProperty=nameWithType>  
 [如何：访问字符串中的字符](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)  
 [在 Visual Basic 中将字符串转换为其他数据类型](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)  
 [字符串](../../../../visual-basic/programming-guide/language-features/strings/index.md)
