---
title: "|= 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aac4fd6016b65daa15da4bd3a414f385edce7c22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f878b-102">|= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f878b-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="f878b-103">OR 赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="f878b-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f878b-104">备注</span><span class="sxs-lookup"><span data-stu-id="f878b-104">Remarks</span></span>  
 <span data-ttu-id="f878b-105">使用 `|=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="f878b-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```  
x |= y  
```  
  
 <span data-ttu-id="f878b-106">等效于</span><span class="sxs-lookup"><span data-stu-id="f878b-106">is equivalent to</span></span>  
  
```  
x = x | y  
```  
  
 <span data-ttu-id="f878b-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="f878b-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="f878b-108">[&#124; 运算符](../../../csharp/language-reference/operators/or-operator.md) 对整型操作数执行按位逻辑 OR 运算，对 bool 操作数执行逻辑 OR 运算。</span><span class="sxs-lookup"><span data-stu-id="f878b-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="f878b-109">不能直接重载 `|=` 运算符，但用户定义的类型可重载 [&#124; 运算符](../../../csharp/language-reference/operators/or-operator.md)（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="f878b-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f878b-110">示例</span><span class="sxs-lookup"><span data-stu-id="f878b-110">Example</span></span>  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f878b-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f878b-111">See Also</span></span>  
 [<span data-ttu-id="f878b-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f878b-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f878b-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f878b-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f878b-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="f878b-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
