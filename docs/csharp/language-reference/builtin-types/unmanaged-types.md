---
title: 非托管类型 - C# 参考
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 8a4599514115aa21f17c32848ce203fea704072e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846454"
---
# <a name="unmanaged-types-c-reference"></a><span data-ttu-id="fd7f1-102">非托管类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="fd7f1-102">Unmanaged types (C# reference)</span></span>

<span data-ttu-id="fd7f1-103">如果某个类型是以下类型之一，则它是非托管类型  ：</span><span class="sxs-lookup"><span data-stu-id="fd7f1-103">A type is an **unmanaged type** if it's any of the following types:</span></span>

- <span data-ttu-id="fd7f1-104">`sbyte`、`byte`、`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`char`、`float`、`double`、`decimal` 或 `bool`</span><span class="sxs-lookup"><span data-stu-id="fd7f1-104">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, or `bool`</span></span>
- <span data-ttu-id="fd7f1-105">任何[枚举](enum.md)类型</span><span class="sxs-lookup"><span data-stu-id="fd7f1-105">Any [enum](enum.md) type</span></span>
- <span data-ttu-id="fd7f1-106">任何[指针](../../programming-guide/unsafe-code-pointers/pointer-types.md)类型</span><span class="sxs-lookup"><span data-stu-id="fd7f1-106">Any [pointer](../../programming-guide/unsafe-code-pointers/pointer-types.md) type</span></span>
- <span data-ttu-id="fd7f1-107">任何用户定义的 [struct](struct.md) 类型，只包含非托管类型的字段，并且在 C# 7.3 及更早版本中，不是构造类型（包含至少一个类型参数的类型）</span><span class="sxs-lookup"><span data-stu-id="fd7f1-107">Any user-defined [struct](struct.md) type that contains fields of unmanaged types only and, in C# 7.3 and earlier, is not a constructed type (a type that includes at least one type argument)</span></span>

<span data-ttu-id="fd7f1-108">从 C# 7.3 开始，可使用 [`unmanaged` 约束](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint)指定：类型参数为“非指针、不可为 null 的非托管类型”。</span><span class="sxs-lookup"><span data-stu-id="fd7f1-108">Beginning with C# 7.3, you can use the [`unmanaged` constraint](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) to specify that a type parameter is a non-pointer, non-nullable unmanaged type.</span></span>

<span data-ttu-id="fd7f1-109">从 C# 8.0 开始，仅包含非托管类型的字段的*构造*结构类型也是非托管类型，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="fd7f1-109">Beginning with C# 8.0, a *constructed* struct type that contains fields of unmanaged types only is also unmanaged, as the following example shows:</span></span>

[!code-csharp[unmanaged constructed types](snippets/UnmanagedTypes.cs#ProgramExample)]

<span data-ttu-id="fd7f1-110">泛型结构可以是非托管类型的源，也可以是不是非托管构造类型的源。</span><span class="sxs-lookup"><span data-stu-id="fd7f1-110">A generic struct may be the source of both unmanaged and not unmanaged constructed types.</span></span> <span data-ttu-id="fd7f1-111">前面的示例定义一个泛型结构 `Coords<T>`，并提供非托管构造类型的示例。</span><span class="sxs-lookup"><span data-stu-id="fd7f1-111">The preceding example defines a generic struct `Coords<T>` and presents the examples of unmanaged constructed types.</span></span> <span data-ttu-id="fd7f1-112">不是非托管类型情况的示例是 `Coords<object>`。</span><span class="sxs-lookup"><span data-stu-id="fd7f1-112">The example of not an unmanaged type is `Coords<object>`.</span></span> <span data-ttu-id="fd7f1-113">它不是非托管性质，因为它具有不是非托管性质的 `object` 类型的字段。</span><span class="sxs-lookup"><span data-stu-id="fd7f1-113">It's not unmanaged because it has the fields of the `object` type, which is not unmanaged.</span></span> <span data-ttu-id="fd7f1-114">如果你希望所有  构造类型都是非托管类型，请在泛型结构的定义中使用 `unmanaged` 约束：</span><span class="sxs-lookup"><span data-stu-id="fd7f1-114">If you want *all* constructed types to be unmanaged types, use the `unmanaged` constraint in the definition of a generic struct:</span></span>

[!code-csharp[unmanaged constraint in type definition](snippets/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a><span data-ttu-id="fd7f1-115">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="fd7f1-115">C# language specification</span></span>

<span data-ttu-id="fd7f1-116">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/unsafe-code.md#pointer-types)的[指针类型](~/_csharplang/spec/introduction.md)部分。</span><span class="sxs-lookup"><span data-stu-id="fd7f1-116">For more information, see the [Pointer types](~/_csharplang/spec/unsafe-code.md#pointer-types) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fd7f1-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd7f1-117">See also</span></span>

- [<span data-ttu-id="fd7f1-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="fd7f1-118">C# reference</span></span>](../index.md)
- [<span data-ttu-id="fd7f1-119">指针类型</span><span class="sxs-lookup"><span data-stu-id="fd7f1-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="fd7f1-120">内存和跨度相关类型</span><span class="sxs-lookup"><span data-stu-id="fd7f1-120">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="fd7f1-121">sizeof 运算符</span><span class="sxs-lookup"><span data-stu-id="fd7f1-121">sizeof operator</span></span>](../operators/sizeof.md)
- [<span data-ttu-id="fd7f1-122">stackalloc 运算符</span><span class="sxs-lookup"><span data-stu-id="fd7f1-122">stackalloc operator</span></span>](../operators/stackalloc.md)
