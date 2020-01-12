---
title: 全球化配置设置
description: 了解对 .NET Core 应用的全球化方面进行配置的运行时设置。例如，如何分析日语日期。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 76cd4a0a0f93f4df3ff243c6024b952576e8e6cb
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740537"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="adf26-103">用于全球化的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="adf26-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="adf26-104">固定模式</span><span class="sxs-lookup"><span data-stu-id="adf26-104">Invariant mode</span></span>

- <span data-ttu-id="adf26-105">确定 .NET Core 应用是否以全球化固定模式运行而无权访问特定区域性的数据和行为，或者是否有权访问区域性数据。</span><span class="sxs-lookup"><span data-stu-id="adf26-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="adf26-106">默认：运行应用并可访问区域性数据 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="adf26-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="adf26-107">有关详细信息，请参阅 [.NET Core 全球化固定模式](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="adf26-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="adf26-108">设置名</span><span class="sxs-lookup"><span data-stu-id="adf26-108">Setting name</span></span> | <span data-ttu-id="adf26-109">值</span><span class="sxs-lookup"><span data-stu-id="adf26-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="adf26-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="adf26-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="adf26-111">`false` - 可访问区域性数据</span><span class="sxs-lookup"><span data-stu-id="adf26-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="adf26-112">`true` - 以固定模式运行</span><span class="sxs-lookup"><span data-stu-id="adf26-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="adf26-113">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="adf26-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="adf26-114">`0` - 可访问区域性数据</span><span class="sxs-lookup"><span data-stu-id="adf26-114">`0` - access to cultural data</span></span><br/><span data-ttu-id="adf26-115">`1` - 以固定模式运行</span><span class="sxs-lookup"><span data-stu-id="adf26-115">`1` - run in invariant mode</span></span> |

## <a name="era-year-ranges"></a><span data-ttu-id="adf26-116">纪元年份范围</span><span class="sxs-lookup"><span data-stu-id="adf26-116">Era year ranges</span></span>

- <span data-ttu-id="adf26-117">确定是否放宽对支持多个纪元的日历的范围检查，或者超出纪元日期范围的日期是否引发 <xref:System.ArgumentOutOfRangeException>。</span><span class="sxs-lookup"><span data-stu-id="adf26-117">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="adf26-118">默认：放宽范围检查 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="adf26-118">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="adf26-119">有关详细信息，请参阅[日历、纪元和日期范围：放宽的范围检查](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks)。</span><span class="sxs-lookup"><span data-stu-id="adf26-119">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="adf26-120">设置名</span><span class="sxs-lookup"><span data-stu-id="adf26-120">Setting name</span></span> | <span data-ttu-id="adf26-121">值</span><span class="sxs-lookup"><span data-stu-id="adf26-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="adf26-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="adf26-122">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="adf26-123">`false` - 放宽的范围检查</span><span class="sxs-lookup"><span data-stu-id="adf26-123">`false` - relaxed range checks</span></span><br/><span data-ttu-id="adf26-124">`true` - 超出范围导致异常</span><span class="sxs-lookup"><span data-stu-id="adf26-124">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="adf26-125">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="adf26-125">**Environment variable**</span></span> | <span data-ttu-id="adf26-126">不可用</span><span class="sxs-lookup"><span data-stu-id="adf26-126">N/A</span></span> | <span data-ttu-id="adf26-127">不可用</span><span class="sxs-lookup"><span data-stu-id="adf26-127">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="adf26-128">日语日期分析</span><span class="sxs-lookup"><span data-stu-id="adf26-128">Japanese date parsing</span></span>

- <span data-ttu-id="adf26-129">确定是否成功分析包含“1”或“Gannen”作为年份的字符串，或是否仅支持“1”。</span><span class="sxs-lookup"><span data-stu-id="adf26-129">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="adf26-130">默认：分析包含“1”或“Gannen”作为年份的字符串 (`false`)。</span><span class="sxs-lookup"><span data-stu-id="adf26-130">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="adf26-131">有关详细信息，请参阅[用多个纪元表示日历中的日期](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)。</span><span class="sxs-lookup"><span data-stu-id="adf26-131">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="adf26-132">设置名</span><span class="sxs-lookup"><span data-stu-id="adf26-132">Setting name</span></span> | <span data-ttu-id="adf26-133">值</span><span class="sxs-lookup"><span data-stu-id="adf26-133">Values</span></span> |
| - | - | - |
| <span data-ttu-id="adf26-134">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="adf26-134">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="adf26-135">`false` - 支持“Gannen”或“1”</span><span class="sxs-lookup"><span data-stu-id="adf26-135">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="adf26-136">`true` - 仅支持“1”</span><span class="sxs-lookup"><span data-stu-id="adf26-136">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="adf26-137">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="adf26-137">**Environment variable**</span></span> | <span data-ttu-id="adf26-138">不可用</span><span class="sxs-lookup"><span data-stu-id="adf26-138">N/A</span></span> | <span data-ttu-id="adf26-139">不可用</span><span class="sxs-lookup"><span data-stu-id="adf26-139">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="adf26-140">日语年份格式</span><span class="sxs-lookup"><span data-stu-id="adf26-140">Japanese year format</span></span>

- <span data-ttu-id="adf26-141">确定是将日本历时代的第一年的格式设置为“Gannen”还是设置为一个数字。</span><span class="sxs-lookup"><span data-stu-id="adf26-141">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="adf26-142">默认：将第一年的格式设置为“Gannen”(`false`)。</span><span class="sxs-lookup"><span data-stu-id="adf26-142">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="adf26-143">有关详细信息，请参阅[用多个纪元表示日历中的日期](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)。</span><span class="sxs-lookup"><span data-stu-id="adf26-143">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="adf26-144">设置名</span><span class="sxs-lookup"><span data-stu-id="adf26-144">Setting name</span></span> | <span data-ttu-id="adf26-145">值</span><span class="sxs-lookup"><span data-stu-id="adf26-145">Values</span></span> |
| - | - | - |
| <span data-ttu-id="adf26-146">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="adf26-146">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="adf26-147">`false` - 将格式设置为“Gannen”</span><span class="sxs-lookup"><span data-stu-id="adf26-147">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="adf26-148">`true` - 将格式设置为数字</span><span class="sxs-lookup"><span data-stu-id="adf26-148">`true` - format as number</span></span> |
| <span data-ttu-id="adf26-149">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="adf26-149">**Environment variable**</span></span> | <span data-ttu-id="adf26-150">不可用</span><span class="sxs-lookup"><span data-stu-id="adf26-150">N/A</span></span> | <span data-ttu-id="adf26-151">不可用</span><span class="sxs-lookup"><span data-stu-id="adf26-151">N/A</span></span> |
