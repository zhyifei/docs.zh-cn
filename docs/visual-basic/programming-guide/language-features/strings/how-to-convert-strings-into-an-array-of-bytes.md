---
title: 如何：在 Visual Basic 中将字符串转换为字节数组
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: da4a47b955b91f4bb39ecd7832da30d76e75d553
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647948"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a>如何：在 Visual Basic 中将字符串转换为字节数组
本主题演示如何将字符串转换为字节数组。  
  
## <a name="example"></a>示例  
 此示例使用<xref:System.Text.Encoding.GetBytes%2A>方法<xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>编码类将字符串转换为字节数组。  
  
 [!code-vb[VbVbalrStrings#74](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-strings-into-an-array-of-bytes_1.vb)]  
  
 你可以从多个编码选项以将字符串转换为字节数组中进行选择：  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>： 获取 ASCII （7 位） 字符的编码设置。  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>： 获取使用 big endian 字节顺序的 utf-16 格式的编码。  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>： 获取系统的当前 ANSI 代码页的编码。  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>： 获取使用 little-endian 字节顺序的 utf-16 格式的编码。  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>： 获取使用 little-endian 字节顺序的 utf-32 格式的编码。  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>： 获取 utf-7 格式的编码。  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>： 获取 utf-8 格式的编码。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Text.Encoding?displayProperty=nameWithType>  
 <xref:System.Text.Encoding.GetBytes%2A>  
 [如何： 将字节数组转换为 Visual Basic 中的字符串](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)
