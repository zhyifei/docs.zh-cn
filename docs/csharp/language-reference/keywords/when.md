---
title: "when（C# 参考）"
ms.date: 2017-03-07
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- when_CSharpKeyword
- when
dev_langs:
- CSharp
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
caps.latest.revision: 30
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
ms.sourcegitcommit: 9ad2eff6eb527f00ce23f463e811aa748def62d0
ms.openlocfilehash: c391c6de51d41577d61278f43d58fade5b7c139f
ms.contentlocale: zh-cn
ms.lasthandoff: 08/11/2017

---
 # <a name="when-c-reference"></a><span data-ttu-id="998c5-102">when（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="998c5-102">when (C# Reference)</span></span>

<span data-ttu-id="998c5-103">在以下两个上下文中，可以使用上下文关键字 `when` 指定筛选条件：</span><span class="sxs-lookup"><span data-stu-id="998c5-103">You can use the `when` contextual keyword to specify a filter condition in two contexts:</span></span>

- <span data-ttu-id="998c5-104">在 [try/catch](try-catch.md) 或 [try/catch/finally](try-catch-finally.md) 块的 `catch` 语句中。</span><span class="sxs-lookup"><span data-stu-id="998c5-104">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="998c5-105">在 [switch](switch.md) 语句的 `case` 标签中。</span><span class="sxs-lookup"><span data-stu-id="998c5-105">In the `case` label of a [switch](switch.md) statement.</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="998c5-106">`catch` 语句中的 `when`</span><span class="sxs-lookup"><span data-stu-id="998c5-106">`when` in a `catch` statement</span></span>

<span data-ttu-id="998c5-107">从 C# 6 开始，`When` 可用于 `catch` 语句中，以指定为执行特定异常处理程序而必须为 true 的条件。</span><span class="sxs-lookup"><span data-stu-id="998c5-107">Starting with C# 6, `When` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="998c5-108">语法为：</span><span class="sxs-lookup"><span data-stu-id="998c5-108">Its syntax is:</span></span>

```csharp
catch ExceptionType [e] when (expr)
```
<span data-ttu-id="998c5-109">其中，*expr* 是一个表达式，其计算结果为布尔值。</span><span class="sxs-lookup"><span data-stu-id="998c5-109">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="998c5-110">如果该表达式返回 `true`，则执行异常处理程序；如果返回 `false`，则不执行。</span><span class="sxs-lookup"><span data-stu-id="998c5-110">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span> 

<span data-ttu-id="998c5-111">以下示例使用 `when` 关键字有条件地执行 @System.Net.HttpRequestException 的处理程序，具体取决于异常消息的文本内容。</span><span class="sxs-lookup"><span data-stu-id="998c5-111">The following example uses the `when` keyword to conditionally execute handlers for an @System.Net.HttpRequestException depending on the text of the exception message.</span></span>

 <span data-ttu-id="998c5-112">[!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]</span><span class="sxs-lookup"><span data-stu-id="998c5-112">[!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]</span></span>  
  
## <a name="when-in-a-switch-statement"></a><span data-ttu-id="998c5-113">`switch` 语句中的 `when`</span><span class="sxs-lookup"><span data-stu-id="998c5-113">`when` in a `switch` statement</span></span>

<span data-ttu-id="998c5-114">从 7 开始，`case` 标签无需是互斥的，且 `case` 标签在 `switch` 语句中的显示顺序可以决定要执行的 switch 块。</span><span class="sxs-lookup"><span data-stu-id="998c5-114">Starting with 7, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="998c5-115">`when` 关键字可指定一个筛选条件，该条件使得仅当筛选条件也为 true 时，与其相关联的 case 标签才为 true。</span><span class="sxs-lookup"><span data-stu-id="998c5-115">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="998c5-116">语法为：</span><span class="sxs-lookup"><span data-stu-id="998c5-116">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```
<span data-ttu-id="998c5-117">其中，*expr* 是与匹配表达式进行比较的常量模式或类型模式，而 *when-condition* 是任意布尔表达式。</span><span class="sxs-lookup"><span data-stu-id="998c5-117">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span> 

<span data-ttu-id="998c5-118">以下示例使用 `when` 关键字针对具有零范围的 `Shape` 对象进行测试，同时针对各种范围大于零的 `Shape` 对象进行测试。</span><span class="sxs-lookup"><span data-stu-id="998c5-118">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span> 

 <span data-ttu-id="998c5-119">[!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="998c5-119">[!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="998c5-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="998c5-120">See also</span></span> 
  [<span data-ttu-id="998c5-121">switch 语句</span><span class="sxs-lookup"><span data-stu-id="998c5-121">switch statement</span></span>](switch.md)  
  [<span data-ttu-id="998c5-122">try/catch 语句</span><span class="sxs-lookup"><span data-stu-id="998c5-122">try/catch statement</span></span>](try-catch.md)  
  [<span data-ttu-id="998c5-123">try/catch/finally 语句</span><span class="sxs-lookup"><span data-stu-id="998c5-123">try/catch/finally statement</span></span>](try-catch-finally.md) 


