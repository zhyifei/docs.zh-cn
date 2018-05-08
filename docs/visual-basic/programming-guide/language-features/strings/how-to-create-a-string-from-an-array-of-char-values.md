---
title: 如何：从 Char 值的数组创建字符串 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 104b329011d69e10a2926f31ce5d296759a3cce8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>如何：从 Char 值的数组创建字符串 (Visual Basic)
此示例创建从单独的字符的字符串"abcd"。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbalrStrings#61](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-create-a-string-from-an-array-of-char-values_1.vb)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此方法没有任何特殊要求。  
  
 语法`"a"c`，其中单个`c`跟随用引号括起来的单个字符，用于创建一个字符文本。  
  
## <a name="robust-programming"></a>可靠编程  
 Null 字符 (等效于`Chr(0)`) 在字符串中导致意外结果时使用的字符串。 Null 字符将包括替换字符串，但在某些情况下将不会显示在 null 字符后面的字符。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.String>  
 [Char 数据类型](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
