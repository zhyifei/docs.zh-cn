---
title: ^ 运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ^_CSharpKeyword
helpviewer_keywords:
- ^ operator [C#]
- bitwise exclusive OR operator [C#]
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
ms.openlocfilehash: f6f09f197502af1bc38bcdef97dd1db0ad9c7c08
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236942"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="f1763-102">^ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f1763-102">^ Operator (C# Reference)</span></span>
<span data-ttu-id="f1763-103">针对整型类型和 `bool` 预定义了二元 `^` 运算符。</span><span class="sxs-lookup"><span data-stu-id="f1763-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="f1763-104">对于整型类型，`^` 会计算其操作数的按位异或。</span><span class="sxs-lookup"><span data-stu-id="f1763-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="f1763-105">对于 `bool` 操作数，`^` 计算其操作数的逻辑异或；即，当且仅当其一个操作数为 `true` 时，结果才为 `true`。</span><span class="sxs-lookup"><span data-stu-id="f1763-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1763-106">备注</span><span class="sxs-lookup"><span data-stu-id="f1763-106">Remarks</span></span>  
 <span data-ttu-id="f1763-107">用户定义的类型可以重载 `^` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="f1763-107">User-defined types can overload the `^` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="f1763-108">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="f1763-108">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1763-109">示例</span><span class="sxs-lookup"><span data-stu-id="f1763-109">Example</span></span>  
 [!code-csharp[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-operator_1.cs)]  
  
 <span data-ttu-id="f1763-110">上一示例中的 `0xf8 ^ 0x3f` 计算执行了以下两个二进制值的按位异或，这与十六进制值 F8 和 3F 对应：</span><span class="sxs-lookup"><span data-stu-id="f1763-110">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>  
  
 `1111 1000`  
  
 `0011 1111`  
  
 <span data-ttu-id="f1763-111">异或的结果是 `1100 0111`，即十六进制中的 C7。</span><span class="sxs-lookup"><span data-stu-id="f1763-111">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1763-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1763-112">See Also</span></span>

- [<span data-ttu-id="f1763-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f1763-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="f1763-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f1763-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="f1763-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="f1763-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
