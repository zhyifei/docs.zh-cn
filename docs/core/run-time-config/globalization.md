---
title: 全球化配置设置
description: 了解对 .NET Core 应用的全球化方面进行配置的运行时设置。例如，如何分析日语日期。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 3764d0eb714c094b44ae843a1e626073ff8d82e4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733455"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="a2d33-103">用于全球化的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="a2d33-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="a2d33-104">固定模式</span><span class="sxs-lookup"><span data-stu-id="a2d33-104">Invariant mode</span></span>

- <span data-ttu-id="a2d33-105">确定 .NET Core 应用是否以全球化固定模式运行而无权访问特定区域性的数据和行为，或者是否有权访问区域性数据。</span><span class="sxs-lookup"><span data-stu-id="a2d33-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="a2d33-106">默认：运行应用并可访问区域性数据 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="a2d33-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="a2d33-107">有关详细信息，请参阅 [.NET Core 全球化固定模式](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="a2d33-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="a2d33-108">设置名</span><span class="sxs-lookup"><span data-stu-id="a2d33-108">Setting name</span></span> | <span data-ttu-id="a2d33-109">值</span><span class="sxs-lookup"><span data-stu-id="a2d33-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a2d33-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a2d33-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="a2d33-111">`false` - 可访问区域性数据</span><span class="sxs-lookup"><span data-stu-id="a2d33-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="a2d33-112">`true` - 以固定模式运行</span><span class="sxs-lookup"><span data-stu-id="a2d33-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="a2d33-113">MSBuild 属性 </span><span class="sxs-lookup"><span data-stu-id="a2d33-113">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="a2d33-114">`false` - 可访问区域性数据</span><span class="sxs-lookup"><span data-stu-id="a2d33-114">`false` - access to cultural data</span></span><br/><span data-ttu-id="a2d33-115">`true` - 以固定模式运行</span><span class="sxs-lookup"><span data-stu-id="a2d33-115">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="a2d33-116">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a2d33-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="a2d33-117">`0` - 可访问区域性数据</span><span class="sxs-lookup"><span data-stu-id="a2d33-117">`0` - access to cultural data</span></span><br/><span data-ttu-id="a2d33-118">`1` - 以固定模式运行</span><span class="sxs-lookup"><span data-stu-id="a2d33-118">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="a2d33-119">示例</span><span class="sxs-lookup"><span data-stu-id="a2d33-119">Examples</span></span>

<span data-ttu-id="a2d33-120">runtimeconfig.json 文件： </span><span class="sxs-lookup"><span data-stu-id="a2d33-120">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="a2d33-121">项目文件：</span><span class="sxs-lookup"><span data-stu-id="a2d33-121">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="a2d33-122">纪元年份范围</span><span class="sxs-lookup"><span data-stu-id="a2d33-122">Era year ranges</span></span>

- <span data-ttu-id="a2d33-123">确定是否放宽对支持多个纪元的日历的范围检查，或者超出纪元日期范围的日期是否引发 <xref:System.ArgumentOutOfRangeException>。</span><span class="sxs-lookup"><span data-stu-id="a2d33-123">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="a2d33-124">默认：放宽范围检查 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="a2d33-124">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="a2d33-125">有关详细信息，请参阅[日历、纪元和日期范围：放宽的范围检查](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks)。</span><span class="sxs-lookup"><span data-stu-id="a2d33-125">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="a2d33-126">设置名</span><span class="sxs-lookup"><span data-stu-id="a2d33-126">Setting name</span></span> | <span data-ttu-id="a2d33-127">值</span><span class="sxs-lookup"><span data-stu-id="a2d33-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a2d33-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a2d33-128">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="a2d33-129">`false` - 放宽的范围检查</span><span class="sxs-lookup"><span data-stu-id="a2d33-129">`false` - relaxed range checks</span></span><br/><span data-ttu-id="a2d33-130">`true` - 超出范围导致异常</span><span class="sxs-lookup"><span data-stu-id="a2d33-130">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="a2d33-131">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a2d33-131">**Environment variable**</span></span> | <span data-ttu-id="a2d33-132">不可用</span><span class="sxs-lookup"><span data-stu-id="a2d33-132">N/A</span></span> | <span data-ttu-id="a2d33-133">不可用</span><span class="sxs-lookup"><span data-stu-id="a2d33-133">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="a2d33-134">日语日期分析</span><span class="sxs-lookup"><span data-stu-id="a2d33-134">Japanese date parsing</span></span>

- <span data-ttu-id="a2d33-135">确定是否成功分析包含“1”或“Gannen”作为年份的字符串，或是否仅支持“1”。</span><span class="sxs-lookup"><span data-stu-id="a2d33-135">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="a2d33-136">默认：分析包含“1”或“Gannen”作为年份的字符串 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="a2d33-136">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="a2d33-137">有关详细信息，请参阅[用多个纪元表示日历中的日期](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)。</span><span class="sxs-lookup"><span data-stu-id="a2d33-137">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="a2d33-138">设置名</span><span class="sxs-lookup"><span data-stu-id="a2d33-138">Setting name</span></span> | <span data-ttu-id="a2d33-139">值</span><span class="sxs-lookup"><span data-stu-id="a2d33-139">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a2d33-140">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a2d33-140">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="a2d33-141">`false` - 支持“Gannen”或“1”</span><span class="sxs-lookup"><span data-stu-id="a2d33-141">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="a2d33-142">`true` - 仅支持“1”</span><span class="sxs-lookup"><span data-stu-id="a2d33-142">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="a2d33-143">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a2d33-143">**Environment variable**</span></span> | <span data-ttu-id="a2d33-144">不可用</span><span class="sxs-lookup"><span data-stu-id="a2d33-144">N/A</span></span> | <span data-ttu-id="a2d33-145">不可用</span><span class="sxs-lookup"><span data-stu-id="a2d33-145">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="a2d33-146">日语年份格式</span><span class="sxs-lookup"><span data-stu-id="a2d33-146">Japanese year format</span></span>

- <span data-ttu-id="a2d33-147">确定是将日本历时代的第一年的格式设置为“Gannen”还是设置为一个数字。</span><span class="sxs-lookup"><span data-stu-id="a2d33-147">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="a2d33-148">默认：将第一年的格式设置为“Gannen”(`false`)。</span><span class="sxs-lookup"><span data-stu-id="a2d33-148">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="a2d33-149">有关详细信息，请参阅[用多个纪元表示日历中的日期](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)。</span><span class="sxs-lookup"><span data-stu-id="a2d33-149">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="a2d33-150">设置名</span><span class="sxs-lookup"><span data-stu-id="a2d33-150">Setting name</span></span> | <span data-ttu-id="a2d33-151">值</span><span class="sxs-lookup"><span data-stu-id="a2d33-151">Values</span></span> |
| - | - | - |
| <span data-ttu-id="a2d33-152">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="a2d33-152">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="a2d33-153">`false` - 将格式设置为“Gannen”</span><span class="sxs-lookup"><span data-stu-id="a2d33-153">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="a2d33-154">`true` - 将格式设置为数字</span><span class="sxs-lookup"><span data-stu-id="a2d33-154">`true` - format as number</span></span> |
| <span data-ttu-id="a2d33-155">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="a2d33-155">**Environment variable**</span></span> | <span data-ttu-id="a2d33-156">不可用</span><span class="sxs-lookup"><span data-stu-id="a2d33-156">N/A</span></span> | <span data-ttu-id="a2d33-157">不可用</span><span class="sxs-lookup"><span data-stu-id="a2d33-157">N/A</span></span> |
