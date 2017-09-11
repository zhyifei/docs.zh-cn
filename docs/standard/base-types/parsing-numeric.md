---
title: "在 .NET 中分析数字字符串"
description: "在 .NET 中分析数字字符串"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e393430a-731a-49fa-83de-ff7ed52d5704
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 85cd57d33b03f7a2105ee3f770b2f8bcc0a57ee4
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-numeric-strings-in-net"></a><span data-ttu-id="6ec16-104">在 .NET 中分析数字字符串</span><span class="sxs-lookup"><span data-stu-id="6ec16-104">Parsing numeric strings in .NET</span></span>

<span data-ttu-id="6ec16-105">所有数字类型都具有两个静态分析方法（`Parse` 和 `TryParse`），可以使用它们将数字的字符串表示形式转换为数字类型。</span><span class="sxs-lookup"><span data-stu-id="6ec16-105">All numeric types have two static parsing methods, `Parse` and `TryParse`, that you can use to convert the string representation of a number into a numeric type.</span></span> <span data-ttu-id="6ec16-106">这两个方法使你可以分析使用[标准数字格式字符串](standard-numeric.md)和[自定义数字格式字符串](custom-numeric.md)中所述的格式字符串生成的字符串。</span><span class="sxs-lookup"><span data-stu-id="6ec16-106">These methods enable you to parse strings that were produced by using the format strings documented in [Standard Numeric Format Strings](standard-numeric.md) and [Custom Numeric Format Strings](custom-numeric.md).</span></span> <span data-ttu-id="6ec16-107">默认情况下，`Parse` 和 `TryParse` 方法可以成功地将仅包含整数十进制数字的字符串转化为整数值。</span><span class="sxs-lookup"><span data-stu-id="6ec16-107">By default, the `Parse` and `TryParse` methods can successfully convert strings that contain integral decimal digits only to integer values.</span></span> <span data-ttu-id="6ec16-108">它们可以将包含整数和小数十进制数字、组分隔符和十进制分隔符的字符串转换为浮点值。</span><span class="sxs-lookup"><span data-stu-id="6ec16-108">They can successfully convert strings that contain integral and fractional decimal digits, group separators, and a decimal separator to floating-point values.</span></span> <span data-ttu-id="6ec16-109">`Parse` 方法在操作失败时引发异常，而 `TryParse` 方法返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="6ec16-109">The `Parse` method throws an exception if the operation fails, whereas the `TryParse` method returns `false`.</span></span>

## <a name="parsing-and-format-providers"></a><span data-ttu-id="6ec16-110">分析和格式提供程序</span><span class="sxs-lookup"><span data-stu-id="6ec16-110">Parsing and format providers</span></span>

<span data-ttu-id="6ec16-111">通常，数值的字符串表示因区域性而异。</span><span class="sxs-lookup"><span data-stu-id="6ec16-111">Typically, the string representations of numeric values differ by culture.</span></span> <span data-ttu-id="6ec16-112">数值字符串的元素都会因区域性而异，如货币符号、组（或千位）分隔符和十进制分隔符。</span><span class="sxs-lookup"><span data-stu-id="6ec16-112">Elements of numeric strings such as currency symbols, group (or thousands) separators, and decimal separators all vary by culture.</span></span> <span data-ttu-id="6ec16-113">分析方法可隐式或显式使用可以识别这些特定于区域性的变体的格式提供程序。</span><span class="sxs-lookup"><span data-stu-id="6ec16-113">Parsing methods either implicitly or explicitly use a format provider that recognizes these culture-specific variations.</span></span> <span data-ttu-id="6ec16-114">如果在对 `Parse` 或 `TryParse` 方法的调用中未指定任何格式提供程序，则会使用与当前线程区域性关联的格式提供程序（[NumberFormatInfo.CurrentInfo](xref:System.Globalization.NumberFormatInfo.CurrentInfo) 属性返回的 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 对象）。</span><span class="sxs-lookup"><span data-stu-id="6ec16-114">If no format provider is specified in a call to the `Parse` or `TryParse` method, the format provider associated with the current thread culture (the [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object returned by the [NumberFormatInfo.CurrentInfo](xref:System.Globalization.NumberFormatInfo.CurrentInfo) property) is used.</span></span> 

<span data-ttu-id="6ec16-115">格式提供程序由 [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) 实现来表示。</span><span class="sxs-lookup"><span data-stu-id="6ec16-115">A format provider is represented by an [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) implementation.</span></span> <span data-ttu-id="6ec16-116">此接口具有单个成员，即 [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) 方法，其单个参数是表示要设置格式的类型的 [Type](xref:System.Type) 对象。</span><span class="sxs-lookup"><span data-stu-id="6ec16-116">This interface has a single member, the [GetFormat](xref:System.IFormatProvider.GetFormat(System.Type)) method, whose single parameter is a [Type](xref:System.Type) object that represents the type to be formatted.</span></span> <span data-ttu-id="6ec16-117">此方法返回提供格式设置信息的对象。</span><span class="sxs-lookup"><span data-stu-id="6ec16-117">This method returns the object that provides formatting information.</span></span> <span data-ttu-id="6ec16-118">.NET 支持以下两个 [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) 实现以便用于分析数字字符串：</span><span class="sxs-lookup"><span data-stu-id="6ec16-118">.NET supports the following two [IFormatProvider](xref:System.Globalization.NumberFormatInfo.CurrentInfo) implementations for parsing numeric strings:</span></span>

* <span data-ttu-id="6ec16-119">[CultureInfo](xref:System.Globalization.CultureInfo) 对象，其 [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) 方法返回提供特定于区域性的格式设置信息的 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="6ec16-119">A [CultureInfo](xref:System.Globalization.CultureInfo) object whose [CultureInfo.GetFormat](xref:System.Globalization.CultureInfo.GetFormat(System.Type)) method returns a [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object that provides culture-specific formatting information.</span></span>

* <span data-ttu-id="6ec16-120">[NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 对象，其 [NumberFormatInfo.GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) 方法返回其自身。</span><span class="sxs-lookup"><span data-stu-id="6ec16-120">A [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object whose [NumberFormatInfo.GetFormat](xref:System.Globalization.NumberFormatInfo.GetFormat(System.Type)) method returns itself.</span></span>

<span data-ttu-id="6ec16-121">下面的示例尝试将数组中的每个字符串都转换为 [Double](xref:System.Double) 值。</span><span class="sxs-lookup"><span data-stu-id="6ec16-121">The following example tries to convert each string in an array to a [Double](xref:System.Double) value.</span></span> <span data-ttu-id="6ec16-122">它首先尝试使用反映“英语(美国)”区域性约定的格式提供程序来分析字符串。</span><span class="sxs-lookup"><span data-stu-id="6ec16-122">It first tries to parse the string by using a format provider that reflects the conventions of the English (United States) culture.</span></span> <span data-ttu-id="6ec16-123">如果此操作引发 [FormatException](xref:System.FormatException)，则它会尝试使用反映“法语(法国)”区域性约定的格式提供程序来分析字符串。</span><span class="sxs-lookup"><span data-stu-id="6ec16-123">If this operation throws a [FormatException](xref:System.FormatException), it tries to parse the string by using a format provider that reflects the conventions of the French (France) culture.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string[] values = { "1,304.16", "$1,456.78", "1,094", "152", 
                          "123,45 €", "1 304,16", "Ae9f" };
      double number;
      CultureInfo culture = null;

      foreach (string value in values) {
         try {
            culture = CultureInfo.CreateSpecificCulture("en-US");
            number = Double.Parse(value, culture);
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
         }   
         catch (FormatException) {
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value);
            culture = CultureInfo.CreateSpecificCulture("fr-FR");
            try {
               number = Double.Parse(value, culture);
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number);
            }
            catch (FormatException) {
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value);
            }
         }
         Console.WriteLine();
      }   
   }
}
// The example displays the following output:
//    en-US: 1,304.16 --> 1304.16
//    
//    en-US: Unable to parse '$1,456.78'.
//    fr-FR: Unable to parse '$1,456.78'.
//    
//    en-US: 1,094 --> 1094
//    
//    en-US: 152 --> 152
//    
//    en-US: Unable to parse '123,45 €'.
//    fr-FR: Unable to parse '123,45 €'.
//    
//    en-US: Unable to parse '1 304,16'.
//    fr-FR: 1 304,16 --> 1304.16
//    
//    en-US: Unable to parse 'Ae9f'.
//    fr-FR: Unable to parse 'Ae9f'.
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim values() As String = { "1,304.16", "$1,456.78", "1,094", "152", 
                                 "123,45 €", "1 304,16", "Ae9f" }
      Dim number As Double
      Dim culture As CultureInfo = Nothing

      For Each value As String In values
         Try
            culture = CultureInfo.CreateSpecificCulture("en-US")
            number = Double.Parse(value, culture)
            Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
         Catch e As FormatException
            Console.WriteLine("{0}: Unable to parse '{1}'.", 
                              culture.Name, value)
            culture = CultureInfo.CreateSpecificCulture("fr-FR")
            Try
               number = Double.Parse(value, culture)
               Console.WriteLine("{0}: {1} --> {2}", culture.Name, value, number)
            Catch ex As FormatException
               Console.WriteLine("{0}: Unable to parse '{1}'.", 
                                 culture.Name, value)
            End Try
         End Try
         Console.WriteLine()
      Next
   End Sub
End Module
' The example displays the following output:
'    en-US: 1,304.16 --> 1304.16
'    
'    en-US: Unable to parse '$1,456.78'.
'    fr-FR: Unable to parse '$1,456.78'.
'    
'    en-US: 1,094 --> 1094
'    
'    en-US: 152 --> 152
'    
'    en-US: Unable to parse '123,45 €'.
'    fr-FR: Unable to parse '123,45 €'.
'    
'    en-US: Unable to parse '1 304,16'.
'    fr-FR: 1 304,16 --> 1304.16
'    
'    en-US: Unable to parse 'Ae9f'.
'    fr-FR: Unable to parse 'Ae9f'.
```

## <a name="parsing-and-numberstyles-values"></a><span data-ttu-id="6ec16-124">分析和 NumberStyles 值</span><span class="sxs-lookup"><span data-stu-id="6ec16-124">Parsing and NumberStyles values</span></span>

<span data-ttu-id="6ec16-125">分析操作可以处理的样式元素（如空格、组分隔符和小数点分隔符）由 [NumberStyles](xref:System.Globalization.NumberStyles) 枚举值定义。</span><span class="sxs-lookup"><span data-stu-id="6ec16-125">The style elements (such as white space, group separators, and decimal separator) that the parse operation can handle are defined by a [NumberStyles](xref:System.Globalization.NumberStyles) enumeration value.</span></span> <span data-ttu-id="6ec16-126">默认情况下，表示整数值的字符串使用 [NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer) 值进行分析，该值仅允许数字、前导和尾随空格以及前导符号。</span><span class="sxs-lookup"><span data-stu-id="6ec16-126">By default, strings that represent integer values are parsed by using the [NumberStyles.Integer](xref:System.Globalization.NumberStyles.Integer) value, which permits only numeric digits, leading and trailing white space, and a leading sign.</span></span> <span data-ttu-id="6ec16-127">表示浮点值的字符串结合使用 [NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) 和 [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) 值进行分析；此复合样式允许数字以及前导和尾随空格、前导符号、十进制分隔符、组分隔符和指数。</span><span class="sxs-lookup"><span data-stu-id="6ec16-127">Strings that represent floating-point values are parsed using a combination of the [NumberStyles.Float](xref:System.Globalization.NumberStyles.Float) and [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) values; this composite style permits decimal digits along with leading and trailing white space, a leading sign, a decimal separator, a group separator, and an exponent.</span></span> <span data-ttu-id="6ec16-128">通过调用包含类型为 [NumberStyles](xref:System.Globalization.NumberStyles) 的参数的 `Parse` 或 `TryParse` 方法的重载以及设置一个或多个 [NumberStyles](xref:System.Globalization.NumberStyles) 标志，可以控制可在字符串中存在的样式元素，以便分析操作成功。</span><span class="sxs-lookup"><span data-stu-id="6ec16-128">By calling an overload of the `Parse` or `TryParse` method that includes a parameter of type [NumberStyles](xref:System.Globalization.NumberStyles) and setting one or more [NumberStyles](xref:System.Globalization.NumberStyles) flags, you can control the style elements that can be present in the string for the parse operation to succeed.</span></span> 

<span data-ttu-id="6ec16-129">例如，包含组分隔符的字符串无法使用 [Int32.Parse(String)](xref:System.Int32.Parse(System.String)) 方法转换为 [Int32](xref:System.Int32) 值。</span><span class="sxs-lookup"><span data-stu-id="6ec16-129">For example, a string that contains a group separator cannot be converted to an [Int32](xref:System.Int32) value by using the [Int32.Parse(String)](xref:System.Int32.Parse(System.String)) method.</span></span> <span data-ttu-id="6ec16-130">但是，如果使用 [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) 标志，则可成功转换，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="6ec16-130">However, the conversion succeeds if you use the [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) flag, as the following example illustrates.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      string value = "1,304";
      int number;
      IFormatProvider provider = CultureInfo.CreateSpecificCulture("en-US");
      if (Int32.TryParse(value, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);

      if (Int32.TryParse(value, NumberStyles.Integer | NumberStyles.AllowThousands, 
                        provider, out number))
         Console.WriteLine("{0} --> {1}", value, number);
      else
         Console.WriteLine("Unable to convert '{0}'", value);
   }
}
// The example displays the following output:
//       Unable to convert '1,304'
//       1,304 --> 1304
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim value As String = "1,304"
      Dim number As Integer
      Dim provider As IFormatProvider = CultureInfo.CreateSpecificCulture("en-US")
      If Int32.TryParse(value, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If

      If Int32.TryParse(value, NumberStyles.Integer Or NumberStyles.AllowThousands, 
                        provider, number) Then
         Console.WriteLine("{0} --> {1}", value, number)
      Else
         Console.WriteLine("Unable to convert '{0}'", value)
      End If
   End Sub
End Module
' The example displays the following output:
'       Unable to convert '1,304'
'       1,304 --> 1304
```

> <span data-ttu-id="6ec16-131">**警告**</span><span class="sxs-lookup"><span data-stu-id="6ec16-131">**Warning**</span></span>
>
> <span data-ttu-id="6ec16-132">分析操作始终使用特定区域性的格式设置约定。</span><span class="sxs-lookup"><span data-stu-id="6ec16-132">The parse operation always uses the formatting conventions of a particular culture.</span></span> <span data-ttu-id="6ec16-133">如果未通过传递 [CultureInfo](xref:System.Globalization.CultureInfo) 或 [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) 对象来指定区域性，则使用与当前线程关联的区域性。</span><span class="sxs-lookup"><span data-stu-id="6ec16-133">If you do not specify a culture by passing a [CultureInfo](xref:System.Globalization.CultureInfo) or [NumberFormatInfo](xref:System.Globalization.NumberFormatInfo) object, the culture associated with the current thread is used.</span></span>
 
<span data-ttu-id="6ec16-134">下表列出 [NumberStyles](xref:System.Globalization.NumberStyles) 枚举的成员并介绍它们对分析操作的影响。</span><span class="sxs-lookup"><span data-stu-id="6ec16-134">The following table lists the members of the [NumberStyles](xref:System.Globalization.NumberStyles) enumeration and describes the effect that they have on the parsing operation.</span></span>

<span data-ttu-id="6ec16-135">NumberStyles 值</span><span class="sxs-lookup"><span data-stu-id="6ec16-135">NumberStyles value</span></span> | <span data-ttu-id="6ec16-136">对要分析的字符串的影响</span><span class="sxs-lookup"><span data-stu-id="6ec16-136">Effect on the string to be parsed</span></span>
------------------ | --------------------------------- 
[<span data-ttu-id="6ec16-137">NumberStyles.None</span><span class="sxs-lookup"><span data-stu-id="6ec16-137">NumberStyles.None</span></span>](xref:System.Globalization.NumberStyles.None) | <span data-ttu-id="6ec16-138">仅允许数字。</span><span class="sxs-lookup"><span data-stu-id="6ec16-138">Only numeric digits are permitted.</span></span>
[<span data-ttu-id="6ec16-139">NumberStyles.AllowDecimalPoint</span><span class="sxs-lookup"><span data-stu-id="6ec16-139">NumberStyles.AllowDecimalPoint</span></span>](xref:System.Globalization.NumberStyles.AllowDecimalPoint) | <span data-ttu-id="6ec16-140">允许十进制分隔符和小数数字。</span><span class="sxs-lookup"><span data-stu-id="6ec16-140">The decimal separator and fractional digits are permitted.</span></span> <span data-ttu-id="6ec16-141">对于整数值，仅允许将零作为小数数字。</span><span class="sxs-lookup"><span data-stu-id="6ec16-141">For integer values, only zero is permitted as a fractional digit.</span></span> <span data-ttu-id="6ec16-142">有效十进制分隔符由 [NumberFormatInfo.NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) 或 [NumberFormatInfo.CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) 属性确定。</span><span class="sxs-lookup"><span data-stu-id="6ec16-142">Valid decimal separators are determined by the [NumberFormatInfo.NumberDecimalSeparator](xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator) or [NumberFormatInfo.CurrencyDecimalSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator) property.</span></span>
[<span data-ttu-id="6ec16-143">NumberStyles.AllowExponent</span><span class="sxs-lookup"><span data-stu-id="6ec16-143">NumberStyles.AllowExponent</span></span>](xref:System.Globalization.NumberStyles.AllowExponent) | <span data-ttu-id="6ec16-144">“e”或“E”字符可以用于指示指数记数法。</span><span class="sxs-lookup"><span data-stu-id="6ec16-144">The "e" or "E" character can be used to indicate exponential notation.</span></span>
[<span data-ttu-id="6ec16-145">NumberStyles.AllowLeadingWhite</span><span class="sxs-lookup"><span data-stu-id="6ec16-145">NumberStyles.AllowLeadingWhite</span></span>](xref:System.Globalization.NumberStyles.AllowLeadingWhite) | <span data-ttu-id="6ec16-146">允许前导空格。</span><span class="sxs-lookup"><span data-stu-id="6ec16-146">Leading white space is permitted.</span></span>
[<span data-ttu-id="6ec16-147">NumberStyles.AllowTrailingWhite</span><span class="sxs-lookup"><span data-stu-id="6ec16-147">NumberStyles.AllowTrailingWhite</span></span>](xref:System.Globalization.NumberStyles.AllowTrailingWhite) | <span data-ttu-id="6ec16-148">允许尾随空格。</span><span class="sxs-lookup"><span data-stu-id="6ec16-148">Trailing white space is permitted.</span></span>
[<span data-ttu-id="6ec16-149">NumberStyles.AllowLeadingSign</span><span class="sxs-lookup"><span data-stu-id="6ec16-149">NumberStyles.AllowLeadingSign</span></span>](xref:System.Globalization.NumberStyles.AllowLeadingSign) | <span data-ttu-id="6ec16-150">正号或负号可以位于数字前面。</span><span class="sxs-lookup"><span data-stu-id="6ec16-150">A positive or negative sign can precede numeric digits.</span></span>
[<span data-ttu-id="6ec16-151">NumberStyles.AllowTrailingSign</span><span class="sxs-lookup"><span data-stu-id="6ec16-151">NumberStyles.AllowTrailingSign</span></span>](xref:System.Globalization.NumberStyles.AllowTrailingSign) | <span data-ttu-id="6ec16-152">正号或负号可以位于数字后面。</span><span class="sxs-lookup"><span data-stu-id="6ec16-152">A positive or negative sign can follow numeric digits.</span></span>
[<span data-ttu-id="6ec16-153">NumberStyles.AllowParentheses</span><span class="sxs-lookup"><span data-stu-id="6ec16-153">NumberStyles.AllowParentheses</span></span>](xref:System.Globalization.NumberStyles.AllowParentheses) | <span data-ttu-id="6ec16-154">括号可以用于指示负值。</span><span class="sxs-lookup"><span data-stu-id="6ec16-154">Parentheses can be used to indicate negative values.</span></span>
[<span data-ttu-id="6ec16-155">NumberStyles.AllowThousands</span><span class="sxs-lookup"><span data-stu-id="6ec16-155">NumberStyles.AllowThousands</span></span>](xref:System.Globalization.NumberStyles.AllowThousands) | <span data-ttu-id="6ec16-156">允许组分隔符。</span><span class="sxs-lookup"><span data-stu-id="6ec16-156">The group separator is permitted.</span></span> <span data-ttu-id="6ec16-157">组分隔符字符由 [NumberFormatInfo.NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) 或 [NumberFormatInfo.CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) 属性确定。</span><span class="sxs-lookup"><span data-stu-id="6ec16-157">The group separator character is determined by the [NumberFormatInfo.NumberGroupSeparator](xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator) or [NumberFormatInfo.CurrencyGroupSeparator](xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator) property.</span></span>
[<span data-ttu-id="6ec16-158">NumberStyles.AllowCurrencySymbol</span><span class="sxs-lookup"><span data-stu-id="6ec16-158">NumberStyles.AllowCurrencySymbol</span></span>](xref:System.Globalization.NumberStyles.AllowCurrencySymbol) | <span data-ttu-id="6ec16-159">允许货币符号。</span><span class="sxs-lookup"><span data-stu-id="6ec16-159">The currency symbol is permitted.</span></span> <span data-ttu-id="6ec16-160">货币符号由 [NumberFormatInfo.CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) 属性定义。</span><span class="sxs-lookup"><span data-stu-id="6ec16-160">The currency symbol is defined by the [NumberFormatInfo.CurrencySymbol](xref:System.Globalization.NumberFormatInfo.CurrencySymbol) property.</span></span>
[<span data-ttu-id="6ec16-161">NumberStyles.AllowHexSpecifier</span><span class="sxs-lookup"><span data-stu-id="6ec16-161">NumberStyles.AllowHexSpecifier</span></span>](xref:System.Globalization.NumberStyles.AllowHexSpecifier) | <span data-ttu-id="6ec16-162">要分析的字符串解释为十六进制数。</span><span class="sxs-lookup"><span data-stu-id="6ec16-162">The string to be parsed is interpreted as a hexadecimal number.</span></span> <span data-ttu-id="6ec16-163">它可以包含十六进制数 0-9、A-F 和 a-f。</span><span class="sxs-lookup"><span data-stu-id="6ec16-163">It can include the hexadecimal digits 0-9, A-F, and a-f.</span></span> <span data-ttu-id="6ec16-164">此标志只能用于分析整数值。</span><span class="sxs-lookup"><span data-stu-id="6ec16-164">This flag can be used only to parse integer values.</span></span>
 
<span data-ttu-id="6ec16-165">此外，[NumberStyles](xref:System.Globalization.NumberStyles) 枚举提供以下复合样式，包括多个 [NumberStyles](xref:System.Globalization.NumberStyles) 标志。</span><span class="sxs-lookup"><span data-stu-id="6ec16-165">In addition, the [NumberStyles](xref:System.Globalization.NumberStyles) enumeration provides the following composite styles, which include multiple [NumberStyles](xref:System.Globalization.NumberStyles) flags.</span></span> 

<span data-ttu-id="6ec16-166">复合 NumberStyles 值</span><span class="sxs-lookup"><span data-stu-id="6ec16-166">Composite NumberStyles value</span></span> | <span data-ttu-id="6ec16-167">包括成员</span><span class="sxs-lookup"><span data-stu-id="6ec16-167">Includes members</span></span>
---------------------------- | ---------------- 
[<span data-ttu-id="6ec16-168">NumberStyles.Integer</span><span class="sxs-lookup"><span data-stu-id="6ec16-168">NumberStyles.Integer</span></span>](xref:System.Globalization.NumberStyles.Integer) | <span data-ttu-id="6ec16-169">包括 [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite)、[NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) 和 [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign) 样式。</span><span class="sxs-lookup"><span data-stu-id="6ec16-169">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), and [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign) styles.</span></span> <span data-ttu-id="6ec16-170">这是用于分析整数值的默认样式。</span><span class="sxs-lookup"><span data-stu-id="6ec16-170">This is the default style used to parse integer values.</span></span>
[<span data-ttu-id="6ec16-171">NumberStyles.Number</span><span class="sxs-lookup"><span data-stu-id="6ec16-171">NumberStyles.Number</span></span>](xref:System.Globalization.NumberStyles.Number) | <span data-ttu-id="6ec16-172">包括 [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite)、[NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite)、[NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign)、[NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign)、[NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) 和 [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) 样式。</span><span class="sxs-lookup"><span data-stu-id="6ec16-172">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowTrailingSign](xref:System.Globalization.NumberStyles.AllowTrailingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint), and [NumberStyles.AllowThousands](xref:System.Globalization.NumberStyles.AllowThousands) styles.</span></span>
[<span data-ttu-id="6ec16-173">NumberStyles.Float</span><span class="sxs-lookup"><span data-stu-id="6ec16-173">NumberStyles.Float</span></span>](xref:System.Globalization.NumberStyles.Float) | <span data-ttu-id="6ec16-174">包括 [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite)、[NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite)、[NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign)、[NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint) 和 [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) 样式。</span><span class="sxs-lookup"><span data-stu-id="6ec16-174">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), [NumberStyles.AllowLeadingSign](xref:System.Globalization.NumberStyles.AllowLeadingSign), [NumberStyles.AllowDecimalPoint](xref:System.Globalization.NumberStyles.AllowDecimalPoint), and [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) styles.</span></span>
[<span data-ttu-id="6ec16-175">NumberStyles.Currency</span><span class="sxs-lookup"><span data-stu-id="6ec16-175">NumberStyles.Currency</span></span>](xref:System.Globalization.NumberStyles.Currency) | <span data-ttu-id="6ec16-176">包括除 [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) 和 [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier) 之外的所有样式。</span><span class="sxs-lookup"><span data-stu-id="6ec16-176">Includes all styles except [NumberStyles.AllowExponent](xref:System.Globalization.NumberStyles.AllowExponent) and [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span></span>
[<span data-ttu-id="6ec16-177">NumberStyles.Any</span><span class="sxs-lookup"><span data-stu-id="6ec16-177">NumberStyles.Any</span></span>](xref:System.Globalization.NumberStyles.Any) | <span data-ttu-id="6ec16-178">包括除 [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier) 之外的所有样式。</span><span class="sxs-lookup"><span data-stu-id="6ec16-178">Includes all styles except [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier).</span></span>
[<span data-ttu-id="6ec16-179">NumberStyles.HexNumber</span><span class="sxs-lookup"><span data-stu-id="6ec16-179">NumberStyles.HexNumber</span></span>](xref:System.Globalization.NumberStyles.HexNumber) | <span data-ttu-id="6ec16-180">包括 [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite)、[NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite) 和 [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier) 样式。</span><span class="sxs-lookup"><span data-stu-id="6ec16-180">Includes the [NumberStyles.AllowLeadingWhite](xref:System.Globalization.NumberStyles.AllowLeadingWhite), [NumberStyles.AllowTrailingWhite](xref:System.Globalization.NumberStyles.AllowTrailingWhite), and [NumberStyles.AllowHexSpecifier](xref:System.Globalization.NumberStyles.AllowHexSpecifier) styles.</span></span>
 
## <a name="parsing-and-unicode-digits"></a><span data-ttu-id="6ec16-181">分析和 Unicode 数字</span><span class="sxs-lookup"><span data-stu-id="6ec16-181">Parsing and Unicode digits</span></span>

<span data-ttu-id="6ec16-182">Unicode 标准为各种书写系统中的数字定义码位。</span><span class="sxs-lookup"><span data-stu-id="6ec16-182">The Unicode standard defines code points for digits in various writing systems.</span></span> <span data-ttu-id="6ec16-183">例如，从 U+0030 到 U+0039 的码位表示从 0 到 9 的基本拉丁文数字，从 U+09E6 到 U+09EF 的码位表示从 0 到 9 的孟加拉文数字，而从 U+FF10 到 U+FF19 的码位表示从 0 到 9 的全角数字。</span><span class="sxs-lookup"><span data-stu-id="6ec16-183">For example, code points from U+0030 to U+0039 represent the basic Latin digits 0 through 9, code points from U+09E6 to U+09EF represent the Bangla digits 0 through 9, and code points from U+FF10 to U+FF19 represent the Fullwidth digits 0 through 9.</span></span> <span data-ttu-id="6ec16-184">但是，分析方法唯一可识别的数字是具有 U+0030 到 U+0039 的码位的基本拉丁文数字 0-9。</span><span class="sxs-lookup"><span data-stu-id="6ec16-184">However, the only numeric digits recognized by parsing methods are the basic Latin digits 0-9 with code points from U+0030 to U+0039.</span></span> <span data-ttu-id="6ec16-185">如果向数字分析方法传递包含任何其他数字的字符串，则该方法会引发 [FormatException](xref:System.FormatException)。</span><span class="sxs-lookup"><span data-stu-id="6ec16-185">If a numeric parsing method is passed a string that contains any other digits, the method throws a [FormatException](xref:System.FormatException).</span></span>

<span data-ttu-id="6ec16-186">下面的示例使用 [Int32.Parse](xref:System.Int32.Parse(System.String)) 方法在不同书写系统中分析由数字组成的字符串。</span><span class="sxs-lookup"><span data-stu-id="6ec16-186">The following example uses the [Int32.Parse](xref:System.Int32.Parse(System.String)) method to parse strings that consist of digits in different writing systems.</span></span> <span data-ttu-id="6ec16-187">正如示例输出所示，虽然尝试分析基本拉丁文数字获得成功，但分析全角、阿拉伯 - 印度文以及孟加拉文数字的尝试将失败。</span><span class="sxs-lookup"><span data-stu-id="6ec16-187">As the output from the example shows, the attempt to parse the basic Latin digits succeeds, but the attempt to parse the Fullwidth, Arabic-Indic, and Bangla digits fails.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      string value;
      // Define a string of basic Latin digits 1-5.
      value = "\u0031\u0032\u0033\u0034\u0035";
      ParseDigits(value);

      // Define a string of Fullwidth digits 1-5.
      value = "\uFF11\uFF12\uFF13\uFF14\uFF15";
      ParseDigits(value);

      // Define a string of Arabic-Indic digits 1-5.
      value = "\u0661\u0662\u0663\u0664\u0665";
      ParseDigits(value);

      // Define a string of Bangla digits 1-5.
      value = "\u09e7\u09e8\u09e9\u09ea\u09eb";
      ParseDigits(value);
   }

   static void ParseDigits(string value)
   {
      try {
         int number = Int32.Parse(value);
         Console.WriteLine("'{0}' --> {1}", value, number);
      }   
      catch (FormatException) {
         Console.WriteLine("Unable to parse '{0}'.", value);      
      }     
   }
}
// The example displays the following output:
//       '12345' --> 12345
//       Unable to parse '１２３４５'.
//       Unable to parse '١٢٣٤٥'.
//       Unable to parse '১২৩৪৫'.
```

```vb
Module Example
   Public Sub Main()
      Dim value As String
      ' Define a string of basic Latin digits 1-5.
      value = ChrW(&h31) + ChrW(&h32) + ChrW(&h33) + ChrW(&h34) + ChrW(&h35)
      ParseDigits(value)

      ' Define a string of Fullwidth digits 1-5.
      value = ChrW(&hff11) + ChrW(&hff12) + ChrW(&hff13) + ChrW(&hff14) + ChrW(&hff15)
      ParseDigits(value)

      ' Define a string of Arabic-Indic digits 1-5.
      value = ChrW(&h661) + ChrW(&h662) + ChrW(&h663) + ChrW(&h664) + ChrW(&h665)
      ParseDigits(value)

      ' Define a string of Bangla digits 1-5.
      value = ChrW(&h09e7) + ChrW(&h09e8) + ChrW(&h09e9) + ChrW(&h09ea) + ChrW(&h09eb)
      ParseDigits(value)
   End Sub

   Sub ParseDigits(value As String)
      Try
         Dim number As Integer = Int32.Parse(value)
         Console.WriteLine("'{0}' --> {1}", value, number)
      Catch e As FormatException
         Console.WriteLine("Unable to parse '{0}'.", value)      
      End Try     
   End Sub
End Module
' The example displays the following output:
'       '12345' --> 12345
'       Unable to parse '１２３４５'.
'       Unable to parse '١٢٣٤٥'.
'       Unable to parse '১২৩৪৫'.
```

## <a name="see-also"></a><span data-ttu-id="6ec16-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ec16-188">See also</span></span>

[<span data-ttu-id="6ec16-189">System.Globalization.NumberStyles</span><span class="sxs-lookup"><span data-stu-id="6ec16-189">System.Globalization.NumberStyles</span></span>](xref:System.Globalization.NumberStyles)

[<span data-ttu-id="6ec16-190">在 .NET 中分析字符串</span><span class="sxs-lookup"><span data-stu-id="6ec16-190">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="6ec16-191">.NET 中的格式设置类型</span><span class="sxs-lookup"><span data-stu-id="6ec16-191">Formatting types in .NET</span></span>](formatting-types.md)


