---
title: "将数组作为自变量传递（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f152173b747a171052ab99f261ed91ced9465fdc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a>将数组作为自变量传递（C# 编程指南）
数组可以作为实参传递给方法形参。 由于数组是引用类型，因此方法可以更改元素的值。  
  
## <a name="passing-single-dimensional-arrays-as-arguments"></a>将一维数组作为参数传递  
 可将初始化的一维数组传递给方法。 例如，下列语句将一个数组发送给了 Print 方法。  
  
 [!code-csharp[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_1.cs)]  
  
 下面的代码演示 Print 方法的部分实现。  
  
 [!code-csharp[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_2.cs)]  
  
 可在同一步骤中初始化并传递新数组，如下例所示。  
  
 [!code-csharp[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_3.cs)]  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 在下面的示例中，先初始化一个字符串数组，然后将其作为参数传递给字符串的 `PrintArray` 方法。 该方法将显示数组的元素。 然后，调用 `ChangeArray` 和 `ChangeArrayElement` 方法，演示根据值发送数组参数不会阻止对数组元素的更改。  
  
### <a name="code"></a>代码  
 [!code-csharp[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_4.cs)]  
  
## <a name="passing-multidimensional-arrays-as-arguments"></a>将多维数组作为参数传递  
 通过与传递一维数组相同的方式，向方法传递初始化的多维数组。  
  
 [!code-csharp[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_5.cs)]  
  
 下列代码演示了 Print 方法的部分声明（该方法接受将二维数组作为其参数）。  
  
 [!code-csharp[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_6.cs)]  
  
 可在同一步骤中初始化并传递新数组，如下例所示。  
  
 [!code-csharp[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_7.cs)]  
  
## <a name="example"></a>示例  
  
### <a name="description"></a>描述  
 在下列示例中，初始化一个整数的二维数组，并将其传递至 `Print2DArray` 方法。 该方法将显示数组的元素。  
  
### <a name="code"></a>代码  
 [!code-csharp[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-as-arguments_8.cs)]  
  
## <a name="see-also"></a>另请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [阵列](../../../csharp/programming-guide/arrays/index.md)  
 [一维数组](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)  
 [多维数组](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)  
 [交错数组](../../../csharp/programming-guide/arrays/jagged-arrays.md)
