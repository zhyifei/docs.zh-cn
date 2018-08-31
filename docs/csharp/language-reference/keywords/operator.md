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
# <a name="operator-c-reference"></a><span data-ttu-id="4e3ce-102">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="4e3ce-102">operator (C# Reference)</span></span>

<span data-ttu-id="4e3ce-103">使用 `operator` 关键字重载内置运算符，或在类或结构声明中提供用户定义的转换。</span><span class="sxs-lookup"><span data-stu-id="4e3ce-103">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>

## <a name="example"></a><span data-ttu-id="4e3ce-104">示例</span><span class="sxs-lookup"><span data-stu-id="4e3ce-104">Example</span></span>

<span data-ttu-id="4e3ce-105">下面是针对分数的一个非常简单的类。</span><span class="sxs-lookup"><span data-stu-id="4e3ce-105">The following is a very simplified class for fractional numbers.</span></span> <span data-ttu-id="4e3ce-106">此类重载 `+` 和 `*` 运算符以执行分数加法和乘法，并提供转换运算符将 `Fraction` 类型转换为 `double` 类型。</span><span class="sxs-lookup"><span data-stu-id="4e3ce-106">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="4e3ce-107">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="4e3ce-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="4e3ce-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e3ce-108">See also</span></span>

- [<span data-ttu-id="4e3ce-109">C# 参考</span><span class="sxs-lookup"><span data-stu-id="4e3ce-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4e3ce-110">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="4e3ce-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4e3ce-111">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="4e3ce-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="4e3ce-112">implicit</span><span class="sxs-lookup"><span data-stu-id="4e3ce-112">implicit</span></span>](implicit.md)
- [<span data-ttu-id="4e3ce-113">explicit</span><span class="sxs-lookup"><span data-stu-id="4e3ce-113">explicit</span></span>](explicit.md)
- [<span data-ttu-id="4e3ce-114">如何：在结构之间实现用户定义的转换</span><span class="sxs-lookup"><span data-stu-id="4e3ce-114">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
