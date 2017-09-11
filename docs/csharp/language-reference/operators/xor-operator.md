---
title: "^ 运算符（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ^_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
caps.latest.revision: 19
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
ms.openlocfilehash: f081dd2979930404639638179444adc05dd462e1
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="56524-102">^ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="56524-102">^ Operator (C# Reference)</span></span>
<span data-ttu-id="56524-103">针对整型类型和 `bool` 预定义了二元 `^` 运算符。</span><span class="sxs-lookup"><span data-stu-id="56524-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="56524-104">对于整型类型，`^` 会计算其操作数的按位异或。</span><span class="sxs-lookup"><span data-stu-id="56524-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="56524-105">对于 `bool` 操作数，`^` 计算其操作数的逻辑异或；即，当且仅当其一个操作数为 `true` 时，结果才为 `true`。</span><span class="sxs-lookup"><span data-stu-id="56524-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56524-106">备注</span><span class="sxs-lookup"><span data-stu-id="56524-106">Remarks</span></span>  
 <span data-ttu-id="56524-107">用户定义的类型可以重载 `^` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="56524-107">User-defined types can overload the `^` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="56524-108">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="56524-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56524-109">示例</span><span class="sxs-lookup"><span data-stu-id="56524-109">Example</span></span>  
 <span data-ttu-id="56524-110">[!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="56524-110">[!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]</span></span>  
  
 <span data-ttu-id="56524-111">上一示例中的 `0xf8 ^ 0x3f` 计算执行了以下两个二进制值的按位异或，这与十六进制值 F8 和 3F 对应：</span><span class="sxs-lookup"><span data-stu-id="56524-111">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>  
  
 `1111 1000`  
  
 `0011 1111`  
  
 <span data-ttu-id="56524-112">异或的结果是 `1100 0111`，即十六进制中的 C7。</span><span class="sxs-lookup"><span data-stu-id="56524-112">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56524-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56524-113">See Also</span></span>  
 <span data-ttu-id="56524-114">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="56524-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="56524-115">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="56524-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="56524-116">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="56524-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

