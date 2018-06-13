---
title: 如何：在字符串内搜索 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], finding
- strings [Visual Basic], searching
- examples [Visual Basic], strings
ms.assetid: ae4c79e0-08ea-489f-bdb2-5eb6d355f284
ms.openlocfilehash: 08a005f2927a76c9b29c1ff0092ea8282188b2b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647678"
---
# <a name="how-to-search-within-a-string-visual-basic"></a>如何：在字符串内搜索 (Visual Basic)
此示例调用<xref:System.String.IndexOf%2A>方法<xref:System.String>要报告的子字符串的第一个匹配项的索引对象。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbalrStrings#71](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-search-within-a-string_1.vb)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   `Imports`语句指定<xref:System>命名空间。 有关详细信息，请参阅 [Imports 语句（.NET 命名空间和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)。  
  
## <a name="robust-programming"></a>可靠编程  
 <xref:System.String.IndexOf%2A>方法将报告的子字符串的第一个匹配项的第一个字符的位置。 索引是基于 0 的这意味着字符串的第一个字符的索引为 0。  
  
 如果<xref:System.String.IndexOf%2A>未找到子字符串，它将返回-1。  
  
 <xref:System.String.IndexOf%2A>方法区分大小写，并使用当前区域性。  
  
 为了优化错误控制，你可能想要在使用字符串搜索`Try`块[重试...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)构造。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.String.IndexOf%2A>  
 [Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Visual Basic 中的字符串简介](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [字符串](../../../../visual-basic/programming-guide/language-features/strings/index.md)
