---
title: 隐式数值转换表 - C# 参考
ms.custom: seodec18
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 9c3efe1dbea355e8bc00ef44e08efcc9d0e0bdca
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424170"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="80638-102">隐式数值转换表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="80638-102">Implicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="80638-103">下表显示 .NET 数值类型之间的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="80638-103">The following table shows the predefined implicit conversions between .NET numeric types.</span></span>
  
|<span data-ttu-id="80638-104">From</span><span class="sxs-lookup"><span data-stu-id="80638-104">From</span></span>|<span data-ttu-id="80638-105">到</span><span class="sxs-lookup"><span data-stu-id="80638-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="80638-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="80638-106">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="80638-107">`short`、`int`、`long`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="80638-107">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="80638-108">byte</span><span class="sxs-lookup"><span data-stu-id="80638-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="80638-109">`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="80638-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="80638-110">char</span><span class="sxs-lookup"><span data-stu-id="80638-110">char</span></span>](char.md)|<span data-ttu-id="80638-111">`ushort`、`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="80638-111">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="80638-112">short</span><span class="sxs-lookup"><span data-stu-id="80638-112">short</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="80638-113">`int`、`long`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="80638-113">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="80638-114">ushort</span><span class="sxs-lookup"><span data-stu-id="80638-114">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="80638-115">`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`。</span><span class="sxs-lookup"><span data-stu-id="80638-115">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="80638-116">int</span><span class="sxs-lookup"><span data-stu-id="80638-116">int</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="80638-117">`long`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="80638-117">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="80638-118">uint</span><span class="sxs-lookup"><span data-stu-id="80638-118">uint</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="80638-119">`long`、`ulong`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="80638-119">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="80638-120">long</span><span class="sxs-lookup"><span data-stu-id="80638-120">long</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="80638-121">`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="80638-121">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="80638-122">ulong</span><span class="sxs-lookup"><span data-stu-id="80638-122">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="80638-123">`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="80638-123">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="80638-124">float</span><span class="sxs-lookup"><span data-stu-id="80638-124">float</span></span>](float.md)|`double`|  
  
## <a name="remarks"></a><span data-ttu-id="80638-125">备注</span><span class="sxs-lookup"><span data-stu-id="80638-125">Remarks</span></span>  

- <span data-ttu-id="80638-126">任何[整型类型](../builtin-types/integral-numeric-types.md)都可以隐式转换为任何[浮点类型](floating-point-types-table.md)。</span><span class="sxs-lookup"><span data-stu-id="80638-126">Any [integral type](../builtin-types/integral-numeric-types.md) is implicitly convertible to any [floating-point type](floating-point-types-table.md).</span></span>

- <span data-ttu-id="80638-127">在从 `int`、`uint`、`long` 或 `ulong` 转换为 `float`，以及从 `long` 或 `ulong` 转换为 `double` 时，可能会丢失精度，但不会丢失量值。</span><span class="sxs-lookup"><span data-stu-id="80638-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
- <span data-ttu-id="80638-128">不存在针对 `char`、`byte` 和 `sbyte` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="80638-128">There are no implicit conversions to the `char`, `byte`, and `sbyte` types.</span></span>  

- <span data-ttu-id="80638-129">不存在从 `double` 和 `decimal` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="80638-129">There are no implicit conversions from the `double` and `decimal` types.</span></span>
  
- <span data-ttu-id="80638-130">`decimal` 类型和 `float` 或 `double` 类型之间不存在隐式转换。</span><span class="sxs-lookup"><span data-stu-id="80638-130">There are no implicit conversions between the `decimal` type and the `float` or `double` types.</span></span>  
  
- <span data-ttu-id="80638-131">类型 `int` 的常量表达式的值（例如，由整数型字面量表示的值）可以转换为 `sbyte`、`byte`、`short`、`ushort`、`uint` 或 `ulong`，前提是它在目标类型的范围内：</span><span class="sxs-lookup"><span data-stu-id="80638-131">A value of a constant expression of type `int` (for example, a value represented by an integral literal) can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

<span data-ttu-id="80638-132">有关隐式转换的详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[隐式转换](~/_csharplang/spec/conversions.md#implicit-conversions)章节。</span><span class="sxs-lookup"><span data-stu-id="80638-132">For more information about implicit conversions, see the [Implicit conversions](~/_csharplang/spec/conversions.md#implicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="80638-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="80638-133">See also</span></span>

- [<span data-ttu-id="80638-134">C# 参考</span><span class="sxs-lookup"><span data-stu-id="80638-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="80638-135">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="80638-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="80638-136">整型类型</span><span class="sxs-lookup"><span data-stu-id="80638-136">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="80638-137">浮点型表</span><span class="sxs-lookup"><span data-stu-id="80638-137">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="80638-138">内置类型表</span><span class="sxs-lookup"><span data-stu-id="80638-138">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="80638-139">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="80638-139">Explicit numeric conversions table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="80638-140">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="80638-140">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
