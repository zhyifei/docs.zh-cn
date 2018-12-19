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
ms.openlocfilehash: 98774a0f7ad86e43178c6d0216e29e7b4767f3f2
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235249"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="db1ae-102">隐式数值转换表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="db1ae-102">Implicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="db1ae-103">下表显示 .NET 数值类型之间的预定义隐式转换。</span><span class="sxs-lookup"><span data-stu-id="db1ae-103">The following table shows the predefined implicit conversions between .NET numeric types.</span></span>
  
|<span data-ttu-id="db1ae-104">From</span><span class="sxs-lookup"><span data-stu-id="db1ae-104">From</span></span>|<span data-ttu-id="db1ae-105">到</span><span class="sxs-lookup"><span data-stu-id="db1ae-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="db1ae-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="db1ae-106">sbyte</span></span>](sbyte.md)|<span data-ttu-id="db1ae-107">`short`、`int`、`long`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="db1ae-107">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="db1ae-108">byte</span><span class="sxs-lookup"><span data-stu-id="db1ae-108">byte</span></span>](byte.md)|<span data-ttu-id="db1ae-109">`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="db1ae-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="db1ae-110">short</span><span class="sxs-lookup"><span data-stu-id="db1ae-110">short</span></span>](short.md)|<span data-ttu-id="db1ae-111">`int`、`long`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="db1ae-111">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="db1ae-112">ushort</span><span class="sxs-lookup"><span data-stu-id="db1ae-112">ushort</span></span>](ushort.md)|<span data-ttu-id="db1ae-113">`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`。</span><span class="sxs-lookup"><span data-stu-id="db1ae-113">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="db1ae-114">int</span><span class="sxs-lookup"><span data-stu-id="db1ae-114">int</span></span>](int.md)|<span data-ttu-id="db1ae-115">`long`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="db1ae-115">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="db1ae-116">uint</span><span class="sxs-lookup"><span data-stu-id="db1ae-116">uint</span></span>](uint.md)|<span data-ttu-id="db1ae-117">`long`、`ulong`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="db1ae-117">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="db1ae-118">long</span><span class="sxs-lookup"><span data-stu-id="db1ae-118">long</span></span>](long.md)|<span data-ttu-id="db1ae-119">`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="db1ae-119">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="db1ae-120">char</span><span class="sxs-lookup"><span data-stu-id="db1ae-120">char</span></span>](char.md)|<span data-ttu-id="db1ae-121">`ushort`、`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="db1ae-121">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="db1ae-122">float</span><span class="sxs-lookup"><span data-stu-id="db1ae-122">float</span></span>](float.md)|`double`|  
|[<span data-ttu-id="db1ae-123">ulong</span><span class="sxs-lookup"><span data-stu-id="db1ae-123">ulong</span></span>](ulong.md)|<span data-ttu-id="db1ae-124">`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="db1ae-124">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db1ae-125">备注</span><span class="sxs-lookup"><span data-stu-id="db1ae-125">Remarks</span></span>  

- <span data-ttu-id="db1ae-126">任何[整型类型](integral-types-table.md)都可以隐式转换为任何[浮点类型](floating-point-types-table.md)。</span><span class="sxs-lookup"><span data-stu-id="db1ae-126">Any [integral type](integral-types-table.md) is implicitly convertible to any [floating-point type](floating-point-types-table.md).</span></span>

- <span data-ttu-id="db1ae-127">在从 `int`、`uint`、`long` 或 `ulong` 转换为 `float`，以及从 `long` 或 `ulong` 转换为 `double` 时，可能会丢失精度，但不会丢失量值。</span><span class="sxs-lookup"><span data-stu-id="db1ae-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
- <span data-ttu-id="db1ae-128">不存在针对 `char` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="db1ae-128">There are no implicit conversions to the `char` type.</span></span>  
  
- <span data-ttu-id="db1ae-129">在 `float` 和 `double` 类型以及 `decimal` 类型之间不存在隐式转换。</span><span class="sxs-lookup"><span data-stu-id="db1ae-129">There are no implicit conversions between the `float` and `double` types and the `decimal` type.</span></span>  
  
- <span data-ttu-id="db1ae-130">类型 `int` 的常量表达式的值（例如，由整数型字面量表示的值）可以转换为 `sbyte`、`byte`、`short``ushort`、`uint` 或 `ulong`，前提是它在目标类型的范围内：</span><span class="sxs-lookup"><span data-stu-id="db1ae-130">A value of a constant expression of type `int` (for example, a value represented by an integral literal) can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

<span data-ttu-id="db1ae-131">有关隐式转换的详细信息，请参阅 [C# 语言规范](../language-specification/index.md)的[隐式转换](~/_csharplang/spec/conversions.md#implicit-conversions)章节。</span><span class="sxs-lookup"><span data-stu-id="db1ae-131">For more information about implicit conversions, see the [Implicit conversions](~/_csharplang/spec/conversions.md#implicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="db1ae-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="db1ae-132">See also</span></span>

- [<span data-ttu-id="db1ae-133">C# 参考</span><span class="sxs-lookup"><span data-stu-id="db1ae-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="db1ae-134">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="db1ae-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="db1ae-135">整型类型表</span><span class="sxs-lookup"><span data-stu-id="db1ae-135">Integral types table</span></span>](integral-types-table.md)
- [<span data-ttu-id="db1ae-136">浮点型表</span><span class="sxs-lookup"><span data-stu-id="db1ae-136">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="db1ae-137">内置类型表</span><span class="sxs-lookup"><span data-stu-id="db1ae-137">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="db1ae-138">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="db1ae-138">Explicit numeric conversions table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="db1ae-139">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="db1ae-139">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
