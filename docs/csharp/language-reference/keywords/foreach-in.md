---
title: foreach，in（C# 参考）
ms.date: 10/11/2017
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: f00ae873e615f653d3e760f82b157a57fdaef6ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="foreach-in-c-reference"></a>foreach，in（C# 参考）
`foreach` 语句针对实现 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 或 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 接口的数组或集合中的每个元素重复一组嵌入语句。 `foreach` 语句用于循环访问集合以获取所需信息，但不用于添加或删除源集合中的项，以避免不可预知的副作用。 如果需要添加或删除源集合中的项，请使用 [for](for.md) 循环。
  
 为数组或集合中的每个元素继续执行嵌入的语句。 为集合中的所有元素完成迭代后，控制将传递给 `foreach` 块之后的下一语句。
  
 在 `foreach` 块中的任何点上，可以使用[中断](break.md)关键字中断该循环，或者可以使用[继续](continue.md)关键字单步执行到循环中的下一次迭代。

 `foreach` 循环还可以通过 [goto](goto.md)、[return](return.md) 或 [throw](throw.md) 语句退出。

 有关 `foreach` 关键字和代码示例的详细信息，请参阅下列主题：  

 [对数组使用 foreach](../../programming-guide/arrays/using-foreach-with-arrays.md)  

 [如何：使用 foreach 访问集合类](../../programming-guide/classes-and-structs/how-to-access-a-collection-class-with-foreach.md)  

## <a name="example"></a>示例
 下面的代码演示了三个示例。

> [!TIP]
> 可以修改这些示例来测试语法，尝试与所需用例更相近的不同用法。 按“运行”以运行该代码，然后编辑并再按一次“运行”。

-   显示整数数组内容的典型 `foreach` 循环

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L12-L26)]

-   执行相同操作的 [for](../../../csharp/language-reference/keywords/for.md) 循环

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L31-L46)]

-   维护数组中元素数计数的 `foreach` 循环

[!code-csharp-interactive[csrefKeywordsIteration#4](./codesnippet/CSharp/foreach-in_1.cs#L51-L69)]
 
## <a name="c-language-specification"></a>C# 语言规范
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>请参阅  

[C# 参考](../index.md)

[C# 编程指南](../../programming-guide/index.md)

[C# 关键字](index.md)

[迭代语句](iteration-statements.md)

[for](for.md)
