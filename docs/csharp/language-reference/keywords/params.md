---
title: 参数数组的 params 关键字 - C# 参考
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 77d7fd19ff57f80f401191027e2fae95026e1966
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738846"
---
# <a name="params-c-reference"></a><span data-ttu-id="044e5-102">params（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="044e5-102">params (C# Reference)</span></span>

<span data-ttu-id="044e5-103">使用 `params` 关键字可以指定采用数目可变的参数的[方法参数](method-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="044e5-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span> <span data-ttu-id="044e5-104">参数类型必须是一维数组。</span><span class="sxs-lookup"><span data-stu-id="044e5-104">The parameter type must be a single-dimensional array.</span></span>

<span data-ttu-id="044e5-105">在方法声明中的 `params` 关键字之后不允许有任何其他参数，并且在方法声明中只允许有一个 `params` 关键字。</span><span class="sxs-lookup"><span data-stu-id="044e5-105">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="044e5-106">如果 `params` 参数的声明类型不是一维数组，则会发生编译器错误 [CS0225](../../misc/cs0225.md)。</span><span class="sxs-lookup"><span data-stu-id="044e5-106">If the declared type of the `params` parameter is not a single-dimensional array, compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

<span data-ttu-id="044e5-107">使用 `params` 参数调用方法时，可以传入：</span><span class="sxs-lookup"><span data-stu-id="044e5-107">When you call a method with a `params` parameter, you can pass in:</span></span>

- <span data-ttu-id="044e5-108">数组元素类型的参数的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="044e5-108">A comma-separated list of arguments of the type of the array elements.</span></span>
- <span data-ttu-id="044e5-109">指定类型的参数的数组。</span><span class="sxs-lookup"><span data-stu-id="044e5-109">An array of arguments of the specified type.</span></span>
- <span data-ttu-id="044e5-110">无参数。</span><span class="sxs-lookup"><span data-stu-id="044e5-110">No arguments.</span></span> <span data-ttu-id="044e5-111">如果未发送任何参数，则 `params` 列表的长度为零。</span><span class="sxs-lookup"><span data-stu-id="044e5-111">If you send no arguments, the length of the `params` list is zero.</span></span>

## <a name="example"></a><span data-ttu-id="044e5-112">示例</span><span class="sxs-lookup"><span data-stu-id="044e5-112">Example</span></span>

<span data-ttu-id="044e5-113">下面的示例演示可向 `params` 形参发送实参的各种方法。</span><span class="sxs-lookup"><span data-stu-id="044e5-113">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="044e5-114">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="044e5-114">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="044e5-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="044e5-115">See also</span></span>

- [<span data-ttu-id="044e5-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="044e5-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="044e5-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="044e5-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="044e5-118">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="044e5-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="044e5-119">方法参数</span><span class="sxs-lookup"><span data-stu-id="044e5-119">Method Parameters</span></span>](method-parameters.md)
