---
title: "-- 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4eb68143103d44defeac7191e7c4ce7d1ee90e9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="---operator-c-reference"></a><span data-ttu-id="ec53d-102">-- 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ec53d-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="ec53d-103">减量运算符 (`--`) 按 1 递减其操作数。</span><span class="sxs-lookup"><span data-stu-id="ec53d-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="ec53d-104">减量运算符可以在其操作数之前或之后出现：`--variable` 和 `variable--`。</span><span class="sxs-lookup"><span data-stu-id="ec53d-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="ec53d-105">第一种形式是前缀递减操作。</span><span class="sxs-lookup"><span data-stu-id="ec53d-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="ec53d-106">操作的结果是操作数递减“后”的值。</span><span class="sxs-lookup"><span data-stu-id="ec53d-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="ec53d-107">第二种形式是后缀递减操作。</span><span class="sxs-lookup"><span data-stu-id="ec53d-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="ec53d-108">操作的结果是操作数递减“前”的值。</span><span class="sxs-lookup"><span data-stu-id="ec53d-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec53d-109">备注</span><span class="sxs-lookup"><span data-stu-id="ec53d-109">Remarks</span></span>  
 <span data-ttu-id="ec53d-110">数值和枚举类型具有预定义的减量运算符。</span><span class="sxs-lookup"><span data-stu-id="ec53d-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="ec53d-111">用户定义的类型可以重载 `--` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="ec53d-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="ec53d-112">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="ec53d-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec53d-113">示例</span><span class="sxs-lookup"><span data-stu-id="ec53d-113">Example</span></span>  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="ec53d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec53d-114">See Also</span></span>  
 [<span data-ttu-id="ec53d-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="ec53d-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ec53d-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ec53d-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ec53d-117">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="ec53d-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
