---
title: "return（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- return_CSharpKeyword
- return
dev_langs:
- CSharp
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 596375a1cba8f5ecbad636a6829c1a0599f8c0f4
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="return-c-reference"></a><span data-ttu-id="34f93-102">return（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="34f93-102">return (C# Reference)</span></span>
<span data-ttu-id="34f93-103">`return` 语句可终止它所在的方法的执行，并将控制权返回给调用方法。</span><span class="sxs-lookup"><span data-stu-id="34f93-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="34f93-104">它还可以返回可选值。</span><span class="sxs-lookup"><span data-stu-id="34f93-104">It can also return an optional value.</span></span> <span data-ttu-id="34f93-105">如果方法是 `void` 类型，则 `return` 语句可以省略。</span><span class="sxs-lookup"><span data-stu-id="34f93-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="34f93-106">如果 return 语句位于 `try` 块中，则 `finally` 块（如果存在）会在控制权返回给调用方法之前进行执行。</span><span class="sxs-lookup"><span data-stu-id="34f93-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34f93-107">示例</span><span class="sxs-lookup"><span data-stu-id="34f93-107">Example</span></span>  
 <span data-ttu-id="34f93-108">在下面的示例中，方法 `A()` 以 [double](../../../csharp/language-reference/keywords/double.md) 值的形式返回变量 `Area`。</span><span class="sxs-lookup"><span data-stu-id="34f93-108">In the following example, the method `A()` returns the variable `Area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 <span data-ttu-id="34f93-109">[!code-cs[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="34f93-109">[!code-cs[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="34f93-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="34f93-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="34f93-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="34f93-111">See Also</span></span>  
 <span data-ttu-id="34f93-112">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="34f93-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="34f93-113">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="34f93-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="34f93-114">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="34f93-114">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="34f93-115">[return 语句](/cpp/cpp/return-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="34f93-115">[return Statement](/cpp/cpp/return-statement-cpp) </span></span>  
 [<span data-ttu-id="34f93-116">跳转语句</span><span class="sxs-lookup"><span data-stu-id="34f93-116">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)

