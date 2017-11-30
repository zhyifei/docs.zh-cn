---
title: "内插的字符串 (Visual Basic)"
ms.date: 10/31/2017
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f865d5a7167847bf869d70a39570413dac271a2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="interpolated-strings-visual-basic-reference"></a><span data-ttu-id="53f8c-102">内插的字符串 （Visual Basic 参考）</span><span class="sxs-lookup"><span data-stu-id="53f8c-102">Interpolated Strings (Visual Basic Reference)</span></span>

<span data-ttu-id="53f8c-103">用于构造字符串。</span><span class="sxs-lookup"><span data-stu-id="53f8c-103">Used to construct strings.</span></span>  <span data-ttu-id="53f8c-104">内插字符串类似于包含内插表达式的模板字符串。</span><span class="sxs-lookup"><span data-stu-id="53f8c-104">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span>  <span data-ttu-id="53f8c-105">内插字符串返回的字符串可替换内插表达式并且包含其字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="53f8c-105">An interpolated string returns a string that replaces the interpolated expressions that it contains with their string representations.</span></span> <span data-ttu-id="53f8c-106">此功能是在 Visual Basic 14 和更高版本中可用。</span><span class="sxs-lookup"><span data-stu-id="53f8c-106">This feature is available in Visual Basic 14 and later versions.</span></span>

<span data-ttu-id="53f8c-107">与[复合格式字符串](../../../../standard/base-types/composite-formatting.md#composite-format-string)相比，内插字符串的参数更易于理解。</span><span class="sxs-lookup"><span data-stu-id="53f8c-107">The arguments of an interpolated string are easier to understand than a [composite format string](../../../../standard/base-types/composite-formatting.md#composite-format-string).</span></span>  <span data-ttu-id="53f8c-108">例如，内插字符串</span><span class="sxs-lookup"><span data-stu-id="53f8c-108">For example, the interpolated string</span></span>  
  
```vb  
Console.WriteLine($"Name = {name}, hours = {hours:hh}")
```  
<span data-ttu-id="53f8c-109">包含 2 个内插表达式：“{name}”和“{hours:hh}”。</span><span class="sxs-lookup"><span data-stu-id="53f8c-109">contains two interpolated expressions, '{name}' and '{hours:hh}'.</span></span> <span data-ttu-id="53f8c-110">等效复合格式字符串为：</span><span class="sxs-lookup"><span data-stu-id="53f8c-110">The equivalent composite format string is:</span></span>

```vb
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

<span data-ttu-id="53f8c-111">内插字符串的结构为：</span><span class="sxs-lookup"><span data-stu-id="53f8c-111">The structure of an interpolated string is:</span></span>  
  
```vb  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

<span data-ttu-id="53f8c-112">其中：</span><span class="sxs-lookup"><span data-stu-id="53f8c-112">where:</span></span> 

- <span data-ttu-id="53f8c-113">*field-width* 是一个带符号整数，表示字段中的字符数。</span><span class="sxs-lookup"><span data-stu-id="53f8c-113">*field-width* is a signed integer that indicates the number of characters in the field.</span></span> <span data-ttu-id="53f8c-114">如果为正数，则字段右对齐；如果为负数，则左对齐。</span><span class="sxs-lookup"><span data-stu-id="53f8c-114">If it is positive, the field is right-aligned; if negative, left-aligned.</span></span> 

- <span data-ttu-id="53f8c-115">“格式字符串”是适合正在设置格式的对象类型的格式字符串。</span><span class="sxs-lookup"><span data-stu-id="53f8c-115">*format-string* is a format string appropriate for the type of object being formatted.</span></span> <span data-ttu-id="53f8c-116">例如，对于<xref:System.DateTime>值，它可以是[标准日期和时间格式字符串](~/docs/standard/base-types/standard-date-and-time-format-strings.md)如"D"或"d"。</span><span class="sxs-lookup"><span data-stu-id="53f8c-116">For example, for a <xref:System.DateTime> value, it could be a [standard date and time format string](~/docs/standard/base-types/standard-date-and-time-format-strings.md) such as "D" or "d".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53f8c-117">不能具有之间的所有空白`$`和`"`开头的字符串。</span><span class="sxs-lookup"><span data-stu-id="53f8c-117">You cannot have any whitespace between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="53f8c-118">这样做会导致编译器错误。</span><span class="sxs-lookup"><span data-stu-id="53f8c-118">Doing so causes a compiler error.</span></span>

 <span data-ttu-id="53f8c-119">可以在可使用字符串的任何位置使用内插字符串。</span><span class="sxs-lookup"><span data-stu-id="53f8c-119">You can use an interpolated string anywhere you can use a string literal.</span></span>  <span data-ttu-id="53f8c-120">每次执行带内插字符串的代码时，都会计算内插字符串。</span><span class="sxs-lookup"><span data-stu-id="53f8c-120">The interpolated string is evaluated each time the code with the interpolated string executes.</span></span> <span data-ttu-id="53f8c-121">这有助于分隔内插字符串的定义和计算结果。</span><span class="sxs-lookup"><span data-stu-id="53f8c-121">This allows you to separate the definition and evaluation of an interpolated string.</span></span>  
  
 <span data-ttu-id="53f8c-122">若要在内插字符串中包含大括号（“{”或“}”），请使用两个大括号，即“{{”或“}}”。</span><span class="sxs-lookup"><span data-stu-id="53f8c-122">To include a curly brace ("{" or "}") in an interpolated string, use two curly braces, "{{" or "}}".</span></span>  <span data-ttu-id="53f8c-123">请参阅“隐式转换”部分以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="53f8c-123">See the Implicit Conversions section for more details.</span></span>  

<span data-ttu-id="53f8c-124">如果内插字符串包含在内插字符串中具有特殊意义的其他字符，例如引号 (")、冒号 (:) 或逗号 (,)，则出现在文本中时应转义这些字符；如果它们是内插表达式中随附的语言元素，则应将其包括在由括号分隔的表达式内。</span><span class="sxs-lookup"><span data-stu-id="53f8c-124">If the interpolated string contains other characters with special meaning in an interpolated string, such as the quotation mark ("), colon (:), or comma (,), they should be escaped if they occur in literal text, or they should be included in an expression delimited by parentheses if they are language elements included in an interpolated expression.</span></span> <span data-ttu-id="53f8c-125">以下示例转义了引号以将其包括在结果字符串中，并使用括号来分隔表达式 `(age == 1 ? "" : "s")`，以防冒号被解读为格式字符串的开头。</span><span class="sxs-lookup"><span data-stu-id="53f8c-125">The following example escapes quotation marks to include them in the result string, and it uses parentheses to delimit the expression `(age == 1 ? "" : "s")` so that the colon is not interpreted as beginning a format string.</span></span>

[!code-vb[interpolated-strings](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings4.vb)]  

## <a name="implicit-conversions"></a><span data-ttu-id="53f8c-126">隐式转换</span><span class="sxs-lookup"><span data-stu-id="53f8c-126">Implicit Conversions</span></span>  

<span data-ttu-id="53f8c-127">内插字符串有 3 种隐式类型转换：</span><span class="sxs-lookup"><span data-stu-id="53f8c-127">There are three implicit type conversions from an interpolated string:</span></span>  

1. <span data-ttu-id="53f8c-128">将内插字符串转换为 <xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="53f8c-128">Conversion of an interpolated string to a <xref:System.String>.</span></span> <span data-ttu-id="53f8c-129">下例返回一个字符串，其内插字符串表达式已替换为字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="53f8c-129">The following example returns a string whose interpolated string expressions have been replaced with their string representations.</span></span> <span data-ttu-id="53f8c-130">例如: </span><span class="sxs-lookup"><span data-stu-id="53f8c-130">For example:</span></span>

   [!code-vb[interpolated-strings1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings1.vb)]  

   <span data-ttu-id="53f8c-131">这是字符串解释的最终结果。</span><span class="sxs-lookup"><span data-stu-id="53f8c-131">This is the final result of a string interpretation.</span></span> <span data-ttu-id="53f8c-132">出现的所有双大括号（“{{”和“}}”）都转换为单大括号。</span><span class="sxs-lookup"><span data-stu-id="53f8c-132">All occurrences of double curly braces ("{{" and "}}") are converted to a single curly brace.</span></span> 

2. <span data-ttu-id="53f8c-133">将内插字符串转换为 <xref:System.IFormattable> 变量，使用此变量可通过单个 <xref:System.IFormattable> 实例创建多个包含区域性特定内容的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="53f8c-133">Conversion of an interpolated string to an <xref:System.IFormattable> variable that allows you create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span> <span data-ttu-id="53f8c-134">对于包括诸如各区域性的正确数字和日期格式之类的内容，这种转换很有用。</span><span class="sxs-lookup"><span data-stu-id="53f8c-134">This is useful for including such things as the correct numeric and date formats for individual cultures.</span></span>  <span data-ttu-id="53f8c-135">出现的所有双大括号（“{{”和“}}”）仍保留为双大括号，直至通过显式或隐式调用 <xref:System.Object.ToString> 方法格式化字符串。</span><span class="sxs-lookup"><span data-stu-id="53f8c-135">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format the string by explicitly or implicitly calling the <xref:System.Object.ToString> method.</span></span>  <span data-ttu-id="53f8c-136">包含的所有内插表达式都转换为 {0}、{1} 等等。</span><span class="sxs-lookup"><span data-stu-id="53f8c-136">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="53f8c-137">以下示例使用反射来显示内插字符串中所创建的 <xref:System.IFormattable> 变量的成员以及字段和属性值。</span><span class="sxs-lookup"><span data-stu-id="53f8c-137">The following example uses reflection to display the members as well as the field and property values of an <xref:System.IFormattable> variable that is created from an interpolated string.</span></span> <span data-ttu-id="53f8c-138">它还将传递<xref:System.IFormattable>变量<xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="53f8c-138">It also passes the <xref:System.IFormattable> variable to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method.</span></span>

   [!code-vb[interpolated-strings2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings2.vb)]  

   <span data-ttu-id="53f8c-139">请注意，只能通过使用反射来检查内插字符串。</span><span class="sxs-lookup"><span data-stu-id="53f8c-139">Note that the interpolated string can be inspected only by using reflection.</span></span> <span data-ttu-id="53f8c-140">如果它将传递到格式设置方法，如字符串<xref:System.Console.WriteLine(System.String)>，其格式项已解决并且返回的结果字符串。</span><span class="sxs-lookup"><span data-stu-id="53f8c-140">If it is passed to a string formatting method, such as <xref:System.Console.WriteLine(System.String)>, its format items are resolved and the result string returned.</span></span> 

3. <span data-ttu-id="53f8c-141">转换到相比内, 插字符串的<xref:System.FormattableString>表示复合格式字符串的变量。</span><span class="sxs-lookup"><span data-stu-id="53f8c-141">Conversion of an interpolated string to a <xref:System.FormattableString> variable that represents a composite format string.</span></span> <span data-ttu-id="53f8c-142">例如，检查复合格式字符串及其呈现为结果字符串的方式可能有助于在生成查询时防止注入攻击。</span><span class="sxs-lookup"><span data-stu-id="53f8c-142">Inspecting the composite format string and how it renders as a result string might, for example, help you protect against an injection attack if you were building a query.</span></span> <span data-ttu-id="53f8c-143">A<xref:System.FormattableString>还包括：</span><span class="sxs-lookup"><span data-stu-id="53f8c-143">A <xref:System.FormattableString> also includes:</span></span>

      - <span data-ttu-id="53f8c-144">A<xref:System.FormattableString.ToString>产生的结果字符串的重载<xref:System.Globalization.CultureInfo.CurrentCulture>。</span><span class="sxs-lookup"><span data-stu-id="53f8c-144">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      
      - <span data-ttu-id="53f8c-145">A<xref:System.FormattableString.Invariant%2A>要求方法能够生成的字符串<xref:System.Globalization.CultureInfo.InvariantCulture>。</span><span class="sxs-lookup"><span data-stu-id="53f8c-145">A <xref:System.FormattableString.Invariant%2A> method that produces a string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      
      - <span data-ttu-id="53f8c-146">A<xref:System.FormattableString.ToString(System.IFormatProvider)>产生指定的区域性的结果字符串的方法。</span><span class="sxs-lookup"><span data-stu-id="53f8c-146">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span> 
  
    <span data-ttu-id="53f8c-147">将出现所有双大括号 ("{{"和"}}") 设置格式之前保持为双大括号。</span><span class="sxs-lookup"><span data-stu-id="53f8c-147">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format.</span></span>  <span data-ttu-id="53f8c-148">包含的所有内插表达式都转换为 {0}、{1} 等等。</span><span class="sxs-lookup"><span data-stu-id="53f8c-148">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   [!code-vb[interpolated-strings3](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings3.vb)]  

## <a name="see-also"></a><span data-ttu-id="53f8c-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53f8c-149">See Also</span></span>  
<span data-ttu-id="53f8c-150">f<xref:System.IFormattable?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="53f8c-150">f <xref:System.IFormattable?displayProperty=nameWithType></span></span>   
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [<span data-ttu-id="53f8c-151">Visual Basic 语言参考</span><span class="sxs-lookup"><span data-stu-id="53f8c-151">Visual Basic Language Reference</span></span>](index.md)  
 