---
title: 调试分析配置设置
description: 了解为 .NET Core 应用配置调试和分析的运行时设置。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998857"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a>用于调试和分析的运行时配置选项

## <a name="enable-diagnostics"></a>启用诊断

- 配置是启用还是禁用调试器、探查器和 EventPipe 诊断。
- 默认：启用 (`1`)。

| | 设置名 | 值 |
| - | - | - |
| **runtimeconfig.json** | 不可用 | 不可用 |
| **环境变量** | `COMPlus_EnableDiagnostics` | `1` - 启用<br/>`0` - 禁用 |

## <a name="enable-profiling"></a>启用分析

- 配置是否为当前正在运行的进程启用分析。
- 默认：禁用 (`0`)。

| | 设置名 | 值 |
| - | - | - |
| **runtimeconfig.json** | 不可用 | 不可用 |
| **环境变量** | `CORECLR_ENABLE_PROFILING` | `0` - 禁用<br/>`1` - 启用 |

## <a name="profiler-guid"></a>探查器 GUID

- 指定要加载到当前正在运行的进程中的探查器 GUID。

| | 设置名 | 值 |
| - | - | - |
| **runtimeconfig.json** | 不可用 | 不可用 |
| **环境变量** | `CORECLR_PROFILER` | string-guid  |

## <a name="profiler-location"></a>探查器位置

- 指定要加载到当前正在运行的进程（或 32 位/64 位进程）的探查器 DLL 路径。
- 如果设置了多个变量，则优先使用指定位数的变量。 它们指定要加载的探查器的位数。
- 有关详细信息，请参阅 [Finding the profiler library](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md)（查找探查器库）。

| | 设置名 | 值 |
| - | - | - |
| **环境变量** | `CORECLR_PROFILER_PATH` | string-path  |
| **环境变量** | `CORECLR_PROFILER_PATH_32` | string-path  |
| **环境变量** | `CORECLR_PROFILER_PATH_64` | string-path  |

## <a name="write-perf-map"></a>写入 Perf 映射

- 允许或禁止在 Linux 系统上写入 /tmp/perf-$pid.map  。
- 默认：禁用 (`0`)。

| | 设置名 | 值 |
| - | - | - |
| **runtimeconfig.json** | 不可用 | 不可用 |
| **环境变量** | `COMPlus_PerfMapEnabled` | `0` - 禁用<br/>`1` - 启用 |

## <a name="perf-log-markers"></a>性能日志标记

- 将 `COMPlus_PerfMapEnabled` 设置为 `1` 时，允许或禁止以性能日志中的标记接受和忽略指定信号。
- 默认：禁用 (`0`)。

| | 设置名 | 值 |
| - | - | - |
| **runtimeconfig.json** | 不可用 | 不可用 |
| **环境变量** | `COMPlus_PerfMapIgnoreSignal` | `0` - 禁用<br/>`1` - 启用 |
