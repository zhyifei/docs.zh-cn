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
ms.openlocfilehash: 152be2d81d1bf340b839d74f169d63d7260f7ca5
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333702"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="74b61-102">^ 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="74b61-102">^ operator (C# Reference)</span></span>

<span data-ttu-id="74b61-103">针对整型类型和 `bool` 预定义了二元 `^` 运算符。</span><span class="sxs-lookup"><span data-stu-id="74b61-103">Binary `^` operators are predefined for the integral types and `bool`.</span></span> <span data-ttu-id="74b61-104">对于整型类型，`^` 会计算其操作数的按位异或。</span><span class="sxs-lookup"><span data-stu-id="74b61-104">For integral types, `^` computes the bitwise exclusive-OR of its operands.</span></span> <span data-ttu-id="74b61-105">对于 `bool` 操作数，`^` 计算其操作数的逻辑异或；即，当且仅当其一个操作数为 `true` 时，结果才为 `true`。</span><span class="sxs-lookup"><span data-stu-id="74b61-105">For `bool` operands, `^` computes the logical exclusive-or of its operands; that is, the result is `true` if and only if exactly one of its operands is `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="74b61-106">备注</span><span class="sxs-lookup"><span data-stu-id="74b61-106">Remarks</span></span>

<span data-ttu-id="74b61-107">用户定义的类型可以重载 `^` 运算符（请参阅[运算符](../keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="74b61-107">User-defined types can overload the `^` operator (see [operator](../keywords/operator.md)).</span></span> <span data-ttu-id="74b61-108">对整数类型的操作通常可用于枚举。</span><span class="sxs-lookup"><span data-stu-id="74b61-108">Operations on integral types are generally allowed on enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="74b61-109">示例</span><span class="sxs-lookup"><span data-stu-id="74b61-109">Example</span></span>

[!code-csharp[csRefOperators#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#30)]

<span data-ttu-id="74b61-110">上一示例中的 `0xf8 ^ 0x3f` 计算执行了以下两个二进制值的按位异或，这与十六进制值 F8 和 3F 对应：</span><span class="sxs-lookup"><span data-stu-id="74b61-110">The computation of `0xf8 ^ 0x3f` in the previous example performs a bitwise exclusive-OR of the following two binary values, which correspond to the hexadecimal values F8 and 3F:</span></span>

`1111 1000`

`0011 1111`

<span data-ttu-id="74b61-111">异或的结果是 `1100 0111`，即十六进制中的 C7。</span><span class="sxs-lookup"><span data-stu-id="74b61-111">The result of the exclusive-OR is `1100 0111`, which is C7 in hexadecimal.</span></span>

## <a name="see-also"></a><span data-ttu-id="74b61-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="74b61-112">See Also</span></span>

- [<span data-ttu-id="74b61-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="74b61-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="74b61-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="74b61-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="74b61-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="74b61-115">C# operators</span></span>](index.md)
