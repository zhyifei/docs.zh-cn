---
title: / 运算符（C# 参考）
ms.date: 04/04/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5b17d122e3e3f75012e084903b6f8975fb53d46c
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8703a-102">/ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="8703a-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="8703a-103">除法运算符 (`/`) 将其第一操作数除以第二操作数。</span><span class="sxs-lookup"><span data-stu-id="8703a-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="8703a-104">所有数值类型都具有预定义的除法运算符。</span><span class="sxs-lookup"><span data-stu-id="8703a-104">All numeric types have predefined division operators.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8703a-105">备注</span><span class="sxs-lookup"><span data-stu-id="8703a-105">Remarks</span></span>  
 <span data-ttu-id="8703a-106">用户定义的类型可以重载 `/` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="8703a-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="8703a-107">重载 `/` 运算符将隐式地重载 [/= operator](division-assignment-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="8703a-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="8703a-108">两个整数相除，其结果始终为整数。</span><span class="sxs-lookup"><span data-stu-id="8703a-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="8703a-109">例如，7 除以 3 得 2。</span><span class="sxs-lookup"><span data-stu-id="8703a-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="8703a-110">不要将这与 Floor 除法相混淆，因为 `/` 运算符是往 0 的方向舍入：-7 / 3 的计算结果是 -2。</span><span class="sxs-lookup"><span data-stu-id="8703a-110">This is not to be confused with floored division, as the `/` operator rounds towards zero: -7 / 3 is -2.</span></span>  
  
 <span data-ttu-id="8703a-111">若要获取有理数形式的商，请使用 `float`、`double` 或 `decimal` 类型。</span><span class="sxs-lookup"><span data-stu-id="8703a-111">To obtain a quotient as a rational number, use the `float`, `double`, or `decimal` types.</span></span> <span data-ttu-id="8703a-112">切换[内置数值类型](../../../csharp/language-reference/keywords/reference-tables-for-types.md)的方法有许多种。</span><span class="sxs-lookup"><span data-stu-id="8703a-112">There are many ways to convert between [built in numeric types](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span></span>  
  
 <span data-ttu-id="8703a-113">若要确定余数，请使用[余数运算符](../../../csharp/language-reference/operators/remainder-operator.md) `%`。</span><span class="sxs-lookup"><span data-stu-id="8703a-113">To determine the remainder, use the [remainder operator](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8703a-114">示例</span><span class="sxs-lookup"><span data-stu-id="8703a-114">Example</span></span>  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8703a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="8703a-115">See Also</span></span>  
 [<span data-ttu-id="8703a-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="8703a-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8703a-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8703a-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8703a-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="8703a-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
