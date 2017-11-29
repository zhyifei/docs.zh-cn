---
title: "+= 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 91286b3c6b9a7239bcd5d5bac0ef08bfd7fa8345
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="2fa01-102">+= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="2fa01-102">+= Operator (C# Reference)</span></span>
<span data-ttu-id="2fa01-103">加法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="2fa01-103">The addition assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2fa01-104">备注</span><span class="sxs-lookup"><span data-stu-id="2fa01-104">Remarks</span></span>  
 <span data-ttu-id="2fa01-105">使用 `+=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="2fa01-105">An expression using the `+=` assignment operator, such as</span></span>  
  
```  
x += y  
```  
  
 <span data-ttu-id="2fa01-106">等效于</span><span class="sxs-lookup"><span data-stu-id="2fa01-106">is equivalent to</span></span>  
  
```  
x = x + y  
```  
  
 <span data-ttu-id="2fa01-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="2fa01-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="2fa01-108">[+ 运算符](../../../csharp/language-reference/operators/addition-operator.md)的含义取决于 `x` 和 `y` 的类型（数值操作数表示加法、字符串操作数表示串联等等）。</span><span class="sxs-lookup"><span data-stu-id="2fa01-108">The meaning of the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) depends on the types of `x` and `y` (addition for numeric operands, concatenation for string operands, and so forth).</span></span>  
  
 <span data-ttu-id="2fa01-109">不能直接重载 `+=` 运算符，但用户定义的类型可重载 [+ 运算符](../../../csharp/language-reference/operators/addition-operator.md)（参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="2fa01-109">The `+=` operator cannot be overloaded directly, but user-defined types can overload the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="2fa01-110">`+=` 运算符还用于指定事件响应中要调用的方法；此类方法称为事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2fa01-110">The `+=` operator is also used to specify a method that will be called in response to an event; such methods are called event handlers.</span></span> <span data-ttu-id="2fa01-111">在此上下文中使用 `+=` 运算符被称为订阅事件。</span><span class="sxs-lookup"><span data-stu-id="2fa01-111">The use of the `+=` operator in this context is referred to as *subscribing to an event*.</span></span> <span data-ttu-id="2fa01-112">有关详细信息，请参阅[如何：订阅和取消订阅事件](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa01-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span> <span data-ttu-id="2fa01-113">和[委托](../../../csharp/programming-guide/delegates/index.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa01-113">and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fa01-114">示例</span><span class="sxs-lookup"><span data-stu-id="2fa01-114">Example</span></span>  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2fa01-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2fa01-115">See Also</span></span>  
 [<span data-ttu-id="2fa01-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="2fa01-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2fa01-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2fa01-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2fa01-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="2fa01-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
