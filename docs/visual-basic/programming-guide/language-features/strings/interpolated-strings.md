---
title: 内插的字符串 (Visual Basic)
ms.date: 10/31/2017
ms.openlocfilehash: 408f3232258b3b4c7fe6ec160149f8ac70b84b03
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2019
ms.locfileid: "59610673"
---
# <a name="interpolated-strings-visual-basic-reference"></a><span data-ttu-id="4ba36-102">内插的字符串 （Visual Basic 参考）</span><span class="sxs-lookup"><span data-stu-id="4ba36-102">Interpolated Strings (Visual Basic Reference)</span></span>

<span data-ttu-id="4ba36-103">用于构造字符串。</span><span class="sxs-lookup"><span data-stu-id="4ba36-103">Used to construct strings.</span></span>  <span data-ttu-id="4ba36-104">内插字符串类似于包含内插表达式的模板字符串。</span><span class="sxs-lookup"><span data-stu-id="4ba36-104">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span>  <span data-ttu-id="4ba36-105">内插字符串返回的字符串可替换内插表达式并且包含其字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="4ba36-105">An interpolated string returns a string that replaces the interpolated expressions that it contains with their string representations.</span></span> <span data-ttu-id="4ba36-106">此功能现已推出 Visual Basic 14 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="4ba36-106">This feature is available in Visual Basic 14 and later versions.</span></span>

<span data-ttu-id="4ba36-107">与[复合格式字符串](../../../../standard/base-types/composite-formatting.md#composite-format-string)相比，内插字符串的参数更易于理解。</span><span class="sxs-lookup"><span data-stu-id="4ba36-107">The arguments of an interpolated string are easier to understand than a [composite format string](../../../../standard/base-types/composite-formatting.md#composite-format-string).</span></span>  <span data-ttu-id="4ba36-108">例如，内插字符串</span><span class="sxs-lookup"><span data-stu-id="4ba36-108">For example, the interpolated string</span></span>

```vb
Console.WriteLine($"Name = {name}, hours = {hours:hh}")
```

<span data-ttu-id="4ba36-109">包含 2 个内插表达式：“{name}”和“{hours:hh}”。</span><span class="sxs-lookup"><span data-stu-id="4ba36-109">contains two interpolated expressions, '{name}' and '{hours:hh}'.</span></span> <span data-ttu-id="4ba36-110">等效复合格式字符串为：</span><span class="sxs-lookup"><span data-stu-id="4ba36-110">The equivalent composite format string is:</span></span>

```vb
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours);
```

<span data-ttu-id="4ba36-111">内插字符串的结构为：</span><span class="sxs-lookup"><span data-stu-id="4ba36-111">The structure of an interpolated string is:</span></span>

```vb
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."
```

<span data-ttu-id="4ba36-112">其中：</span><span class="sxs-lookup"><span data-stu-id="4ba36-112">where:</span></span>

- <span data-ttu-id="4ba36-113">*field-width* 是一个带符号整数，表示字段中的字符数。</span><span class="sxs-lookup"><span data-stu-id="4ba36-113">*field-width* is a signed integer that indicates the number of characters in the field.</span></span> <span data-ttu-id="4ba36-114">如果为正数，则字段右对齐；如果为负数，则左对齐。</span><span class="sxs-lookup"><span data-stu-id="4ba36-114">If it is positive, the field is right-aligned; if negative, left-aligned.</span></span>

- <span data-ttu-id="4ba36-115">“格式字符串”是适合正在设置格式的对象类型的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="4ba36-115">*format-string* is a format string appropriate for the type of object being formatted.</span></span> <span data-ttu-id="4ba36-116">例如，对于<xref:System.DateTime>的值，它可以是[标准日期和时间格式字符串](~/docs/standard/base-types/standard-date-and-time-format-strings.md)如"D"或"d"。</span><span class="sxs-lookup"><span data-stu-id="4ba36-116">For example, for a <xref:System.DateTime> value, it could be a [standard date and time format string](~/docs/standard/base-types/standard-date-and-time-format-strings.md) such as "D" or "d".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4ba36-117">字符串开头的 `$` 和 `"` 之间不能有任何空格。</span><span class="sxs-lookup"><span data-stu-id="4ba36-117">You cannot have any white space between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="4ba36-118">这样做会导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="4ba36-118">Doing so causes a compiler error.</span></span>

<span data-ttu-id="4ba36-119">可以在可使用字符串的任何位置使用内插字符串。</span><span class="sxs-lookup"><span data-stu-id="4ba36-119">You can use an interpolated string anywhere you can use a string literal.</span></span>  <span data-ttu-id="4ba36-120">每次执行带内插字符串的代码时，都会计算内插字符串。</span><span class="sxs-lookup"><span data-stu-id="4ba36-120">The interpolated string is evaluated each time the code with the interpolated string executes.</span></span> <span data-ttu-id="4ba36-121">这有助于分隔内插字符串的定义和计算结果。</span><span class="sxs-lookup"><span data-stu-id="4ba36-121">This allows you to separate the definition and evaluation of an interpolated string.</span></span>

<span data-ttu-id="4ba36-122">若要在内插字符串中包含大括号（“{”或“}”），请使用两个大括号，即“{{”或“}}”。</span><span class="sxs-lookup"><span data-stu-id="4ba36-122">To include a curly brace ("{" or "}") in an interpolated string, use two curly braces, "{{" or "}}".</span></span>  <span data-ttu-id="4ba36-123">请参阅“隐式转换”部分以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="4ba36-123">See the Implicit Conversions section for more details.</span></span>

<span data-ttu-id="4ba36-124">如果内插字符串包含在内插字符串中具有特殊意义的其他字符，例如引号 (")、冒号 (:) 或逗号 (,)，则出现在文本中时应转义这些字符；如果它们是内插表达式中随附的语言元素，则应将其包括在由括号分隔的表达式内。</span><span class="sxs-lookup"><span data-stu-id="4ba36-124">If the interpolated string contains other characters with special meaning in an interpolated string, such as the quotation mark ("), colon (:), or comma (,), they should be escaped if they occur in literal text, or they should be included in an expression delimited by parentheses if they are language elements included in an interpolated expression.</span></span> <span data-ttu-id="4ba36-125">以下示例转义了引号以将其包括在结果字符串中，并使用括号来分隔表达式 `(age == 1 ? "" : "s")`，以防冒号被解读为格式字符串的开头。</span><span class="sxs-lookup"><span data-stu-id="4ba36-125">The following example escapes quotation marks to include them in the result string, and it uses parentheses to delimit the expression `(age == 1 ? "" : "s")` so that the colon is not interpreted as beginning a format string.</span></span>

[!code-vb[interpolated-strings](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings4.vb)]

## <a name="implicit-conversions"></a><span data-ttu-id="4ba36-126">隐式转换</span><span class="sxs-lookup"><span data-stu-id="4ba36-126">Implicit Conversions</span></span>

<span data-ttu-id="4ba36-127">内插字符串有 3 种隐式类型转换：</span><span class="sxs-lookup"><span data-stu-id="4ba36-127">There are three implicit type conversions from an interpolated string:</span></span>

1. <span data-ttu-id="4ba36-128">将内插字符串转换为 <xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="4ba36-128">Conversion of an interpolated string to a <xref:System.String>.</span></span> <span data-ttu-id="4ba36-129">下例返回一个字符串，其内插字符串表达式已替换为字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="4ba36-129">The following example returns a string whose interpolated string expressions have been replaced with their string representations.</span></span> <span data-ttu-id="4ba36-130">例如：</span><span class="sxs-lookup"><span data-stu-id="4ba36-130">For example:</span></span>

   [!code-vb[interpolated-strings1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings1.vb)]

   <span data-ttu-id="4ba36-131">这是字符串解释的最终结果。</span><span class="sxs-lookup"><span data-stu-id="4ba36-131">This is the final result of a string interpretation.</span></span> <span data-ttu-id="4ba36-132">出现的所有双大括号（“{{”和“}}”）都转换为单大括号。</span><span class="sxs-lookup"><span data-stu-id="4ba36-132">All occurrences of double curly braces ("{{" and "}}") are converted to a single curly brace.</span></span>

2. <span data-ttu-id="4ba36-133">将内插字符串转换为 <xref:System.IFormattable> 变量，使用此变量可通过单个 <xref:System.IFormattable> 实例创建多个包含区域性特定内容的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="4ba36-133">Conversion of an interpolated string to an <xref:System.IFormattable> variable that allows you create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span> <span data-ttu-id="4ba36-134">对于包括诸如各区域性的正确数字和日期格式之类的内容，这种转换很有用。</span><span class="sxs-lookup"><span data-stu-id="4ba36-134">This is useful for including such things as the correct numeric and date formats for individual cultures.</span></span>  <span data-ttu-id="4ba36-135">出现的所有双大括号（“{{”和“}}”）仍保留为双大括号，直至通过显式或隐式调用 <xref:System.Object.ToString> 方法格式化字符串。</span><span class="sxs-lookup"><span data-stu-id="4ba36-135">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format the string by explicitly or implicitly calling the <xref:System.Object.ToString> method.</span></span>  <span data-ttu-id="4ba36-136">所有包含的内插表达式都转换为{0}， {1}，依次类推。</span><span class="sxs-lookup"><span data-stu-id="4ba36-136">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>

   <span data-ttu-id="4ba36-137">以下示例使用反射来显示内插字符串中所创建的 <xref:System.IFormattable> 变量的成员以及字段和属性值。</span><span class="sxs-lookup"><span data-stu-id="4ba36-137">The following example uses reflection to display the members as well as the field and property values of an <xref:System.IFormattable> variable that is created from an interpolated string.</span></span> <span data-ttu-id="4ba36-138">并将 <xref:System.IFormattable> 变量传递给 <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="4ba36-138">It also passes the <xref:System.IFormattable> variable to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method.</span></span>

   [!code-vb[interpolated-strings2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings2.vb)]

   <span data-ttu-id="4ba36-139">请注意，只能通过使用反射来检查内插字符串。</span><span class="sxs-lookup"><span data-stu-id="4ba36-139">Note that the interpolated string can be inspected only by using reflection.</span></span> <span data-ttu-id="4ba36-140">如果将其传递给字符串格式设置方法，例如 <xref:System.Console.WriteLine(System.String)>，则会解析其格式项并返回结果字符串。</span><span class="sxs-lookup"><span data-stu-id="4ba36-140">If it is passed to a string formatting method, such as <xref:System.Console.WriteLine(System.String)>, its format items are resolved and the result string returned.</span></span>

3. <span data-ttu-id="4ba36-141">内插字符串转换为<xref:System.FormattableString>表示复合格式字符串的变量。</span><span class="sxs-lookup"><span data-stu-id="4ba36-141">Conversion of an interpolated string to a <xref:System.FormattableString> variable that represents a composite format string.</span></span> <span data-ttu-id="4ba36-142">例如，检查复合格式字符串及其呈现为结果字符串的方式可能有助于在生成查询时防止注入攻击。</span><span class="sxs-lookup"><span data-stu-id="4ba36-142">Inspecting the composite format string and how it renders as a result string might, for example, help you protect against an injection attack if you were building a query.</span></span> <span data-ttu-id="4ba36-143">一个<xref:System.FormattableString>还包括：</span><span class="sxs-lookup"><span data-stu-id="4ba36-143">A <xref:System.FormattableString> also includes:</span></span>

      - <span data-ttu-id="4ba36-144"><xref:System.FormattableString.ToString> 重载，生成 <xref:System.Globalization.CultureInfo.CurrentCulture> 的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="4ba36-144">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>

      - <span data-ttu-id="4ba36-145">一个<xref:System.FormattableString.Invariant%2A>方法，生成的字符串<xref:System.Globalization.CultureInfo.InvariantCulture>。</span><span class="sxs-lookup"><span data-stu-id="4ba36-145">A <xref:System.FormattableString.Invariant%2A> method that produces a string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>

      - <span data-ttu-id="4ba36-146"><xref:System.FormattableString.ToString(System.IFormatProvider)> 方法，生成特定区域性的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="4ba36-146">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

    <span data-ttu-id="4ba36-147">出现的所有双大括号 ("{{"和"}}") 仍保留为双大括号直至您设置的格式。</span><span class="sxs-lookup"><span data-stu-id="4ba36-147">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format.</span></span>  <span data-ttu-id="4ba36-148">所有包含的内插表达式都转换为{0}， {1}，依次类推。</span><span class="sxs-lookup"><span data-stu-id="4ba36-148">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>

   [!code-vb[interpolated-strings3](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings3.vb)]

## <a name="see-also"></a><span data-ttu-id="4ba36-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ba36-149">See also</span></span>

- <xref:System.IFormattable?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- [<span data-ttu-id="4ba36-150">Visual Basic 语言参考</span><span class="sxs-lookup"><span data-stu-id="4ba36-150">Visual Basic Language Reference</span></span>](index.md)
