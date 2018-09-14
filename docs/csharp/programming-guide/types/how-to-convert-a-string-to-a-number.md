---
title: 如何：将字符串转换为数字（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#]
- conversions [C#], string to int
- converting strings to int [C#]
- strings [C#], converting to int
ms.assetid: 467b9979-86ee-4afd-b734-30299cda91e3
ms.openlocfilehash: 1f11ba3981b219d3b3a7817afd75fa78f2ccf78a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521748"
---
# <a name="how-to-convert-a-string-to-a-number-c-programming-guide"></a>如何：将字符串转换为数字（C# 编程指南）
可以使用 <xref:System.Convert> 类中的方法或使用各种数值类型（int、long、float 等）中的 `TryParse` 方法将[字符串](../../../csharp/language-reference/keywords/string.md)转换为数字。  
  
 如果你具有字符串，则调用 `TryParse` 方法（例如，[`int.TryParse("11", out number)`](xref:System.Int32.TryParse%2A)）会稍微更加高效且简单。  使用 <xref:System.Convert> 方法对于实现 <xref:System.IConvertible> 的常规对象更有用。  
  
 可以对预期字符串会包含的数值类型（如 <xref:System.Int32?displayProperty=nameWithType> 类型）使用 `Parse` 或 `TryParse` 方法。  <xref:System.Convert.ToUInt32%2A?displayProperty=nameWithType> 方法在内部使用 <xref:System.Int32.Parse%2A>。  如果字符串的格式无效，则 `Parse` 会引发异常，而 `TryParse` 会返回 [false](../../../csharp/language-reference/keywords/false.md)。  
  
## <a name="example"></a>示例  
 `Parse` 和 `TryParse` 方法会忽略字符串开头和末尾的空白符，但其他所有字符都必须是组成合适数值类型（int、long、ulong、float、decimal 等）的字符。  如果组成数字的字符中有任何空白符，都会导致错误出现。  例如，可以使用 `decimal.TryParse` 分析“10”、“10.3”、“  10  ”，但不能使用此方法分析从“10X”、“1 0”（注意空格）、“10 .3”（注意空格）、“10e1”（`float.TryParse` 在此处适用）等中分析出 10。  
  
 下面的示例演示了对 `Parse` 和 `TryParse` 的成功调用和不成功的调用。  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#25](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_2.cs)]  
[!code-csharp[csProgGuideTypes#26](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_3.cs)]  
[!code-csharp[csProgGuideTypes#27](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_4.cs)]  
[!code-csharp[csProgGuideTypes#28](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_5.cs)]  
[!code-csharp[csProgGuideTypes#100](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_6.cs)]  
  
## <a name="example"></a>示例  
 下表列出了 <xref:System.Convert> 类中可使用的一些方法。  
  
|数值类型|方法|  
|------------------|------------|  
|`decimal`|<xref:System.Convert.ToDecimal%28System.String%29>|  
|`float`|<xref:System.Convert.ToSingle%28System.String%29>|  
|`double`|<xref:System.Convert.ToDouble%28System.String%29>|  
|`short`|<xref:System.Convert.ToInt16%28System.String%29>|  
|`int`|<xref:System.Convert.ToInt32%28System.String%29>|  
|`long`|<xref:System.Convert.ToInt64%28System.String%29>|  
|`ushort`|<xref:System.Convert.ToUInt16%28System.String%29>|  
|`uint`|<xref:System.Convert.ToUInt32%28System.String%29>|  
|`ulong`|<xref:System.Convert.ToUInt64%28System.String%29>|  
  
 此示例调用 <xref:System.Convert.ToInt32%28System.String%29?displayProperty=nameWithType> 方法将输入的 [string](../../../csharp/language-reference/keywords/string.md) 转换为 [int](../../../csharp/language-reference/keywords/int.md)。 代码将捕获此方法可能引发的最常见的两个异常：<xref:System.FormatException> 和 <xref:System.OverflowException>。 如果该数字可以递增而不溢出整数存储位置，则程序使结果加上 1 并打印输出。  
  
 [!code-csharp[csProgGuideTypes#5555](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_1.cs)]  
[!code-csharp[csProgGuideTypes#24](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-string-to-a-number_7.cs)]  
  
## <a name="see-also"></a>请参阅

- [类型](../../../csharp/programming-guide/types/index.md)  
- [如何：确定字符串是否表示数值](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)  
- [.NET Framework 4 格式设置实用工具](https://code.msdn.microsoft.com/NET-Framework-4-Formatting-9c4dae8d)
