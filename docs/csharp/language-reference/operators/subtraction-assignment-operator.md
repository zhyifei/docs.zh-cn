---
title: -= 运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: dc3cedafc57e1c6ec9bc34ca4e2c2aa9c604848c
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239574"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="8c44d-102">-= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="8c44d-102">-= Operator (C# Reference)</span></span>
<span data-ttu-id="8c44d-103">减法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="8c44d-103">The subtraction assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c44d-104">备注</span><span class="sxs-lookup"><span data-stu-id="8c44d-104">Remarks</span></span>  
 <span data-ttu-id="8c44d-105">使用 `-=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="8c44d-105">An expression using the `-=` assignment operator, such as</span></span>  
  
```csharp  
x -= y  
```  
  
 <span data-ttu-id="8c44d-106">等效于</span><span class="sxs-lookup"><span data-stu-id="8c44d-106">is equivalent to</span></span>  
  
```csharp  
x = x - y  
```  
  
 <span data-ttu-id="8c44d-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="8c44d-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="8c44d-108">[- 运算符](../../../csharp/language-reference/operators/subtraction-operator.md)的含义取决于 `x` 和 `y` 的类型（例如，对于数值操作数，其含义为相减；对于委托操作数，其含义为移除委托）。</span><span class="sxs-lookup"><span data-stu-id="8c44d-108">The meaning of the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>  
  
 <span data-ttu-id="8c44d-109">不能直接重载 `-=` 运算符，但用户定义的类型可重载 [- 运算符](../../../csharp/language-reference/operators/subtraction-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="8c44d-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="8c44d-110">C# 中也使用 -= 运算符来取消订阅事件。</span><span class="sxs-lookup"><span data-stu-id="8c44d-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="8c44d-111">有关更多信息，请参见[如何：订阅和取消订阅事件](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)。</span><span class="sxs-lookup"><span data-stu-id="8c44d-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c44d-112">示例</span><span class="sxs-lookup"><span data-stu-id="8c44d-112">Example</span></span>  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8c44d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c44d-113">See Also</span></span>

- [<span data-ttu-id="8c44d-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="8c44d-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="8c44d-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8c44d-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="8c44d-116">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="8c44d-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
