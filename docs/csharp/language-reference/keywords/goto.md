---
title: goto（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: 2dd70a30b885dcdae9637b02e8c34ac39f4879fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216799"
---
# <a name="goto-c-reference"></a><span data-ttu-id="2bae8-102">goto（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="2bae8-102">goto (C# Reference)</span></span>
<span data-ttu-id="2bae8-103">`goto` 语句将程序控制直接传递给标记语句。</span><span class="sxs-lookup"><span data-stu-id="2bae8-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>  
  
 <span data-ttu-id="2bae8-104">`goto` 的一个通常用法是将控制传递给特定的 switch-case 标签或 `switch` 语句中的默认标签。</span><span class="sxs-lookup"><span data-stu-id="2bae8-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>  
  
 <span data-ttu-id="2bae8-105">`goto` 语句还用于跳出深嵌套循环。</span><span class="sxs-lookup"><span data-stu-id="2bae8-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bae8-106">示例</span><span class="sxs-lookup"><span data-stu-id="2bae8-106">Example</span></span>  
 <span data-ttu-id="2bae8-107">下面的示例演示了 `goto` 在 [switch](../../../csharp/language-reference/keywords/switch.md) 语句中的使用。</span><span class="sxs-lookup"><span data-stu-id="2bae8-107">The following example demonstrates using `goto` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="2bae8-108">示例</span><span class="sxs-lookup"><span data-stu-id="2bae8-108">Example</span></span>  
 <span data-ttu-id="2bae8-109">下面的示例演示了使用 `goto` 跳出嵌套循环。</span><span class="sxs-lookup"><span data-stu-id="2bae8-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="2bae8-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="2bae8-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2bae8-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bae8-111">See Also</span></span>  
 [<span data-ttu-id="2bae8-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="2bae8-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2bae8-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2bae8-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2bae8-114">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="2bae8-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="2bae8-115">goTo 语句</span><span class="sxs-lookup"><span data-stu-id="2bae8-115">goto Statement</span></span>](/cpp/cpp/goto-statement-cpp)  
 [<span data-ttu-id="2bae8-116">跳转语句</span><span class="sxs-lookup"><span data-stu-id="2bae8-116">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
