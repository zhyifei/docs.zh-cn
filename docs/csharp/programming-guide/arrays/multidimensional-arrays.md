---
title: 多维数组（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], multidimensional
- multidimensional arrays [C#]
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
ms.openlocfilehash: a1d7a0a014c330682316e869f6727082fa3b31ef
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45668049"
---
# <a name="multidimensional-arrays-c-programming-guide"></a>多维数组（C# 编程指南）

数组可具有多个维度。 例如，以下声明创建一个具有四行两列的二维数组。  
  
 [!code-csharp[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]  
  
 以下声明创建一个具有三个维度（4、2 和 3）的数组。  
  
 [!code-csharp[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]  
  
## <a name="array-initialization"></a>数组初始化

 声明后即可初始化数组，如以下示例所示。  
  
 [!code-csharp[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]  
  
 还可在不指定秩的情况下初始化数组。  
  
 [!code-csharp[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]  
  
 如果选择在不初始化的情况下声明数组变量，则必须使用 `new` 运算符将数组赋予变量。 `new` 的用法如以下示例所示。  
  
 [!code-csharp[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]  
  
 以下示例将值赋予特定的数组元素。  
  
 [!code-csharp[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]  
  
 同样，以下示例将获取特定数组元素的值并将其赋予变量 `elementValue`。  
  
 [!code-csharp[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]  
  
 以下代码示例将数组元素初始化为默认值（交错数组除外）。  
  
 [!code-csharp[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [数组](../../../csharp/programming-guide/arrays/index.md)  
- [一维数组](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
- [交错数组](../../../csharp/programming-guide/arrays/jagged-arrays.md)
