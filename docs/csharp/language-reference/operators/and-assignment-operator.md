---
title: '&amp;= 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: f3a6fe20ca89a90b5a64118d73fb39e9a364d1e9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506396"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="676a7-102">&amp;= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="676a7-102">&amp;= Operator (C# Reference)</span></span>
<span data-ttu-id="676a7-103">AND 赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="676a7-103">The AND assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="676a7-104">备注</span><span class="sxs-lookup"><span data-stu-id="676a7-104">Remarks</span></span>  
 <span data-ttu-id="676a7-105">使用 `&=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="676a7-105">An expression using the `&=` assignment operator, such as</span></span>  
  
```csharp  
x &= y  
```  
  
 <span data-ttu-id="676a7-106">等效于</span><span class="sxs-lookup"><span data-stu-id="676a7-106">is equivalent to</span></span>  
  
```csharp  
x = x & y  
```  
  
 <span data-ttu-id="676a7-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="676a7-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="676a7-108">[& 运算符](../../../csharp/language-reference/operators/and-operator.md) 对整型操作数执行按位逻辑 AND 运算，对 `bool` 操作数执行逻辑 AND 运算。</span><span class="sxs-lookup"><span data-stu-id="676a7-108">The [& operator](../../../csharp/language-reference/operators/and-operator.md) performs a bitwise logical AND operation on integral operands and logical AND on `bool` operands.</span></span>  
  
 <span data-ttu-id="676a7-109">不能直接重载 `&=` 运算符，但用户定义的类型可重载二元 [& 运算符](../../../csharp/language-reference/operators/and-operator.md)（参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="676a7-109">The `&=` operator cannot be overloaded directly, but user-defined types can overload the binary [& operator](../../../csharp/language-reference/operators/and-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="676a7-110">示例</span><span class="sxs-lookup"><span data-stu-id="676a7-110">Example</span></span>  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="676a7-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="676a7-111">See Also</span></span>

- [<span data-ttu-id="676a7-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="676a7-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="676a7-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="676a7-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="676a7-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="676a7-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
