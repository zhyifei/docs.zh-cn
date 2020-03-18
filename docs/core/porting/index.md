---
title: 从 .NET Framework 移植到 .NET Core
description: 了解移植过程以及发现在将 .NET Framework 项目移植到 .NET Core 时可能有用的工具。
author: cartermp
ms.date: 10/22/2019
ms.openlocfilehash: e483bb6e48dad6c3bf71bfa81e704a137fc02094
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "75937321"
---
# <a name="overview-of-porting-from-net-framework-to-net-core"></a>从 .NET Framework 移植到 .NET Core 的概述

你可能有些代码当前正在 .NET Framework 上运行，但你想将这些代码移植到 .NET Core。 本文提供以下内容：

* 移植过程概述。
* 在将代码移植到 .NET Core 时，可能会发现一系列有用的工具。

## <a name="overview-of-the-porting-process"></a>移植过程概述

建议在将项目移植到 .NET Core 时使用以下过程：

1. 将希望移植的所有项目重定向到目标 .NET Framework 4.7.2 或更高版本。

   此步骤可确保在 .NET Core 不支持特殊 API 的情况下，可以为特定于 .NET Framework 的目标使用备用 API。

2. 使用 [.NET 可移植性分析器](../../standard/analyzers/portability-analyzer.md)来分析程序集，并查看这些程序集是否可移植到 .NET Core。

   API 可移植性分析器工具可分析已编译的程序集并生成报表。 此报表显示高级别可移植性摘要，以及你所使用的不适用于 NET Core 的各个 API 细目。

3. 将 [.NET API 分析器](../../standard/analyzers/api-analyzer.md)安装到项目中，以识别在某些平台上会引发 <xref:System.PlatformNotSupportedException> 的 API 以及一些其他潜在的兼容性问题。

   此工具与可移植性分析器类似，但它不会分析是否可以在 .NET Core 上构建代码，而是分析你是否正在以会导致在运行时引发 <xref:System.PlatformNotSupportedException> 的某种方式使用 API。 尽管这并不常见，但如果从 .NET Framework 4.7.2 或更高版本进行移动，最好进行检查。 如需详细了解会在 .NET Core 上引发异常的 API 信息，请参阅[在 .NET Core上始终引发异常的 API](../compatibility/unsupported-apis.md)。

4. 通过 `packages.config`Visual Studio 中的转换工具[将所有 ](/nuget/consume-packages/package-references-in-project-files) 依赖项转换为 [PackageReference](/nuget/consume-packages/migrate-packages-config-to-package-reference) 格式。

   此步骤涉及到转换旧 `packages.config` 格式的依赖项。 `packages.config` 不适用于 .NET Core，因此，如果你有包依赖项，则需要进行此转换。

5. 为 .NET Core 创建新项目并覆盖源文件，或尝试使用工具转换现有的项目文件。

   .NET Core 使用不同于 .NET Framework 的更简化的[项目文件格式](../tools/csproj.md)。 需要将项目文件转换为此格式才能继续操作。

6. 移植测试代码。

   由于移植到 .NET Core 对代码库来说是很大的更改，因此强烈建议移植测试项目，以便在移植代码后运行测试。 MSTest、xUnit 和 NUnit 都适用于 .NET Core。

此外，可以尝试使用 [dotnet try-convert](https://github.com/dotnet/try-convert) 工具通过一次操作将较小的解决方案或单个项目移植到 .NET Core 项目文件格式。 不能保证 `dotnet try-convert` 适用于所有项目，它可能导致所依赖的行为发生细微变化。 使用它作为起点  ，以自动化可自动执行的基本操作。 作为用于迁移项目的一种解决方案，它并不是万无一失的。

## <a name="next-steps"></a>后续步骤

>[!div class="nextstepaction"]
>[分析依赖项](third-party-deps.md)
