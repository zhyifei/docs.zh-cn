---
title: 运算符关键字（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: c3bfada235993670bf158fe9803a09707b2b3251
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929867"
---
# <a name="operator-c-reference"></a>运算符（C# 参考）

使用 `operator` 关键字重载内置运算符，或在类或结构声明中提供用户定义的转换。

## <a name="example"></a>示例

下面是针对分数的一个非常简单的类。 此类重载 `+` 和 `*` 运算符以执行分数加法和乘法，并提供转换运算符将 `Fraction` 类型转换为 `double` 类型。

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a>C# 语言规范

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 关键字](index.md)
- [implicit](implicit.md)
- [explicit](explicit.md)
- [如何：在结构之间实现用户定义的转换](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
