---
title: "在 .NET 中分析日期和时间字符串"
description: "在 .NET 中分析日期和时间字符串"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 07/29/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: e61514cd-5329-4eb8-b122-482fffb54ab7
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f0131baa0874880b6697458426da5ae9ce1705b7
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="parsing-date-and-time-strings-in-net"></a><span data-ttu-id="62c8b-104">在 .NET 中分析日期和时间字符串</span><span class="sxs-lookup"><span data-stu-id="62c8b-104">Parsing date and time strings in .NET</span></span>

<span data-ttu-id="62c8b-105">分析方法会将日期和时间的字符串表示形式转换为等效的 [DateTime](xref:System.DateTime) 对象。</span><span class="sxs-lookup"><span data-stu-id="62c8b-105">Parsing methods convert the string representation of a date and time to an equivalent [DateTime](xref:System.DateTime) object.</span></span> <span data-ttu-id="62c8b-106">[Parse](xref:System.DateTime.Parse(System.String)) 和 [TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) 方法可转换日期和时间的多个常见表示形式中的任何一个。</span><span class="sxs-lookup"><span data-stu-id="62c8b-106">The [Parse](xref:System.DateTime.Parse(System.String)) and [TryParse](xref:System.DateTime.TryParse(System.String,System.DateTime@)) methods convert any of several common representations of a date and time.</span></span> <span data-ttu-id="62c8b-107">[ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) 和 [TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)) 方法会转换符合日期和时间格式字符串指定的模式的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="62c8b-107">The [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) and [TryParseExact](xref:System.DateTime.TryParseExact(System.String,System.String,System.IFormatProvider,System.Globalization.DateTimeStyles,System.DateTime@)) methods convert a string representation that conforms to the pattern specified by a date and time format string.</span></span> <span data-ttu-id="62c8b-108">（请参见有关[标准日期和时间格式字符串](standard-datetime.md)和[自定义日期和时间格式字符串](custom-datetime.md)的主题。）</span><span class="sxs-lookup"><span data-stu-id="62c8b-108">(See the topics on [standard date and time format strings](standard-datetime.md) and [custom date and time format strings](custom-datetime.md).)</span></span> 

<span data-ttu-id="62c8b-109">分析受提供信息（如用于日期和时间分隔符的字符串，以及月、日和纪元的名称）的格式提供程序影响。</span><span class="sxs-lookup"><span data-stu-id="62c8b-109">Parsing is influenced by the properties of a format provider that supplies information such as the strings used for date and time separators, and the names of months, days, and eras.</span></span> <span data-ttu-id="62c8b-110">格式提供程序受当前 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 对象影响，该对象由当前线程区域性隐式提供或由分析方法的 [IFormatProvider](xref:System.IFormatProvider) 参数显式提供。</span><span class="sxs-lookup"><span data-stu-id="62c8b-110">The format provider is the current [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object, which is provided implicitly by the current thread culture or explicitly by the [IFormatProvider](xref:System.IFormatProvider) parameter of a parsing method.</span></span> <span data-ttu-id="62c8b-111">对于 [IFormatProvider](xref:System.IFormatProvider) 参数，应指定一个表示区域性的 [CultureInfo](xref:System.Globalization.CultureInfo) 对象或指定一个 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="62c8b-111">For the [IFormatProvider](xref:System.IFormatProvider) parameter, specify a [CultureInfo](xref:System.Globalization.CultureInfo) object, which represents a culture, or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object.</span></span> 

<span data-ttu-id="62c8b-112">要分析的日期的字符串表示形式必须包含月份以及至少日或年。</span><span class="sxs-lookup"><span data-stu-id="62c8b-112">The string representation of a date to be parsed must include the month and at least a day or year.</span></span> <span data-ttu-id="62c8b-113">时间的字符串表示形式必须包含小时以及至少分钟或 AM/PM 指示符。</span><span class="sxs-lookup"><span data-stu-id="62c8b-113">The string representation of a time must include the hour and at least minutes or the AM/PM designator.</span></span> <span data-ttu-id="62c8b-114">但是，分析会在可能时为省略的组成部分提供默认值。</span><span class="sxs-lookup"><span data-stu-id="62c8b-114">However, parsing supplies default values for omitted components if possible.</span></span> <span data-ttu-id="62c8b-115">缺失日期默认为当前日期，缺失年份默认为当前年份，缺失的月中几号默认为月的第一天，缺失时间默认值为午夜。</span><span class="sxs-lookup"><span data-stu-id="62c8b-115">A missing date defaults to the current date, a missing year defaults to the current year, a missing day of the month defaults to the first day of the month, and a missing time defaults to midnight.</span></span> 

<span data-ttu-id="62c8b-116">如果字符串表示形式仅指定时间，则分析会返回其 [Year](xref:System.DateTime.Year)、[Month](xref:System.DateTime.Month) 和 [Day](xref:System.DateTime.Day) 属性设置为 [Today](xref:System.DateTime.Today) 属性相应值的 [DateTime](xref:System.DateTime) 对象。</span><span class="sxs-lookup"><span data-stu-id="62c8b-116">If the string representation specifies only a time, parsing returns a [DateTime](xref:System.DateTime) object with its [Year](xref:System.DateTime.Year), [Month](xref:System.DateTime.Month), and [Day](xref:System.DateTime.Day) properties set to the corresponding values of the [Today](xref:System.DateTime.Today) property.</span></span> <span data-ttu-id="62c8b-117">但是，如果在分析方法中指定了 [DateTimeStyles.NoCurrentDateDefault](xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault) 常量，则生成的年、月和日属性会设置为值 1。</span><span class="sxs-lookup"><span data-stu-id="62c8b-117">However, if the [DateTimeStyles.NoCurrentDateDefault](xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault) constant is specified in the parsing method, the resulting year, month, and day properties are set to the value 1.</span></span>

<span data-ttu-id="62c8b-118">除了日期和时间组成部分，日期和时间的字符串表示形式还可以包含指示时间与协调世界时 (UTC) 相差多少的偏移量。</span><span class="sxs-lookup"><span data-stu-id="62c8b-118">In addition to a date and a time component, the string representation of a date and time can include an offset that indicates how much the time differs from Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="62c8b-119">例如，字符串“2/14/2007 5:32:00 -7:00”定义比 UTC 早七个小时的时间。</span><span class="sxs-lookup"><span data-stu-id="62c8b-119">For example, the string "2/14/2007 5:32:00 -7:00" defines a time that is seven hours earlier than UTC.</span></span> <span data-ttu-id="62c8b-120">如果在时间的字符串表示形式中省略了偏移量，则分析会返回其 [Kind](xref:System.DateTime.Kind) 属性设置为 [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified) 的 [DateTime](xref:System.DateTime) 对象。</span><span class="sxs-lookup"><span data-stu-id="62c8b-120">If an offset is omitted from the string representation of a time, parsing returns a [DateTime](xref:System.DateTime) object with its [Kind](xref:System.DateTime.Kind) property set to [DateTimeKind.Unspecified](xref:System.DateTimeKind.Unspecified).</span></span> <span data-ttu-id="62c8b-121">如果指定了偏移量，则分析会返回其 [Kind](xref:System.DateTime.Kind) 属性设置为 [Local](xref:System.DateTimeKind.Local) 并且其值调整为计算机本地时区的 [DateTime](xref:System.DateTime) 对象。</span><span class="sxs-lookup"><span data-stu-id="62c8b-121">If an offset is specified, parsing returns a [DateTime](xref:System.DateTime) object with its [Kind](xref:System.DateTime.Kind) property set to [Local](xref:System.DateTimeKind.Local) and its value adjusted to the local time zone of your machine.</span></span> <span data-ttu-id="62c8b-122">可以通过将 [DateTimeStyles](xref:System.Globalization.DateTimeStyles) 常量与分析方法结合使用来修改此行为。</span><span class="sxs-lookup"><span data-stu-id="62c8b-122">You can modify this behavior by using a [DateTimeStyles](xref:System.Globalization.DateTimeStyles) constant with the parsing method.</span></span>

<span data-ttu-id="62c8b-123">格式提供程序还用于解释不明确的数字日期。</span><span class="sxs-lookup"><span data-stu-id="62c8b-123">The format provider is also used to interpret an ambiguous numeric date.</span></span> <span data-ttu-id="62c8b-124">例如，不清楚字符串“02/03/04”所表示的日期的哪些组成部分是月、日和年。</span><span class="sxs-lookup"><span data-stu-id="62c8b-124">For example, it is not clear which components of the date represented by the string "02/03/04" are the month, day, and year.</span></span> <span data-ttu-id="62c8b-125">在这种情况下，组成部分根据格式提供程序中相似日期格式的顺序进行解释。</span><span class="sxs-lookup"><span data-stu-id="62c8b-125">In this case, the components are interpreted according to the order of similar date formats in the format provider.</span></span> 

## <a name="parse"></a><span data-ttu-id="62c8b-126">分析</span><span class="sxs-lookup"><span data-stu-id="62c8b-126">Parse</span></span>

<span data-ttu-id="62c8b-127">下面的代码示例说明如何使用 `Parse` 方法将字符串转换为 `DateTime`。</span><span class="sxs-lookup"><span data-stu-id="62c8b-127">The following code example illustrates the use of the `Parse` method to convert a string into a `DateTime`.</span></span> <span data-ttu-id="62c8b-128">此示例使用与当前线程关联的区域性执行分析。</span><span class="sxs-lookup"><span data-stu-id="62c8b-128">This example uses the culture associated with the current thread to perform the parse.</span></span> <span data-ttu-id="62c8b-129">如果与当前区域性关联的 [CultureInfo](xref:System.Globalization.CultureInfo) 无法分析输入字符串，则会引发 [FormatException](xref:System.FormatException)。</span><span class="sxs-lookup"><span data-stu-id="62c8b-129">If the [CultureInfo](xref:System.Globalization.CultureInfo) associated with the current culture cannot parse the input string, a [FormatException](xref:System.FormatException) is thrown.</span></span>

```csharp
string MyString = "Jan 1, 2009";
DateTime MyDateTime = DateTime.Parse(MyString);
Console.WriteLine(MyDateTime);
// Displays the following output on a system whose culture is en-US:
//       1/1/2009 12:00:00 AM
```

```vb
Dim MyString As String = "Jan 1, 2009"
Dim MyDateTime As DateTime = DateTime.Parse(MyString)
Console.WriteLine(MyDateTime)
' Displays the following output on a system whose culture is en-US:
'       1/1/2009 12:00:00 AM
```

<span data-ttu-id="62c8b-130">还可以指定设置为该对象定义的区域性之一的 `CultureInfo`，也可以指定 [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) 属性返回的标准 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 对象之一。</span><span class="sxs-lookup"><span data-stu-id="62c8b-130">You can also specify a `CultureInfo` set to one of the cultures defined by that object, or you can specify one of the standard [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) objects returned by the [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) property.</span></span> <span data-ttu-id="62c8b-131">下面的代码示例使用格式提供程序将德语字符串分析为 `DateTime`。</span><span class="sxs-lookup"><span data-stu-id="62c8b-131">The following code example uses a format provider to parse a German string into a `DateTime`.</span></span> <span data-ttu-id="62c8b-132">定义了表示 de-DE 区域性的 `CultureInfo`，并使用所分析的字符串进行传递以确保此特定字符串分析成功。</span><span class="sxs-lookup"><span data-stu-id="62c8b-132">A `CultureInfo` representing the de-DE culture is defined and passed with the string being parsed to ensure successful parsing of this particular string.</span></span> <span data-ttu-id="62c8b-133">这会排除处于 `CurrentThread` 的 `CurrentCulture` 中的任何设置。</span><span class="sxs-lookup"><span data-stu-id="62c8b-133">This precludes whatever setting is in the `CurrentCulture` of the `CurrentThread`.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("de-DE");
      string MyString = "12 Juni 2008";
      DateTime MyDateTime = DateTime.Parse(MyString, MyCultureInfo);
      Console.WriteLine(MyDateTime);
   }
}
// The example displays the following output:
//       6/12/2008 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("de-DE")
      Dim MyString As String = "12 Juni 2008"
      Dim MyDateTime As DateTime = DateTime.Parse(MyString, MyCultureInfo)
      Console.WriteLine(MyDateTime)
   End Sub
End Module
' The example displays the following output:
'       6/12/2008 12:00:00 AM
```

<span data-ttu-id="62c8b-134">但是，虽然可以使用 [Parse](xref:System.DateTime.Parse(System.String)) 方法的重载指定自定义格式提供程序，但是该方法不支持使用非标准格式提供程序。</span><span class="sxs-lookup"><span data-stu-id="62c8b-134">However, although you can use overloads of the [Parse](xref:System.DateTime.Parse(System.String)) method to specify custom format providers, the method does not support the use of non-standard format providers.</span></span> <span data-ttu-id="62c8b-135">若要分析非标准格式的日期和时间，请改为使用 [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) 方法。</span><span class="sxs-lookup"><span data-stu-id="62c8b-135">To parse a date and time expressed in a non-standard format, use the [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method instead.</span></span>

<span data-ttu-id="62c8b-136">下面的代码示例使用 [DateTimeStyles](xref:System.Globalization.DateTimeStyles) 枚举指定当前日期和时间信息不应添加到字符串未定义的字段的 `DateTime`。</span><span class="sxs-lookup"><span data-stu-id="62c8b-136">The following code example uses the [DateTimeStyles](xref:System.Globalization.DateTimeStyles) enumeration to specify that the current date and time information should not be added to the `DateTime` for fields that the string does not define.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("de-DE");
      string MyString = "12 Juni 2008";
      DateTime MyDateTime = DateTime.Parse(MyString, MyCultureInfo, 
                                           DateTimeStyles.NoCurrentDateDefault);
      Console.WriteLine(MyDateTime);
   }
}
// The example displays the following output if the current culture is en-US:
//      6/12/2008 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("de-DE")
      Dim MyString As String = "12 Juni 2008"
      Dim MyDateTime As DateTime = DateTime.Parse(MyString, MyCultureInfo)
      Console.WriteLine(MyDateTime)
   End Sub
End Module
' The example displays the following output:
'       6/12/2008 12:00:00 AM
```

## <a name="parseexact"></a><span data-ttu-id="62c8b-137">ParseExact</span><span class="sxs-lookup"><span data-stu-id="62c8b-137">ParseExact</span></span>

<span data-ttu-id="62c8b-138">[DateTime.ParseExact]((xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) 方法将符合指定字符串模式的字符串转换为 `DateTime` 对象。</span><span class="sxs-lookup"><span data-stu-id="62c8b-138">The [DateTime.ParseExact]((xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method converts a string that conforms to a specified string pattern to a `DateTime` object.</span></span> <span data-ttu-id="62c8b-139">将未采用指定形式的字符串传递给此方法时，会引发 [FormatException](xref:System.FormatException)。</span><span class="sxs-lookup"><span data-stu-id="62c8b-139">When a string that is not of the form specified is passed to this method, a [FormatException](xref:System.FormatException) is thrown.</span></span> <span data-ttu-id="62c8b-140">可以指定一种标准日期和时间格式说明符或自定义日期和时间格式说明符的有限组合。</span><span class="sxs-lookup"><span data-stu-id="62c8b-140">You can specify one of the standard date and time format specifiers or a limited combination of the custom date and time format specifiers.</span></span> <span data-ttu-id="62c8b-141">使用自定义格式说明符可以构造自定义识别字符串。</span><span class="sxs-lookup"><span data-stu-id="62c8b-141">Using the custom format specifiers, it is possible for you to construct a custom recognition string.</span></span> <span data-ttu-id="62c8b-142">有关说明符的说明，请参见有关[标准日期和时间格式字符串](standard-datetime.md)和[自定义日期和时间格式字符串](custom-datetime.md)的主题。</span><span class="sxs-lookup"><span data-stu-id="62c8b-142">For an explanation of the specifiers, see the topics on [standard date and time format strings](standard-datetime.md) and [custom date and time format strings](custom-datetime.md).</span></span> 

<span data-ttu-id="62c8b-143">[ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) 方法的每个重载还具有 [IFormatProvider](xref:System.IFormatProvider) 参数，它通常提供有关字符串格式设置的特定于区域性的信息。</span><span class="sxs-lookup"><span data-stu-id="62c8b-143">Each overload of the [ParseExact](xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)) method also has an [IFormatProvider](xref:System.IFormatProvider) parameter that typically provides culture-specific information about the formatting of the string.</span></span> <span data-ttu-id="62c8b-144">通常，此 [IFormatProvider](xref:System.IFormatProvider) 对象是表示标准区域性的 [CultureInfo](xref:System.Globalization.CultureInfo) 对象或是 [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) 属性返回的 [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) 对象。</span><span class="sxs-lookup"><span data-stu-id="62c8b-144">Typically, this [IFormatProvider](xref:System.IFormatProvider) object is a [CultureInfo](xref:System.Globalization.CultureInfo) object that represents a standard culture or a [DateTimeFormatInfo](xref:System.Globalization.DateTimeFormatInfo) object that is returned by the [CultureInfo.DateTimeFormat](xref:System.Globalization.CultureInfo.DateTimeFormat) property.</span></span> <span data-ttu-id="62c8b-145">但是，与其他日期和时间分析函数不同，此方法还支持定义非标准日期和时间格式的 [IFormatProvider](xref:System.IFormatProvider)。</span><span class="sxs-lookup"><span data-stu-id="62c8b-145">However, unlike the other date and time parsing functions, this method also supports an [IFormatProvider](xref:System.IFormatProvider) that defines a non-standard date and time format.</span></span> 

<span data-ttu-id="62c8b-146">在下面的代码示例中，向 `ParseExact` 方法传递了一个要分析的字符串对象，后跟一个格式说明符后，再后跟一个 `CultureInfo` 对象。</span><span class="sxs-lookup"><span data-stu-id="62c8b-146">In the following code example, the `ParseExact` method is passed a string object to parse, followed by a format specifier, followed by a `CultureInfo` object.</span></span> <span data-ttu-id="62c8b-147">此 `ParseExact` 方法只能分析在 en-US 区域性中显示长日期模式的字符串。</span><span class="sxs-lookup"><span data-stu-id="62c8b-147">This `ParseExact` method can only parse strings that exhibit the long date pattern in the en-US culture.</span></span>

```csharp
using System;
using System.Globalization;

public class Example
{
   public static void Main()
   {
      CultureInfo MyCultureInfo = new CultureInfo("en-US");
      string[] MyString = {" Friday, April 10, 2009", "Friday, April 10, 2009"};
      foreach (string dateString in MyString)
      {
         try {
            DateTime MyDateTime = DateTime.ParseExact(dateString, "D", MyCultureInfo);
            Console.WriteLine(MyDateTime);
         }
         catch (FormatException) {
            Console.WriteLine("Unable to parse '{0}'", dateString);
         }
      }
   }
}
// The example displays the following output:
//       Unable to parse ' Friday, April 10, 2009'
//       4/10/2009 12:00:00 AM
```

```vb
Imports System.Globalization

Module Example
   Public Sub Main()
      Dim MyCultureInfo As CultureInfo = new CultureInfo("en-US")
      Dim MyString() As String = {" Friday, April 10, 2009", "Friday, April 10, 2009"}
      For Each dateString As String In MyString
         Try
            Dim MyDateTime As DateTime = DateTime.ParseExact(dateString, "D", _
                                                             MyCultureInfo)
            Console.WriteLine(MyDateTime)
         Catch e As FormatException
            Console.WriteLine("Unable to parse '{0}'", dateString)
         End Try
      Next
   End Sub
End Module
' The example displays the following output:
'       Unable to parse ' Friday, April 10, 2009'
'       4/10/2009 12:00:00 AM
```

## <a name="see-also"></a><span data-ttu-id="62c8b-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62c8b-148">See Also</span></span>

[<span data-ttu-id="62c8b-149">在 .NET 中分析字符串</span><span class="sxs-lookup"><span data-stu-id="62c8b-149">Parsing strings in .NET</span></span>](parsing-strings.md)

[<span data-ttu-id="62c8b-150">.NET 中的格式设置类型</span><span class="sxs-lookup"><span data-stu-id="62c8b-150">Formatting types in .NET</span></span>](formatting-types.md)

[<span data-ttu-id="62c8b-151">.NET 中的类型转换</span><span class="sxs-lookup"><span data-stu-id="62c8b-151">Type conversion in .NET</span></span>](type-conversion.md)


