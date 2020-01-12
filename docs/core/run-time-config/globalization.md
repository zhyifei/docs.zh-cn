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
# <a name="run-time-configuration-options-for-globalization"></a>用于全球化的运行时配置选项

## <a name="invariant-mode"></a>固定模式

- 确定 .NET Core 应用是否以全球化固定模式运行而无权访问特定区域性的数据和行为，或者是否有权访问区域性数据。
- 默认：运行应用并可访问区域性数据 (`false`)。
- 有关详细信息，请参阅 [.NET Core 全球化固定模式](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)。

| | 设置名 | 值 |
| - | - | - |
| **runtimeconfig.json** | `System.Globalization.Invariant` | `false` - 可访问区域性数据<br/>`true` - 以固定模式运行 |
| **环境变量** | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | `0` - 可访问区域性数据<br/>`1` - 以固定模式运行 |

## <a name="era-year-ranges"></a>纪元年份范围

- 确定是否放宽对支持多个纪元的日历的范围检查，或者超出纪元日期范围的日期是否引发 <xref:System.ArgumentOutOfRangeException>。
- 默认：放宽范围检查 (`false`)。
- 有关详细信息，请参阅[日历、纪元和日期范围：放宽的范围检查](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks)。

| | 设置名 | 值 |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | `false` - 放宽的范围检查<br/>`true` - 超出范围导致异常 |
| **环境变量** | 不可用 | 不可用 |

## <a name="japanese-date-parsing"></a>日语日期分析

- 确定是否成功分析包含“1”或“Gannen”作为年份的字符串，或是否仅支持“1”。
- 默认：分析包含“1”或“Gannen”作为年份的字符串 (`false`)。
- 有关详细信息，请参阅[用多个纪元表示日历中的日期](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)。

| | 设置名 | 值 |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | `false` - 支持“Gannen”或“1”<br/>`true` - 仅支持“1” |
| **环境变量** | 不可用 | 不可用 |

## <a name="japanese-year-format"></a>日语年份格式

- 确定是将日本历时代的第一年的格式设置为“Gannen”还是设置为一个数字。
- 默认：将第一年的格式设置为“Gannen”(`false`)。
- 有关详细信息，请参阅[用多个纪元表示日历中的日期](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras)。

| | 设置名 | 值 |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | `false` - 将格式设置为“Gannen”<br/>`true` - 将格式设置为数字 |
| **环境变量** | 不可用 | 不可用 |
