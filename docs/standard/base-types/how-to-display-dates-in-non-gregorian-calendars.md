---
title: "如何：用非公历日历显示日期"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET Framework], dates
- dates [.NET Framework], formatting
- calendars [.NET Framework], displaying dates
- displaying date and time data
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a79860091e549dcf4eaa7090947f9506eceb6119
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-dates-in-non-gregorian-calendars"></a>如何：用非公历日历显示日期
<xref:System.DateTime>和<xref:System.DateTimeOffset>类型使用它们的默认日历为公历。 这意味着，调用日期和时间值的 `ToString` 方法会用公历日历显示该日期和时间的字符串表示形式，即使该日期和时间是使用其他日历创建的。 这一点在以下示例中，使用两种不同方式与波斯历，创建日期和时间值，但仍在公历日历显示这些日期和时间值时，它调用<xref:System.DateTime.ToString%2A>方法。 此示例对于用特定日历显示日期，反映了两种常用但不正确的方法。  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 两种不同的方法可以用于以特定日历显示日期。 第一种方法要求日历是特定区域性的默认日历。 第二种方法可以与任何日历一起使用。  
  
### <a name="to-display-the-date-for-a-cultures-default-calendar"></a>针对区域性默认日历显示日期  
  
1.  实例化日历对象派生自<xref:System.Globalization.Calendar>类，表示要使用的日历。  
  
2.  实例化<xref:System.Globalization.CultureInfo>对象表示的区域性的格式设置将用于显示日期。  
  
3.  调用<xref:System.Array.Exists%2A?displayProperty=nameWithType>方法来确定日历对象是否为返回的数组的成员<xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>属性。 这表示日历可用作的默认日历<xref:System.Globalization.CultureInfo>对象。 如果它不是数组的成员，请按照“用任何日历显示日期”部分中的说明执行。  
  
4.  日历将对象分配给<xref:System.Globalization.DateTimeFormatInfo.Calendar%2A>属性<xref:System.Globalization.DateTimeFormatInfo>返回对象<xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>属性。  
  
    > [!NOTE]
    >  <xref:System.Globalization.CultureInfo>类还具有<xref:System.Globalization.CultureInfo.Calendar%2A>属性。 但是，它是只读的和常量;它不会更改以反映新的默认日历分配给<xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType>属性。  
  
5.  调用<xref:System.DateTime.ToString%2A>或<xref:System.DateTime.ToString%2A>方法，并将其传递<xref:System.Globalization.CultureInfo>对象在上一步中修改了其默认日历。  
  
### <a name="to-display-the-date-in-any-calendar"></a>用任何日历显示日期  
  
1.  实例化日历对象派生自<xref:System.Globalization.Calendar>类，表示要使用的日历。  
  
2.  确定应在日期和时间值的字符串表示形式中出现的日期和时间元素。  
  
3.  对于每个你想要显示的日期和时间元素，调用日历对象`Get`... 方法。 有以下方法可用：  
  
    -   <xref:System.Globalization.Calendar.GetYear%2A>将年份显示以适当的日历。  
  
    -   <xref:System.Globalization.Calendar.GetMonth%2A>显示相应的日历中的月。  
  
    -   <xref:System.Globalization.Calendar.GetDayOfMonth%2A>若要显示的每月天数数以适当的日历。  
  
    -   <xref:System.Globalization.Calendar.GetHour%2A>在适当的日历中显示的时间。  
  
    -   <xref:System.Globalization.Calendar.GetMinute%2A>以显示在相应的日历中的小时分钟。  
  
    -   <xref:System.Globalization.Calendar.GetSecond%2A>若要以适当的日历分钟内显示秒数。  
  
    -   <xref:System.Globalization.Calendar.GetMilliseconds%2A>以在相应的日历中的第二个显示毫秒数。  
  
## <a name="example"></a>示例  
 该示例使用两个不同日历显示日期。 它在将回历定义为 ar-JO 区域性的默认日历之后显示日期，并使用波斯日历（fa-IR 区域性不支持将它作为可选日历）显示日期。  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 每个<xref:System.Globalization.CultureInfo>对象都可以支持一个或多个日历，由指示<xref:System.Globalization.CultureInfo.OptionalCalendars%2A>属性。 以下方法之一指定为区域性的默认日历，并且返回的只读的<xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=nameWithType>属性。 另一个可选日历可以被指定为默认值通过分配<xref:System.Globalization.Calendar>对象，表示日历<xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=nameWithType>属性返回<xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>属性。 但是，某些日历，由表示波斯历如<xref:System.Globalization.PersianCalendar>类中，不能作为任何区域性的可选日历。  
  
 该示例定义了一个可重用的日历实用工具类 `CalendarUtility`，用于处理有关使用特定日历生成日期的字符串表示形式的许多详细信息。 `CalendarUtility` 类包含以下成员：  
  
-   其单个参数是参数化构造函数<xref:System.Globalization.Calendar>对象是用来表示日期。 这会分配给类的私有字段。  
  
-   `CalendarExists`返回一个布尔值，该值表示日历的私有方法`CalendarUtility`对象受<xref:System.Globalization.CultureInfo>传递给方法作为参数的对象。 该方法包装对的调用<xref:System.Array.Exists%2A?displayProperty=nameWithType>方法，向其传递<xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=nameWithType>数组。  
  
-   `HasSameName`分配给一个私有方法<xref:System.Predicate%601>，传入作为参数传递给委托<xref:System.Array.Exists%2A?displayProperty=nameWithType>方法。 数组的每个成员都会传递给该方法，直到该方法返回 `true`。 该方法确定可选日历的名称是否与 `CalendarUtility` 对象表示的日历相同。  
  
-   `DisplayDate`传递两个参数的重载的公共方法： 请<xref:System.DateTime>或<xref:System.DateTimeOffset>值，用以在所表示的日历`CalendarUtility`对象和要使用其格式设置规则的区域性。 它在返回日期的字符串表示形式时的行为取决于要使用其格式设置规则的区域性是否支持目标日历。  
  
 无论用于创建日历<xref:System.DateTime>或<xref:System.DateTimeOffset>在此示例中，该值通常表示为公历日期的值。 这是因为<xref:System.DateTime>和<xref:System.DateTimeOffset>类型并不保留任何日历信息。 它们在内部表示自 0001 年 1 月 1 日午夜以来所经历的时钟周期数。 该数字的解释取决于日历。 对于大多数区域性，默认日历是公历。  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要对 System.Core.dll 的引用。  
  
 在命令行上使用 csc.exe 或 vb.exe 代码编译。 若要编译中的代码[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，将其放入控制台应用程序项目模板。  
  
## <a name="see-also"></a>另请参阅  
 [执行格式设置操作](../../../docs/standard/base-types/performing-formatting-operations.md)
