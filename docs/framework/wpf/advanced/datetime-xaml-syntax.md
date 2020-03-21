---
title: DateTime XAML 语法
ms.date: 03/30/2017
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
ms.openlocfilehash: 57b73d3b80f0392b99aacfbfac4d8709f72d52e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186329"
---
# <a name="datetime-xaml-syntax"></a><span data-ttu-id="ca2a8-102">DateTime XAML 语法</span><span class="sxs-lookup"><span data-stu-id="ca2a8-102">DateTime XAML Syntax</span></span>
<span data-ttu-id="ca2a8-103">某些控件（如<xref:System.Windows.Controls.Calendar>和<xref:System.Windows.Controls.DatePicker>） 具有使用<xref:System.DateTime>类型的属性。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-103">Some controls, such as <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>, have properties that use the <xref:System.DateTime> type.</span></span> <span data-ttu-id="ca2a8-104">虽然通常会在运行时在代码隐藏中指定这些控件的初始日期或时间，但可以在 XAML 中指定初始日期或时间。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-104">Although you typically specify an initial date or time for these controls in the code-behind at run time, you can specify an initial date or time in XAML.</span></span> <span data-ttu-id="ca2a8-105">WPF XAML 解析器使用内置的<xref:System.DateTime>XAML 文本语法处理值解析。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-105">The WPF XAML parser handles parsing of <xref:System.DateTime> values using a built-in XAML text syntax.</span></span> <span data-ttu-id="ca2a8-106">本主题介绍<xref:System.DateTime>XAML 文本语法的具体细节。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-106">This topic describes the specifics of the <xref:System.DateTime> XAML text syntax.</span></span>  

<a name="where_datetime_xaml_syntax_is_used"></a>
## <a name="when-to-use-datetime-xaml-syntax"></a><span data-ttu-id="ca2a8-107">DateTime XAML 语法的使用场合</span><span class="sxs-lookup"><span data-stu-id="ca2a8-107">When To Use DateTime XAML Syntax</span></span>  
 <span data-ttu-id="ca2a8-108">无需经常对 XAML 中的日期进行设置，而且设置也可能并不合适。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-108">Setting dates in XAML is not always necessary and may not even be desirable.</span></span> <span data-ttu-id="ca2a8-109">例如，可以使用 属性<xref:System.DateTime.Now%2A?displayProperty=nameWithType>在运行时初始化日期，也可以根据用户输入在代码后面执行日历的所有日期调整。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-109">For example, you could use the <xref:System.DateTime.Now%2A?displayProperty=nameWithType> property to initialize a date at run time, or you could do all your date adjustments for a calendar in the code-behind based on user input.</span></span> <span data-ttu-id="ca2a8-110">但是，在某些情况下，您可能希望将日期硬编码到<xref:System.Windows.Controls.Calendar>和<xref:System.Windows.Controls.DatePicker>控件模板中。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-110">However, there are scenarios where you may want to hard-code dates into a <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker> in a control template.</span></span> <span data-ttu-id="ca2a8-111"><xref:System.DateTime> XAML 语法必须用于这些方案。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-111">The <xref:System.DateTime> XAML syntax must be used for these scenarios.</span></span>  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a><span data-ttu-id="ca2a8-112">DateTime XAML 语法是本机行为</span><span class="sxs-lookup"><span data-stu-id="ca2a8-112">DateTime XAML Syntax is a Native Behavior</span></span>  
 <span data-ttu-id="ca2a8-113"><xref:System.DateTime>是在 CLR 的基类库中定义的类。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-113"><xref:System.DateTime> is a class that is defined in the base class libraries of the CLR.</span></span> <span data-ttu-id="ca2a8-114">由于基类库与 CLR 的其余部分的关系，因此无法应用于<xref:System.ComponentModel.TypeConverterAttribute>类并使用类型转换器处理来自 XAML 的字符串并将其转换为<xref:System.DateTime>运行时对象模型中的字符串。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-114">Because of how the base class libraries relate to the rest of the CLR, it is not possible to apply <xref:System.ComponentModel.TypeConverterAttribute> to the class and use a type converter to process strings from XAML and convert them to <xref:System.DateTime> in the run time object model.</span></span> <span data-ttu-id="ca2a8-115">没有提供转换行为的 `DateTimeConverter` 类；本主题中描述的转换行为源于 WPF XAML 分析器。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-115">There is no `DateTimeConverter` class that provides the conversion behavior; the conversion behavior described in this topic is native to the WPF XAML parser.</span></span>  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>
## <a name="format-strings-for-datetime-xaml-syntax"></a><span data-ttu-id="ca2a8-116">DateTime XAML 语法的格式字符串</span><span class="sxs-lookup"><span data-stu-id="ca2a8-116">Format Strings for DateTime XAML Syntax</span></span>  
 <span data-ttu-id="ca2a8-117">可以使用格式字符串指定 的<xref:System.DateTime>格式。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-117">You can specify the format of a <xref:System.DateTime> with a format string.</span></span> <span data-ttu-id="ca2a8-118">格式字符串会规范可用于创建值的文本语法。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-118">Format strings formalize the text syntax that can be used to create a value.</span></span> <span data-ttu-id="ca2a8-119"><xref:System.DateTime>现有 WPF 控件的值通常只使用 时间组件的日期组件<xref:System.DateTime>，而不是时间组件的日期组件。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-119"><xref:System.DateTime> values for the existing WPF controls generally only use the date components of <xref:System.DateTime> and not the time components.</span></span>  
  
 <span data-ttu-id="ca2a8-120">在 XAML 中指定 时<xref:System.DateTime>，可以互换使用任何格式字符串。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-120">When specifying a <xref:System.DateTime> in XAML, you can use any of the format strings interchangeably.</span></span>  
  
 <span data-ttu-id="ca2a8-121">还可以使用未在本主题中专门显示的格式和格式字符串。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-121">You can also use formats and format strings that are not specifically shown in this topic.</span></span> <span data-ttu-id="ca2a8-122">从技术上讲，WPF XAML<xref:System.DateTime>解析器指定然后解析的任何值的 XAML 都使用 内部调用 ，<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>因此可以使用 XAML 输入接受<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>的任何字符串。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-122">Technically, the XAML for any <xref:System.DateTime> value that is specified and then parsed by the WPF XAML parser uses an internal  call to <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, therefore you could use any string accepted by <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> for your XAML input.</span></span> <span data-ttu-id="ca2a8-123">有关详细信息，请参阅 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-123">For more information, see <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ca2a8-124">DateTime XAML 语法始终`en-us`用作<xref:System.Globalization.CultureInfo>本机转换。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-124">The DateTime XAML syntax always uses `en-us` as the <xref:System.Globalization.CultureInfo> for its native conversion.</span></span> <span data-ttu-id="ca2a8-125">这不受 XAML <xref:System.Windows.FrameworkElement.Language%2A> `xml:lang`中的值或值的影响，因为 XAML 属性级别类型转换在没有该上下文的情况下进行。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-125">This is not influenced by <xref:System.Windows.FrameworkElement.Language%2A> value or `xml:lang` value in the XAML, because XAML attribute-level type conversion acts without that context.</span></span> <span data-ttu-id="ca2a8-126">出于区域性差异的原因，请不要尝试插入此处所示的格式字符串，例如，日期和月份的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-126">Do not attempt to interpolate the format strings shown here due to cultural variations, such as the order in which day and month appear.</span></span> <span data-ttu-id="ca2a8-127">此处所示的格式字符串是在分析 XAML 时（不考虑其他区域性设置）使用的确切格式字符串。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-127">The format strings shown here are the exact format strings used when parsing the XAML regardless of other culture settings.</span></span>  
  
 <span data-ttu-id="ca2a8-128">以下各节介绍一些常见的<xref:System.DateTime>格式字符串。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-128">The following sections describe some of the common <xref:System.DateTime> format strings.</span></span>  
  
### <a name="short-date-pattern-d"></a><span data-ttu-id="ca2a8-129">短日期模式（“d”）</span><span class="sxs-lookup"><span data-stu-id="ca2a8-129">Short Date Pattern ("d")</span></span>  
 <span data-ttu-id="ca2a8-130">下面显示了 XAML 中<xref:System.DateTime>a 的短日期格式：</span><span class="sxs-lookup"><span data-stu-id="ca2a8-130">The following shows the short date format for a <xref:System.DateTime> in XAML:</span></span>  
  
 `M/d/YYYY`  
  
 <span data-ttu-id="ca2a8-131">这是最简单的形式，可指定 WPF 控件一般使用的所有必要信息，并且不受针对时间部分的偶然时区偏移的影响，因此比其他格式更适用。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-131">This is the simplest form that specifies all necessary information for typical usages by WPF controls, and cannot be influenced by accidental time zone offsets versus a time component, and is therefore recommended over the other formats.</span></span>  
  
 <span data-ttu-id="ca2a8-132">例如，若要指定日期 2010 年 6 月 1 日，可使用以下字符串：</span><span class="sxs-lookup"><span data-stu-id="ca2a8-132">For example, to specify the date of June 1, 2010, use the following string:</span></span>  
  
 `3/1/2010`  
  
 <span data-ttu-id="ca2a8-133">有关详细信息，请参阅 <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-133">For more information, see <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="sortable-datetime-pattern-s"></a><span data-ttu-id="ca2a8-134">可排序 DateTime 模式（“s”）</span><span class="sxs-lookup"><span data-stu-id="ca2a8-134">Sortable DateTime Pattern ("s")</span></span>  
 <span data-ttu-id="ca2a8-135">下面显示了 XAML<xref:System.DateTime>中的可排序模式：</span><span class="sxs-lookup"><span data-stu-id="ca2a8-135">The following shows the sortable <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 <span data-ttu-id="ca2a8-136">例如，若要指定日期 2010 年 6 月 1 日，可使用以下字符串（时间部分全部输入为 0）：</span><span class="sxs-lookup"><span data-stu-id="ca2a8-136">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a><span data-ttu-id="ca2a8-137">RFC1123 模式（“r”）</span><span class="sxs-lookup"><span data-stu-id="ca2a8-137">RFC1123 Pattern ("r")</span></span>  
 <span data-ttu-id="ca2a8-138">RFC1123 模式很有用，因为它可以是来自其他日期生成器的字符串输入，这些字符生成器出于区域性固定原因同样使用 RFC1123 模式。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-138">The RFC1123 pattern is useful because it could be a string input from other date generators that also use the RFC1123 pattern for culture invariant reasons.</span></span> <span data-ttu-id="ca2a8-139">下面显示了 XAML 中的 RFC1123<xref:System.DateTime>模式：</span><span class="sxs-lookup"><span data-stu-id="ca2a8-139">The following shows the RFC1123 <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 <span data-ttu-id="ca2a8-140">例如，若要指定日期 2010 年 6 月 1 日，可使用以下字符串（时间部分全部输入为 0）：</span><span class="sxs-lookup"><span data-stu-id="ca2a8-140">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a><span data-ttu-id="ca2a8-141">其他格式和模式</span><span class="sxs-lookup"><span data-stu-id="ca2a8-141">Other Formats and Patterns</span></span>  
 <span data-ttu-id="ca2a8-142">如前所述，XAML 中可以<xref:System.DateTime>指定为可作为<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>输入的任何字符串。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-142">As stated previously, a <xref:System.DateTime> in XAML can be specified as any string that is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ca2a8-143">这包括其他形式化格式（例如<xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>）和未正式作为特定<xref:System.Globalization.DateTimeFormatInfo>格式的格式。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-143">This includes other formalized formats (for example <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), and formats that are not formalized as a particular <xref:System.Globalization.DateTimeFormatInfo> form.</span></span> <span data-ttu-id="ca2a8-144">例如，窗体`YYYY/mm/dd`可以接受为<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>的输入。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-144">For example, the form `YYYY/mm/dd` is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ca2a8-145">本主题并没有试图介绍所有可能有效的格式，而是推荐将短日期模式作为一种标准做法。</span><span class="sxs-lookup"><span data-stu-id="ca2a8-145">This topic does not attempt to describe all possible formats that work, and instead recommends the short date pattern as a standard practice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca2a8-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca2a8-146">See also</span></span>

- [<span data-ttu-id="ca2a8-147">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="ca2a8-147">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
