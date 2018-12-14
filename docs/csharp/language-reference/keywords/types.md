---
title: 类型（C# 参考）
ms.date: 07/20/2015
helpviewer_keywords:
- types [C#]
- data types [C#], type system
ms.assetid: 16b984df-f417-4e02-b1e6-4589d4a614ea
ms.openlocfilehash: f5a3ad9fef108c1eec2ba63d68bc5015d2f6c430
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53142952"
---
# <a name="types-c-reference"></a><span data-ttu-id="d35d7-102">类型（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="d35d7-102">Types (C# Reference)</span></span>

<span data-ttu-id="d35d7-103">C# 类型化系统包含以下类别：</span><span class="sxs-lookup"><span data-stu-id="d35d7-103">The C# typing system contains the following categories:</span></span>

- [<span data-ttu-id="d35d7-104">值类型</span><span class="sxs-lookup"><span data-stu-id="d35d7-104">Value types</span></span>](value-types.md)

- [<span data-ttu-id="d35d7-105">引用类型</span><span class="sxs-lookup"><span data-stu-id="d35d7-105">Reference types</span></span>](reference-types.md)

- [<span data-ttu-id="d35d7-106">指针类型</span><span class="sxs-lookup"><span data-stu-id="d35d7-106">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)

 <span data-ttu-id="d35d7-107">值类型的变量可存储数据，引用类型的变量可存储对实际数据的引用。</span><span class="sxs-lookup"><span data-stu-id="d35d7-107">Variables that are value types store data, and those that are reference types store references to the actual data.</span></span> <span data-ttu-id="d35d7-108">引用类型的实例也被称作对象。</span><span class="sxs-lookup"><span data-stu-id="d35d7-108">Instances of reference types are also referred to as objects.</span></span> <span data-ttu-id="d35d7-109">仅在[不安全](unsafe.md)模式下才可使用指针类型。</span><span class="sxs-lookup"><span data-stu-id="d35d7-109">Pointer types can be used only in [unsafe](unsafe.md) mode.</span></span>

 <span data-ttu-id="d35d7-110">可将值类型转换为引用类型，并通过[装箱和取消装箱](../../../csharp/programming-guide/types/boxing-and-unboxing.md)再次转换回值类型。</span><span class="sxs-lookup"><span data-stu-id="d35d7-110">It's possible to convert a value type to a reference type, and back again to a value type, by using [boxing and unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span> <span data-ttu-id="d35d7-111">除已装箱值类型外，不可将引用类型转换为值类型。</span><span class="sxs-lookup"><span data-stu-id="d35d7-111">With the exception of a boxed value type, you cannot convert a reference type to a value type.</span></span>

 <span data-ttu-id="d35d7-112">本部分还介绍了 [void](void.md)。</span><span class="sxs-lookup"><span data-stu-id="d35d7-112">This section also introduces [void](void.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d35d7-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d35d7-113">See also</span></span>

- [<span data-ttu-id="d35d7-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="d35d7-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d35d7-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d35d7-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d35d7-116">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="d35d7-116">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="d35d7-117">类型参考表</span><span class="sxs-lookup"><span data-stu-id="d35d7-117">Reference Tables for Types</span></span>](reference-tables-for-types.md)
- [<span data-ttu-id="d35d7-118">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="d35d7-118">Casting and Type Conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="d35d7-119">类型</span><span class="sxs-lookup"><span data-stu-id="d35d7-119">Types</span></span>](../../programming-guide/types/index.md)
