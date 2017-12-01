---
title: "如何：用前导零填充数字"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- numbers [.NET Framework], format strings
ms.assetid: 0b2c2cb5-c580-4891-8d81-cb632f5ec384
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6266807a01e8119ae1410a1ba09cab55c788b4d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pad-a-number-with-leading-zeros"></a>如何：用前导零填充数字
通过结合使用“D”[标准数字格式字符串](../../../docs/standard/base-types/standard-numeric-format-strings.md)和精度说明符，将前导零添加到整数。 你可以通过使用[自定义数字格式字符串](../../../docs/standard/base-types/custom-numeric-format-strings.md)，将前导零添加到整数和浮点数。 本主题介绍如何通过这两种方法用前导零填充数字。  
  
### <a name="to-pad-an-integer-with-leading-zeros-to-a-specific-length"></a>使用前导零将整数填充到特定的长度  
  
1.  确定整数值要显示的最小位数。 在此数字中包括任何前导位。  
  
2.  确定是要将整数显示为十进制值还是十六进制值。  
  
    -   若要将整数显示为十进制值，调用其`ToString(String)`方法，并传递字符串"D*n*"的值作为`format`参数，其中 *n* 表示字符串的最小长度。  
  
    -   若要将整数显示为十六进制值，调用其`ToString(String)`方法并传递字符串"X*n*"的值作为`format`参数，其中 *n* 表示字符串的最小长度。  
  
     你还可以使用格式字符串在方法中，如<xref:System.String.Format%2A>或<xref:System.Console.WriteLine%2A>，使用[复合格式设置](../../../docs/standard/base-types/composite-formatting.md)。  
  
 以下示例使用前导零设置若干整数值的格式，以便格式化数字的总长度至少为八个字符。  
  
 [!code-csharp[Formatting.HowTo.PadNumber#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#1)]
 [!code-vb[Formatting.HowTo.PadNumber#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#1)]  
  
### <a name="to-pad-an-integer-with-a-specific-number-of-leading-zeros"></a>使用特定数目的前导零填充整数  
  
1.  确定希望整数值显示多少个前导零。  
  
2.  确定是要将整数显示为十进制值还是十六进制值。 将整数格式化为十进制值需要使用“D”标准格式说明符；将整数格式化为十六进制值需要使用“X”标准格式说明符。  
  
3.  通过调用整数值的 `ToString("D").Length` 或 `ToString("X").Length` 方法，确定未填充的数字字符串的长度。  
  
4.  将你要在格式化字符串中包括的前导零的数目添加到未填充的数字字符串的长度上。 这定义了填充字符串的总长度。  
  
5.  调用整数值的`ToString(String)`方法，并传递字符串"D*n*"对于十进制字符串和"X*n*"对于十六进制字符串，其中 *n*表示填充的字符串的总长度。 你还可以使用"D*n*"或"X*n*"格式在支持复合格式设置的方法的字符串。  
  
 下面的示例使用五个前导零来填充整数值。  
  
 [!code-csharp[Formatting.HowTo.PadNumber#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#2)]
 [!code-vb[Formatting.HowTo.PadNumber#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#2)]  
  
### <a name="to-pad-a-numeric-value-with-leading-zeros-to-a-specific-length"></a>使用前导零将数值填充到特定的长度  
  
1.  确定数字的字符串表示形式要在小数点的左侧保留的位数。 在此总位数中包括任何前导零。  
  
2.  定义使用零占位符 ("0") 来表示零的最小数目的自定义数字格式字符串。  
  
3.  调用数字的 `ToString(String)` 方法并向其传递自定义格式字符串。 也可以将自定义格式字符串与支持复合格式设置的方法一起使用。  
  
 以下示例使用前导零设置若干数值的格式，以便格式化数字的总长度在小数点的左侧至少为八位。  
  
 [!code-csharp[Formatting.HowTo.PadNumber#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#3)]
 [!code-vb[Formatting.HowTo.PadNumber#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#3)]  
  
### <a name="to-pad-a-numeric-value-with-a-specific-number-of-leading-zeros"></a>使用特定数目的前导零填充数值  
  
1.  确定希望数值具有多少个前导零。  
  
2.  确定未填充数字字符串中小数点左侧的位数。 具体方法为：  
  
    1.  确定数字的字符串表示形式是否包括小数点符号。  
  
    2.  如果它包括小数点符号，则确定小数点左侧的字符数。  
  
         - 或 -  
  
         如果它不包括小数点符号，则确定字符串的长度。  
  
3.  创建一个自定义格式字符串，它为在字符串中出现的每个前导零使用零占位符（"0"），并且使用零占位符或位占位符（"#"）来表示默认字符串中的每一位。  
  
4.  将自定义格式字符串作为对数字的 `ToString(String)` 方法或支持复合格式设置的方法的参数提供。  
  
 下面的示例使用五个前导零来填充两个 <xref:System.Double> 值。  
  
 [!code-csharp[Formatting.HowTo.PadNumber#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.PadNumber/cs/Pad1.cs#4)]
 [!code-vb[Formatting.HowTo.PadNumber#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.PadNumber/vb/Pad1.vb#4)]  
  
## <a name="see-also"></a>另请参阅  
 [Custom Numeric Format Strings](../../../docs/standard/base-types/custom-numeric-format-strings.md)  
 [标准数字格式字符串](../../../docs/standard/base-types/standard-numeric-format-strings.md)  
 [复合格式设置](../../../docs/standard/base-types/composite-formatting.md)
