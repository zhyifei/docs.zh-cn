---
title: "设置数值结果表的格式（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 16976f5a59bd4eb0eca29553aff87d4fe0b1d247
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="formatting-numeric-results-table-c-reference"></a><span data-ttu-id="6c254-102">设置数值结果表的格式（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="6c254-102">Formatting Numeric Results Table (C# Reference)</span></span>
<span data-ttu-id="6c254-103">可通过使用 <xref:System.String.Format%2A?displayProperty=fullName> 方法或 <xref:System.Console.Write%2A?displayProperty=fullName> 或 <xref:System.Console.WriteLine%2A?displayProperty=fullName> 方法（这两种方法调用 `String.Format`）来设置数值结果的格式。</span><span class="sxs-lookup"><span data-stu-id="6c254-103">You can format numeric results by using the <xref:System.String.Format%2A?displayProperty=fullName> method, or through the <xref:System.Console.Write%2A?displayProperty=fullName> or <xref:System.Console.WriteLine%2A?displayProperty=fullName> method, which calls `String.Format`.</span></span> <span data-ttu-id="6c254-104">通过使用格式字符串指定格式。</span><span class="sxs-lookup"><span data-stu-id="6c254-104">The format is specified by using format strings.</span></span> <span data-ttu-id="6c254-105">下表包含支持的标准格式字符串。</span><span class="sxs-lookup"><span data-stu-id="6c254-105">The following table contains the supported standard format strings.</span></span> <span data-ttu-id="6c254-106">格式字符串采用以下形式：`Axx`，其中 `A` 是格式说明符，`xx` 是精度说明符。</span><span class="sxs-lookup"><span data-stu-id="6c254-106">The format string takes the following form: `Axx`, where `A` is the format specifier and `xx` is the precision specifier.</span></span> <span data-ttu-id="6c254-107">格式说明符控制应用于数值的格式类型，而精度说明符则控制格式化输出的有效位数或小数位数。</span><span class="sxs-lookup"><span data-stu-id="6c254-107">The format specifier controls the type of formatting applied to the numeric value, and the precision specifier controls the number of significant digits or decimal places of the formatted output.</span></span> <span data-ttu-id="6c254-108">精度说明符值的范围为 0 到 99。</span><span class="sxs-lookup"><span data-stu-id="6c254-108">The value of the precision specifier ranges from 0 to 99.</span></span>  
  
 <span data-ttu-id="6c254-109">有关标准格式字符串和自定义格式字符串的详细信息，请参阅[格式设置类型](../../../standard/base-types/formatting-types.md)。</span><span class="sxs-lookup"><span data-stu-id="6c254-109">For more information about standard and custom formatting strings, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="6c254-110">有关 `String.Format` 方法的更多信息，请参见 <xref:System.String.Format%2A?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="6c254-110">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=fullName>.</span></span>  
  
|<span data-ttu-id="6c254-111">格式说明符</span><span class="sxs-lookup"><span data-stu-id="6c254-111">Format Specifier</span></span>|<span data-ttu-id="6c254-112">描述</span><span class="sxs-lookup"><span data-stu-id="6c254-112">Description</span></span>|<span data-ttu-id="6c254-113">示例</span><span class="sxs-lookup"><span data-stu-id="6c254-113">Examples</span></span>|<span data-ttu-id="6c254-114">输出</span><span class="sxs-lookup"><span data-stu-id="6c254-114">Output</span></span>|  
|----------------------|-----------------|--------------|------------|  
|<span data-ttu-id="6c254-115">C 或 c</span><span class="sxs-lookup"><span data-stu-id="6c254-115">C or c</span></span>|<span data-ttu-id="6c254-116">货币</span><span class="sxs-lookup"><span data-stu-id="6c254-116">Currency</span></span>|<span data-ttu-id="6c254-117">Console.Write("{0:C}", 2.5);</span><span class="sxs-lookup"><span data-stu-id="6c254-117">Console.Write("{0:C}", 2.5);</span></span><br /><br /> <span data-ttu-id="6c254-118">Console.Write("{0:C}", -2.5);</span><span class="sxs-lookup"><span data-stu-id="6c254-118">Console.Write("{0:C}", -2.5);</span></span>|<span data-ttu-id="6c254-119">$2.50</span><span class="sxs-lookup"><span data-stu-id="6c254-119">$2.50</span></span><br /><br /> <span data-ttu-id="6c254-120">($2.50)</span><span class="sxs-lookup"><span data-stu-id="6c254-120">($2.50)</span></span>|  
|<span data-ttu-id="6c254-121">D 或 d</span><span class="sxs-lookup"><span data-stu-id="6c254-121">D or d</span></span>|<span data-ttu-id="6c254-122">Decimal</span><span class="sxs-lookup"><span data-stu-id="6c254-122">Decimal</span></span>|<span data-ttu-id="6c254-123">Console.Write("{0:D5}", 25);</span><span class="sxs-lookup"><span data-stu-id="6c254-123">Console.Write("{0:D5}", 25);</span></span>|<span data-ttu-id="6c254-124">00025</span><span class="sxs-lookup"><span data-stu-id="6c254-124">00025</span></span>|  
|<span data-ttu-id="6c254-125">E 或 e</span><span class="sxs-lookup"><span data-stu-id="6c254-125">E or e</span></span>|<span data-ttu-id="6c254-126">科学记数法</span><span class="sxs-lookup"><span data-stu-id="6c254-126">Scientific</span></span>|<span data-ttu-id="6c254-127">Console.Write("{0:E}", 250000);</span><span class="sxs-lookup"><span data-stu-id="6c254-127">Console.Write("{0:E}", 250000);</span></span>|<span data-ttu-id="6c254-128">2.500000E+005</span><span class="sxs-lookup"><span data-stu-id="6c254-128">2.500000E+005</span></span>|  
|<span data-ttu-id="6c254-129">F 或 f</span><span class="sxs-lookup"><span data-stu-id="6c254-129">F or f</span></span>|<span data-ttu-id="6c254-130">定点</span><span class="sxs-lookup"><span data-stu-id="6c254-130">Fixed-point</span></span>|<span data-ttu-id="6c254-131">Console.Write("{0:F2}", 25);</span><span class="sxs-lookup"><span data-stu-id="6c254-131">Console.Write("{0:F2}", 25);</span></span><br /><br /> <span data-ttu-id="6c254-132">Console.Write("{0:F0}", 25);</span><span class="sxs-lookup"><span data-stu-id="6c254-132">Console.Write("{0:F0}", 25);</span></span>|<span data-ttu-id="6c254-133">25.00</span><span class="sxs-lookup"><span data-stu-id="6c254-133">25.00</span></span><br /><br /> <span data-ttu-id="6c254-134">25</span><span class="sxs-lookup"><span data-stu-id="6c254-134">25</span></span>|  
|<span data-ttu-id="6c254-135">G 或 g</span><span class="sxs-lookup"><span data-stu-id="6c254-135">G or g</span></span>|<span data-ttu-id="6c254-136">常规</span><span class="sxs-lookup"><span data-stu-id="6c254-136">General</span></span>|<span data-ttu-id="6c254-137">Console.Write("{0:G}", 2.5);</span><span class="sxs-lookup"><span data-stu-id="6c254-137">Console.Write("{0:G}", 2.5);</span></span>|<span data-ttu-id="6c254-138">2.5</span><span class="sxs-lookup"><span data-stu-id="6c254-138">2.5</span></span>|  
|<span data-ttu-id="6c254-139">N 或 n</span><span class="sxs-lookup"><span data-stu-id="6c254-139">N or n</span></span>|<span data-ttu-id="6c254-140">数字</span><span class="sxs-lookup"><span data-stu-id="6c254-140">Number</span></span>|<span data-ttu-id="6c254-141">Console.Write("{0:N}", 2500000);</span><span class="sxs-lookup"><span data-stu-id="6c254-141">Console.Write("{0:N}", 2500000);</span></span>|<span data-ttu-id="6c254-142">2,500,000.00</span><span class="sxs-lookup"><span data-stu-id="6c254-142">2,500,000.00</span></span>|  
|<span data-ttu-id="6c254-143">X 或 x</span><span class="sxs-lookup"><span data-stu-id="6c254-143">X or x</span></span>|<span data-ttu-id="6c254-144">十六进制</span><span class="sxs-lookup"><span data-stu-id="6c254-144">Hexadecimal</span></span>|<span data-ttu-id="6c254-145">Console.Write("{0:X}", 250);</span><span class="sxs-lookup"><span data-stu-id="6c254-145">Console.Write("{0:X}", 250);</span></span><br /><br /> <span data-ttu-id="6c254-146">Console.Write("{0:X}", 0xffff);</span><span class="sxs-lookup"><span data-stu-id="6c254-146">Console.Write("{0:X}", 0xffff);</span></span>|<span data-ttu-id="6c254-147">FA</span><span class="sxs-lookup"><span data-stu-id="6c254-147">FA</span></span><br /><br /> <span data-ttu-id="6c254-148">FFFF</span><span class="sxs-lookup"><span data-stu-id="6c254-148">FFFF</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6c254-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c254-149">See Also</span></span>  
 <span data-ttu-id="6c254-150">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6c254-150">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6c254-151">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6c254-151">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6c254-152">[标准数字格式字符串](../../../standard/base-types/standard-numeric-format-strings.md) </span><span class="sxs-lookup"><span data-stu-id="6c254-152">[Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md) </span></span>  
 <span data-ttu-id="6c254-153">[类型参考表](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span><span class="sxs-lookup"><span data-stu-id="6c254-153">[Reference Tables for Types](../../../csharp/language-reference/keywords/reference-tables-for-types.md) </span></span>  
 [<span data-ttu-id="6c254-154">字符串</span><span class="sxs-lookup"><span data-stu-id="6c254-154">string</span></span>](../../../csharp/language-reference/keywords/string.md)

