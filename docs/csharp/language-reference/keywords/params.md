---
title: params（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: d7e0094d0f60aa201ae7229983f3e4b9764d2cbc
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37960190"
---
# <a name="params-c-reference"></a><span data-ttu-id="5aa66-102">params（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5aa66-102">params (C# Reference)</span></span>
<span data-ttu-id="5aa66-103">使用 `params` 关键字可以指定采用数目可变的参数的[方法参数](../../../csharp/language-reference/keywords/method-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="5aa66-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="5aa66-104">可以发送参数声明中所指定类型的逗号分隔的参数列表或指定类型的参数数组。</span><span class="sxs-lookup"><span data-stu-id="5aa66-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="5aa66-105">还可以不发送参数。</span><span class="sxs-lookup"><span data-stu-id="5aa66-105">You also can send no arguments.</span></span> <span data-ttu-id="5aa66-106">如果未发送任何参数，则 `params` 列表的长度为零。</span><span class="sxs-lookup"><span data-stu-id="5aa66-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="5aa66-107">在方法声明中的 `params` 关键字之后不允许有任何其他参数，并且在方法声明中只允许有一个 `params` 关键字。</span><span class="sxs-lookup"><span data-stu-id="5aa66-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5aa66-108">示例</span><span class="sxs-lookup"><span data-stu-id="5aa66-108">Example</span></span>  
 <span data-ttu-id="5aa66-109">下面的示例演示可向 `params` 形参发送实参的各种方法。</span><span class="sxs-lookup"><span data-stu-id="5aa66-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5aa66-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5aa66-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5aa66-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="5aa66-111">See Also</span></span>  
 [<span data-ttu-id="5aa66-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5aa66-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5aa66-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5aa66-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5aa66-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="5aa66-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5aa66-115">方法参数</span><span class="sxs-lookup"><span data-stu-id="5aa66-115">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
