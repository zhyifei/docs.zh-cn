---
title: "bool（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1d52955d64a6c8063e4ea93ceb096459c1c5e984
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="bool-c-reference"></a>bool（C# 参考）
`bool` 关键字是 <xref:System.Boolean?displayProperty=nameWithType> 的别名。 它用于声明变量来存储布尔值 [true](../../../csharp/language-reference/keywords/true.md) 和 [false](../../../csharp/language-reference/keywords/false.md)。  
  
> [!NOTE]
>  如果需要一个也可以有 `null` 值的布尔型变量，请使用 `bool?`。 有关详细信息，请参阅[可以为 Null 的类型](../../../csharp/programming-guide/nullable-types/index.md)。  
  
## <a name="literals"></a>文本  
 可将布尔值赋给 `bool` 变量。 也可以将计算结果为 `bool` 类型的表达式赋给 `bool` 变量。  
  
 [!code-csharp[csrefKeywordsTypes#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_1.cs)]  
  
 `bool` 变量的默认值为 `false`。 `bool?` 变量的默认值为 `null`。  
  
## <a name="conversions"></a>转换  
在 C++ 中，`bool` 类型的值可转换为 `int` 类型的值；也就是说，`false` 相当于零，而 `true` 相当于非零。在 C# 中，不存在 `bool` 类型与其他类型之间的相互转换。例如，下面的 `if` 语句在 C# 中无效：
  
 [!code-csharp[csrefKeywordsTypes#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_2.cs)]  
  
 若要测试 `int` 类型的变量，必须将该变量与一个值（例如零）进行显式比较，如下所示：  
  
 [!code-csharp[csrefKeywordsTypes#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_3.cs)]  
  
## <a name="example"></a>示例  
 在此例中，你通过键盘输入一个字符，然后程序检查输入的字符是否是一个字母。 如果字符是一个字母，则程序检查它是大写还是小写。 执行这些检查使用的是 <xref:System.Char.IsLetter%2A> 和 <xref:System.Char.IsLower%2A>，二者均返回 `bool` 类型：  
  
 [!code-csharp[csrefKeywordsTypes#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/bool_4.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [整数类型表](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [内置类型表](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [隐式数值转换表](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [显式数值转换表](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
