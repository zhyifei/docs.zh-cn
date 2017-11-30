---
title: "return（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 90c84b51c6ee57864eac552bc488c9f9c15e9394
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="return-c-reference"></a><span data-ttu-id="0d5ee-102">return（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="0d5ee-102">return (C# Reference)</span></span>
<span data-ttu-id="0d5ee-103">`return` 语句可终止它所在的方法的执行，并将控制权返回给调用方法。</span><span class="sxs-lookup"><span data-stu-id="0d5ee-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="0d5ee-104">它还可以返回可选值。</span><span class="sxs-lookup"><span data-stu-id="0d5ee-104">It can also return an optional value.</span></span> <span data-ttu-id="0d5ee-105">如果方法是 `void` 类型，则 `return` 语句可以省略。</span><span class="sxs-lookup"><span data-stu-id="0d5ee-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="0d5ee-106">如果 return 语句位于 `try` 块中，则 `finally` 块（如果存在）会在控制权返回给调用方法之前进行执行。</span><span class="sxs-lookup"><span data-stu-id="0d5ee-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d5ee-107">示例</span><span class="sxs-lookup"><span data-stu-id="0d5ee-107">Example</span></span>  
 <span data-ttu-id="0d5ee-108">在下面的示例中，该方法`CalculateArea()`返回局部变量`area`作为[double](../../../csharp/language-reference/keywords/double.md)值。</span><span class="sxs-lookup"><span data-stu-id="0d5ee-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="0d5ee-109">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="0d5ee-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0d5ee-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d5ee-110">See Also</span></span>  
 [<span data-ttu-id="0d5ee-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="0d5ee-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0d5ee-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="0d5ee-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0d5ee-113">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="0d5ee-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="0d5ee-114">return 语句</span><span class="sxs-lookup"><span data-stu-id="0d5ee-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)  
 [<span data-ttu-id="0d5ee-115">跳转语句</span><span class="sxs-lookup"><span data-stu-id="0d5ee-115">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
