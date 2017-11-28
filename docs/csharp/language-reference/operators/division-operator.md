---
title: "/ 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9e12e5c472266ea75d3f572a2091bd0784ea5dcf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="8e9db-102">/ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="8e9db-102">/ Operator (C# Reference)</span></span>
<span data-ttu-id="8e9db-103">除法运算符 (`/`) 将其第一操作数除以第二操作数。</span><span class="sxs-lookup"><span data-stu-id="8e9db-103">The division operator (`/`) divides its first operand by its second operand.</span></span> <span data-ttu-id="8e9db-104">所有数值类型都具有预定义的除法运算符。</span><span class="sxs-lookup"><span data-stu-id="8e9db-104">All numeric types have predefined division operators.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e9db-105">备注</span><span class="sxs-lookup"><span data-stu-id="8e9db-105">Remarks</span></span>  
 <span data-ttu-id="8e9db-106">用户定义的类型可以重载 `/` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="8e9db-106">User-defined types can overload the `/` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="8e9db-107">重载 `/` 运算符将隐式地重载 [/= operator](division-assignment-operator.md)。</span><span class="sxs-lookup"><span data-stu-id="8e9db-107">An overload of the `/` operator implicitly overloads the [/= operator](division-assignment-operator.md).</span></span>  
  
 <span data-ttu-id="8e9db-108">两个整数相除，其结果始终为整数。</span><span class="sxs-lookup"><span data-stu-id="8e9db-108">When you divide two integers, the result is always an integer.</span></span> <span data-ttu-id="8e9db-109">例如，7 除以 3 得 2。</span><span class="sxs-lookup"><span data-stu-id="8e9db-109">For example, the result of 7 / 3 is 2.</span></span> <span data-ttu-id="8e9db-110">要确定 7 除以 3 的余数，请使用余数运算符 ([%](../../../csharp/language-reference/operators/modulus-operator.md))。</span><span class="sxs-lookup"><span data-stu-id="8e9db-110">To determine the remainder of 7 / 3, use the remainder operator ([%](../../../csharp/language-reference/operators/modulus-operator.md)).</span></span> <span data-ttu-id="8e9db-111">要获得有理数或分数形式的商，请将被除数或除数设为类型 `float` 或类型 `double`。</span><span class="sxs-lookup"><span data-stu-id="8e9db-111">To obtain a quotient as a rational number or fraction, give the dividend or divisor type `float` or type `double`.</span></span> <span data-ttu-id="8e9db-112">如果通过将数字置于小数点右侧的方式以十进制表示被除数或除数，则可以隐式地分配类型，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="8e9db-112">You can assign the type implicitly if you express the dividend or divisor as a decimal by putting a digit to the right side of the decimal point, as the following example shows.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e9db-113">示例</span><span class="sxs-lookup"><span data-stu-id="8e9db-113">Example</span></span>  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8e9db-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e9db-114">See Also</span></span>  
 [<span data-ttu-id="8e9db-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="8e9db-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8e9db-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8e9db-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8e9db-117">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="8e9db-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
