---
title: dotnet sln 命令
description: 使用 dotnet-sln 命令，可以便捷地在解决方案文件中添加、删除和列出项目。
ms.date: 10/29/2019
ms.openlocfilehash: 18702c7638798117bd04d5c6a829d64cc6bf18a8
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73191819"
---
# <a name="dotnet-sln"></a>dotnet sln

**本文适用于：✓** .NET Core 1.x SDK 及更高版本

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>name

`dotnet sln` - 修改 .NET Core 解决方案文件。

## <a name="synopsis"></a>摘要

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a>说明

使用 `dotnet sln` 命令，可以便捷地在解决方案文件中添加、删除和列出项目。

若要使用 `dotnet sln` 命令，必须存在解决方案文件。 如果需要创建一个解决方案文件，请使用 [dotnet new](dotnet-new.md) 命令，如下例所示：

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a>自变量

- **`SOLUTION_FILE`**

  要使用的解决方案文件。 如果未指定，此命令会搜索当前目录来获取一个项目文件。 如果目录中有多个解决方案文件，必须指定一个。

## <a name="options"></a>选项

- **`-h|--help`**

  打印出有关命令的简短帮助。

## <a name="commands"></a>命令

### `add`

将一个或多个项目添加到解决方案文件中。

#### <a name="synopsis"></a>摘要

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH>
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a>自变量

- **`SOLUTION_FILE`**

  要使用的解决方案文件。 如果未指定，此命令会搜索当前目录来获取一个项目文件。 如果目录中有多个解决方案文件，必须指定一个。

- **`PROJECT_PATH`**

  要添加到解决方案的项目的路径。 通过用空格将项目彼此隔开，可以添加多个项目。 Unix/Linux shell [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))扩展由 `dotnet sln` 命令正确处理。

#### <a name="options"></a>选项

- **`-h|--help`**

  打印出有关命令的简短帮助。

- **`--in-root`**

  将项目放在解决方案的根目录下，而不是创建解决方案文件夹。 自 .NET Core 3.0 SDK 起可用。

- **`-s|--solution-folder`**

  要将项目添加到的目标解决方案文件夹路径。 自 .NET Core 3.0 SDK 起可用。

### `remove`

从解决方案文件中删除一个或多个项目。

#### <a name="synopsis"></a>摘要

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH>
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a>自变量

- **`SOLUTION_FILE`**

  要使用的解决方案文件。 如果未指定，此命令会搜索当前目录来获取一个项目文件。 如果目录中有多个解决方案文件，必须指定一个。

- **`PROJECT_PATH`**

  要从解决方案中删除的项目路径。 通过用空格将项目彼此隔开，可以删除多个项目。 Unix/Linux shell [glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))扩展由 `dotnet sln` 命令正确处理。

#### <a name="options"></a>选项

- **`-h|--help`**

  打印出有关命令的简短帮助。

### `list`

列出解决方案文件中的所有项目。

#### <a name="synopsis"></a>摘要

```dotnetcli
dotnet sln list [-h|--help]
```
  
#### <a name="arguments"></a>自变量

- **`SOLUTION_FILE`**

  要使用的解决方案文件。 如果未指定，此命令会搜索当前目录来获取一个项目文件。 如果目录中有多个解决方案文件，必须指定一个。

#### <a name="options"></a>选项

- **`-h|--help`**

  打印出有关命令的简短帮助。

## <a name="examples"></a>示例

将一个 C# 项目添加到解决方案中：

```dotnetcli
dotnet sln todo.sln add todo-app/todo-app.csproj
```

从解决方案中删除一个 C# 项目：

```dotnetcli
dotnet sln todo.sln remove todo-app/todo-app.csproj
```

将多个 C# 项目添加到解决方案中：

```dotnetcli
dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
```

从解决方案中删除多个 C# 项目：

```dotnetcli
dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
```

使用 glob 模式（仅限 Unix/Linux）将多个 C# 项目添加到解决方案中：

```dotnetcli
dotnet sln todo.sln add **/*.csproj
```

使用 glob 模式（仅限 Unix/Linux）将多个 C# 项目从解决方案中删除：

```dotnetcli
dotnet sln todo.sln remove **/*.csproj
```
