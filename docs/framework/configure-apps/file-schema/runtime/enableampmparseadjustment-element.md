---
title: <EnableAmPmParseAdjustment> 元素
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d1a14199debbb90827c1ea95347d485a636329
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704838"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="ba7fb-102">\<EnableAmPmParseAdjustment > 元素</span><span class="sxs-lookup"><span data-stu-id="ba7fb-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="ba7fb-103">确定是否日期和时间分析方法使用调整后的规则集来分析日期字符串包含天、 月、 小时和 AM/PM 指示符。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="ba7fb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ba7fb-104">\<configuration></span></span>  
 <span data-ttu-id="ba7fb-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="ba7fb-105">\<runtime></span></span>  
<span data-ttu-id="ba7fb-106">\<EnableAmPmParseAdjustment></span><span class="sxs-lookup"><span data-stu-id="ba7fb-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba7fb-107">语法</span><span class="sxs-lookup"><span data-stu-id="ba7fb-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba7fb-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ba7fb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ba7fb-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba7fb-110">特性</span><span class="sxs-lookup"><span data-stu-id="ba7fb-110">Attributes</span></span>  
  
|<span data-ttu-id="ba7fb-111">特性</span><span class="sxs-lookup"><span data-stu-id="ba7fb-111">Attribute</span></span>|<span data-ttu-id="ba7fb-112">描述</span><span class="sxs-lookup"><span data-stu-id="ba7fb-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ba7fb-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ba7fb-114">指定是否日期和时间分析方法使用调整后的规则集来分析日期字符串包含仅日、 月、 小时和 AM/PM 指示符。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="ba7fb-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="ba7fb-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ba7fb-116">“值”</span><span class="sxs-lookup"><span data-stu-id="ba7fb-116">Value</span></span>|<span data-ttu-id="ba7fb-117">Description</span><span class="sxs-lookup"><span data-stu-id="ba7fb-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ba7fb-118">0</span><span class="sxs-lookup"><span data-stu-id="ba7fb-118">0</span></span>|<span data-ttu-id="ba7fb-119">日期和时间分析方法不使用调整后的规则用于分析包含仅日、 月、 小时和 AM/PM 指示符的日期字符串。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="ba7fb-120">1</span><span class="sxs-lookup"><span data-stu-id="ba7fb-120">1</span></span>|<span data-ttu-id="ba7fb-121">日期和时间分析方法的分析包含仅日、 月、 小时和 AM/PM 指示符的日期字符串使用调整后的规则。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba7fb-122">子元素</span><span class="sxs-lookup"><span data-stu-id="ba7fb-122">Child Elements</span></span>  
 <span data-ttu-id="ba7fb-123">无。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba7fb-124">父元素</span><span class="sxs-lookup"><span data-stu-id="ba7fb-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ba7fb-125">元素</span><span class="sxs-lookup"><span data-stu-id="ba7fb-125">Element</span></span>|<span data-ttu-id="ba7fb-126">描述</span><span class="sxs-lookup"><span data-stu-id="ba7fb-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ba7fb-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ba7fb-128">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba7fb-129">备注</span><span class="sxs-lookup"><span data-stu-id="ba7fb-129">Remarks</span></span>  
 <span data-ttu-id="ba7fb-130">`<EnableAmPmParseAdjustment>`元素控制以下方法如何分析日期字符串，其中包含日期和月份后, 跟一小时和 AM/PM 指示符 （如"4/10 6 AM"):</span><span class="sxs-lookup"><span data-stu-id="ba7fb-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="ba7fb-131">没有其他模式会受到影响。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="ba7fb-132">`<EnableAmPmParseAdjustment>`元素不起任何作用<xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>， <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>， <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>，和<xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ba7fb-133">在.NET Core 和.NET Native，默认情况下启用的调整后的 AM/PM 分析规则。 </span><span class="sxs-lookup"><span data-stu-id="ba7fb-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="ba7fb-134">如果分析的调整规则未启用，该字符串的第一个数字解释为 12 小时制时钟的小时和 AM/PM 指示符除外的字符串的其余部分将被忽略。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="ba7fb-135">日期和时间分析方法返回包含当前日期和从日期字符串中提取一天的小时。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="ba7fb-136">如果启用了分析的调整规则，分析方法的日期和月份为属于当前年份，解释和解释为 12 小时制的小时的时间。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="ba7fb-137">下表说明了中的差异<xref:System.DateTime>值时<xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType>方法用于分析字符串""4/10 6 AM"与`<EnableAmPmParseAdjustment>`元素的`enabled`属性设置为"0"或"1"。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="ba7fb-138">它假定今天的日期为 2017 年 1 月 5 日，并像使用特定的区域性的"G"格式字符串格式化显示的日期。</span><span class="sxs-lookup"><span data-stu-id="ba7fb-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="ba7fb-139">区域性名称</span><span class="sxs-lookup"><span data-stu-id="ba7fb-139">Culture name</span></span>|<span data-ttu-id="ba7fb-140">enabled="0"</span><span class="sxs-lookup"><span data-stu-id="ba7fb-140">enabled="0"</span></span>|<span data-ttu-id="ba7fb-141">enabled="1"</span><span class="sxs-lookup"><span data-stu-id="ba7fb-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="ba7fb-142">en-US</span><span class="sxs-lookup"><span data-stu-id="ba7fb-142">en-US</span></span>|<span data-ttu-id="ba7fb-143">2017 年 1 月 5 日 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="ba7fb-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="ba7fb-144">2017 年 4 月 10 日上午 6:00:00</span><span class="sxs-lookup"><span data-stu-id="ba7fb-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="ba7fb-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="ba7fb-145">en-GB</span></span>|<span data-ttu-id="ba7fb-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="ba7fb-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="ba7fb-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="ba7fb-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba7fb-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba7fb-148">See also</span></span>

- [<span data-ttu-id="ba7fb-149">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="ba7fb-149">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [<span data-ttu-id="ba7fb-150">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="ba7fb-150">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
