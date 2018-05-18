---
title: 对数组使用 foreach（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: 8511d9dd3b7155d2f6bca229f264071b54ed173b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a>对数组使用 foreach（C# 编程指南）
C# 还提供 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 语句。 该语句提供一种简单、明了的方法来循环访问数组或任何可枚举集合的元素。 `foreach` 语句按数组或集合类型的枚举器返回的顺序处理元素，该顺序通常是从第 0 个元素到最后一个元素。 例如，以下代码创建一个名为 `numbers` 的数组，并使用 `foreach` 语句循环访问该数组：  
  
 [!code-csharp[csProgGuideArrays#28](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_1.cs)]  
  
 借助多维数组，你可以使用相同的方法来循环访问元素，例如：  
  
 [!code-csharp[csProgGuideArrays#29](../../../csharp/programming-guide/arrays/codesnippet/CSharp/using-foreach-with-arrays_2.cs)]  
  
 但对于多维数组，使用嵌套的 [for](../../../csharp/language-reference/keywords/for.md) 循环可以更好地控制数组元素。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Array>  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [数组](../../../csharp/programming-guide/arrays/index.md)  
 [一维数组](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [交错数组](../../../csharp/programming-guide/arrays/jagged-arrays.md)
