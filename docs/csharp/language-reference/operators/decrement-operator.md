---
title: "-- 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- --_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 100e68f3b07164b0cfb398a32f47137f2726943f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="---operator-c-reference"></a><span data-ttu-id="c3ff6-102">-- 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c3ff6-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="c3ff6-103">减量运算符 (`--`) 按 1 递减其操作数。</span><span class="sxs-lookup"><span data-stu-id="c3ff6-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="c3ff6-104">减量运算符可以在其操作数之前或之后出现：`--variable` 和 `variable--`。</span><span class="sxs-lookup"><span data-stu-id="c3ff6-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="c3ff6-105">第一种形式是前缀递减操作。</span><span class="sxs-lookup"><span data-stu-id="c3ff6-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="c3ff6-106">操作的结果是操作数递减“后”的值。</span><span class="sxs-lookup"><span data-stu-id="c3ff6-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="c3ff6-107">第二种形式是后缀递减操作。</span><span class="sxs-lookup"><span data-stu-id="c3ff6-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="c3ff6-108">操作的结果是操作数递减“前”的值。</span><span class="sxs-lookup"><span data-stu-id="c3ff6-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3ff6-109">备注</span><span class="sxs-lookup"><span data-stu-id="c3ff6-109">Remarks</span></span>  
 <span data-ttu-id="c3ff6-110">数值和枚举类型具有预定义的减量运算符。</span><span class="sxs-lookup"><span data-stu-id="c3ff6-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="c3ff6-111">用户定义的类型可以重载 `--` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="c3ff6-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="c3ff6-112">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="c3ff6-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3ff6-113">示例</span><span class="sxs-lookup"><span data-stu-id="c3ff6-113">Example</span></span>  
 <span data-ttu-id="c3ff6-114">[!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c3ff6-114">[!code-cs[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3ff6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3ff6-115">See Also</span></span>  
 <span data-ttu-id="c3ff6-116">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c3ff6-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c3ff6-117">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c3ff6-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="c3ff6-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="c3ff6-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

