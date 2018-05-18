---
title: 传递参数（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: a1ccfff8081d101eee46360009653b0591dfb3ff
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="passing-parameters-c-programming-guide"></a>传递参数（C# 编程指南）
在 C# 中，实参可以按值或按引用传递给形参。 按引用传递使函数成员、方法、属性、索引器、运算符和构造函数可以更改参数的值，并让该更改在调用环境中保持。 若要按引用传递参数，且具有更改值的意向，请使用 `ref` 或 `out` 关键字。 若要按引用传递，且只有避免复制而不更改值的意向，请使用 `in` 修饰符。 为简单起见，本主题的示例中只使用 `ref` 关键字。 有关 `in`、`ref` 和 `out` 之间的差异的详细信息，请参阅 [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md)、[ref](../../../csharp/language-reference/keywords/ref.md)、[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) 和[使用 ref 和 out 传递数组](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)。  
  
 以下示例演示值与引用参数之间的差异。  
  
 [!code-csharp[csProgGuideParameters#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/passing-parameters_1.cs)]  
  
 有关详细信息，请参阅下列主题：  
  
-   [传递值类型参数](../../../csharp/programming-guide/classes-and-structs/passing-value-type-parameters.md)  
  
-   [传递引用类型参数](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [方法](../../../csharp/programming-guide/classes-and-structs/methods.md)
