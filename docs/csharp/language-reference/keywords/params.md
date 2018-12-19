---
title: params 关键字 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: dd9699eb50f7dffc7c2f4976a79afbf689ba2470
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235837"
---
# <a name="params-c-reference"></a><span data-ttu-id="0a5e0-102">params（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0a5e0-102">params (C# Reference)</span></span>

<span data-ttu-id="0a5e0-103">使用 `params` 关键字可以指定采用数目可变的参数的[方法参数](method-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="0a5e0-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span>

<span data-ttu-id="0a5e0-104">可以发送参数声明中所指定类型的逗号分隔的参数列表或指定类型的参数数组。</span><span class="sxs-lookup"><span data-stu-id="0a5e0-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="0a5e0-105">还可以不发送参数。</span><span class="sxs-lookup"><span data-stu-id="0a5e0-105">You also can send no arguments.</span></span> <span data-ttu-id="0a5e0-106">如果未发送任何参数，则 `params` 列表的长度为零。</span><span class="sxs-lookup"><span data-stu-id="0a5e0-106">If you send no arguments, the length of the `params` list is zero.</span></span>

<span data-ttu-id="0a5e0-107">在方法声明中的 `params` 关键字之后不允许有任何其他参数，并且在方法声明中只允许有一个 `params` 关键字。</span><span class="sxs-lookup"><span data-stu-id="0a5e0-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="0a5e0-108">声明的 `params` 参数类型必须是一维数组，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="0a5e0-108">The declared type of the `params` parameter must be a single-dimensional array, as the following example shows.</span></span> <span data-ttu-id="0a5e0-109">否则，发生编译器错误 [CS0225](../../misc/cs0225.md)。</span><span class="sxs-lookup"><span data-stu-id="0a5e0-109">Otherwise, a compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

## <a name="example"></a><span data-ttu-id="0a5e0-110">示例</span><span class="sxs-lookup"><span data-stu-id="0a5e0-110">Example</span></span>

<span data-ttu-id="0a5e0-111">下面的示例演示可向 `params` 形参发送实参的各种方法。</span><span class="sxs-lookup"><span data-stu-id="0a5e0-111">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)] 

## <a name="c-language-specification"></a><span data-ttu-id="0a5e0-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="0a5e0-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="0a5e0-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a5e0-113">See also</span></span>

- [<span data-ttu-id="0a5e0-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="0a5e0-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0a5e0-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="0a5e0-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0a5e0-116">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="0a5e0-116">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0a5e0-117">方法参数</span><span class="sxs-lookup"><span data-stu-id="0a5e0-117">Method Parameters</span></span>](method-parameters.md)