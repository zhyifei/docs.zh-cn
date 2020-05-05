---
title: $ - 字符串内插 - C# 参考
description: 与传统的字符串复合格式设置相比，字符串内插提供更具可读性且更方便的语法，用于设置字符串输出的格式。
ms.date: 09/02/2019
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.openlocfilehash: 2b95fa5fe5cecd4825e8c17a33f7795c6c9480c6
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738376"
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="b4967-103">$ - 字符串内插（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b4967-103">$ - string interpolation (C# reference)</span></span>

<span data-ttu-id="b4967-104">`$` 特殊字符将字符串文本标识为内插字符串  。</span><span class="sxs-lookup"><span data-stu-id="b4967-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="b4967-105">内插字符串是可能包含内插表达式的字符串文本  。</span><span class="sxs-lookup"><span data-stu-id="b4967-105">An interpolated string is a string literal that might contain *interpolation expressions*.</span></span> <span data-ttu-id="b4967-106">将内插字符串解析为结果字符串时，带有内插表达式的项会替换为表达式结果的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="b4967-106">When an interpolated string is resolved to a result string, items with interpolation expressions are replaced by the string representations of the expression results.</span></span> <span data-ttu-id="b4967-107">从 C# 6 开始可以使用此功能。</span><span class="sxs-lookup"><span data-stu-id="b4967-107">This feature is available starting with C# 6.</span></span>

<span data-ttu-id="b4967-108">与使用[字符串复合格式设置](../../../standard/base-types/composite-formatting.md)功能创建格式化字符串相比，字符串内插提供的语法更具可读性，且更加方便。</span><span class="sxs-lookup"><span data-stu-id="b4967-108">String interpolation provides a more readable and convenient syntax to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="b4967-109">下面的示例使用了这两种功能生成同样的输出结果：</span><span class="sxs-lookup"><span data-stu-id="b4967-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a><span data-ttu-id="b4967-110">内插字符串的结构</span><span class="sxs-lookup"><span data-stu-id="b4967-110">Structure of an interpolated string</span></span>

<span data-ttu-id="b4967-111">若要将字符串标识为内插字符串，可在该字符串前面加上 `$` 符号。</span><span class="sxs-lookup"><span data-stu-id="b4967-111">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="b4967-112">字符串文本开头的 `$` 和 `"` 之间不能有任何空格。</span><span class="sxs-lookup"><span data-stu-id="b4967-112">You cannot have any white space between the `$` and the `"` that starts a string literal.</span></span>

<span data-ttu-id="b4967-113">具备内插表达式的项的结构如下所示：</span><span class="sxs-lookup"><span data-stu-id="b4967-113">The structure of an item with an interpolation expression is as follows:</span></span>

```csharp
{<interpolationExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="b4967-114">括号中的元素是可选的。</span><span class="sxs-lookup"><span data-stu-id="b4967-114">Elements in square brackets are optional.</span></span> <span data-ttu-id="b4967-115">下表说明了每个元素：</span><span class="sxs-lookup"><span data-stu-id="b4967-115">The following table describes each element:</span></span>

|<span data-ttu-id="b4967-116">元素</span><span class="sxs-lookup"><span data-stu-id="b4967-116">Element</span></span>|<span data-ttu-id="b4967-117">描述</span><span class="sxs-lookup"><span data-stu-id="b4967-117">Description</span></span>|
|-------------|-----------------|
|`interpolationExpression`|<span data-ttu-id="b4967-118">生成需要设置格式的结果的表达式。</span><span class="sxs-lookup"><span data-stu-id="b4967-118">The expression that produces a result to be formatted.</span></span> <span data-ttu-id="b4967-119">`null` 的字符串表示形式为 <xref:System.String.Empty?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="b4967-119">String representation of `null` is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="b4967-120">常数表达式，它的值定义表达式结果的字符串表示形式中的最小字符数。</span><span class="sxs-lookup"><span data-stu-id="b4967-120">The constant expression whose value defines the minimum number of characters in the string representation of the expression result.</span></span> <span data-ttu-id="b4967-121">如果值为正，则字符串表示形式为右对齐；如果值为负，则为左对齐。</span><span class="sxs-lookup"><span data-stu-id="b4967-121">If positive, the string representation is right-aligned; if negative, it's left-aligned.</span></span> <span data-ttu-id="b4967-122">有关详细信息，请参阅[对齐组件](../../../standard/base-types/composite-formatting.md#alignment-component)。</span><span class="sxs-lookup"><span data-stu-id="b4967-122">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="b4967-123">受表达式结果类型支持的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="b4967-123">A format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="b4967-124">有关更多信息，请参阅[格式字符串组件](../../../standard/base-types/composite-formatting.md#format-string-component)。</span><span class="sxs-lookup"><span data-stu-id="b4967-124">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="b4967-125">以下示例使用上述可选的格式设置组件：</span><span class="sxs-lookup"><span data-stu-id="b4967-125">The following example uses optional formatting components described above:</span></span>

[!code-csharp-interactive[specify alignment and format string](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a><span data-ttu-id="b4967-126">特殊字符</span><span class="sxs-lookup"><span data-stu-id="b4967-126">Special characters</span></span>

<span data-ttu-id="b4967-127">要在内插字符串生成的文本中包含大括号 "{" 或 "}"，请使用两个大括号，即 "{{" 或 "}}"。</span><span class="sxs-lookup"><span data-stu-id="b4967-127">To include a brace, "{" or "}", in the text produced by an interpolated string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="b4967-128">有关详细信息，请参阅[转义大括号](../../../standard/base-types/composite-formatting.md#escaping-braces)。</span><span class="sxs-lookup"><span data-stu-id="b4967-128">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="b4967-129">因为冒号（“:”）在内插表达式项中具有特殊含义，为了在内插表达式中使用[条件运算符](../operators/conditional-operator.md)，请将表达式放在括号内。</span><span class="sxs-lookup"><span data-stu-id="b4967-129">As the colon (":") has special meaning in an interpolation expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolation expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="b4967-130">以下示例演示如何将大括号含入结果字符串中，以及如何在内插表达式中使用条件运算符：</span><span class="sxs-lookup"><span data-stu-id="b4967-130">The following example shows how to include a brace in a result string and how to use a conditional operator in an interpolation expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="b4967-131">内插逐字字符串以 `$` 字符开头，后跟 `@` 字符。</span><span class="sxs-lookup"><span data-stu-id="b4967-131">An interpolated verbatim string starts with the `$` character followed by the `@` character.</span></span> <span data-ttu-id="b4967-132">有关逐字字符串的详细信息，请参阅[字符串](../builtin-types/reference-types.md)和[逐字标识符](verbatim.md)主题。</span><span class="sxs-lookup"><span data-stu-id="b4967-132">For more information about verbatim strings, see the [string](../builtin-types/reference-types.md) and [verbatim identifier](verbatim.md) topics.</span></span>

> [!NOTE]
> <span data-ttu-id="b4967-133">从 C# 8.0 开始，可以按任意顺序使用 `$` 和 `@` 标记：`$@"..."` 和 `@$"..."` 均为有效的内插逐字字符串。</span><span class="sxs-lookup"><span data-stu-id="b4967-133">Starting with C# 8.0, you can use the `$` and `@` tokens in any order: both `$@"..."` and `@$"..."` are valid interpolated verbatim strings.</span></span> <span data-ttu-id="b4967-134">在早期 C# 版本中，`$` 标记必须出现在 `@` 标记之前。</span><span class="sxs-lookup"><span data-stu-id="b4967-134">In earlier C# versions, the `$` token must appear before the `@` token.</span></span>

## <a name="implicit-conversions-and-how-to-specify-iformatprovider-implementation"></a><span data-ttu-id="b4967-135">隐式转换和指定 `IFormatProvider` 实现的方式</span><span class="sxs-lookup"><span data-stu-id="b4967-135">Implicit conversions and how to specify `IFormatProvider` implementation</span></span>

<span data-ttu-id="b4967-136">内插字符串有 3 种隐式转换：</span><span class="sxs-lookup"><span data-stu-id="b4967-136">There are three implicit conversions from an interpolated string:</span></span>

1. <span data-ttu-id="b4967-137">将内插字符串转换为 <xref:System.String> 实例，该类例是内插字符串的解析结果，其中内插表达式项被替换为结果的格式设置正确的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="b4967-137">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolation expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="b4967-138">此转换使用 <xref:System.Globalization.CultureInfo.CurrentCulture> 设置表达式结果的格式。</span><span class="sxs-lookup"><span data-stu-id="b4967-138">This conversion uses the <xref:System.Globalization.CultureInfo.CurrentCulture> to format expression results.</span></span>

1. <span data-ttu-id="b4967-139">将内插字符串转换为表示复合格式字符串的 <xref:System.FormattableString> 实例，同时也将表达式结果格式化。</span><span class="sxs-lookup"><span data-stu-id="b4967-139">Conversion of an interpolated string to a <xref:System.FormattableString> instance that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="b4967-140">这允许通过单个 <xref:System.FormattableString> 实例创建多个包含区域性特定内容的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="b4967-140">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="b4967-141">要执行此操作，请调用以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="b4967-141">To do that, call one of the following methods:</span></span>

      - <span data-ttu-id="b4967-142"><xref:System.FormattableString.ToString> 重载，生成 <xref:System.Globalization.CultureInfo.CurrentCulture> 的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="b4967-142">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="b4967-143"><xref:System.FormattableString.Invariant%2A> 方法，生成 <xref:System.Globalization.CultureInfo.InvariantCulture> 的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="b4967-143">An <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="b4967-144"><xref:System.FormattableString.ToString(System.IFormatProvider)> 方法，生成特定区域性的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="b4967-144">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

    <span data-ttu-id="b4967-145">还可以使用 <xref:System.FormattableString.ToString(System.IFormatProvider)> 方法，以提供支持自定义格式设置的 <xref:System.IFormatProvider> 接口的用户定义实现。</span><span class="sxs-lookup"><span data-stu-id="b4967-145">You can also use the <xref:System.FormattableString.ToString(System.IFormatProvider)> method to provide a user-defined implementation of the <xref:System.IFormatProvider> interface that supports custom formatting.</span></span> <span data-ttu-id="b4967-146">有关详细信息，请参阅[在 .NET 中设置类型格式](../../../standard/base-types/formatting-types.md)一文中的[使用 ICustomFormatter 进行自定义格式设置](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter)部分。</span><span class="sxs-lookup"><span data-stu-id="b4967-146">For more information, see the [Custom formatting with ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) section of the [Formatting types in .NET](../../../standard/base-types/formatting-types.md) article.</span></span>

1. <span data-ttu-id="b4967-147">将内插字符串转换为 <xref:System.IFormattable> 实例，使用此实例也可通过单个 <xref:System.IFormattable> 实例创建多个包含区域性特定内容的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="b4967-147">Conversion of an interpolated string to an <xref:System.IFormattable> instance that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="b4967-148">以下示例通过隐式转换为 <xref:System.FormattableString> 来创建特定于区域性的结果字符串：</span><span class="sxs-lookup"><span data-stu-id="b4967-148">The following example uses implicit conversion to <xref:System.FormattableString> to create culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a><span data-ttu-id="b4967-149">其他资源</span><span class="sxs-lookup"><span data-stu-id="b4967-149">Additional resources</span></span>

<span data-ttu-id="b4967-150">如果你不熟悉字符串内插，请参阅 [C# 中的字符串内插](../../tutorials/exploration/interpolated-strings.yml)交互式教程。</span><span class="sxs-lookup"><span data-stu-id="b4967-150">If you are new to string interpolation, see the [String interpolation in C#](../../tutorials/exploration/interpolated-strings.yml) interactive tutorial.</span></span> <span data-ttu-id="b4967-151">还可查看另一个 [C# 中的字符串内插](../../tutorials/string-interpolation.md)教程，该教程演示了如何使用内插字符串生成带格式的字符串。</span><span class="sxs-lookup"><span data-stu-id="b4967-151">You can also check another [String interpolation in C#](../../tutorials/string-interpolation.md) tutorial that demonstrates how to use interpolated strings to produce formatted strings.</span></span>

## <a name="compilation-of-interpolated-strings"></a><span data-ttu-id="b4967-152">内插字符串编译</span><span class="sxs-lookup"><span data-stu-id="b4967-152">Compilation of interpolated strings</span></span>

<span data-ttu-id="b4967-153">如果内插字符串类型为 `string`，则通常将其转换为 <xref:System.String.Format%2A?displayProperty=nameWithType> 方法调用。</span><span class="sxs-lookup"><span data-stu-id="b4967-153">If an interpolated string has the type `string`, it's typically transformed into a <xref:System.String.Format%2A?displayProperty=nameWithType> method call.</span></span> <span data-ttu-id="b4967-154">如果分析的行为等同于串联，则编译器可将 <xref:System.String.Format%2A?displayProperty=nameWithType> 替换为 <xref:System.String.Concat%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="b4967-154">The compiler may replace <xref:System.String.Format%2A?displayProperty=nameWithType> with <xref:System.String.Concat%2A?displayProperty=nameWithType> if the analyzed behavior would be equivalent to concatenation.</span></span>

<span data-ttu-id="b4967-155">如果内插字符串类型为 <xref:System.IFormattable> 或 <xref:System.FormattableString>，则编译器会生成对 <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType> 方法的调用。</span><span class="sxs-lookup"><span data-stu-id="b4967-155">If an interpolated string has the type <xref:System.IFormattable> or <xref:System.FormattableString>, the compiler generates a call to the <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType> method.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b4967-156">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="b4967-156">C# language specification</span></span>

<span data-ttu-id="b4967-157">有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)的[内插字符串](~/_csharplang/spec/expressions.md#interpolated-strings)部分。</span><span class="sxs-lookup"><span data-stu-id="b4967-157">For more information, see the [Interpolated strings](~/_csharplang/spec/expressions.md#interpolated-strings) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b4967-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4967-158">See also</span></span>

- [<span data-ttu-id="b4967-159">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b4967-159">C# reference</span></span>](../index.md)
- [<span data-ttu-id="b4967-160">C# 特殊字符</span><span class="sxs-lookup"><span data-stu-id="b4967-160">C# special characters</span></span>](index.md)
- [<span data-ttu-id="b4967-161">字符串</span><span class="sxs-lookup"><span data-stu-id="b4967-161">Strings</span></span>](../../programming-guide/strings/index.md)
- [<span data-ttu-id="b4967-162">标准数字格式字符串</span><span class="sxs-lookup"><span data-stu-id="b4967-162">Standard numeric format strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
- [<span data-ttu-id="b4967-163">复合格式设置</span><span class="sxs-lookup"><span data-stu-id="b4967-163">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- <xref:System.String.Format%2A?displayProperty=nameWithType>
