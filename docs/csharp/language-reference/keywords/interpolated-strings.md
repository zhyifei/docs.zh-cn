---
title: "内插字符串 (C#)"
ms.date: 10/18/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b8a1fe0be82a0e09d61c66ed463199ff626c9faa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="interpolated-strings-c-reference"></a><span data-ttu-id="42caf-102">内插字符串（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="42caf-102">Interpolated Strings (C# Reference)</span></span>

<span data-ttu-id="42caf-103">用于构造字符串。</span><span class="sxs-lookup"><span data-stu-id="42caf-103">Used to construct strings.</span></span>  <span data-ttu-id="42caf-104">内插字符串类似于包含内插表达式的模板字符串。</span><span class="sxs-lookup"><span data-stu-id="42caf-104">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span>  <span data-ttu-id="42caf-105">内插字符串返回的字符串可替换内插表达式并且包含其字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="42caf-105">An interpolated string returns a string that replaces the interpolated expressions that it contains with their string representations.</span></span> <span data-ttu-id="42caf-106">此功能是在 C# 6 和更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="42caf-106">This feature is available in C# 6 and later versions.</span></span>

<span data-ttu-id="42caf-107">与[复合格式字符串](../../../standard/base-types/composite-formatting.md#composite-format-string)相比，内插字符串的参数更易于理解。</span><span class="sxs-lookup"><span data-stu-id="42caf-107">The arguments of an interpolated string are easier to understand than a [composite format string](../../../standard/base-types/composite-formatting.md#composite-format-string).</span></span>  <span data-ttu-id="42caf-108">例如，内插字符串</span><span class="sxs-lookup"><span data-stu-id="42caf-108">For example, the interpolated string</span></span>  
  
```csharp  
Console.WriteLine($"Name = {name}, hours = {hours:hh}");
```  
<span data-ttu-id="42caf-109">包含两个内插表达式：{name} 和 { hour:hh}。</span><span class="sxs-lookup"><span data-stu-id="42caf-109">contains two interpolated expressions, '{name}' and '{hour:hh}'.</span></span> <span data-ttu-id="42caf-110">等效的复合格式字符串为：</span><span class="sxs-lookup"><span data-stu-id="42caf-110">The equivalent composite format string is:</span></span>

```csharp
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

<span data-ttu-id="42caf-111">内插字符串的结构为：</span><span class="sxs-lookup"><span data-stu-id="42caf-111">The structure of an interpolated string is:</span></span>  
  
```  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

<span data-ttu-id="42caf-112">其中：</span><span class="sxs-lookup"><span data-stu-id="42caf-112">where:</span></span> 

- <span data-ttu-id="42caf-113">*field-width* 是一个带符号整数，表示字段中的字符数。</span><span class="sxs-lookup"><span data-stu-id="42caf-113">*field-width* is a signed integer that indicates the number of characters in the field.</span></span> <span data-ttu-id="42caf-114">如果为正数，则字段右对齐；如果为负数，则左对齐。</span><span class="sxs-lookup"><span data-stu-id="42caf-114">If it is positive, the field is right-aligned; if negative, left-aligned.</span></span> 

- <span data-ttu-id="42caf-115">“格式字符串”是适合正在设置格式的对象类型的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="42caf-115">*format-string* is a format string appropriate for the type of object being formatted.</span></span> <span data-ttu-id="42caf-116">例如，对于 <xref:System.DateTime> 值，它可能是标准的日期和时间格式字符串，例如“D”或“d”。</span><span class="sxs-lookup"><span data-stu-id="42caf-116">For example, for a <xref:System.DateTime> value, it could be a standard date and time format string such as "D" or "d".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42caf-117">该字符串开头的`$`和`"`之间不能有任何空白，否则会导致编译时错误。</span><span class="sxs-lookup"><span data-stu-id="42caf-117">You cannot have any whitespace between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="42caf-118">这样做会导致编译时错误。</span><span class="sxs-lookup"><span data-stu-id="42caf-118">Doing so causes a compile time error.</span></span>

 <span data-ttu-id="42caf-119">可以在可使用字符串的任何位置使用内插字符串。</span><span class="sxs-lookup"><span data-stu-id="42caf-119">You can use an interpolated string anywhere you can use a string literal.</span></span>  <span data-ttu-id="42caf-120">每次执行带内插字符串的代码时，都会计算内插字符串。</span><span class="sxs-lookup"><span data-stu-id="42caf-120">The interpolated string is evaluated each time the code with the interpolated string executes.</span></span> <span data-ttu-id="42caf-121">这有助于分隔内插字符串的定义和计算结果。</span><span class="sxs-lookup"><span data-stu-id="42caf-121">This allows you to separate the definition and evaluation of an interpolated string.</span></span>  
  
 <span data-ttu-id="42caf-122">若要在内插字符串中包含大括号（“{”或“}”），请使用两个大括号，即“{{”或“}}”。</span><span class="sxs-lookup"><span data-stu-id="42caf-122">To include a curly brace ("{" or "}") in an interpolated string, use two curly braces, "{{" or "}}".</span></span>  <span data-ttu-id="42caf-123">请参阅“隐式转换”部分以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="42caf-123">See the Implicit Conversions section for more details.</span></span>  

<span data-ttu-id="42caf-124">如果内插字符串包含在内插字符串中具有特殊意义的其他字符，例如引号 (")、冒号 (:) 或逗号 (,)，则出现在文本中时应转义这些字符；如果它们是内插表达式中随附的语言元素，则应将其包括在由括号分隔的表达式内。</span><span class="sxs-lookup"><span data-stu-id="42caf-124">If the interpolated string contains other characters with special meaning in an interpolated string, such as the quotation mark ("), colon (:), or comma (,), they should be escaped if they occur in literal text, or they should be included in an expression delimited by parentheses if they are language elements included in an interpolated expression.</span></span> <span data-ttu-id="42caf-125">以下示例转义了引号以将其包括在结果字符串中，并使用括号来分隔表达式 `(age == 1 ? "" : "s")`，以防冒号被解读为格式字符串的开头。</span><span class="sxs-lookup"><span data-stu-id="42caf-125">The following example escapes quotation marks to include them in the result string, and it uses parentheses to delimit the expression `(age == 1 ? "" : "s")` so that the colon is not interpreted as beginning a format string.</span></span>

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]  

<span data-ttu-id="42caf-126">原义内插字符串使用`$`字符跟`@`字符。</span><span class="sxs-lookup"><span data-stu-id="42caf-126">Verbatim interpolated strings use the `$` character followed by the `@` character.</span></span> <span data-ttu-id="42caf-127">有关原义字符串的详细信息，请参阅[字符串](string.md)主题。</span><span class="sxs-lookup"><span data-stu-id="42caf-127">For more information about verbatim strings, see the [string](string.md) topic.</span></span> <span data-ttu-id="42caf-128">下面的代码是上一个使用原义内插字符串的代码片段的修改版本：</span><span class="sxs-lookup"><span data-stu-id="42caf-128">The following code is a modified version of the previous snippet using a verbatim interpolated string:</span></span>

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings5.cs#1)]  

<span data-ttu-id="42caf-129">格式设置的更改是必需的，因为原义字符串不遵循`\`转义序列。</span><span class="sxs-lookup"><span data-stu-id="42caf-129">The formatting changes are necessary because verbatim strings do not obey `\` escape sequences.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="42caf-130">在原义内插字符串中，`$`令牌必须在`@`令牌之前出现。</span><span class="sxs-lookup"><span data-stu-id="42caf-130">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>


## <a name="implicit-conversions"></a><span data-ttu-id="42caf-131">隐式转换</span><span class="sxs-lookup"><span data-stu-id="42caf-131">Implicit Conversions</span></span>  

<span data-ttu-id="42caf-132">内插字符串有 3 种隐式类型转换：</span><span class="sxs-lookup"><span data-stu-id="42caf-132">There are three implicit type conversions from an interpolated string:</span></span>  

1. <span data-ttu-id="42caf-133">将内插字符串转换为 <xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="42caf-133">Conversion of an interpolated string to a <xref:System.String>.</span></span> <span data-ttu-id="42caf-134">下例返回一个字符串，其内插字符串表达式已替换为字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="42caf-134">The following example returns a string whose interpolated string expressions have been replaced with their string representations.</span></span> <span data-ttu-id="42caf-135">例如: </span><span class="sxs-lookup"><span data-stu-id="42caf-135">For example:</span></span>

   [!code-csharp[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]  

   <span data-ttu-id="42caf-136">这是字符串解释的最终结果。</span><span class="sxs-lookup"><span data-stu-id="42caf-136">This is the final result of a string interpretation.</span></span> <span data-ttu-id="42caf-137">出现的所有双大括号（“{{”和“}}”）都转换为单大括号。</span><span class="sxs-lookup"><span data-stu-id="42caf-137">All occurrences of double curly braces ("{{" and "}}") are converted to a single curly brace.</span></span> 

2. <span data-ttu-id="42caf-138">将内插字符串转换为 <xref:System.IFormattable> 变量，使用此变量可通过单个 <xref:System.IFormattable> 实例创建多个包含区域性特定内容的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="42caf-138">Conversion of an interpolated string to an <xref:System.IFormattable> variable that allows you create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span> <span data-ttu-id="42caf-139">对于包括诸如各区域性的正确数字和日期格式之类的内容，这种转换很有用。</span><span class="sxs-lookup"><span data-stu-id="42caf-139">This is useful for including such things as the correct numeric and date formats for individual cultures.</span></span>  <span data-ttu-id="42caf-140">出现的所有双大括号（“{{”和“}}”）仍保留为双大括号，直至通过显式或隐式调用 <xref:System.Object.ToString> 方法格式化字符串。</span><span class="sxs-lookup"><span data-stu-id="42caf-140">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format the string by explicitly or implicitly calling the <xref:System.Object.ToString> method.</span></span>  <span data-ttu-id="42caf-141">包含的所有内插表达式都转换为 {0}、{1} 等等。</span><span class="sxs-lookup"><span data-stu-id="42caf-141">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="42caf-142">以下示例使用反射来显示内插字符串中所创建的 <xref:System.IFormattable> 变量的成员以及字段和属性值。</span><span class="sxs-lookup"><span data-stu-id="42caf-142">The following example uses reflection to display the members as well as the field and property values of an <xref:System.IFormattable> variable that is created from an interpolated string.</span></span> <span data-ttu-id="42caf-143">它还将传递<xref:System.IFormattable>变量<xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="42caf-143">It also passes the <xref:System.IFormattable> variable to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method.</span></span>

   [!code-csharp[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]  

   <span data-ttu-id="42caf-144">请注意，只能通过使用反射来检查内插字符串。</span><span class="sxs-lookup"><span data-stu-id="42caf-144">Note that the interpolated string can be inspected only by using reflection.</span></span> <span data-ttu-id="42caf-145">如果它将传递到格式设置方法，如字符串<xref:System.Console.WriteLine(System.String)>，其格式项已解决并且返回的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="42caf-145">If it is passed to a string formatting method, such as <xref:System.Console.WriteLine(System.String)>, its format items are resolved and the result string returned.</span></span> 

3. <span data-ttu-id="42caf-146">将内插字符串转换为表示复合格式字符串的 <xref:System.FormattableString> 变量。</span><span class="sxs-lookup"><span data-stu-id="42caf-146">Conversion of an interpolated string to an <xref:System.FormattableString> variable that represents a composite format string.</span></span> <span data-ttu-id="42caf-147">例如，检查复合格式字符串及其呈现为结果字符串的方式可能有助于在生成查询时防止注入攻击。</span><span class="sxs-lookup"><span data-stu-id="42caf-147">Inspecting the composite format string and how it renders as a result string might, for example, help you protect against an injection attack if you were building a query.</span></span> <span data-ttu-id="42caf-148"><xref:System.FormattableString> 还包括 <xref:System.FormattableString.ToString> 重载，可为 <xref:System.Globalization.CultureInfo.InvariantCulture> 和 <xref:System.Globalization.CultureInfo.CurrentCulture> 生成结果字符串。</span><span class="sxs-lookup"><span data-stu-id="42caf-148"><xref:System.FormattableString> also includes <xref:System.FormattableString.ToString> overloads that let you produce result strings for the <xref:System.Globalization.CultureInfo.InvariantCulture> and <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>  <span data-ttu-id="42caf-149">出现的所有双大括号（“{{”和“}}”）都保留为双大括号，直至格式化。</span><span class="sxs-lookup"><span data-stu-id="42caf-149">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces, until you format.</span></span>  <span data-ttu-id="42caf-150">包含的所有内插表达式都转换为 {0}、{1} 等等。</span><span class="sxs-lookup"><span data-stu-id="42caf-150">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   [!code-csharp[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]  

## <a name="language-specification"></a><span data-ttu-id="42caf-151">语言规范</span><span class="sxs-lookup"><span data-stu-id="42caf-151">Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="42caf-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42caf-152">See Also</span></span>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [<span data-ttu-id="42caf-153">C# 参考</span><span class="sxs-lookup"><span data-stu-id="42caf-153">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="42caf-154">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="42caf-154">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
