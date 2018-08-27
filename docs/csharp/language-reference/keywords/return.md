---
title: return（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 1b6a1ce2a8587c8630fece3d5c9a2186fbbc9c22
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001471"
---
# <a name="return-c-reference"></a><span data-ttu-id="3ccff-102">return（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3ccff-102">return (C# Reference)</span></span>
<span data-ttu-id="3ccff-103">`return` 语句可终止它所在的方法的执行，并将控制权返回给调用方法。</span><span class="sxs-lookup"><span data-stu-id="3ccff-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="3ccff-104">它还可以返回可选值。</span><span class="sxs-lookup"><span data-stu-id="3ccff-104">It can also return an optional value.</span></span> <span data-ttu-id="3ccff-105">如果方法是 `void` 类型，则 `return` 语句可以省略。</span><span class="sxs-lookup"><span data-stu-id="3ccff-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="3ccff-106">如果 return 语句位于 `try` 块中，则 `finally` 块（如果存在）会在控制权返回给调用方法之前进行执行。</span><span class="sxs-lookup"><span data-stu-id="3ccff-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ccff-107">示例</span><span class="sxs-lookup"><span data-stu-id="3ccff-107">Example</span></span>  
 <span data-ttu-id="3ccff-108">在下面的示例中，方法 `CalculateArea()` 以 [double](../../../csharp/language-reference/keywords/double.md) 值的形式返回本地变量 `area`。</span><span class="sxs-lookup"><span data-stu-id="3ccff-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="3ccff-109">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3ccff-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3ccff-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ccff-110">See Also</span></span>

- [<span data-ttu-id="3ccff-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3ccff-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="3ccff-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3ccff-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3ccff-113">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="3ccff-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="3ccff-114">return 语句</span><span class="sxs-lookup"><span data-stu-id="3ccff-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)  
- [<span data-ttu-id="3ccff-115">跳转语句</span><span class="sxs-lookup"><span data-stu-id="3ccff-115">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
