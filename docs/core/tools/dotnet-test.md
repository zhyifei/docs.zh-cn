---
title: "dotnet-test 命令 - .NET Core CLI | Microsoft Docs"
description: "`dotnet test` 命令用于执行给定项目中的单元测试。"
keywords: "dotnet-test, CLI, CLI 命令, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/25/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 4bf0aef4-148a-41c6-bb95-0a9e1af8762e
ms.translationtype: Human Translation
ms.sourcegitcommit: 3cc29c37879a3edafb05b482698393f521b6c3b3
ms.openlocfilehash: b4b0ac5a58fa37e5b39bcba262ba0fac443725e6
ms.contentlocale: zh-cn
ms.lasthandoff: 03/26/2017

---

#<a name="dotnet-test"></a>dotnet-test

## <a name="name"></a>名称

`dotnet-test` - 用于执行单元测试的 .NET 测试驱动程序。

## <a name="synopsis"></a>摘要

`dotnet test [<PROJECT>] [-s|--settings] [-t|--list-tests] [--filter] [-a|--test-adapter-path] [-l|--logger] [-c|--configuration] [-f|--framework] [-o|--output] [-d|--diag] [--no-build] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>描述

`dotnet test` 命令用于执行给定项目中的单元测试。 单元测试是控制台应用程序项目，它包含单元测试框架（如 MSTest、NUnit 或 xUnit）和该框架的 dotnet 测试运行程序上的依赖项。 单元测试打包为 NuGet 包并还原为该项目的普通依赖项。

测试项目还必须指定测试运行程序。 使用普通 `<PackageReference>` 元素指定，如下方示例项目文件所示：

[!code-xml[XUnit 基本模板](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="options"></a>选项

`PROJECT`
    
指定测试项目的路径。 如果省略，则默认为当前目录。

`-h|--help`

打印出有关命令的简短帮助。

`-s|--settings <SETTINGS_FILE>`

运行测试时要使用的设置。 

`-t|--list-tests`

列出当前项目中发现的所有测试。 

`--filter <EXPRESSION>`

使用给定表达式筛选掉当前项目中的测试。 有关筛选支持的详细信息，请参阅[使用 TestCaseFilter 在 Visual Studio 中运行选择性单元测试](https://aka.ms/vstest-filtering)。

`-a|--test-adapter-path <PATH_TO_ADAPTER>`

在测试运行中使用来自指定路径的自定义测试适配器。 

`-l|--logger <LoggerUri/FriendlyName>`

指定测试结果记录器。 

`-c|--configuration <CONFIGURATION>`

生成所根据的配置。 默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。

`-f|--framework <FRAMEWORK>`

查找特定[框架](../../standard/frameworks.md)的测试二进制文件。

`-o|--output <OUTPUT_DIRECTORY>`

查找要运行的二进制文件的目录。

`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`

启用测试平台的诊断模式，并将诊断消息写入指定文件。 

`--no-build` 

运行前不生成测试项目。

`-v|--verbosity <LEVEL>`

设置命令的详细级别。 允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。

## <a name="examples"></a>示例

运行当前目录所含项目中的测试：

`dotnet test` 

运行 `test1` 项目中的测试：

`dotnet test ~/projects/test1/test1.csproj` 

## <a name="see-also"></a>请参阅

* [目标框架](../../standard/frameworks.md)
* [运行时标识符 (RID) 目录](../rid-catalog.md)

