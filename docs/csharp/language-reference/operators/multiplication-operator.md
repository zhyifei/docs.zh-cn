---
title: '* 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: f4490c4632d9344eb879ea55c20787b838781d91
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333728"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="7e31a-102">\* 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="7e31a-102">\* operator (C# Reference)</span></span>

<span data-ttu-id="7e31a-103">乘法运算符 (`*`) 计算操作数的乘积。</span><span class="sxs-lookup"><span data-stu-id="7e31a-103">The multiplication operator (`*`) computes the product of its operands.</span></span> <span data-ttu-id="7e31a-104">所有数值类型都具有预定义的乘法运算符。</span><span class="sxs-lookup"><span data-stu-id="7e31a-104">All numeric types have predefined multiplication operators.</span></span>

<span data-ttu-id="7e31a-105">`*` 还用作取消引用运算符，用于对指针执行读取和写入操作。</span><span class="sxs-lookup"><span data-stu-id="7e31a-105">`*` also serves as the dereference operator, which allows reading and writing to a pointer.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e31a-106">备注</span><span class="sxs-lookup"><span data-stu-id="7e31a-106">Remarks</span></span>

<span data-ttu-id="7e31a-107">`*` 运算符还用于声明指针类型和取消引用指针。</span><span class="sxs-lookup"><span data-stu-id="7e31a-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="7e31a-108">此运算符仅可用于不安全的上下文，通过使用 [unsafe](../keywords/unsafe.md) 关键字表示，且需要 [/unsafe](../compiler-options/unsafe-compiler-option.md) 编译器选项。</span><span class="sxs-lookup"><span data-stu-id="7e31a-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../keywords/unsafe.md) keyword, and requiring the [/unsafe](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="7e31a-109">取消引用运算符也称为间接寻址运算符。</span><span class="sxs-lookup"><span data-stu-id="7e31a-109">The dereference operator is also known as the indirection operator.</span></span>

<span data-ttu-id="7e31a-110">用户定义的类型可以重载二元 `*` 运算符（请参阅[运算符](../keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="7e31a-110">User-defined types can overload the binary `*` operator (see [operator](../keywords/operator.md)).</span></span> <span data-ttu-id="7e31a-111">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="7e31a-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>

## <a name="example"></a><span data-ttu-id="7e31a-112">示例</span><span class="sxs-lookup"><span data-stu-id="7e31a-112">Example</span></span>

[!code-csharp-interactive[csRefOperators#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#50)]

## <a name="example"></a><span data-ttu-id="7e31a-113">示例</span><span class="sxs-lookup"><span data-stu-id="7e31a-113">Example</span></span>

[!code-csharp[csRefOperators#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#51)]

## <a name="see-also"></a><span data-ttu-id="7e31a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e31a-114">See also</span></span>

- [<span data-ttu-id="7e31a-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="7e31a-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7e31a-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7e31a-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7e31a-117">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="7e31a-117">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="7e31a-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="7e31a-118">C# Operators</span></span>](index.md)