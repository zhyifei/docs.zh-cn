---
title: .NET Core CLI
titleSuffix: ''
description: .NET Core CLI 及其功能概述。
ms.date: 08/14/2017
ms.openlocfilehash: b0a8e0dd8cf77bb6f7567c27e9972f62515ec0f2
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920485"
---
# <a name="net-core-cli-overview"></a>.NET Core CLI 概述

.NET Core 命令行接口 (CLI) 工具是用于开发、生成、运行和发布 .NET Core 应用程序的跨平台工具链。

.NET Core CLI 包含在 [.NET Core SDK](../sdk.md) 中。 若要了解如何安装 .NET Core SDK，请参阅[安装 .NET Core SDK](../install/sdk.md)。

## <a name="cli-commands"></a>CLI 命令

默认安装以下命令：

<!-- markdownlint-disable MD025 -->

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**基本命令**

- [new](dotnet-new.md)
- [restore](dotnet-restore.md)
- [build](dotnet-build.md)
- [publish](dotnet-publish.md)
- [run](dotnet-run.md)
- [test](dotnet-test.md)
- [vstest](dotnet-vstest.md)
- [pack](dotnet-pack.md)
- [migrate](dotnet-migrate.md)
- [clean](dotnet-clean.md)
- [sln](dotnet-sln.md)
- [help](dotnet-help.md)
- [store](dotnet-store.md)

**项目修改命令**

- [add package](dotnet-add-package.md)
- [add reference](dotnet-add-reference.md)
- [remove package](dotnet-remove-package.md)
- [remove reference](dotnet-remove-reference.md)
- [list reference](dotnet-list-reference.md)

**高级命令**

- [nuget delete](dotnet-nuget-delete.md)
- [nuget locals](dotnet-nuget-locals.md)
- [nuget push](dotnet-nuget-push.md)
- [msbuild](dotnet-msbuild.md)
- [dotnet install script](dotnet-install-script.md)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**基本命令**

- [new](dotnet-new.md)
- [restore](dotnet-restore.md)
- [build](dotnet-build.md)
- [publish](dotnet-publish.md)
- [run](dotnet-run.md)
- [test](dotnet-test.md)
- [vstest](dotnet-vstest.md)
- [pack](dotnet-pack.md)
- [migrate](dotnet-migrate.md)
- [clean](dotnet-clean.md)
- [sln](dotnet-sln.md)

**项目修改命令**

- [add package](dotnet-add-package.md)
- [add reference](dotnet-add-reference.md)
- [remove package](dotnet-remove-package.md)
- [remove reference](dotnet-remove-reference.md)
- [list reference](dotnet-list-reference.md)

**高级命令**

- [nuget delete](dotnet-nuget-delete.md)
- [nuget locals](dotnet-nuget-locals.md)
- [nuget push](dotnet-nuget-push.md)
- [msbuild](dotnet-msbuild.md)
- [dotnet install script](dotnet-install-script.md)

---

CLI 采用可使你为项目指定其他工具的扩展性模型。 有关详细信息，请参阅 [.NET Core CLI 扩展性模型](extensibility.md)主题。

## <a name="command-structure"></a>命令结构

CLI 命令结构包含[驱动程序（“dotnet”）](#driver)和[命令](#command)，还可能包含命令[参数](#arguments)和[选项](#options)。 在大部分 CLI 操作中可看到此模式，例如创建新控制台应用并从命令行运行该应用，因为从名为 *my_app* 的目录中执行时，显示以下命令：

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```dotnetcli
dotnet new console
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```dotnetcli
dotnet new console
dotnet restore
dotnet build --output /build_output
dotnet /build_output/my_app.dll
```

---

### <a name="driver"></a>驱动程序

驱动程序名为 [dotnet](dotnet.md)，并具有两项职责，即运行[依赖于框架的应用](../deploying/index.md)或执行命令。 

若要运行依赖于框架的应用，请在驱动程序后指定应用，例如，`dotnet /path/to/my_app.dll`。 从应用的 DLL 驻留的文件夹执行命令时，只需执行 `dotnet my_app.dll` 即可。 如果要使用特定版本的 .NET Core 运行时，请使用 `--fx-version <VERSION>` 选项（请参阅 [dotnet 命令](dotnet.md)参考）。

为驱动程序提供命令时，`dotnet.exe` 启动 CLI 命令执行过程。 例如：

```dotnetcli
dotnet build
```

首先，驱动程序确定要使用的 SDK 版本。 如果没有任何[“global.json”](global-json.md)，则使用可用的最新版本 SDK。 这有可能是预览版或稳定版，具体取决于计算机上的最新版本。  确定 SDK 版本后，它便会执行命令。

### <a name="command"></a>命令

由命令执行操作。 例如，`dotnet build` 生成代码。 `dotnet publish` 发布代码。 使用 `dotnet {command}` 约定将命令作为控制台应用程序实现。

### <a name="arguments"></a>自变量

在命令行上传递的参数是被调用的命令的参数。 例如，执行 `dotnet publish my_app.csproj` 时，`my_app.csproj` 参数指示要发布的项目，并被传递到 `publish` 命令。

### <a name="options"></a>选项

在命令行上传递的选项是被调用的命令的选项。 例如，执行 `dotnet publish --output /build_output` 时，`--output` 选项及其值被传递到 `publish` 命令。

## <a name="migration-from-projectjson"></a>从 project.json 迁移

如果使用预览版 2 工具生成基于 *project.json* 的项目，请查阅 [dotnet 迁移](dotnet-migrate.md)主题，了解将你的项目迁移到 MSBuild/ *.csproj* 以使用版本工具的信息。 对于预览版 2 工具发布之前所创建的 .NET Core 项目，请按照[从 DNX 迁移到 .NET Core CLI (project.json)](../migration/from-dnx.md) 中的指南手动更新项目，然后使用 `dotnet migrate` 或直接升级项目。

## <a name="see-also"></a>请参阅

- [dotnet/sdk GitHub 存储库](https://github.com/dotnet/sdk/)
- [.NET Core 安装指南](https://aka.ms/dotnetcoregs)
