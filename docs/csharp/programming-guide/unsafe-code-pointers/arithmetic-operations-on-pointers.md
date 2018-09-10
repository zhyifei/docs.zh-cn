---
title: 指针的算术运算（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: 3694699466f7a200eecd5eef85f60fa19f9584a8
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43862298"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="ba070-102">指针的算术运算（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="ba070-102">Arithmetic Operations on Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="ba070-103">本主题讨论如何使用算术运算符 `+` 和 **-** 操作指针。</span><span class="sxs-lookup"><span data-stu-id="ba070-103">This topic discusses using the arithmetic operators `+` and **-** to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ba070-104">不能对 void 指针执行任何算术运算。</span><span class="sxs-lookup"><span data-stu-id="ba070-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="ba070-105">对指针执行加减数值操作</span><span class="sxs-lookup"><span data-stu-id="ba070-105">Adding and Subtracting Numeric Values to or From Pointers</span></span>  
 <span data-ttu-id="ba070-106">可以将类型为 [int](../../../csharp/language-reference/keywords/int.md)、[uint](../../../csharp/language-reference/keywords/uint.md)、[long](../../../csharp/language-reference/keywords/long.md) 或 [ulong](../../../csharp/language-reference/keywords/ulong.md) 的值 `n` 与 `void*` 以外任何类型的指针 `p` 相加。</span><span class="sxs-lookup"><span data-stu-id="ba070-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer, `p`,of any type except `void*`.</span></span> <span data-ttu-id="ba070-107">结果 `p+n` 是加上 `n * sizeof(p) to the address of p` 得到的指针。</span><span class="sxs-lookup"><span data-stu-id="ba070-107">The result `p+n` is the pointer resulting from adding `n * sizeof(p) to the address of p`.</span></span> <span data-ttu-id="ba070-108">同样，`p-n` 是从 `p` 的地址中减去 `n * sizeof(p)` 得到的指针。</span><span class="sxs-lookup"><span data-stu-id="ba070-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(p)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="ba070-109">指针相减</span><span class="sxs-lookup"><span data-stu-id="ba070-109">Subtracting Pointers</span></span>  
 <span data-ttu-id="ba070-110">也可以对相同类型的指针进行减法运算。</span><span class="sxs-lookup"><span data-stu-id="ba070-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="ba070-111">计算结果的类型始终为 `long`。</span><span class="sxs-lookup"><span data-stu-id="ba070-111">The result is always of the type `long`.</span></span> <span data-ttu-id="ba070-112">例如，如果 `p1` 和 `p2` 都是类型为 `pointer-type*` 的指针，则表达式 `p1-p2` 的计算结果为：</span><span class="sxs-lookup"><span data-stu-id="ba070-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 <span data-ttu-id="ba070-113">当算术运算溢出指针范围时，不会产生异常，并且结果取决于实现。</span><span class="sxs-lookup"><span data-stu-id="ba070-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba070-114">示例</span><span class="sxs-lookup"><span data-stu-id="ba070-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ba070-115">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ba070-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ba070-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba070-116">See Also</span></span>

- [<span data-ttu-id="ba070-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ba070-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="ba070-118">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="ba070-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="ba070-119">指针表达式</span><span class="sxs-lookup"><span data-stu-id="ba070-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="ba070-120">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="ba070-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="ba070-121">操作指针</span><span class="sxs-lookup"><span data-stu-id="ba070-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="ba070-122">指针类型</span><span class="sxs-lookup"><span data-stu-id="ba070-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="ba070-123">类型</span><span class="sxs-lookup"><span data-stu-id="ba070-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="ba070-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="ba070-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="ba070-125">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="ba070-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="ba070-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="ba070-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
