---
title: $ - 字符串内插（C# 参考）
description: 与传统的字符串复合格式设置相比，字符串内插提供更具可读性且更方便的语法，用于设置字符串输出的格式。
ms.date: 03/26/2018
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.author: ronpet
ms.openlocfilehash: 2009b3620bc4874520221a4ea847222feafca01b
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "43000971"
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="7df59-103">$ - 字符串内插（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="7df59-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="7df59-104">`$` 特殊字符将字符串文本标识为内插字符串。</span><span class="sxs-lookup"><span data-stu-id="7df59-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="7df59-105">内插字符串是可能包含内插表达式的字符串文本。</span><span class="sxs-lookup"><span data-stu-id="7df59-105">An interpolated string is a string literal that might contain *interpolated expressions*.</span></span> <span data-ttu-id="7df59-106">将内插字符串解析为结果字符串时，带有内插表达式的项会替换为表达式结果的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="7df59-106">When an interpolated string is resolved to a result string, items with interpolated expressions are replaced by the string representations of the expression results.</span></span> <span data-ttu-id="7df59-107">此功能在 C# 6 及该语言的更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="7df59-107">This feature is available in C# 6 and later versions of the language.</span></span>

<span data-ttu-id="7df59-108">与使用[字符串复合格式设置](../../../standard/base-types/composite-formatting.md)功能创建格式化字符串相比，字符串内插提供的语法更具可读性，且更加方便。</span><span class="sxs-lookup"><span data-stu-id="7df59-108">String interpolation provides a more readable and convenient syntax to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="7df59-109">下面的示例使用了这两种功能生成同样的输出结果：</span><span class="sxs-lookup"><span data-stu-id="7df59-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a><span data-ttu-id="7df59-110">内插字符串的结构</span><span class="sxs-lookup"><span data-stu-id="7df59-110">Structure of an interpolated string</span></span>

<span data-ttu-id="7df59-111">若要将字符串标识为内插字符串，可在该字符串前面加上 `$` 符号。</span><span class="sxs-lookup"><span data-stu-id="7df59-111">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="7df59-112">字符串文本开头的 `$` 和 `"` 之间不能有任何空格。</span><span class="sxs-lookup"><span data-stu-id="7df59-112">You cannot have any white space between the `$` and the `"` that starts a string literal.</span></span> <span data-ttu-id="7df59-113">如果有空格，会导致编译时错误。</span><span class="sxs-lookup"><span data-stu-id="7df59-113">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="7df59-114">具备内插表达式的项的结构如下所示：</span><span class="sxs-lookup"><span data-stu-id="7df59-114">The structure of an item with an interpolated expression is as follows:</span></span>

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="7df59-115">括号中的元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="7df59-115">Elements in square brackets are optional.</span></span> <span data-ttu-id="7df59-116">下表说明了每个元素：</span><span class="sxs-lookup"><span data-stu-id="7df59-116">The following table describes each element:</span></span>

|<span data-ttu-id="7df59-117">元素</span><span class="sxs-lookup"><span data-stu-id="7df59-117">Element</span></span>|<span data-ttu-id="7df59-118">描述</span><span class="sxs-lookup"><span data-stu-id="7df59-118">Description</span></span>|
|-------------|-----------------|
|`interpolatedExpression`|<span data-ttu-id="7df59-119">生成需要设置格式的结果的表达式。</span><span class="sxs-lookup"><span data-stu-id="7df59-119">The expression that produces a result to be formatted.</span></span> <span data-ttu-id="7df59-120">`null` 结果的字符串表示形式为 <xref:System.String.Empty?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="7df59-120">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="7df59-121">常数表达式，它的值定义内插表达式结果的字符串表示形式中的最小字符数。</span><span class="sxs-lookup"><span data-stu-id="7df59-121">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolated expression.</span></span> <span data-ttu-id="7df59-122">如果值为正，则字符串表示形式为右对齐；如果值为负，则为左对齐。</span><span class="sxs-lookup"><span data-stu-id="7df59-122">If positive, the string representation is right-aligned; if negative, it's left-aligned.</span></span> <span data-ttu-id="7df59-123">有关详细信息，请参阅[对齐组件](../../../standard/base-types/composite-formatting.md#alignment-component)。</span><span class="sxs-lookup"><span data-stu-id="7df59-123">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="7df59-124">受表达式结果类型支持的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="7df59-124">A format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="7df59-125">有关更多信息，请参阅[格式字符串组件](../../../standard/base-types/composite-formatting.md#format-string-component)。</span><span class="sxs-lookup"><span data-stu-id="7df59-125">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="7df59-126">以下示例使用上述可选的格式设置组件：</span><span class="sxs-lookup"><span data-stu-id="7df59-126">The following example uses optional formatting components described above:</span></span>

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a><span data-ttu-id="7df59-127">特殊字符</span><span class="sxs-lookup"><span data-stu-id="7df59-127">Special characters</span></span>

<span data-ttu-id="7df59-128">要在内插字符串生成的文本中包含大括号 "{" 或 "}"，请使用两个大括号，即 "{{" 或 "}}"。</span><span class="sxs-lookup"><span data-stu-id="7df59-128">To include a brace, "{" or "}", in the text produced by an interpolated string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="7df59-129">有关详细信息，请参阅[转义大括号](../../../standard/base-types/composite-formatting.md#escaping-braces)。</span><span class="sxs-lookup"><span data-stu-id="7df59-129">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="7df59-130">因为冒号 (":") 在内插表达式项中具有特殊含义，为了在内插表达式中使用[条件运算符](../operators/conditional-operator.md)，请将表达式放在括号内。</span><span class="sxs-lookup"><span data-stu-id="7df59-130">As the colon (":") has special meaning in an interpolated expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolated expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="7df59-131">以下示例演示如何将大括号含入结果字符串中，以及如何在内插表达式中使用条件运算符：</span><span class="sxs-lookup"><span data-stu-id="7df59-131">The following example shows how to include a brace in a result string and how to use a conditional operator in an interpolated expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="7df59-132">逐字内插字符串以 `$` 字符开头，后跟 `@` 字符。</span><span class="sxs-lookup"><span data-stu-id="7df59-132">A verbatim interpolated string starts with the `$` character followed by the `@` character.</span></span> <span data-ttu-id="7df59-133">有关逐字字符串的详细信息，请参阅[字符串](../keywords/string.md)和[逐字标识符](verbatim.md)主题。</span><span class="sxs-lookup"><span data-stu-id="7df59-133">For more information about verbatim strings, see the [string](../keywords/string.md) and [verbatim identifier](verbatim.md) topics.</span></span>

> [!NOTE]
> <span data-ttu-id="7df59-134">在逐字内插字符串中，`$` 标记必须出现 `@` 标记之前。</span><span class="sxs-lookup"><span data-stu-id="7df59-134">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

## <a name="implicit-conversions-and-specifying-iformatprovider-implementation"></a><span data-ttu-id="7df59-135">隐式转换和指定 `IFormatProvider` 实现</span><span class="sxs-lookup"><span data-stu-id="7df59-135">Implicit conversions and specifying `IFormatProvider` implementation</span></span>

<span data-ttu-id="7df59-136">内插字符串有 3 种隐式转换：</span><span class="sxs-lookup"><span data-stu-id="7df59-136">There are three implicit conversions from an interpolated string:</span></span>

1. <span data-ttu-id="7df59-137">将内插字符串转换为 <xref:System.String> 实例，该类例是内插字符串的解析结果，其中内插表达式项被替换为结果的格式设置正确的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="7df59-137">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolated expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="7df59-138">此类转换使用当前区域性。</span><span class="sxs-lookup"><span data-stu-id="7df59-138">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="7df59-139">将内插字符串转换为表示复合格式字符串的 <xref:System.FormattableString> 实例，同时也将表达式结果格式化。</span><span class="sxs-lookup"><span data-stu-id="7df59-139">Conversion of an interpolated string to a <xref:System.FormattableString> instance that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="7df59-140">这允许通过单个 <xref:System.FormattableString> 实例创建多个包含区域性特定内容的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="7df59-140">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="7df59-141">要执行此操作，请调用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="7df59-141">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="7df59-142"><xref:System.FormattableString.ToString> 重载，生成 <xref:System.Globalization.CultureInfo.CurrentCulture> 的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="7df59-142">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="7df59-143"><xref:System.FormattableString.Invariant%2A> 方法，生成 <xref:System.Globalization.CultureInfo.InvariantCulture> 的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="7df59-143">An <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="7df59-144"><xref:System.FormattableString.ToString(System.IFormatProvider)> 方法，生成特定区域性的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="7df59-144">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

    <span data-ttu-id="7df59-145">你还可使用 <xref:System.FormattableString.ToString(System.IFormatProvider)> 方法，以提供支持自定义格式设置的 <xref:System.IFormatProvider> 接口的用户定义实现。</span><span class="sxs-lookup"><span data-stu-id="7df59-145">You also can use the <xref:System.FormattableString.ToString(System.IFormatProvider)> method to provide a user-defined implementation of the <xref:System.IFormatProvider> interface that supports custom formatting.</span></span> <span data-ttu-id="7df59-146">有关详细信息，请参见[使用 ICustomFormatter 进行自定义格式设置](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter)。</span><span class="sxs-lookup"><span data-stu-id="7df59-146">For more information, see [Custom Formatting with ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span></span>

1. <span data-ttu-id="7df59-147">将内插字符串转换为 <xref:System.IFormattable> 实例，使用此实例也可通过单个 <xref:System.IFormattable> 实例创建多个包含区域性特定内容的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="7df59-147">Conversion of an interpolated string to an <xref:System.IFormattable> instance that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="7df59-148">以下示例通过隐式转换为 <xref:System.FormattableString> 来创建特定于区域性的结果字符串：</span><span class="sxs-lookup"><span data-stu-id="7df59-148">The following example uses implicit conversion to <xref:System.FormattableString> to create culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a><span data-ttu-id="7df59-149">其他资源</span><span class="sxs-lookup"><span data-stu-id="7df59-149">Additional resources</span></span>

<span data-ttu-id="7df59-150">如果不熟悉字符串内插，请参阅 [C# 中的字符串内插](../../quick-starts/interpolated-strings.yml)快速入门。</span><span class="sxs-lookup"><span data-stu-id="7df59-150">If you are new to string interpolation, see the [String interpolation in C#](../../quick-starts/interpolated-strings.yml) quickstart.</span></span> <span data-ttu-id="7df59-151">请参阅 [C# 中的字符串内插](../../tutorials/string-interpolation.md)教程查看更多相关示例。</span><span class="sxs-lookup"><span data-stu-id="7df59-151">For more examples, see the [String interpolation in C#](../../tutorials/string-interpolation.md) tutorial.</span></span>

## <a name="see-also"></a><span data-ttu-id="7df59-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="7df59-152">See also</span></span>

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [<span data-ttu-id="7df59-153">复合格式设置</span><span class="sxs-lookup"><span data-stu-id="7df59-153">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="7df59-154">字符串</span><span class="sxs-lookup"><span data-stu-id="7df59-154">Strings</span></span>](../../programming-guide/strings/index.md)
- [<span data-ttu-id="7df59-155">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7df59-155">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7df59-156">C# 特殊字符</span><span class="sxs-lookup"><span data-stu-id="7df59-156">C# Special Characters</span></span>](index.md)
- [<span data-ttu-id="7df59-157">C# 参考</span><span class="sxs-lookup"><span data-stu-id="7df59-157">C# Reference</span></span>](../index.md)
