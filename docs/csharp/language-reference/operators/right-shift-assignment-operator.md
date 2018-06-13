---
title: '&gt;&gt;= 运算符（C# 参考）'
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: ccc3f688d985b9e35404550f0c53a7acf8095dd5
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171413"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="2c279-102">&gt;&gt;= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="2c279-102">&gt;&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="2c279-103">右移赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="2c279-103">The right-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c279-104">备注</span><span class="sxs-lookup"><span data-stu-id="2c279-104">Remarks</span></span>  
 <span data-ttu-id="2c279-105">形式如下的表达式</span><span class="sxs-lookup"><span data-stu-id="2c279-105">An expression of the form</span></span>  
  
```csharp  
x >>= y  
```  
  
 <span data-ttu-id="2c279-106">计算结果为</span><span class="sxs-lookup"><span data-stu-id="2c279-106">is evaluated as</span></span>  
  
```csharp  
x = x >> y  
```  
  
 <span data-ttu-id="2c279-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="2c279-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="2c279-108">[>> 运算符](../../../csharp/language-reference/operators/right-shift-operator.md) 将 `x` 右移 `y` 指定的量。</span><span class="sxs-lookup"><span data-stu-id="2c279-108">The [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>  
  
 <span data-ttu-id="2c279-109">不能直接重载 >>= 运算符，但用户定义的类型可重载 [>> 运算符](../../../csharp/language-reference/operators/right-shift-operator.md)（参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="2c279-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c279-110">示例</span><span class="sxs-lookup"><span data-stu-id="2c279-110">Example</span></span>  
 [!code-csharp[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="2c279-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c279-111">See Also</span></span>  
 [<span data-ttu-id="2c279-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="2c279-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2c279-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2c279-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2c279-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="2c279-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
