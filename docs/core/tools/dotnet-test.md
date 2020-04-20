---
title: dotnet test 命令
description: dotnet test 命令可用于在给定项目中执行单元测试。
ms.date: 02/27/2020
ms.openlocfilehash: f9df03cda01bdaf649394a58e96903e764193338
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463378"
---
# <a name="dotnet-test"></a>dotnet test

 本文适用于： ✔️ .NET Core 2.1 SDK 及更高版本

## <a name="name"></a>“属性”

`dotnet test` - 用于执行单元测试的 .NET 测试驱动程序。

## <a name="synopsis"></a>摘要

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION>]
    [-a|--test-adapter-path <PATH_TO_ADAPTER>] [--blame]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_FRIENDLY_NAME>]
    [-d|--diag <PATH_TO_DIAGNOSTICS_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER_URI/FRIENDLY_NAME>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <PATH>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a>描述

`dotnet test` 命令用于执行给定项目中的单元测试。 `dotnet test` 命令启动为项目指定的测试运行程序控制台应用程序。 测试运行程序执行为单元测试框架（例如 MSTest、NUnit 或 xUnit）定义的测试，并报告每个测试是否成功。 如果所有测试均成功，测试运行程序将返回 0 作为退出代码；否则将返回 1。 测试运行程序和单元测试库打包为 NuGet 包并还原为该项目的普通依赖项。

测试项目使用普通 `<PackageReference>` 元素指定测试运行程序，如下方示例项目文件所示：

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

## <a name="arguments"></a>自变量

- **`PROJECT | SOLUTION`**

  测试项目或解决方案的路径。 如未指定，则默认为当前目录。

## <a name="options"></a>选项

- **`a|--test-adapter-path <PATH_TO_ADAPTER>`**

  在测试运行中使用来自指定路径的自定义测试适配器。

- **`--blame`**

  在意见模式中运行测试。 此选项有助于隔离导致测试主机出现故障的有问题的测试。 它会在当前目录中创建一个输出文件 (Sequence.xml)，其中捕获了故障前的测试执行顺序  。

- **`c|--configuration <CONFIGURATION>`**

  定义生成配置。 默认值为 `Debug`，但项目配置可以替代此默认 SDK 设置。

- **`-collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  为测试运行启用数据收集器。 有关详细信息，请参阅[监视和分析测试运行](https://aka.ms/vstest-collect)。

- **`d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  启用测试平台的诊断模式，并将诊断消息写入指定文件。

- **`f|--framework <FRAMEWORK>`**

  查找特定[框架](../../standard/frameworks.md)的测试二进制文件。

- **`--filter <EXPRESSION>`**

  使用给定表达式筛选掉当前项目中的测试。 有关详细信息，请参阅[筛选选项详细信息](#filter-option-details)部分。 若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。

- **`h|--help`**

  打印出有关命令的简短帮助。

- **`--interactive`**

  允许命令停止并等待用户输入或操作。 例如，完成身份验证。 自 .NET Core 3.0 SDK 起可用。

- **`l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  指定测试结果记录器。 与 MSBuild 不同，dotnet 测试不接受缩写，应使用 `-l "console;verbosity=detailed"`，而不使用 `-l "console;v=d"`。

- **`--no-build`**

  不在运行测试项目之前生成它。 还将隐式设置 - `--no-restore` 标记。

- **`--nologo`**

  运行测试，而不显示 Microsoft TestPlatform 横幅。 自 .NET Core 3.0 SDK 起可用。

- **`--no-restore`**

  运行此命令时不执行隐式还原。

- **`-o|--output <OUTPUT_DIRECTORY>`**

  查找要运行的二进制文件的目录。

- **`-r|--results-directory <PATH>`**

  用于放置测试结果的目录。 如果指定的目录不存在，则会创建该目录。

- **`--runtime <RUNTIME_IDENTIFIER>`**

  要针对其测试的目标运行时。

- **`-s|--settings <SETTINGS_FILE>`**

  `.runsettings` 文件用于运行测试。 [使用 `.runsettings` 文件配置单元测试。](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)

- **`-t|--list-tests`**

  列出当前项目中发现的所有测试。

- **`-v|--verbosity <LEVEL>`**

  设置命令的详细级别。 允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。 默认值为 `minimal`。 有关详细信息，请参阅 <xref:Microsoft.Build.Framework.LoggerVerbosity>。

- `RunSettings` 参数

  参数在测试中作为 `RunSettings` 配置传递。 参数在“-- ”（注意 -- 后的空格）后被指定为 `[name]=[value]` 对。 空格用于分隔多个 `[name]=[value]` 对。

  示例：`dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`

  有关详细信息，请参阅 [vstest.console.exe：传递 RunSettings 参数](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)。

## <a name="examples"></a>示例

- 运行当前目录所含项目中的测试：

  ```dotnetcli
  dotnet test
  ```

- 运行 `test1` 项目中的测试：

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- 在当前目录运行项目中的测试，并以 trx 格式生成测试结果文件：

  ```dotnetcli
  dotnet test --logger trx
  ```

- 在当前目录中运行项目中的测试，并将详细的测试结果记录到控制台：

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```

## <a name="filter-option-details"></a>筛选选项详细信息

`--filter <EXPRESSION>`

`<Expression>` 格式为 `<property><operator><value>[|&<Expression>]`。

`<property>` 是 `Test Case` 的特性。 下面介绍了常用单元测试框架支持的属性：

| 测试框架 | 支持的属性                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>“属性”</li><li>ClassName</li><li>Priority</li><li>TestCategory</li></ul> |
| xUnit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Traits</li></ul>                                   |

`<operator>` 说明了属性和值之间的关系：

| 运算符 | 函数        |
| :------: | --------------- |
| `=`      | 完全匹配     |
| `!=`     | 非完全匹配 |
| `~`      | 包含        |
| `!~`     | 不包含    |

`<value>` 是字符串。 所有查找都不区分大小写。

不含 `<operator>` 的表达式自动被视为 `FullyQualifiedName` 属性上的 `contains`（例如，`dotnet test --filter xyz` 与 `dotnet test --filter FullyQualifiedName~xyz` 相同）。

表达式可与条件运算符结合使用：

| 运算符            | 函数 |
| ------------------- | -------- |
| <code>&#124;</code> | 或       |
| `&`                 | AND      |

使用条件运算符时，可以用括号将表达式括起来（例如，`(Name~TestMethod1) | (Name~TestMethod2)`）。

若要获取使用选择性单元测试筛选的其他信息和示例，请参阅[运行选择性单元测试](../testing/selective-unit-tests.md)。

## <a name="see-also"></a>请参阅

- [框架和目标](../../standard/frameworks.md)
- [.NET Core 运行时标识符 (RID) 目录](../rid-catalog.md)
- [通过命令行传递 runsettings 参数](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
