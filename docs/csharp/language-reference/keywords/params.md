---
title: "params（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- params_CSharpKeyword
- params
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5999911b96d17c710096e74c8f3da65223e778fc
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="params-c-reference"></a><span data-ttu-id="671a9-102">params（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="671a9-102">params (C# Reference)</span></span>
<span data-ttu-id="671a9-103">使用 `params` 关键字可以指定采用数目可变的参数的[方法参数](../../../csharp/language-reference/keywords/method-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="671a9-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="671a9-104">可以发送参数声明中所指定类型的逗号分隔的参数列表或指定类型的参数数组。</span><span class="sxs-lookup"><span data-stu-id="671a9-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="671a9-105">还可以不发送参数。</span><span class="sxs-lookup"><span data-stu-id="671a9-105">You also can send no arguments.</span></span> <span data-ttu-id="671a9-106">如果未发送任何参数，则 `params` 列表的长度为零。</span><span class="sxs-lookup"><span data-stu-id="671a9-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="671a9-107">在方法声明中的 `params` 关键字之后不允许有任何其他参数，并且在方法声明中只允许有一个 `params` 关键字。</span><span class="sxs-lookup"><span data-stu-id="671a9-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="671a9-108">示例</span><span class="sxs-lookup"><span data-stu-id="671a9-108">Example</span></span>  
 <span data-ttu-id="671a9-109">下面的示例演示可向 `params` 形参发送实参的各种方法。</span><span class="sxs-lookup"><span data-stu-id="671a9-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 <span data-ttu-id="671a9-110">[!code-cs[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="671a9-110">[!code-cs[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="671a9-111">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="671a9-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="671a9-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="671a9-112">See Also</span></span>  
 <span data-ttu-id="671a9-113">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="671a9-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="671a9-114">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="671a9-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="671a9-115">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="671a9-115">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="671a9-116">方法参数</span><span class="sxs-lookup"><span data-stu-id="671a9-116">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

