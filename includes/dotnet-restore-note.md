---
ms.openlocfilehash: e140b375f4f289df895052aa093f03f381d62488
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102732"
---
无需运行 [`dotnet restore`](~/docs/core/tools/dotnet-restore.md)，因为它由所有需要还原的命令隐式运行，如 `dotnet new`、`dotnet build`、`dotnet run`、`dotnet test`、`dotnet publish` 和 `dotnet pack`。 若要禁用隐式还原，请使用 `--no-restore` 选项。

在执行显式还原有意义的某些情况下，例如 [Azure DevOps Services 中的持续集成生成](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core)中，或在需要显式控制还原发生时间的生成系统中，`dotnet restore` 命令仍然有用。

有关如何使用 NuGet 源的信息，请参阅 [`dotnet restore` 文档](../docs/core/tools/dotnet-restore.md)。
