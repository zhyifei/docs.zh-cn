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
ms.openlocfilehash: c443451a0fd9fffec97377efc611e0ccfe534f06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54606720"
---
# <a name="datetime-xaml-syntax"></a><span data-ttu-id="013e6-102">DateTime XAML 语法</span><span class="sxs-lookup"><span data-stu-id="013e6-102">DateTime XAML Syntax</span></span>
<span data-ttu-id="013e6-103">某些控件，例如<xref:System.Windows.Controls.Calendar>并<xref:System.Windows.Controls.DatePicker>，具有使用的属性<xref:System.DateTime>类型。</span><span class="sxs-lookup"><span data-stu-id="013e6-103">Some controls, such as <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>, have properties that use the <xref:System.DateTime> type.</span></span> <span data-ttu-id="013e6-104">虽然通常会在运行时在代码隐藏中指定这些控件的初始日期或时间，但可以在 XAML 中指定初始日期或时间。</span><span class="sxs-lookup"><span data-stu-id="013e6-104">Although you typically specify an initial date or time for these controls in the code-behind at run time, you can specify an initial date or time in XAML.</span></span> <span data-ttu-id="013e6-105">WPF XAML 分析器处理的分析<xref:System.DateTime>值使用内置的 XAML 文本语法。</span><span class="sxs-lookup"><span data-stu-id="013e6-105">The WPF XAML parser handles parsing of <xref:System.DateTime> values using a built-in XAML text syntax.</span></span> <span data-ttu-id="013e6-106">本主题介绍的细节<xref:System.DateTime>XAML 文本语法。</span><span class="sxs-lookup"><span data-stu-id="013e6-106">This topic describes the specifics of the <xref:System.DateTime> XAML text syntax.</span></span>  
  
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a><span data-ttu-id="013e6-107">DateTime XAML 语法的使用场合</span><span class="sxs-lookup"><span data-stu-id="013e6-107">When To Use DateTime XAML Syntax</span></span>  
 <span data-ttu-id="013e6-108">无需经常对 XAML 中的日期进行设置，而且设置也可能并不合适。</span><span class="sxs-lookup"><span data-stu-id="013e6-108">Setting dates in XAML is not always necessary and may not even be desirable.</span></span> <span data-ttu-id="013e6-109">例如，可以使用<xref:System.DateTime.Now%2A?displayProperty=nameWithType>属性传入以初始化日期在运行的时，也可以根据用户输入在代码隐藏中为日历执行所有日期进行调整。</span><span class="sxs-lookup"><span data-stu-id="013e6-109">For example, you could use the <xref:System.DateTime.Now%2A?displayProperty=nameWithType> property to initialize a date at run time, or you could do all your date adjustments for a calendar in the code-behind based on user input.</span></span> <span data-ttu-id="013e6-110">但是，有些的情况下，可能要硬编码日期到<xref:System.Windows.Controls.Calendar>和<xref:System.Windows.Controls.DatePicker>控件模板中。</span><span class="sxs-lookup"><span data-stu-id="013e6-110">However, there are scenarios where you may want to hard-code dates into a <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker> in a control template.</span></span> <span data-ttu-id="013e6-111"><xref:System.DateTime> XAML 语法必须用于这些方案。</span><span class="sxs-lookup"><span data-stu-id="013e6-111">The <xref:System.DateTime> XAML syntax must be used for these scenarios.</span></span>  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a><span data-ttu-id="013e6-112">DateTime XAML 语法是本机行为</span><span class="sxs-lookup"><span data-stu-id="013e6-112">DateTime XAML Syntax is a Native Behavior</span></span>  
 <span data-ttu-id="013e6-113"><xref:System.DateTime> 是在 CLR 基类库中定义的类。</span><span class="sxs-lookup"><span data-stu-id="013e6-113"><xref:System.DateTime> is a class that is defined in the base class libraries of the CLR.</span></span> <span data-ttu-id="013e6-114">由于如何基类库与 CLR 的其余部分相关联，它不能应用<xref:System.ComponentModel.TypeConverterAttribute>的类和使用的类型转换器处理 XAML 中的字符串，并将它们转换为<xref:System.DateTime>运行的时对象模型中。</span><span class="sxs-lookup"><span data-stu-id="013e6-114">Because of how the base class libraries relate to the rest of the CLR, it is not possible to apply <xref:System.ComponentModel.TypeConverterAttribute> to the class and use a type converter to process strings from XAML and convert them to <xref:System.DateTime> in the run time object model.</span></span> <span data-ttu-id="013e6-115">没有提供转换行为的 `DateTimeConverter` 类；本主题中描述的转换行为源于 WPF XAML 分析器。</span><span class="sxs-lookup"><span data-stu-id="013e6-115">There is no `DateTimeConverter` class that provides the conversion behavior; the conversion behavior described in this topic is native to the WPF XAML parser.</span></span>  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a><span data-ttu-id="013e6-116">DateTime XAML 语法的格式字符串</span><span class="sxs-lookup"><span data-stu-id="013e6-116">Format Strings for DateTime XAML Syntax</span></span>  
 <span data-ttu-id="013e6-117">你可以指定的格式<xref:System.DateTime>有一个格式字符串。</span><span class="sxs-lookup"><span data-stu-id="013e6-117">You can specify the format of a <xref:System.DateTime> with a format string.</span></span> <span data-ttu-id="013e6-118">格式字符串会规范可用于创建值的文本语法。</span><span class="sxs-lookup"><span data-stu-id="013e6-118">Format strings formalize the text syntax that can be used to create a value.</span></span> <span data-ttu-id="013e6-119"><xref:System.DateTime> 对于现有 WPF 控件通常仅使用日期组成部分的值<xref:System.DateTime>而不是时间组件。</span><span class="sxs-lookup"><span data-stu-id="013e6-119"><xref:System.DateTime> values for the existing WPF controls generally only use the date components of <xref:System.DateTime> and not the time components.</span></span>  
  
 <span data-ttu-id="013e6-120">指定时<xref:System.DateTime>在 XAML，您可以使用任何格式字符串互换。</span><span class="sxs-lookup"><span data-stu-id="013e6-120">When specifying a <xref:System.DateTime> in XAML, you can use any of the format strings interchangeably.</span></span>  
  
 <span data-ttu-id="013e6-121">还可以使用未在本主题中专门显示的格式和格式字符串。</span><span class="sxs-lookup"><span data-stu-id="013e6-121">You can also use formats and format strings that are not specifically shown in this topic.</span></span> <span data-ttu-id="013e6-122">从技术上讲，任何 XAML<xref:System.DateTime>值，该值指定，然后分析 WPF XAML 分析器使用的内部调用<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>，因此可以使用接受的任何字符串<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>对于你的 XAML 输入。</span><span class="sxs-lookup"><span data-stu-id="013e6-122">Technically, the XAML for any <xref:System.DateTime> value that is specified and then parsed by the WPF XAML parser uses an internal  call to <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, therefore you could use any string accepted by <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> for your XAML input.</span></span> <span data-ttu-id="013e6-123">有关详细信息，请参阅 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="013e6-123">For more information, see <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="013e6-124">DateTime XAML 语法始终使用`en-us`作为<xref:System.Globalization.CultureInfo>其本机转换。</span><span class="sxs-lookup"><span data-stu-id="013e6-124">The DateTime XAML syntax always uses `en-us` as the <xref:System.Globalization.CultureInfo> for its native conversion.</span></span> <span data-ttu-id="013e6-125">这不受<xref:System.Windows.FrameworkElement.Language%2A>值或`xml:lang`XAML，这是因为 XAML 属性级别的类型转换操作而无需该上下文值。</span><span class="sxs-lookup"><span data-stu-id="013e6-125">This is not influenced by <xref:System.Windows.FrameworkElement.Language%2A> value or `xml:lang` value in the XAML, because XAML attribute-level type conversion acts without that context.</span></span> <span data-ttu-id="013e6-126">出于区域性差异的原因，请不要尝试插入此处所示的格式字符串，例如，日期和月份的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="013e6-126">Do not attempt to interpolate the format strings shown here due to cultural variations, such as the order in which day and month appear.</span></span> <span data-ttu-id="013e6-127">此处所示的格式字符串是在分析 XAML 时（不考虑其他区域性设置）使用的确切格式字符串。</span><span class="sxs-lookup"><span data-stu-id="013e6-127">The format strings shown here are the exact format strings used when parsing the XAML regardless of other culture settings.</span></span>  
  
 <span data-ttu-id="013e6-128">以下各节介绍了一些常见<xref:System.DateTime>格式字符串。</span><span class="sxs-lookup"><span data-stu-id="013e6-128">The following sections describe some of the common <xref:System.DateTime> format strings.</span></span>  
  
### <a name="short-date-pattern-d"></a><span data-ttu-id="013e6-129">短日期模式（“d”）</span><span class="sxs-lookup"><span data-stu-id="013e6-129">Short Date Pattern ("d")</span></span>  
 <span data-ttu-id="013e6-130">以下显示的短日期格式<xref:System.DateTime>在 XAML 中：</span><span class="sxs-lookup"><span data-stu-id="013e6-130">The following shows the short date format for a <xref:System.DateTime> in XAML:</span></span>  
  
 `M/d/YYYY`  
  
 <span data-ttu-id="013e6-131">这是最简单的形式，可指定 WPF 控件一般使用的所有必要信息，并且不受针对时间部分的偶然时区偏移的影响，因此比其他格式更适用。</span><span class="sxs-lookup"><span data-stu-id="013e6-131">This is the simplest form that specifies all necessary information for typical usages by WPF controls, and cannot be influenced by accidental time zone offsets versus a time component, and is therefore recommended over the other formats.</span></span>  
  
 <span data-ttu-id="013e6-132">例如，若要指定日期 2010 年 6 月 1 日，可使用以下字符串：</span><span class="sxs-lookup"><span data-stu-id="013e6-132">For example, to specify the date of June 1, 2010, use the following string:</span></span>  
  
 `3/1/2010`  
  
 <span data-ttu-id="013e6-133">有关详细信息，请参阅 <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="013e6-133">For more information, see <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="sortable-datetime-pattern-s"></a><span data-ttu-id="013e6-134">可排序 DateTime 模式（“s”）</span><span class="sxs-lookup"><span data-stu-id="013e6-134">Sortable DateTime Pattern ("s")</span></span>  
 <span data-ttu-id="013e6-135">下面的示例演示可排序<xref:System.DateTime>在 XAML 中的模式：</span><span class="sxs-lookup"><span data-stu-id="013e6-135">The following shows the sortable <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 <span data-ttu-id="013e6-136">例如，若要指定日期 2010 年 6 月 1 日，可使用以下字符串（时间部分全部输入为 0）：</span><span class="sxs-lookup"><span data-stu-id="013e6-136">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a><span data-ttu-id="013e6-137">RFC1123 模式（“r”）</span><span class="sxs-lookup"><span data-stu-id="013e6-137">RFC1123 Pattern ("r")</span></span>  
 <span data-ttu-id="013e6-138">RFC1123 模式很有用，因为它可以是来自其他日期生成器的字符串输入，这些字符生成器出于区域性固定原因同样使用 RFC1123 模式。</span><span class="sxs-lookup"><span data-stu-id="013e6-138">The RFC1123 pattern is useful because it could be a string input from other date generators that also use the RFC1123 pattern for culture invariant reasons.</span></span> <span data-ttu-id="013e6-139">下面的示例演示 RFC1123<xref:System.DateTime>在 XAML 中的模式：</span><span class="sxs-lookup"><span data-stu-id="013e6-139">The following shows the RFC1123 <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 <span data-ttu-id="013e6-140">例如，若要指定日期 2010 年 6 月 1 日，可使用以下字符串（时间部分全部输入为 0）：</span><span class="sxs-lookup"><span data-stu-id="013e6-140">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a><span data-ttu-id="013e6-141">其他格式和模式</span><span class="sxs-lookup"><span data-stu-id="013e6-141">Other Formats and Patterns</span></span>  
 <span data-ttu-id="013e6-142">如前所述，<xref:System.DateTime>在 XAML 中可以指定为可接受任何字符串作为输入的<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="013e6-142">As stated previously, a <xref:System.DateTime> in XAML can be specified as any string that is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="013e6-143">这包括其他正式化的格式 (例如<xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>)，以及未正式化为特定的格式<xref:System.Globalization.DateTimeFormatInfo>窗体。</span><span class="sxs-lookup"><span data-stu-id="013e6-143">This includes other formalized formats (for example <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), and formats that are not formalized as a particular <xref:System.Globalization.DateTimeFormatInfo> form.</span></span> <span data-ttu-id="013e6-144">例如，窗体`YYYY/mm/dd`是可接受作为输入的<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="013e6-144">For example, the form `YYYY/mm/dd` is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="013e6-145">本主题并没有试图介绍所有可能有效的格式，而是推荐将短日期模式作为一种标准做法。</span><span class="sxs-lookup"><span data-stu-id="013e6-145">This topic does not attempt to describe all possible formats that work, and instead recommends the short date pattern as a standard practice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="013e6-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="013e6-146">See also</span></span>
- [<span data-ttu-id="013e6-147">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="013e6-147">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
