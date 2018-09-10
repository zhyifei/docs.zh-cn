---
title: 作为对象的数组（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: f1abe10839c30d48f56ac6044d75d290a59b4cce
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505554"
---
# <a name="arrays-as-objects-c-programming-guide"></a>作为对象的数组（C# 编程指南）

在 C# 中，数组实际上是对象，而不只是如在 C 和 C++ 中的连续内存的可寻址区域。 <xref:System.Array> 是所有数组类型的抽象基类型。 可以使用 <xref:System.Array> 具有的属性和其他类成员。 例如，使用 <xref:System.Array.Length%2A> 属性来获取数组的长度。 以下代码可将 `numbers` 数组的长度 `5` 分配给名为 `lengthOfNumbers` 的变量：  
  
 [!code-csharp[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]  
  
 <xref:System.Array> 类可提供多种其他有用的方法和属性，用于对数组进行排序、搜索和复制。  
  
## <a name="example"></a>示例

 此示例使用 <xref:System.Array.Rank%2A> 属性显示数组的维数。  
  
 [!code-csharp[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [数组](../../../csharp/programming-guide/arrays/index.md)  
- [一维数组](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
- [交错数组](../../../csharp/programming-guide/arrays/jagged-arrays.md)
