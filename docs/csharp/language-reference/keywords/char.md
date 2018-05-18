---
title: char（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 67efc4b9600d7d722ebbef83819e143506a93c26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="char-c-reference"></a>char（C# 参考）
`char` 关键字用于声明 <xref:System.Char?displayProperty=nameWithType> 结构的实例，.NET Framework 使用该结构来表示 Unicode 字符。 `Char` 对象的值为 16 位的数字（序号）值。  
  
 Unicode 字符用于表示世界各地大多数的书面语言。  
  
|类型|范围|大小|.NET Framework 类型|  
|----------|-----------|----------|-------------------------|  
|`char`|U+0000 到 U+FFFF|Unicode 16 位字符|<xref:System.Char?displayProperty=nameWithType>|  
  
## <a name="literals"></a>文本  
 `char` 类型的常量可以编写为字符文本、十六进制转义序列或 Unicode 表示形式。 还可转换整型字符代码。 在下面的示例中，使用相同的字符 `X` 对四个 `char` 变量进行初始化：  
  
 [!code-csharp[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]  
  
## <a name="conversions"></a>转换  
 `char` 可隐式转换为 [ushort](../../../csharp/language-reference/keywords/ushort.md)、[int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md)、[ulong](../../../csharp/language-reference/keywords/ulong.md)、[float](../../../csharp/language-reference/keywords/float.md)、[double](../../../csharp/language-reference/keywords/double.md) 或 [decimal](../../../csharp/language-reference/keywords/decimal.md)。 但是无法将其他类型隐式转换为 `char` 类型。  
  
 <xref:System.Char?displayProperty=nameWithType> 类型提供多种适用于 `char` 值的静态方法。  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Char>  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [整型表](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [显式数值转换表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [可以为 null 的类型](../../../csharp/programming-guide/nullable-types/index.md)  
 [字符串](../../../csharp/programming-guide/strings/index.md)
