---
title: $ - 字符串内插（C# 参考）
description: 与传统的字符串复合格式设置相比，字符串内插提供更具可读性且更方便的语法，用于设置字符串输出的格式。
ms.date: 03/26/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cabb40c9c449780c8c2a504aad3e53938e2ed957
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="061b6-103">$ - 字符串内插（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="061b6-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="061b6-104">`$` 特殊字符将字符串文本标识为内插字符串。</span><span class="sxs-lookup"><span data-stu-id="061b6-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="061b6-105">内插字符串类似于包含内插表达式的模板字符串。</span><span class="sxs-lookup"><span data-stu-id="061b6-105">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span> <span data-ttu-id="061b6-106">将内插字符串解析为结果字符串时，带有内插表达式的项会替换为表达式结果的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="061b6-106">When the interpolated string is resolved to the result string, items with interpolated expressions are replaced by the string representations of the expression results.</span></span> <span data-ttu-id="061b6-107">此功能在 C# 6 及更高版本中提供。</span><span class="sxs-lookup"><span data-stu-id="061b6-107">This feature is available in C# 6 and later versions.</span></span>

<span data-ttu-id="061b6-108">与使用[字符串复合格式设置](../../../standard/base-types/composite-formatting.md)功能创建格式化字符串相比，字符串内插提供的语法更具可读性，且更加方便。</span><span class="sxs-lookup"><span data-stu-id="061b6-108">String interpolation provides a more readable and convenient syntax to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="061b6-109">下面的示例使用了这两种功能生成同样的输出结果：</span><span class="sxs-lookup"><span data-stu-id="061b6-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

> [!NOTE]
> <span data-ttu-id="061b6-110">字符串开头的 `$` 和 `"` 之间不能有任何空格。</span><span class="sxs-lookup"><span data-stu-id="061b6-110">You cannot have any white space between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="061b6-111">如果有空格，会导致编译时错误。</span><span class="sxs-lookup"><span data-stu-id="061b6-111">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="061b6-112">具备内插表达式的项的结构如下所示：</span><span class="sxs-lookup"><span data-stu-id="061b6-112">The structure of an item with an interpolated expression is as follows:</span></span>

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="061b6-113">括号中的元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="061b6-113">Elements in square brackets are optional.</span></span> <span data-ttu-id="061b6-114">下表对每个元素进行了描述。</span><span class="sxs-lookup"><span data-stu-id="061b6-114">The following table describes each element.</span></span>

|<span data-ttu-id="061b6-115">元素</span><span class="sxs-lookup"><span data-stu-id="061b6-115">Element</span></span>|<span data-ttu-id="061b6-116">描述</span><span class="sxs-lookup"><span data-stu-id="061b6-116">Description</span></span>|
|-------------|-----------------|
|`interpolatedExpression`|<span data-ttu-id="061b6-117">可计算获取要进行格式设置的结果的表达式。</span><span class="sxs-lookup"><span data-stu-id="061b6-117">The expression to evaluate to get a result to be formatted.</span></span> <span data-ttu-id="061b6-118">`null` 结果的字符串表示形式为 <xref:System.String.Empty?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="061b6-118">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="061b6-119">常数表达式，它的值定义内插表达式结果的字符串表示形式中的最小字符数。</span><span class="sxs-lookup"><span data-stu-id="061b6-119">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolated expression.</span></span> <span data-ttu-id="061b6-120">如果值为正，则字符串表示形式为右对齐；如果值为负，则为左对齐。</span><span class="sxs-lookup"><span data-stu-id="061b6-120">If positive, the string representation is right-aligned; if negative, it is left-aligned.</span></span> <span data-ttu-id="061b6-121">有关详细信息，请参阅[对齐组件](../../../standard/base-types/composite-formatting.md#alignment-component)。</span><span class="sxs-lookup"><span data-stu-id="061b6-121">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="061b6-122">表达式结果的类型所支持的一个标准格式字符串或自定义格式字符串。</span><span class="sxs-lookup"><span data-stu-id="061b6-122">A standard or custom format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="061b6-123">有关更多信息，请参阅[格式字符串组件](../../../standard/base-types/composite-formatting.md#format-string-component)。</span><span class="sxs-lookup"><span data-stu-id="061b6-123">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="061b6-124">以下示例使用上述可选的格式设置组件：</span><span class="sxs-lookup"><span data-stu-id="061b6-124">The following example uses optional formatting components described above:</span></span>

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

<span data-ttu-id="061b6-125">要在内插字符串生成的文本中包含大括号（“{”或“}”），请使用两个大括号，即“{{”或“}}”。</span><span class="sxs-lookup"><span data-stu-id="061b6-125">To include a brace ("{" or "}") in the text produced by an interpolated string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="061b6-126">有关详细信息，请参阅[转义大括号](../../../standard/base-types/composite-formatting.md#escaping-braces)。</span><span class="sxs-lookup"><span data-stu-id="061b6-126">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="061b6-127">因为冒号 (:) 在内插表达式项中具有特殊含义，为了在内插表达式中使用[条件运算符](../operators/conditional-operator.md)，请将表达式放在括号内。</span><span class="sxs-lookup"><span data-stu-id="061b6-127">As the colon (:) has special meaning in an interpolated expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolated expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="061b6-128">以下示例演示如何将大括号含入结果字符串中，以及如何在内插表达式中使用条件运算符：</span><span class="sxs-lookup"><span data-stu-id="061b6-128">The following example shows how to include a brace into the result string and how to use a conditional operator in an interpolated expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="061b6-129">逐字内插字符串使用 `$` 字符，后跟 `@` 字符。</span><span class="sxs-lookup"><span data-stu-id="061b6-129">Verbatim interpolated strings use the `$` character followed by the `@` character.</span></span> <span data-ttu-id="061b6-130">有关逐字字符串的详细信息，请参阅[字符串](../keywords/string.md)主题。</span><span class="sxs-lookup"><span data-stu-id="061b6-130">For more information about verbatim strings, see the [string](../keywords/string.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="061b6-131">在逐字内插字符串中，`$` 标记必须出现 `@` 标记之前。</span><span class="sxs-lookup"><span data-stu-id="061b6-131">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

<span data-ttu-id="061b6-132">内插字符串有 3 种隐式转换：</span><span class="sxs-lookup"><span data-stu-id="061b6-132">There are three implicit conversions from an interpolated string:</span></span>

1. <span data-ttu-id="061b6-133">将内插字符串转换为 <xref:System.String> 实例，该类例是内插字符串的解析结果，其中内插表达式项被替换为结果的格式设置正确的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="061b6-133">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolated expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="061b6-134">此类转换使用当前区域性。</span><span class="sxs-lookup"><span data-stu-id="061b6-134">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="061b6-135">将内插字符串转换为表示复合格式字符串的 <xref:System.FormattableString> 实例，同时也将表达式结果格式化。</span><span class="sxs-lookup"><span data-stu-id="061b6-135">Conversion of an interpolated string to a <xref:System.FormattableString> instance that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="061b6-136">这允许通过单个 <xref:System.FormattableString> 实例创建多个包含区域性特定内容的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="061b6-136">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="061b6-137">要执行此操作，请调用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="061b6-137">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="061b6-138"><xref:System.FormattableString.ToString> 重载，生成 <xref:System.Globalization.CultureInfo.CurrentCulture> 的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="061b6-138">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="061b6-139"><xref:System.FormattableString.Invariant%2A> 方法，生成 <xref:System.Globalization.CultureInfo.InvariantCulture> 的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="061b6-139">A <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="061b6-140"><xref:System.FormattableString.ToString(System.IFormatProvider)> 方法，生成特定区域性的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="061b6-140">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

1. <span data-ttu-id="061b6-141">将内插字符串转换为 <xref:System.IFormattable> 实例，使用此实例也可通过单个 <xref:System.IFormattable> 实例创建多个包含区域性特定内容的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="061b6-141">Conversion of an interpolated string to an <xref:System.IFormattable> instance that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="061b6-142">以下示例通过隐式转换为 <xref:System.FormattableString> 来创建特定于区域性的结果字符串：</span><span class="sxs-lookup"><span data-stu-id="061b6-142">The following example uses implicit conversion to <xref:System.FormattableString> to create culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

<span data-ttu-id="061b6-143">如果不熟悉字符串内插，请参阅 [C# 中的字符串内插](../../quick-starts/interpolated-strings.yml)快速入门。</span><span class="sxs-lookup"><span data-stu-id="061b6-143">If you are new to the string interpolation, check the [String interpolation in C#](../../quick-starts/interpolated-strings.yml) quickstart.</span></span> <span data-ttu-id="061b6-144">请参阅[字符串内插](../../tutorials/string-interpolation.md)教程查看更多相关示例。</span><span class="sxs-lookup"><span data-stu-id="061b6-144">For more examples, see the [string interpolation tutorial](../../tutorials/string-interpolation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="061b6-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="061b6-145">See also</span></span>  
 <xref:System.String.Format%2A?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 [<span data-ttu-id="061b6-146">复合格式设置</span><span class="sxs-lookup"><span data-stu-id="061b6-146">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)  
 [<span data-ttu-id="061b6-147">字符串</span><span class="sxs-lookup"><span data-stu-id="061b6-147">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="061b6-148">C# 特殊字符</span><span class="sxs-lookup"><span data-stu-id="061b6-148">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)  
 [<span data-ttu-id="061b6-149">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="061b6-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="061b6-150">C# 参考</span><span class="sxs-lookup"><span data-stu-id="061b6-150">C# Reference</span></span>](../../../csharp/language-reference/index.md)  