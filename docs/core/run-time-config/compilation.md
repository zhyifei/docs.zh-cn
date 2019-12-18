---
title: 编译配置设置
description: 了解用于为 .NET Core 应用配置 JIT 编译器工作原理的运行时设置。
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bcc445b6edc48d9432ee614b0b19c9c25621f4a0
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998875"
---
# <a name="run-time-configuration-options-for-compilation"></a>用于编译的运行时配置选项

## <a name="tiered-compilation"></a>分层编译

- 配置 JIT 编译器是否使用[分层编译](../whats-new/dotnet-core-3-0.md#tiered-compilation)。
- 在 NET Core 3.0 及更高版本中，默认情况下已启用分层编译。
- 在 NET Core 2.1 和 2.2 中，默认情况下已禁用分层编译。

| | 设置名 | 值 |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation` | `true` - 启用<br/>`false` - 禁用 |
| **环境变量** | `COMPlus_TieredCompilation` | `1` - 启用<br/>`0` - 禁用 |
