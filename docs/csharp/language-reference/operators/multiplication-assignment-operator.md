---
title: '*= 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: f8604cdadeda14a5761bc923bd966186fd258a6d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245345"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d0095-102">\*= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d0095-102">\*= Operator (C# Reference)</span></span>
<span data-ttu-id="d0095-103">二进制乘法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="d0095-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0095-104">备注</span><span class="sxs-lookup"><span data-stu-id="d0095-104">Remarks</span></span>  
 <span data-ttu-id="d0095-105">使用 `*=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="d0095-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```csharp  
x *= y  
```  
  
 <span data-ttu-id="d0095-106">等效于</span><span class="sxs-lookup"><span data-stu-id="d0095-106">is equivalent to</span></span>  
  
```csharp  
x = x * y  
```  
  
 <span data-ttu-id="d0095-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="d0095-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="d0095-108">针对数值类型预定义了 [\* 运算符](../../../csharp/language-reference/operators/multiplication-operator.md)以进行乘法运算。</span><span class="sxs-lookup"><span data-stu-id="d0095-108">The [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="d0095-109">不能直接重载 `*=` 运算符，但用户定义的类型可重载 [\* 运算符](../../../csharp/language-reference/operators/multiplication-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="d0095-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0095-110">示例</span><span class="sxs-lookup"><span data-stu-id="d0095-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d0095-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0095-111">See Also</span></span>

- [<span data-ttu-id="d0095-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="d0095-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="d0095-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d0095-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="d0095-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="d0095-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
