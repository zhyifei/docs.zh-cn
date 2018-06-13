---
title: -- 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
ms.openlocfilehash: 25f301bc0b2bc9bf51b0a44f26b2efabae00e452
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288796"
---
# <a name="---operator-c-reference"></a><span data-ttu-id="7a928-102">-- 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="7a928-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="7a928-103">减量运算符 (`--`) 按 1 递减其操作数。</span><span class="sxs-lookup"><span data-stu-id="7a928-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="7a928-104">减量运算符可以在其操作数之前或之后出现：`--variable` 和 `variable--`。</span><span class="sxs-lookup"><span data-stu-id="7a928-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="7a928-105">第一种形式是前缀递减操作。</span><span class="sxs-lookup"><span data-stu-id="7a928-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="7a928-106">操作的结果是操作数递减“后”的值。</span><span class="sxs-lookup"><span data-stu-id="7a928-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="7a928-107">第二种形式是后缀递减操作。</span><span class="sxs-lookup"><span data-stu-id="7a928-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="7a928-108">操作的结果是操作数递减“前”的值。</span><span class="sxs-lookup"><span data-stu-id="7a928-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a928-109">备注</span><span class="sxs-lookup"><span data-stu-id="7a928-109">Remarks</span></span>  
 <span data-ttu-id="7a928-110">数值和枚举类型具有预定义的减量运算符。</span><span class="sxs-lookup"><span data-stu-id="7a928-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="7a928-111">用户定义的类型可以重载 `--` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="7a928-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="7a928-112">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="7a928-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7a928-113">示例</span><span class="sxs-lookup"><span data-stu-id="7a928-113">Example</span></span>  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="7a928-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a928-114">See Also</span></span>  
 [<span data-ttu-id="7a928-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="7a928-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7a928-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7a928-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7a928-117">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="7a928-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
