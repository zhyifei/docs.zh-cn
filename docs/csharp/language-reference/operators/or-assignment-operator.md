---
title: '|= 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: fe56005ce94656b5e8a075cddfb91dc0da096cf7
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45653364"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="664c9-102">|= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="664c9-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="664c9-103">OR 赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="664c9-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="664c9-104">备注</span><span class="sxs-lookup"><span data-stu-id="664c9-104">Remarks</span></span>  
 <span data-ttu-id="664c9-105">使用 `|=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="664c9-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```csharp  
x |= y  
```  
  
 <span data-ttu-id="664c9-106">等效于</span><span class="sxs-lookup"><span data-stu-id="664c9-106">is equivalent to</span></span>  
  
```csharp  
x = x | y  
```  
  
 <span data-ttu-id="664c9-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="664c9-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="664c9-108">[&#124; 运算符](../../../csharp/language-reference/operators/or-operator.md) 对整型操作数执行按位逻辑 OR 运算，对 bool 操作数执行逻辑 OR 运算。</span><span class="sxs-lookup"><span data-stu-id="664c9-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="664c9-109">不能直接重载 `|=` 运算符，但用户定义的类型可重载 [&#124; 运算符](../../../csharp/language-reference/operators/or-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="664c9-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="664c9-110">示例</span><span class="sxs-lookup"><span data-stu-id="664c9-110">Example</span></span>  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="664c9-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="664c9-111">See Also</span></span>

- [<span data-ttu-id="664c9-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="664c9-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="664c9-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="664c9-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="664c9-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="664c9-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
