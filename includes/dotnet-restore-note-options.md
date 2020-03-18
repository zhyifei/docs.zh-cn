---
ms.openlocfilehash: 47811d3fab2e4fa531d383dfe818e3cac5613eb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "72179990"
---
> [!NOTE]
> 从 .NET Core 2.0 开始，无需运行 [`dotnet restore`](~/docs/core/tools/dotnet-restore.md)，因为它由所有需要还原的命令隐式运行，如 `dotnet build` 和 `dotnet run`。 在执行显式还原有意义的某些情况下，例如 [Azure DevOps Services 中的持续集成生成](/azure/devops/build-release/apps/aspnet/build-aspnet-core)中，或在需要显式控制还原发生时间的生成系统中，它仍然是有效的命令。
>
> 以长格式传递命令时，该命令也支持 `dotnet restore` 选项（例如，`--source`）。 不支持缩写选项，例如 `-s`。
