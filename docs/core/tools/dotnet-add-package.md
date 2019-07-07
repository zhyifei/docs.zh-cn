---
title: dotnet add package 命令
description: “dotnet add package”命令可便于添加对项目的 NuGet 包引用。
ms.date: 06/26/2019
ms.openlocfilehash: 50a352be66f2b4bd4498d79f61dc01f56d4b00c5
ms.sourcegitcommit: 4a3c95e91289d16c38979575a245a4f76b0da147
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/05/2019
ms.locfileid: "67569502"
---
# <a name="dotnet-add-package"></a>dotnet add package

**本文适用于：✓** .NET Core 1.x SDK 及更高版本

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet add package` - 向项目文件添加包引用。

## <a name="synopsis"></a>摘要

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [--interactive] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a>说明

使用 `dotnet add package` 命令可方便地向项目文件添加包引用。 运行该命令后，还有一个兼容性检查，确保包与项目中的框架兼容。 如果通过了该检查，则将 `<PackageReference>` 元素添加到项目文件并运行 [dotnet 还原](dotnet-restore.md)。

[!INCLUDE[DotNet Restore Note](../../../includes/dotnet-restore-note.md)]

例如，将 `Newtonsoft.Json` 添加到 ToDo.csproj  后的输出如以下示例所示：

```console
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\Temp\projects\consoleproj\consoleproj.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 79ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/12.0.1/newtonsoft.json.12.0.1.nupkg 232ms
log  : Installing Newtonsoft.Json 12.0.1.
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '12.0.1' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

*ToDo.csproj* 文件现包含用于引用的包的 [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 元素。

```xml
<PackageReference Include="Newtonsoft.Json" Version="12.0.1" />
```

## <a name="arguments"></a>自变量

* **`PROJECT`**

  指定项目文件。 如果未指定，此命令会搜索当前目录来获取一个项目文件。

* **`PACKAGE_NAME`**

  要添加的包引用。

## <a name="options"></a>选项

* **`-f|--framework <FRAMEWORK>`**

  仅在以特定[框架](../../standard/frameworks.md)为目标时添加包引用。

* **`-h|--help`**

  打印出有关命令的简短帮助。

* **`--interactive`**

  允许命令停止并等待用户输入或操作（例如，完成身份验证）。 从 .NET Core 2.1 SDK，版本 2.1.400 或更高版本开始可用。

* **`-n|--no-restore`**

  在不执行还原预览和兼容性检查的情况下添加包引用。

* **`--package-directory <PACKAGE_DIRECTORY>`**

  要在其中还原包的目录。 Windows 上的默认包还原位置为 `%userprofile%\.nuget\packages`，macOS 和 Linux 上的默认包还原位置为 `~/.nuget/packages`。 有关详细信息，请参阅[在 NuGet 中管理全局包、缓存和临时文件夹](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders)。

* **`-s|--source <SOURCE>`**

  要在还原操作期间使用的 NuGet 包源。

* **`-v|--version <VERSION>`**

  包的版本。 请参阅 [NuGet 包版本控制](https://docs.microsoft.com/nuget/reference/package-versioning)。

## <a name="examples"></a>示例

* 将 `Newtonsoft.Json` NuGet 包添加到项目：

  ```console
  dotnet add package Newtonsoft.Json
  ```

* 向项目添加特定版本的包：

  ```console
  dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0
  ```

* 使用特定的 NuGet 源添加包：

  ```console
  dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json
  ```

## <a name="see-also"></a>请参阅

- [在 NuGet 中管理全局包、缓存和临时文件夹](https://docs.microsoft.com/nuget/consume-packages/managing-the-global-packages-and-cache-folders)
- [NuGet 包版本控制](https://docs.microsoft.com/nuget/reference/package-versioning)
