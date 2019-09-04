---
title: <EnableAmPmParseAdjustment> 元素
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f132ce0a114a6fc904d86ca3ce893c447366523f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252630"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="d68d5-102">\<EnableAmPmParseAdjustment > 元素</span><span class="sxs-lookup"><span data-stu-id="d68d5-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="d68d5-103">确定日期和时间分析方法是否使用经过调整的规则集来分析包含 day、month、hour 和 AM/PM 指示符的日期字符串。</span><span class="sxs-lookup"><span data-stu-id="d68d5-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
<span data-ttu-id="d68d5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d68d5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d68d5-105">&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="d68d5-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="d68d5-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<EnableAmPmParseAdjustment>**</span><span class="sxs-lookup"><span data-stu-id="d68d5-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<EnableAmPmParseAdjustment>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d68d5-107">语法</span><span class="sxs-lookup"><span data-stu-id="d68d5-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d68d5-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d68d5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d68d5-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d68d5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d68d5-110">特性</span><span class="sxs-lookup"><span data-stu-id="d68d5-110">Attributes</span></span>  
  
|<span data-ttu-id="d68d5-111">特性</span><span class="sxs-lookup"><span data-stu-id="d68d5-111">Attribute</span></span>|<span data-ttu-id="d68d5-112">描述</span><span class="sxs-lookup"><span data-stu-id="d68d5-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="d68d5-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="d68d5-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="d68d5-114">指定日期和时间分析方法是否使用经过调整的规则集来分析只包含 day、month、hour 和 AM/PM 指示符的日期字符串。</span><span class="sxs-lookup"><span data-stu-id="d68d5-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="d68d5-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="d68d5-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="d68d5-116">值</span><span class="sxs-lookup"><span data-stu-id="d68d5-116">Value</span></span>|<span data-ttu-id="d68d5-117">Description</span><span class="sxs-lookup"><span data-stu-id="d68d5-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d68d5-118">0</span><span class="sxs-lookup"><span data-stu-id="d68d5-118">0</span></span>|<span data-ttu-id="d68d5-119">日期和时间分析方法不使用调整的规则来分析日期字符串，这些字符串只包含日、月、小时和 AM/PM 指示符。</span><span class="sxs-lookup"><span data-stu-id="d68d5-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="d68d5-120">1</span><span class="sxs-lookup"><span data-stu-id="d68d5-120">1</span></span>|<span data-ttu-id="d68d5-121">日期和时间分析方法使用经过调整的规则，用于分析日期字符串，这些字符串只包含日、月、小时和 AM/PM 指示符。</span><span class="sxs-lookup"><span data-stu-id="d68d5-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d68d5-122">子元素</span><span class="sxs-lookup"><span data-stu-id="d68d5-122">Child Elements</span></span>  
 <span data-ttu-id="d68d5-123">无。</span><span class="sxs-lookup"><span data-stu-id="d68d5-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d68d5-124">父元素</span><span class="sxs-lookup"><span data-stu-id="d68d5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d68d5-125">元素</span><span class="sxs-lookup"><span data-stu-id="d68d5-125">Element</span></span>|<span data-ttu-id="d68d5-126">描述</span><span class="sxs-lookup"><span data-stu-id="d68d5-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d68d5-127">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="d68d5-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="d68d5-128">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="d68d5-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d68d5-129">备注</span><span class="sxs-lookup"><span data-stu-id="d68d5-129">Remarks</span></span>  
 <span data-ttu-id="d68d5-130">`<EnableAmPmParseAdjustment>`元素控制以下方法如何分析包含数字日和月后跟一个小时和 AM/PM 指示符的日期字符串（例如 "4/10 6 AM"）：</span><span class="sxs-lookup"><span data-stu-id="d68d5-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="d68d5-131">其他模式不受影响。</span><span class="sxs-lookup"><span data-stu-id="d68d5-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="d68d5-132">`<EnableAmPmParseAdjustment>`元素对<xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>、、和<xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>方法不起作用<xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType>。 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d68d5-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d68d5-133">在.NET Core 和.NET Native，默认情况下启用的调整后的 AM/PM 分析规则。</span><span class="sxs-lookup"><span data-stu-id="d68d5-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="d68d5-134">如果未启用解析调整规则，则会将字符串的第一个数字解释为12小时制的小时，而除 AM/PM 指示符之外的字符串的其余部分将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d68d5-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="d68d5-135">解析方法返回的日期和时间由当前日期和从日期字符串提取的日期中的小时组成。</span><span class="sxs-lookup"><span data-stu-id="d68d5-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="d68d5-136">如果启用了解析调整规则，则分析方法会将日期和月份解释为属于当前年份，并将时间解释为12小时制的小时。</span><span class="sxs-lookup"><span data-stu-id="d68d5-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="d68d5-137"><xref:System.DateTime>下表说明了<xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType>当使用方法分析字符串 " `<EnableAmPmParseAdjustment>` 4/10 6 AM" （元素的`enabled`属性设置为 "0" 或 "1"）时，值中的差异。</span><span class="sxs-lookup"><span data-stu-id="d68d5-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="d68d5-138">它假定今天的日期为2017年1月5日，并使用指定的区域性的 "G" 格式字符串来显示日期。</span><span class="sxs-lookup"><span data-stu-id="d68d5-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="d68d5-139">区域性名称</span><span class="sxs-lookup"><span data-stu-id="d68d5-139">Culture name</span></span>|<span data-ttu-id="d68d5-140">enabled = "0"</span><span class="sxs-lookup"><span data-stu-id="d68d5-140">enabled="0"</span></span>|<span data-ttu-id="d68d5-141">enabled = "1"</span><span class="sxs-lookup"><span data-stu-id="d68d5-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="d68d5-142">en-US</span><span class="sxs-lookup"><span data-stu-id="d68d5-142">en-US</span></span>|<span data-ttu-id="d68d5-143">上午 1/5/2017 4:00:00</span><span class="sxs-lookup"><span data-stu-id="d68d5-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="d68d5-144">上午 4/10/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="d68d5-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="d68d5-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="d68d5-145">en-GB</span></span>|<span data-ttu-id="d68d5-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="d68d5-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="d68d5-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="d68d5-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d68d5-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="d68d5-148">See also</span></span>

- [<span data-ttu-id="d68d5-149">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="d68d5-149">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="d68d5-150">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="d68d5-150">\<configuration> Element</span></span>](../configuration-element.md)
