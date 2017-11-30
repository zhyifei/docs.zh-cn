---
title: "goto（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords: goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aa12a7547cfcd4a2076b5b0a308139f8a823f482
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="goto-c-reference"></a><span data-ttu-id="dd379-102">goto（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="dd379-102">goto (C# Reference)</span></span>
<span data-ttu-id="dd379-103">`goto` 语句将程序控制直接传递给标记语句。</span><span class="sxs-lookup"><span data-stu-id="dd379-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>  
  
 <span data-ttu-id="dd379-104">`goto` 的一个通常用法是将控制传递给特定的 switch-case 标签或 `switch` 语句中的默认标签。</span><span class="sxs-lookup"><span data-stu-id="dd379-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>  
  
 <span data-ttu-id="dd379-105">`goto` 语句还用于跳出深嵌套循环。</span><span class="sxs-lookup"><span data-stu-id="dd379-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd379-106">示例</span><span class="sxs-lookup"><span data-stu-id="dd379-106">Example</span></span>  
 <span data-ttu-id="dd379-107">下面的示例演示了 `goto` 在 [switch](../../../csharp/language-reference/keywords/switch.md) 语句中的使用。</span><span class="sxs-lookup"><span data-stu-id="dd379-107">The following example demonstrates using `goto` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="dd379-108">示例</span><span class="sxs-lookup"><span data-stu-id="dd379-108">Example</span></span>  
 <span data-ttu-id="dd379-109">下面的示例演示了使用 `goto` 跳出嵌套循环。</span><span class="sxs-lookup"><span data-stu-id="dd379-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="dd379-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="dd379-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dd379-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd379-111">See Also</span></span>  
 [<span data-ttu-id="dd379-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="dd379-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="dd379-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="dd379-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dd379-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="dd379-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="dd379-115">goto 语句</span><span class="sxs-lookup"><span data-stu-id="dd379-115">goto Statement</span></span>](/cpp/cpp/goto-statement-cpp)  
 [<span data-ttu-id="dd379-116">跳转语句</span><span class="sxs-lookup"><span data-stu-id="dd379-116">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
