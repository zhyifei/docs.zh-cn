---
title: dotnet sln 命令 - .NET Core CLI
description: 使用 dotnet-sln 命令，可以便捷地在解决方案文件中添加、删除和列出项目。
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 845e666b9d8a8b206c7e1978a7dde9f33ffb8a32
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-sln"></a>dotnet sln

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet sln` - 修改 .NET Core 解决方案文件。

## <a name="synopsis"></a>摘要

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a>描述

使用 `dotnet sln` 命令，可以便捷地在解决方案文件中添加、删除和列出项目。

## <a name="commands"></a>命令

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

将一个或多个项目添加到解决方案文件中。 基于 Unix/Linux 的终端支持[通配模式](https://en.wikipedia.org/wiki/Glob_(programming))。

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

从解决方案文件中删除一个或多个项目。 基于 Unix/Linux 的终端支持[通配模式](https://en.wikipedia.org/wiki/Glob_(programming))。

`list`

列出解决方案文件中的所有项目。

## <a name="arguments"></a>自变量

`SOLUTION_NAME`

要使用的解决方案文件。 如果未指定，此命令会搜索当前目录来获取一个项目文件。 如果目录中有多个解决方案文件，必须指定一个。

## <a name="options"></a>选项

`-h|--help`

打印出有关命令的简短帮助。

## <a name="examples"></a>示例

将一个 C# 项目添加到解决方案中：

`dotnet sln todo.sln add todo-app/todo-app.csproj`

从解决方案中删除一个 C# 项目：

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

将多个 C# 项目添加到解决方案中：

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

从解决方案中删除多个 C# 项目：

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

使用通配模式将多个 C# 项目添加到解决方案中：

`dotnet sln todo.sln add **/*.csproj`

使用通配模式从解决方案中删除多个 C# 项目：

`dotnet sln todo.sln remove **/*.csproj`
