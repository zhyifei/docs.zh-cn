---
title: "隐式数值转换表（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f6b1705dca357fd2a155fc1ea9c7fe0f65bad8a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="58b4f-102">隐式数值转换表（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="58b4f-102">Implicit Numeric Conversions Table (C# Reference)</span></span>
<span data-ttu-id="58b4f-103">下表显示预定义隐式数值转换。</span><span class="sxs-lookup"><span data-stu-id="58b4f-103">The following table shows the predefined implicit numeric conversions.</span></span> <span data-ttu-id="58b4f-104">隐式转换可能会在许多情况下出现（包括方法调用和赋值语句）。</span><span class="sxs-lookup"><span data-stu-id="58b4f-104">Implicit conversions might occur in many situations, including method invoking and assignment statements.</span></span>  
  
|<span data-ttu-id="58b4f-105">From</span><span class="sxs-lookup"><span data-stu-id="58b4f-105">From</span></span>|<span data-ttu-id="58b4f-106">到</span><span class="sxs-lookup"><span data-stu-id="58b4f-106">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="58b4f-107">sbyte</span><span class="sxs-lookup"><span data-stu-id="58b4f-107">sbyte</span></span>](../../../csharp/language-reference/keywords/sbyte.md)|<span data-ttu-id="58b4f-108">`short`、`int`、`long`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="58b4f-108">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="58b4f-109">byte</span><span class="sxs-lookup"><span data-stu-id="58b4f-109">byte</span></span>](../../../csharp/language-reference/keywords/byte.md)|<span data-ttu-id="58b4f-110">`short`、`ushort`、`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="58b4f-110">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="58b4f-111">short</span><span class="sxs-lookup"><span data-stu-id="58b4f-111">short</span></span>](../../../csharp/language-reference/keywords/short.md)|<span data-ttu-id="58b4f-112">`int`、`long`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="58b4f-112">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="58b4f-113">ushort</span><span class="sxs-lookup"><span data-stu-id="58b4f-113">ushort</span></span>](../../../csharp/language-reference/keywords/ushort.md)|<span data-ttu-id="58b4f-114">`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`。</span><span class="sxs-lookup"><span data-stu-id="58b4f-114">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="58b4f-115">int</span><span class="sxs-lookup"><span data-stu-id="58b4f-115">int</span></span>](../../../csharp/language-reference/keywords/int.md)|<span data-ttu-id="58b4f-116">`long`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="58b4f-116">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="58b4f-117">uint</span><span class="sxs-lookup"><span data-stu-id="58b4f-117">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)|<span data-ttu-id="58b4f-118">`long`、`ulong`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="58b4f-118">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="58b4f-119">long</span><span class="sxs-lookup"><span data-stu-id="58b4f-119">long</span></span>](../../../csharp/language-reference/keywords/long.md)|<span data-ttu-id="58b4f-120">`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="58b4f-120">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="58b4f-121">char</span><span class="sxs-lookup"><span data-stu-id="58b4f-121">char</span></span>](../../../csharp/language-reference/keywords/char.md)|<span data-ttu-id="58b4f-122">`ushort`、`int`、`uint`、`long`、`ulong`、`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="58b4f-122">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="58b4f-123">float</span><span class="sxs-lookup"><span data-stu-id="58b4f-123">float</span></span>](../../../csharp/language-reference/keywords/float.md)|`double`|  
|[<span data-ttu-id="58b4f-124">ulong</span><span class="sxs-lookup"><span data-stu-id="58b4f-124">ulong</span></span>](../../../csharp/language-reference/keywords/ulong.md)|<span data-ttu-id="58b4f-125">`float`、`double` 或 `decimal`</span><span class="sxs-lookup"><span data-stu-id="58b4f-125">`float`, `double`, or `decimal`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58b4f-126">备注</span><span class="sxs-lookup"><span data-stu-id="58b4f-126">Remarks</span></span>  
  
-   <span data-ttu-id="58b4f-127">在从 `int`、`uint`、`long` 或 `ulong` 转换为 `float`，以及从 `long` 或 `ulong` 转换为 `double` 时，可能会丢失精度，但不会丢失量值。</span><span class="sxs-lookup"><span data-stu-id="58b4f-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`,  `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
-   <span data-ttu-id="58b4f-128">不存在针对 `char` 类型的隐式转换。</span><span class="sxs-lookup"><span data-stu-id="58b4f-128">There are no implicit conversions to the `char` type.</span></span>  
  
-   <span data-ttu-id="58b4f-129">浮点类型与 `decimal` 类型之间不存在隐式转换。</span><span class="sxs-lookup"><span data-stu-id="58b4f-129">There are no implicit conversions between floating-point types and the `decimal` type.</span></span>  
  
-   <span data-ttu-id="58b4f-130">`int` 类型的常数表达式可以转换为 `sbyte`、`byte`、`short`、`ushort`、`uint` 或 `ulong`，前提是常数表达式的值处于目标类型的范围内。</span><span class="sxs-lookup"><span data-stu-id="58b4f-130">A constant expression of type `int` can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided the value of the constant expression is within the range of the destination type.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="58b4f-131">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="58b4f-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="58b4f-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58b4f-132">See Also</span></span>  
 [<span data-ttu-id="58b4f-133">C# 参考</span><span class="sxs-lookup"><span data-stu-id="58b4f-133">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="58b4f-134">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="58b4f-134">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="58b4f-135">整型表</span><span class="sxs-lookup"><span data-stu-id="58b4f-135">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="58b4f-136">内置类型表</span><span class="sxs-lookup"><span data-stu-id="58b4f-136">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="58b4f-137">显式数值转换表</span><span class="sxs-lookup"><span data-stu-id="58b4f-137">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [<span data-ttu-id="58b4f-138">强制转换和类型转换</span><span class="sxs-lookup"><span data-stu-id="58b4f-138">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)
