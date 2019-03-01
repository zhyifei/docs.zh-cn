---
title: 如何：将十六进制字符串转换为数字 (Visual Basic)
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: c8ef615b6874642fa9ad1b22fe9d7f7745d4ffde
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200996"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>如何：将十六进制字符串转换为数字 (Visual Basic)
此示例将十六进制字符串转换为整数使用<xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>方法。  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>将十六进制字符串转换为数字  
  
-   使用<xref:System.Convert.ToInt32(System.String,System.Int32)>方法将转换为整数的基数为 16 表达的数字。  
  
     第一个参数<xref:System.Convert.ToInt32(System.String,System.Int32)>方法是要转换的字符串。 第二个参数用于描述; 表示的数字的基础十六进制是以 16 为基数。  
  
     [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]  

- 请注意，十六进制字符串有以下限制：

   - 它不能包括`&h`前缀。
   - 它不能包括`_`数字分隔符。

   如果前缀或数字分隔符的存在，调用<xref:System.Convert.ToInt32(System.String,System.Int32)>方法会抛出<xref:System.FormatException>。

## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
