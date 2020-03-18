---
title: 传递参数 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: 60ac7a8d982e7788f07debce114896859385c8e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705465"
---
# <a name="passing-parameters-c-programming-guide"></a>传递参数（C# 编程指南）
在 C# 中，实参可以按值或按引用传递给形参。 按引用传递使函数成员、方法、属性、索引器、运算符和构造函数可以更改参数的值，并让该更改在调用环境中保持。 若要按引用传递参数，且具有更改值的意向，请使用 `ref` 或 `out` 关键字。 若要按引用传递，且只有避免复制而不更改值的意向，请使用 `in` 修饰符。 为简单起见，本主题的示例中只使用 `ref` 关键字。 有关 `in`、`ref` 和 `out` 之间差异的详细信息，请参阅 [in](../../language-reference/keywords/in-parameter-modifier.md)、[ref](../../language-reference/keywords/ref.md) 及 [out](../../language-reference/keywords/out-parameter-modifier.md)。  
  
 以下示例演示值与引用参数之间的差异。  
  
 [!code-csharp[csProgGuideParameters#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#10)]  
  
 有关详细信息，请参阅下列主题：  
  
- [传递值类型参数](./passing-value-type-parameters.md)  
  
- [传递引用类型参数](./passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a>C# 语言规范  

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/expressions.md#argument-lists)中的[参数列表](/dotnet/csharp/language-reference/language-specification/introduction)。 该语言规范是 C# 语法和用法的权威资料。
  
## <a name="see-also"></a>另请参阅

- [C# 编程指南](../index.md)
- [方法](./methods.md)
