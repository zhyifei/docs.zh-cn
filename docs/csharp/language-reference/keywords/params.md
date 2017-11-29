---
title: "params（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e66cfc8e7b131a4443ee227df5e39c7e3b775324
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="params-c-reference"></a><span data-ttu-id="5881a-102">params（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5881a-102">params (C# Reference)</span></span>
<span data-ttu-id="5881a-103">使用 `params` 关键字可以指定采用数目可变的参数的[方法参数](../../../csharp/language-reference/keywords/method-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="5881a-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="5881a-104">可以发送参数声明中所指定类型的逗号分隔的参数列表或指定类型的参数数组。</span><span class="sxs-lookup"><span data-stu-id="5881a-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="5881a-105">还可以不发送参数。</span><span class="sxs-lookup"><span data-stu-id="5881a-105">You also can send no arguments.</span></span> <span data-ttu-id="5881a-106">如果未发送任何参数，则 `params` 列表的长度为零。</span><span class="sxs-lookup"><span data-stu-id="5881a-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="5881a-107">在方法声明中的 `params` 关键字之后不允许有任何其他参数，并且在方法声明中只允许有一个 `params` 关键字。</span><span class="sxs-lookup"><span data-stu-id="5881a-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5881a-108">示例</span><span class="sxs-lookup"><span data-stu-id="5881a-108">Example</span></span>  
 <span data-ttu-id="5881a-109">下面的示例演示可向 `params` 形参发送实参的各种方法。</span><span class="sxs-lookup"><span data-stu-id="5881a-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="5881a-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5881a-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5881a-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5881a-111">See Also</span></span>  
 [<span data-ttu-id="5881a-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5881a-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5881a-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5881a-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5881a-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="5881a-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5881a-115">方法参数</span><span class="sxs-lookup"><span data-stu-id="5881a-115">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
