---
title: 如何：从 Char 值的数组创建字符串
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 03138a851afc55f735cc66edeb345817428a0452
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344390"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a>如何：从 Char 值的数组创建字符串 (Visual Basic)
此示例从单个字符创建字符串 "abcd"。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此方法没有特殊要求。  
  
 语法 `"a"c`，其中单个 `c` 跟在引号中的单个字符，用于创建字符文本。  
  
## <a name="robust-programming"></a>可靠的编程  
 字符串中的 Null 字符（等效于 `Chr(0)`）在使用字符串时导致意外的结果。 字符串中将包含 null 字符，但在某些情况下，将不会显示空字符后面的字符。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.String>
- [Char 数据类型](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [数据类型](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
