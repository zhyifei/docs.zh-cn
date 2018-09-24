---
title: params 关键字（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 089e31f3aad12c2303619e2a1998d0d6a5a0ad86
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46490661"
---
# <a name="params-c-reference"></a>params（C# 参考）

使用 `params` 关键字可以指定采用数目可变的参数的[方法参数](method-parameters.md)。

可以发送参数声明中所指定类型的逗号分隔的参数列表或指定类型的参数数组。 还可以不发送参数。 如果未发送任何参数，则 `params` 列表的长度为零。

在方法声明中的 `params` 关键字之后不允许有任何其他参数，并且在方法声明中只允许有一个 `params` 关键字。

声明的 `params` 参数类型必须是一维数组，如以下示例所示。 否则，发生编译器错误 [CS0225](../../misc/cs0225.md)。

## <a name="example"></a>示例

下面的示例演示可向 `params` 形参发送实参的各种方法。

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)] 

## <a name="c-language-specification"></a>C# 语言规范

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 关键字](index.md)
- [方法参数](method-parameters.md)