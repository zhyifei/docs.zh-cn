---
title: "如何：将十六进制字符串转换为数字 (Visual Basic)"
ms.custom: 
ms.date: 01/31/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
author: petrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: c35ac615e3f87710f934a1cf66e6546625298bd0
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>如何：将十六进制字符串转换为数字 (Visual Basic)
此示例将十六进制字符串转换为整数使用<xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>方法。  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>将十六进制字符串转换为数字  
  
-   使用<xref:System.Convert.ToInt32(System.String,System.Int32)>方法将转换为整数的基数为 16 表达的数字。  
  
     第一个参数<xref:System.Convert.ToInt32(System.String,System.Int32)>方法是要转换的字符串。 第二个参数描述中; 表示的数字哪些基十六进制是基数为 16。  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- 请注意的十六进制字符串具有以下限制：

   - 它不能包括`&h`前缀。
   - 它不能包括`_`数字分隔符。

   如果前缀或数字分隔符的存在，对的调用<xref:System.Convert.ToInt32(System.String,System.Int32)>方法抛出异常<xref:System.FormatException>。

## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
