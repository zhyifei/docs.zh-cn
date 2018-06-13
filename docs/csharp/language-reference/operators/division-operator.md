---
title: / 运算符（C# 参考）
ms.date: 04/04/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 9d0bbff1fd9f4ab3c93c879d12ccd5fde1187b44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33272566"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="fc516-102">/ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="fc516-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="fc516-103">除法运算符 (`/`) 将其第一操作数除以第二操作数。</span><span class="sxs-lookup"><span data-stu-id="fc516-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="fc516-104">所有数值类型都具有预定义的除法运算符。</span><span class="sxs-lookup"><span data-stu-id="fc516-104">All numeric types have predefined division operators.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="fc516-105">备注</span><span class="sxs-lookup"><span data-stu-id="fc516-105">Remarks</span></span>  
 <span data-ttu-id="fc516-106">用户定义的类型可以重载 `/` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="fc516-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="fc516-107">重载 `/` 运算符将隐式地重载 [/= operator](division-assignment-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="fc516-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="fc516-108">两个整数相除，其结果始终为整数。</span><span class="sxs-lookup"><span data-stu-id="fc516-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="fc516-109">例如，7 除以 3 得 2。</span><span class="sxs-lookup"><span data-stu-id="fc516-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="fc516-110">不要将这与 Floor 除法相混淆，因为 `/` 运算符是往 0 的方向舍入：-7 / 3 的计算结果是 -2。</span><span class="sxs-lookup"><span data-stu-id="fc516-110">This is not to be confused with floored division, as the `/` operator rounds towards zero: -7 / 3 is -2.</span></span>  
  
 <span data-ttu-id="fc516-111">若要获取有理数形式的商，请使用 `float`、`double` 或 `decimal` 类型。</span><span class="sxs-lookup"><span data-stu-id="fc516-111">To obtain a quotient as a rational number, use the `float`, `double`, or `decimal` types.</span></span> <span data-ttu-id="fc516-112">切换[内置数值类型](../../../csharp/language-reference/keywords/reference-tables-for-types.md)的方法有许多种。</span><span class="sxs-lookup"><span data-stu-id="fc516-112">There are many ways to convert between [built in numeric types](../../../csharp/language-reference/keywords/reference-tables-for-types.md).</span></span>  
  
 <span data-ttu-id="fc516-113">若要确定余数，请使用[余数运算符](../../../csharp/language-reference/operators/remainder-operator.md) `%`。</span><span class="sxs-lookup"><span data-stu-id="fc516-113">To determine the remainder, use the [remainder operator](../../../csharp/language-reference/operators/remainder-operator.md) `%`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc516-114">示例</span><span class="sxs-lookup"><span data-stu-id="fc516-114">Example</span></span>  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="fc516-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc516-115">See Also</span></span>  
 [<span data-ttu-id="fc516-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="fc516-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fc516-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fc516-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fc516-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="fc516-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
