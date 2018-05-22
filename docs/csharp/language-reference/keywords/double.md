---
title: double（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- double
- double_CSharpKeyword
helpviewer_keywords:
- double data type [C#]
ms.assetid: 0980e11b-6004-4102-abcf-cfc280fc6991
ms.openlocfilehash: 3683b51dfd0ef653ab8bfff6705b96a37e21a10a
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
---
# <a name="double-c-reference"></a>double（C# 参考）
`double` 关键字表示存储 64 位浮点值的简单类型。 下表显示了 `double` 类型的精度和大致范围。  
  
|类型|大致范围|精度|.NET Framework 类型|  
|----------|-----------------------|---------------|-------------------------|  
|`double`|±5.0 × 10<sup>−324</sup> 到 ±1.7 × 10<sup>308</sup>|15-16 位|<xref:System.Double?displayProperty=nameWithType>|  
  
## <a name="literals"></a>文本  
 默认情况下，赋值运算符右侧的实数被视为 `double`。 但是，如果希望整数被视为 `double`，可使用后缀 d 或 D，例如：  
  
```csharp  
double x = 3D;  
```  
  
## <a name="conversions"></a>转换  
 可以在表达式中混合使用数值整型和浮点类型。 在这种情况下，整数类型将转换为浮点类型。 根据以下规则对表达式求值：  
  
-   如果浮点类型之一是 `double`，则该表达式的计算结果为 `double` 类型，在关系表达式或布尔表达式中为 [bool](../../../csharp/language-reference/keywords/bool.md) 类型。  
  
-   如果表达式中无 `double` 类型，则该表达式的计算结果为 [float](../../../csharp/language-reference/keywords/float.md) 类型，在关系表达式或布尔表达式中为 [bool](../../../csharp/language-reference/keywords/bool.md) 类型。  
  
 浮点表达式可以包含下列值集：  
  
-   正零和负零。  
  
-   正无穷大和负无穷大。  
  
-   非数字值 (NaN)。  
  
-   一组有限的非零值。  
  
 有关这些值的详细信息，请参阅 [IEEE](http://www.ieee.org) 网站中提供的二进制浮点算术的 IEEE 标准。  
  
## <a name="example"></a>示例  
 在下面的示例中，将 [int](../../../csharp/language-reference/keywords/int.md)、[short](../../../csharp/language-reference/keywords/short.md)、[float](../../../csharp/language-reference/keywords/float.md) 和 `double` 相加可得出 `double` 结果。  
  
 [!code-csharp[csrefKeywordsTypes#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/double_1.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [默认值表](../../../csharp/language-reference/keywords/default-values-table.md)  
 [内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [浮点型表](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
 [隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [显式数值转换表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
