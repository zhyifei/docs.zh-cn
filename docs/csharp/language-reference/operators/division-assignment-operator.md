---
title: /= 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: c31ff374e6af4c08c329a971fdd8af169e239395
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="743eb-102">/= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="743eb-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="743eb-103">除法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="743eb-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="743eb-104">备注</span><span class="sxs-lookup"><span data-stu-id="743eb-104">Remarks</span></span>  
 <span data-ttu-id="743eb-105">使用 `/=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="743eb-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```csharp  
x /= y  
```  
  
 <span data-ttu-id="743eb-106">等效于</span><span class="sxs-lookup"><span data-stu-id="743eb-106">is equivalent to</span></span>  
  
```csharp  
x = x / y  
```  
  
 <span data-ttu-id="743eb-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="743eb-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="743eb-108">为数值类型预定义了 [/ 运算符](../../../csharp/language-reference/operators/division-operator.md)以进行除法运算。</span><span class="sxs-lookup"><span data-stu-id="743eb-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="743eb-109">不能直接重载 `/=` 运算符，但用户定义的类型可重载 [/ 运算符](../../../csharp/language-reference/operators/division-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="743eb-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="743eb-110">对于所有复合赋值运算符，隐式重载二元运算符会重载等效的复合赋值。</span><span class="sxs-lookup"><span data-stu-id="743eb-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="743eb-111">示例</span><span class="sxs-lookup"><span data-stu-id="743eb-111">Example</span></span>  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="743eb-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="743eb-112">See Also</span></span>  
 [<span data-ttu-id="743eb-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="743eb-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="743eb-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="743eb-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="743eb-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="743eb-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
