---
title: 非托管类型 - C# 参考
ms.date: 07/23/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 2b675be5dbc61006725549f4b69284326650401d
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512074"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="dd244-102">非托管类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="dd244-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="dd244-103">**非托管类型**指任何不是引用类型或构造类型（包含至少一个类型参数）的类型，且在任何级别的嵌套中不含引用类型或构造类型字段。</span><span class="sxs-lookup"><span data-stu-id="dd244-103">An **unmanaged type** is any type that isn't a reference type or constructed type (a type that includes at least one type argument), and doesn't contain reference type or constructed type fields at any level of nesting.</span></span> <span data-ttu-id="dd244-104">换言之，非托管类型即为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="dd244-104">In other words, an unmanaged type is one of the following:</span></span>

- <span data-ttu-id="dd244-105">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char`、`float`、`double`、`decimal` 或 `bool`</span><span class="sxs-lookup"><span data-stu-id="dd244-105">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="dd244-106">任何[枚举](../keywords/enum.md)类型</span><span class="sxs-lookup"><span data-stu-id="dd244-106">Any [enum](../keywords/enum.md) type</span></span>
- <span data-ttu-id="dd244-107">任何[指针](../../programming-guide/unsafe-code-pointers/pointer-types.md)类型</span><span class="sxs-lookup"><span data-stu-id="dd244-107">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="dd244-108">任何不是[构造](../keywords/struct.md)类型且仅包含非托管类型字段的用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="dd244-108">Any user-defined [struct](../keywords/struct.md) type that is not a constructed type and contains fields of unmanaged types only</span></span>

<span data-ttu-id="dd244-109">从 C# 7.3 开始，可使用 [`unmanaged` 约束](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint)指定：类型参数为“非指针非托管类型”。</span><span class="sxs-lookup"><span data-stu-id="dd244-109">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer unmanaged type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="dd244-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="dd244-110">C# language specification</span></span>

<span data-ttu-id="dd244-111">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[指针类型](~/_csharplang/spec/unsafe-code.md#pointer-types)部分。</span><span class="sxs-lookup"><span data-stu-id="dd244-111">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dd244-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd244-112">See also</span></span>

- [<span data-ttu-id="dd244-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="dd244-113">C# reference</span></span>](../index.md)
- [<span data-ttu-id="dd244-114">指针类型</span><span class="sxs-lookup"><span data-stu-id="dd244-114">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="dd244-115">内存和跨度相关类型</span><span class="sxs-lookup"><span data-stu-id="dd244-115">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="dd244-116">sizeof 运算符</span><span class="sxs-lookup"><span data-stu-id="dd244-116">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="dd244-117">stackalloc 运算符</span><span class="sxs-lookup"><span data-stu-id="dd244-117">stackalloc operator</span></span>](../operators/stackalloc.md)
