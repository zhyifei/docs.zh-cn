---
title: "DateTime XAML 语法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55e261018e6c7b9fea9ad449c5e92a131df40807
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="datetime-xaml-syntax"></a>DateTime XAML 语法
某些控件，如<xref:System.Windows.Controls.Calendar>和<xref:System.Windows.Controls.DatePicker>，已使用的属性<xref:System.DateTime>类型。 虽然通常会在运行时在代码隐藏中指定这些控件的初始日期或时间，但可以在 XAML 中指定初始日期或时间。 WPF XAML 分析器处理分析<xref:System.DateTime>值使用内置的 XAML 文本语法。 本主题描述的细节<xref:System.DateTime>XAML 文本语法。  
  
  
<a name="where_datetime_xaml_syntax_is_used"></a>   
## <a name="when-to-use-datetime-xaml-syntax"></a>DateTime XAML 语法的使用场合  
 无需经常对 XAML 中的日期进行设置，而且设置也可能并不合适。 例如，可以使用<xref:System.DateTime.Now%2A?displayProperty=nameWithType>初始化在运行的时，或你的日期的属性无法执行所有的日期调整此根据用户输入的代码隐藏文件中的日历。 但是，有一些情况下你可能想为硬编码日期到<xref:System.Windows.Controls.Calendar>和<xref:System.Windows.Controls.DatePicker>控件模板中。 <xref:System.DateTime> XAML 语法必须可用于这些方案。  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a>DateTime XAML 语法是本机行为  
 <xref:System.DateTime>是在 CLR 基类库中定义的类。 由于如何基类库与 CLR 的其余部分，它不能应用<xref:System.ComponentModel.TypeConverterAttribute>到类，然后使用用于处理 XAML 中的字符串，并将它们转换为的类型转换器<xref:System.DateTime>运行的时对象模型中。 没有提供转换行为的 `DateTimeConverter` 类；本主题中描述的转换行为源于 WPF XAML 分析器。  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>   
## <a name="format-strings-for-datetime-xaml-syntax"></a>DateTime XAML 语法的格式字符串  
 您可以指定的格式<xref:System.DateTime>使用格式字符串。 格式字符串会规范可用于创建值的文本语法。 <xref:System.DateTime>值对于现有 WPF 控件通常只使用的日期组件<xref:System.DateTime>并不是时间组件。  
  
 指定时<xref:System.DateTime>在 XAML 中，你可以使用任何格式字符串的互换。  
  
 还可以使用未在本主题中专门显示的格式和格式字符串。 从技术上讲，任何 XAML<xref:System.DateTime>值，然后分析 WPF XAML 分析器并指定使用对的内部调用<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>，因此您无法使用接受任意字符串<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>用于 XAML 输入。 有关更多信息，请参见<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>。  
  
> [!IMPORTANT]
>  DateTime XAML 语法始终使用`en-us`作为<xref:System.Globalization.CultureInfo>为其本机的转换。 这不受<xref:System.Windows.FrameworkElement.Language%2A>值或`xml:lang`值在 XAML 中，这是因为 XAML 特性级类型转换操作而无需该上下文。 出于区域性差异的原因，请不要尝试插入此处所示的格式字符串，例如，日期和月份的显示顺序。 此处所示的格式字符串是在分析 XAML 时（不考虑其他区域性设置）使用的确切格式字符串。  
  
 以下各节描述了一些常见<xref:System.DateTime>格式字符串。  
  
### <a name="short-date-pattern-d"></a>短日期模式（“d”）  
 下面的示例演示的短日期格式<xref:System.DateTime>在 XAML 中：  
  
 `M/d/YYYY`  
  
 这是最简单的形式，可指定 WPF 控件一般使用的所有必要信息，并且不受针对时间部分的偶然时区偏移的影响，因此比其他格式更适用。  
  
 例如，若要指定日期 2010 年 6 月 1 日，可使用以下字符串：  
  
 `3/1/2010`  
  
 有关更多信息，请参见<xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>。  
  
### <a name="sortable-datetime-pattern-s"></a>可排序 DateTime 模式（“s”）  
 下面的示例演示可排序<xref:System.DateTime>在 XAML 中的模式：  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 例如，若要指定日期 2010 年 6 月 1 日，可使用以下字符串（时间部分全部输入为 0）：  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a>RFC1123 模式（“r”）  
 RFC1123 模式很有用，因为它可以是来自其他日期生成器的字符串输入，这些字符生成器出于区域性固定原因同样使用 RFC1123 模式。 下面的示例演示 RFC1123<xref:System.DateTime>在 XAML 中的模式：  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 例如，若要指定日期 2010 年 6 月 1 日，可使用以下字符串（时间部分全部输入为 0）：  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a>其他格式和模式  
 如前所述，<xref:System.DateTime>在 XAML 中可以将它指定为任何字符串都是可接受的作为输入<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>。 这包括其他正式的格式 (例如<xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>)，和不规范化为特定的格式<xref:System.Globalization.DateTimeFormatInfo>窗体。 例如，窗体`YYYY/mm/dd`是可接受的作为输入<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>。 本主题并没有试图介绍所有可能有效的格式，而是推荐将短日期模式作为一种标准做法。  
  
## <a name="see-also"></a>另请参阅  
 [XAML 概述 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
