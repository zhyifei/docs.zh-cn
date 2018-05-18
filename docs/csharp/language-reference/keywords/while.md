---
title: while（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: 23c5ca3bb7dc401a894a6c3918fbaec9a9306153
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="while-c-reference"></a>while（C# 参考）
`while` 语句执行一条语句或一个语句块，直到指定的表达式的计算结果为 `false` 为止。  
  
## <a name="example"></a>示例  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a>示例  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a>示例  
 因为 `while` 表达式的测试在每次执行循环之前开始，所以 `while` 循环执行零次或多次。 这不同于 [do](../../../csharp/language-reference/keywords/do.md) 循环，该循环执行一次或多次。  
  
 [break](../../../csharp/language-reference/keywords/break.md)、[goto](../../../csharp/language-reference/keywords/goto.md)、[return](../../../csharp/language-reference/keywords/return.md) 或 [throw](../../../csharp/language-reference/keywords/throw.md) 语句将控制转移到循环外时，`while` 循环可能终止。 若要将控制传递到下一个迭代，而不退出循环，则使用 [continue](../../../csharp/language-reference/keywords/continue.md) 语句。 注意前面三个示例的输出差异，具体取决于 `int n` 递增的位置。 在以下示例中，未生成任何输出。  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [While 语句 (C++)](/cpp/cpp/while-statement-cpp)  
 [迭代语句](../../../csharp/language-reference/keywords/iteration-statements.md)
