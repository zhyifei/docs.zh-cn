---
title: unsafe 关键字（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: 79cb246c4094f02d1319d28fcc94d0d3d5bd9cb5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53128422"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="c7d45-102">unsafe（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c7d45-102">unsafe (C# Reference)</span></span>

<span data-ttu-id="c7d45-103">`unsafe` 关键字表示不安全上下文，该上下文是任何涉及指针的操作所必需的。</span><span class="sxs-lookup"><span data-stu-id="c7d45-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="c7d45-104">有关详细信息，请参阅[不安全代码和指针](../../programming-guide/unsafe-code-pointers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d45-104">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="c7d45-105">可在类型或成员的声明中使用 `unsafe` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="c7d45-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="c7d45-106">因此，类型或成员的整个正文范围均被视为不安全上下文。</span><span class="sxs-lookup"><span data-stu-id="c7d45-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="c7d45-107">以下面使用 `unsafe` 修饰符声明的方法为例：</span><span class="sxs-lookup"><span data-stu-id="c7d45-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="c7d45-108">不安全上下文的范围从参数列表扩展到方法的结尾，因此也可在以下参数列表中使用指针：</span><span class="sxs-lookup"><span data-stu-id="c7d45-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

<span data-ttu-id="c7d45-109">还可以使用不安全块从而能够使用该块内的不安全代码。</span><span class="sxs-lookup"><span data-stu-id="c7d45-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="c7d45-110">例如:</span><span class="sxs-lookup"><span data-stu-id="c7d45-110">For example:</span></span>

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="c7d45-111">若要编译不安全代码，必须指定 [/unsafe](../compiler-options/unsafe-compiler-option.md) 编译器选项。</span><span class="sxs-lookup"><span data-stu-id="c7d45-111">To compile unsafe code, you must specify the [/unsafe](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="c7d45-112">不能通过公共语言运行时验证不安全代码。</span><span class="sxs-lookup"><span data-stu-id="c7d45-112">Unsafe code is not verifiable by the common language runtime.</span></span>

## <a name="example"></a><span data-ttu-id="c7d45-113">示例</span><span class="sxs-lookup"><span data-stu-id="c7d45-113">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="c7d45-114">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="c7d45-114">C# language specification</span></span>

<span data-ttu-id="c7d45-115">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[不安全代码](~/_csharplang/spec/unsafe-code.md)。</span><span class="sxs-lookup"><span data-stu-id="c7d45-115">For more information, see [Unsafe code](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="c7d45-116">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="c7d45-116">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7d45-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7d45-117">See also</span></span>

- [<span data-ttu-id="c7d45-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c7d45-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c7d45-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c7d45-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c7d45-120">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="c7d45-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c7d45-121">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="c7d45-121">fixed Statement</span></span>](fixed-statement.md)
- [<span data-ttu-id="c7d45-122">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="c7d45-122">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="c7d45-123">固定大小的缓冲区</span><span class="sxs-lookup"><span data-stu-id="c7d45-123">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)