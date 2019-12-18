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
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="4051a-103">用于编译的运行时配置选项</span><span class="sxs-lookup"><span data-stu-id="4051a-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="4051a-104">分层编译</span><span class="sxs-lookup"><span data-stu-id="4051a-104">Tiered compilation</span></span>

- <span data-ttu-id="4051a-105">配置 JIT 编译器是否使用[分层编译](../whats-new/dotnet-core-3-0.md#tiered-compilation)。</span><span class="sxs-lookup"><span data-stu-id="4051a-105">Configures whether the JIT compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span>
- <span data-ttu-id="4051a-106">在 NET Core 3.0 及更高版本中，默认情况下已启用分层编译。</span><span class="sxs-lookup"><span data-stu-id="4051a-106">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="4051a-107">在 NET Core 2.1 和 2.2 中，默认情况下已禁用分层编译。</span><span class="sxs-lookup"><span data-stu-id="4051a-107">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>

| | <span data-ttu-id="4051a-108">设置名</span><span class="sxs-lookup"><span data-stu-id="4051a-108">Setting name</span></span> | <span data-ttu-id="4051a-109">值</span><span class="sxs-lookup"><span data-stu-id="4051a-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="4051a-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="4051a-110">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="4051a-111">`true` - 启用</span><span class="sxs-lookup"><span data-stu-id="4051a-111">`true` - enabled</span></span><br/><span data-ttu-id="4051a-112">`false` - 禁用</span><span class="sxs-lookup"><span data-stu-id="4051a-112">`false` - disabled</span></span> |
| <span data-ttu-id="4051a-113">**环境变量**</span><span class="sxs-lookup"><span data-stu-id="4051a-113">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="4051a-114">`1` - 启用</span><span class="sxs-lookup"><span data-stu-id="4051a-114">`1` - enabled</span></span><br/><span data-ttu-id="4051a-115">`0` - 禁用</span><span class="sxs-lookup"><span data-stu-id="4051a-115">`0` - disabled</span></span> |
