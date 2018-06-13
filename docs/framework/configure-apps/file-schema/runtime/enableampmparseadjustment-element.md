---
title: '&lt;EnableAmPmParseAdjustment&gt;元素'
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b17f521be31fa4082d9418c7dad734e37994bbb5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752814"
---
# <a name="ltenableampmparseadjustmentgt-element"></a><span data-ttu-id="f34ae-102">&lt;EnableAmPmParseAdjustment&gt;元素</span><span class="sxs-lookup"><span data-stu-id="f34ae-102">&lt;EnableAmPmParseAdjustment&gt; Element</span></span>
<span data-ttu-id="f34ae-103">确定是否日期和事件分析方法使用调整后的一组规则来分析包含日、 月、 小时和 AM/PM 指示符的日期字符串。</span><span class="sxs-lookup"><span data-stu-id="f34ae-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="f34ae-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f34ae-104">\<configuration></span></span>  
 <span data-ttu-id="f34ae-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="f34ae-105">\<runtime></span></span>  
<span data-ttu-id="f34ae-106">\<EnableAmPmParseAdjustment ></span><span class="sxs-lookup"><span data-stu-id="f34ae-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f34ae-107">语法</span><span class="sxs-lookup"><span data-stu-id="f34ae-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f34ae-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f34ae-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f34ae-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f34ae-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f34ae-110">特性</span><span class="sxs-lookup"><span data-stu-id="f34ae-110">Attributes</span></span>  
  
|<span data-ttu-id="f34ae-111">特性</span><span class="sxs-lookup"><span data-stu-id="f34ae-111">Attribute</span></span>|<span data-ttu-id="f34ae-112">描述</span><span class="sxs-lookup"><span data-stu-id="f34ae-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="f34ae-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="f34ae-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="f34ae-114">指定是否日期和事件分析方法使用调整后的一组规则来分析包含仅日、 月、 小时和 AM/PM 指示符的日期字符串。</span><span class="sxs-lookup"><span data-stu-id="f34ae-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="f34ae-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="f34ae-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="f34ae-116">值</span><span class="sxs-lookup"><span data-stu-id="f34ae-116">Value</span></span>|<span data-ttu-id="f34ae-117">描述</span><span class="sxs-lookup"><span data-stu-id="f34ae-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f34ae-118">0</span><span class="sxs-lookup"><span data-stu-id="f34ae-118">0</span></span>|<span data-ttu-id="f34ae-119">日期和事件分析方法不使用调整后的规则用于分析包含仅日、 月、 小时和 AM/PM 指示符的日期字符串。</span><span class="sxs-lookup"><span data-stu-id="f34ae-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="f34ae-120">1</span><span class="sxs-lookup"><span data-stu-id="f34ae-120">1</span></span>|<span data-ttu-id="f34ae-121">日期和事件分析方法使用调整后的规则来分析包含仅日、 月、 小时和 AM/PM 指示符的日期字符串。</span><span class="sxs-lookup"><span data-stu-id="f34ae-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f34ae-122">子元素</span><span class="sxs-lookup"><span data-stu-id="f34ae-122">Child Elements</span></span>  
 <span data-ttu-id="f34ae-123">无。</span><span class="sxs-lookup"><span data-stu-id="f34ae-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f34ae-124">父元素</span><span class="sxs-lookup"><span data-stu-id="f34ae-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f34ae-125">元素</span><span class="sxs-lookup"><span data-stu-id="f34ae-125">Element</span></span>|<span data-ttu-id="f34ae-126">描述</span><span class="sxs-lookup"><span data-stu-id="f34ae-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f34ae-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="f34ae-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f34ae-128">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="f34ae-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f34ae-129">备注</span><span class="sxs-lookup"><span data-stu-id="f34ae-129">Remarks</span></span>  
 <span data-ttu-id="f34ae-130">`<EnableAmPmParseAdjustment>`元素控制以下方法如何分析日期字符串包含的一天和月后跟一个小时的时间和 AM/PM 指示符 （如"4/10 6 AM"):</span><span class="sxs-lookup"><span data-stu-id="f34ae-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="f34ae-131">没有其他模式会受到影响。</span><span class="sxs-lookup"><span data-stu-id="f34ae-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="f34ae-132">`<EnableAmPmParseAdjustment>`元素没有任何影响<xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>， <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>， <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>，和<xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="f34ae-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f34ae-133">在.NET 核心和.NET Native，默认情况下启用的调整后的 AM/PM 分析规则。</span><span class="sxs-lookup"><span data-stu-id="f34ae-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="f34ae-134">如果未启用分析的调整规则，该字符串的第一个数字解释为 12 小时时钟小时和除外 AM/PM 指示符的字符串的其余部分将被忽略。</span><span class="sxs-lookup"><span data-stu-id="f34ae-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="f34ae-135">日期和时间分析方法返回包含当前日期和从日期字符串中提取一天中的小时。</span><span class="sxs-lookup"><span data-stu-id="f34ae-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="f34ae-136">如果启用了分析的调整规则，分析方法解释的日期和月份为属于当前年份，并解释为 12 小时制的小时的时间。</span><span class="sxs-lookup"><span data-stu-id="f34ae-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="f34ae-137">下表说明了中的差异<xref:System.DateTime>值时<xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType>方法用于分析字符串""4/10 6 AM"与`<EnableAmPmParseAdjustment>`元素的`enabled`属性设置为"0"或"1"。</span><span class="sxs-lookup"><span data-stu-id="f34ae-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="f34ae-138">它假定今天的日期是 2017 年 1 月 5 日，并显示的日期，就像它使用指定的区域性"G"格式字符串格式设置。</span><span class="sxs-lookup"><span data-stu-id="f34ae-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="f34ae-139">区域性名称</span><span class="sxs-lookup"><span data-stu-id="f34ae-139">Culture name</span></span>|<span data-ttu-id="f34ae-140">启用 ="0"</span><span class="sxs-lookup"><span data-stu-id="f34ae-140">enabled="0"</span></span>|<span data-ttu-id="f34ae-141">启用 ="1"</span><span class="sxs-lookup"><span data-stu-id="f34ae-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="f34ae-142">en-US</span><span class="sxs-lookup"><span data-stu-id="f34ae-142">en-US</span></span>|<span data-ttu-id="f34ae-143">2017 年 1/5/4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="f34ae-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="f34ae-144">4/10/2017年 6:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="f34ae-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="f34ae-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="f34ae-145">en-GB</span></span>|<span data-ttu-id="f34ae-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="f34ae-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="f34ae-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="f34ae-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f34ae-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="f34ae-148">See Also</span></span>  
 [<span data-ttu-id="f34ae-149">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="f34ae-149">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
 [<span data-ttu-id="f34ae-150">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="f34ae-150">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
