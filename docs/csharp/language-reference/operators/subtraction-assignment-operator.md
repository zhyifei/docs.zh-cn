---
title: "-= 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 443f0d717288a491838d23eaa63218150bd346d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="--operator-c-reference"></a><span data-ttu-id="68a4f-102">-= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="68a4f-102">-= Operator (C# Reference)</span></span>
<span data-ttu-id="68a4f-103">减法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="68a4f-103">The subtraction assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68a4f-104">备注</span><span class="sxs-lookup"><span data-stu-id="68a4f-104">Remarks</span></span>  
 <span data-ttu-id="68a4f-105">使用 `-=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="68a4f-105">An expression using the `-=` assignment operator, such as</span></span>  
  
```  
x -= y  
```  
  
 <span data-ttu-id="68a4f-106">等效于</span><span class="sxs-lookup"><span data-stu-id="68a4f-106">is equivalent to</span></span>  
  
```  
x = x - y  
```  
  
 <span data-ttu-id="68a4f-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="68a4f-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="68a4f-108">[- 运算符](../../../csharp/language-reference/operators/subtraction-operator.md)的含义取决于 `x` 和 `y` 的类型（例如，对于数值操作数，其含义为相减；对于委托操作数，其含义为移除委托）。</span><span class="sxs-lookup"><span data-stu-id="68a4f-108">The meaning of the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>  
  
 <span data-ttu-id="68a4f-109">不能直接重载 `-=` 运算符，但用户定义的类型可重载 [- 运算符](../../../csharp/language-reference/operators/subtraction-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="68a4f-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="68a4f-110">C# 中也使用 -= 运算符来取消订阅事件。</span><span class="sxs-lookup"><span data-stu-id="68a4f-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="68a4f-111">有关详细信息，请参阅[如何：订阅和取消订阅事件](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。</span><span class="sxs-lookup"><span data-stu-id="68a4f-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="68a4f-112">示例</span><span class="sxs-lookup"><span data-stu-id="68a4f-112">Example</span></span>  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="68a4f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68a4f-113">See Also</span></span>  
 [<span data-ttu-id="68a4f-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="68a4f-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="68a4f-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="68a4f-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="68a4f-116">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="68a4f-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
