---
title: 设置数值结果表的格式 - C# 参考
ms.custom: seodec18
description: 了解 C# 标准数字格式字符串
ms.date: 09/20/2018
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: 0f2b5bc54a0e9055d64a95dc229eaadf66687b43
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421965"
---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="b47cd-103">设置数值结果表的格式（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b47cd-103">Formatting numeric results table (C# Reference)</span></span>

<span data-ttu-id="b47cd-104">下表显示了设置数值结果格式的受支持格式说明符。</span><span class="sxs-lookup"><span data-stu-id="b47cd-104">The following table shows supported format specifiers for formatting numeric results.</span></span> <span data-ttu-id="b47cd-105">最后一列中的格式化结果对应于“en-US”<xref:System.Globalization.CultureInfo>。</span><span class="sxs-lookup"><span data-stu-id="b47cd-105">The formatted result in the last column corresponds to the "en-US" <xref:System.Globalization.CultureInfo>.</span></span>

|<span data-ttu-id="b47cd-106">格式说明符</span><span class="sxs-lookup"><span data-stu-id="b47cd-106">Format specifier</span></span>|<span data-ttu-id="b47cd-107">说明</span><span class="sxs-lookup"><span data-stu-id="b47cd-107">Description</span></span>|<span data-ttu-id="b47cd-108">示例</span><span class="sxs-lookup"><span data-stu-id="b47cd-108">Examples</span></span>|<span data-ttu-id="b47cd-109">结果</span><span class="sxs-lookup"><span data-stu-id="b47cd-109">Result</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="b47cd-110">C 或 c</span><span class="sxs-lookup"><span data-stu-id="b47cd-110">C or c</span></span>|<span data-ttu-id="b47cd-111">货币</span><span class="sxs-lookup"><span data-stu-id="b47cd-111">Currency</span></span>|`string s = $"{2.5:C}";`<br /><br /> `string s = $"{-2.5:C}";`|<span data-ttu-id="b47cd-112">$2.50</span><span class="sxs-lookup"><span data-stu-id="b47cd-112">$2.50</span></span><br /><br /> <span data-ttu-id="b47cd-113">($2.50)</span><span class="sxs-lookup"><span data-stu-id="b47cd-113">($2.50)</span></span>|  
|<span data-ttu-id="b47cd-114">D 或 d</span><span class="sxs-lookup"><span data-stu-id="b47cd-114">D or d</span></span>|<span data-ttu-id="b47cd-115">十进制</span><span class="sxs-lookup"><span data-stu-id="b47cd-115">Decimal</span></span>|`string s = $"{25:D5}";`|<span data-ttu-id="b47cd-116">00025</span><span class="sxs-lookup"><span data-stu-id="b47cd-116">00025</span></span>|  
|<span data-ttu-id="b47cd-117">E 或 e</span><span class="sxs-lookup"><span data-stu-id="b47cd-117">E or e</span></span>|<span data-ttu-id="b47cd-118">指数</span><span class="sxs-lookup"><span data-stu-id="b47cd-118">Exponential</span></span>|`string s = $"{250000:E2}";`|<span data-ttu-id="b47cd-119">2.50E+005</span><span class="sxs-lookup"><span data-stu-id="b47cd-119">2.50E+005</span></span>|  
|<span data-ttu-id="b47cd-120">F 或 f</span><span class="sxs-lookup"><span data-stu-id="b47cd-120">F or f</span></span>|<span data-ttu-id="b47cd-121">定点</span><span class="sxs-lookup"><span data-stu-id="b47cd-121">Fixed-point</span></span>|`string s = $"{2.5:F2}";`<br /><br /> `string s = $"{2.5:F0}";`|<span data-ttu-id="b47cd-122">2.50</span><span class="sxs-lookup"><span data-stu-id="b47cd-122">2.50</span></span><br /><br /> <span data-ttu-id="b47cd-123">3</span><span class="sxs-lookup"><span data-stu-id="b47cd-123">3</span></span>|  
|<span data-ttu-id="b47cd-124">G 或 g</span><span class="sxs-lookup"><span data-stu-id="b47cd-124">G or g</span></span>|<span data-ttu-id="b47cd-125">常规</span><span class="sxs-lookup"><span data-stu-id="b47cd-125">General</span></span>|`string s = $"{2.5:G}";`|<span data-ttu-id="b47cd-126">2.5</span><span class="sxs-lookup"><span data-stu-id="b47cd-126">2.5</span></span>|  
|<span data-ttu-id="b47cd-127">N 或 n</span><span class="sxs-lookup"><span data-stu-id="b47cd-127">N or n</span></span>|<span data-ttu-id="b47cd-128">Numeric</span><span class="sxs-lookup"><span data-stu-id="b47cd-128">Numeric</span></span>|`string s = $"{2500000:N}";`|<span data-ttu-id="b47cd-129">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="b47cd-129">2,500,000.00</span></span>|  
|<span data-ttu-id="b47cd-130">P 或 p</span><span class="sxs-lookup"><span data-stu-id="b47cd-130">P or p</span></span>|<span data-ttu-id="b47cd-131">百分比</span><span class="sxs-lookup"><span data-stu-id="b47cd-131">Percent</span></span>|`string s = $"{0.25:P}";`|<span data-ttu-id="b47cd-132">25.00%</span><span class="sxs-lookup"><span data-stu-id="b47cd-132">25.00%</span></span>|  
|<span data-ttu-id="b47cd-133">R 或 r</span><span class="sxs-lookup"><span data-stu-id="b47cd-133">R or r</span></span>|<span data-ttu-id="b47cd-134">往返过程</span><span class="sxs-lookup"><span data-stu-id="b47cd-134">Round-trip</span></span>|`string s = $"{2.5:R}";`|<span data-ttu-id="b47cd-135">2.5</span><span class="sxs-lookup"><span data-stu-id="b47cd-135">2.5</span></span>|  
|<span data-ttu-id="b47cd-136">X 或 x</span><span class="sxs-lookup"><span data-stu-id="b47cd-136">X or x</span></span>|<span data-ttu-id="b47cd-137">十六进制</span><span class="sxs-lookup"><span data-stu-id="b47cd-137">Hexadecimal</span></span>|`string s = $"{250:X}";`<br /><br /> `string s = $"{0xffff:X}";`|<span data-ttu-id="b47cd-138">FA</span><span class="sxs-lookup"><span data-stu-id="b47cd-138">FA</span></span><br /><br /> <span data-ttu-id="b47cd-139">FFFF</span><span class="sxs-lookup"><span data-stu-id="b47cd-139">FFFF</span></span>|  

## <a name="remarks"></a><span data-ttu-id="b47cd-140">备注</span><span class="sxs-lookup"><span data-stu-id="b47cd-140">Remarks</span></span>

<span data-ttu-id="b47cd-141">使用格式说明符可以创建格式字符串。</span><span class="sxs-lookup"><span data-stu-id="b47cd-141">You use a format specifier to create a format string.</span></span> <span data-ttu-id="b47cd-142">格式字符串的格式如下：`Axx`，其中</span><span class="sxs-lookup"><span data-stu-id="b47cd-142">The format string is of the following form: `Axx`, where</span></span>

- <span data-ttu-id="b47cd-143">`A` 是格式说明符，控制应用于数值的格式设置类型。</span><span class="sxs-lookup"><span data-stu-id="b47cd-143">`A` is the format specifier, which controls the type of formatting applied to the numeric value.</span></span>
- <span data-ttu-id="b47cd-144">`xx` 是精度说明符，影响格式化输出中的位数。</span><span class="sxs-lookup"><span data-stu-id="b47cd-144">`xx` is the precision specifier, which affects the number of digits in the formatted output.</span></span> <span data-ttu-id="b47cd-145">精度说明符值的范围为 0 到 99。</span><span class="sxs-lookup"><span data-stu-id="b47cd-145">The value of the precision specifier ranges from 0 to 99.</span></span>

<span data-ttu-id="b47cd-146">十进制（“D”或“d”）和十六进制（“X”或“x”）格式说明符仅支持用于整型类型。</span><span class="sxs-lookup"><span data-stu-id="b47cd-146">The decimal ("D" or "d") and hexadecimal ("X" or "x") format specifiers are supported only for integral types.</span></span> <span data-ttu-id="b47cd-147">往返（“R”或“r”）格式说明符仅支持用于 <xref:System.Single>、<xref:System.Double> 和 <xref:System.Numerics.BigInteger> 类型。</span><span class="sxs-lookup"><span data-stu-id="b47cd-147">The round-trip ("R" or "r") format specifier is supported only for <xref:System.Single>, <xref:System.Double>, and <xref:System.Numerics.BigInteger> types.</span></span>

<span data-ttu-id="b47cd-148">下列支持标准数字格式字符串：</span><span class="sxs-lookup"><span data-stu-id="b47cd-148">Standard numeric format strings are supported by:</span></span>

- <span data-ttu-id="b47cd-149">所有数字类型的一些 `ToString` 方法重载。</span><span class="sxs-lookup"><span data-stu-id="b47cd-149">Some overloads of the `ToString` method of all numeric types.</span></span> <span data-ttu-id="b47cd-150">例如，可以向 <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> 和 <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> 方法提供数字格式字符串。</span><span class="sxs-lookup"><span data-stu-id="b47cd-150">For example, you can supply a numeric format string to the <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType> and <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> methods.</span></span>

- <span data-ttu-id="b47cd-151">例如，由 <xref:System.String.Format%2A?displayProperty=nameWithType> 方法提供支持的 .NET [复合格式设置功能](../../../standard/base-types/composite-formatting.md)。</span><span class="sxs-lookup"><span data-stu-id="b47cd-151">The .NET [composite formatting feature](../../../standard/base-types/composite-formatting.md), which is supported by the <xref:System.String.Format%2A?displayProperty=nameWithType> method, for example.</span></span>

- <span data-ttu-id="b47cd-152">[内插字符串](../tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="b47cd-152">[Interpolated strings](../tokens/interpolated.md).</span></span>

<span data-ttu-id="b47cd-153">有关详细信息，请参阅[标准数值格式字符串](../../../standard/base-types/standard-numeric-format-strings.md)。</span><span class="sxs-lookup"><span data-stu-id="b47cd-153">For more information, see [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b47cd-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="b47cd-154">See also</span></span>

- [<span data-ttu-id="b47cd-155">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b47cd-155">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b47cd-156">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b47cd-156">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b47cd-157">格式设置类型</span><span class="sxs-lookup"><span data-stu-id="b47cd-157">Formatting types</span></span>](../../../standard/base-types/formatting-types.md)
- [<span data-ttu-id="b47cd-158">复合格式设置</span><span class="sxs-lookup"><span data-stu-id="b47cd-158">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="b47cd-159">字符串内插</span><span class="sxs-lookup"><span data-stu-id="b47cd-159">String interpolation</span></span>](../tokens/interpolated.md)
- [<span data-ttu-id="b47cd-160">string</span><span class="sxs-lookup"><span data-stu-id="b47cd-160">string</span></span>](string.md)
