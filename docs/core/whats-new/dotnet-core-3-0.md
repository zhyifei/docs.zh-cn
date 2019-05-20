---
title: .NET Core 3.0 的新增功能
description: 了解 .NET Core 3.0 的新增功能。
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 05/06/2019
ms.openlocfilehash: 8d6ff6bc55384281119600f2323212441c1815e9
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452483"
---
# <a name="whats-new-in-net-core-30-preview-5"></a>.NET Core 3.0（预览版 5）的新增功能

本文介绍 .NET Core 3.0（通过预览版 5）的新增功能。 最大的增强功能之一是对 Windows 桌面应用程序（仅限 Windows）的支持。 通过使用 .NET Core 3.0 SDK 组件 Windows 桌面，可以移植 Windows 窗体和 Windows Presentation Foundation (WPF) 应用程序。 为清楚起见，Windows 桌面组件仅在 Windows 上受支持，且仅在 Windows 中包含。 有关详细信息，请参阅本文后面的 [Windows 桌面](#windows-desktop)部分。

.NET Core 3.0 添加了对 C#8.0 的支持。 强烈建议使用最新版本的 Visual Studio 2019 Update 1 预览版或带有 OmniSharp 扩展的 VSCode。

立即在 Windows、Mac 和 Linux 上[下载并开始使用 .NET Core 3.0 预览版 5](https://aka.ms/netcore3download)。

有关每个预览版本的详细信息，请参阅以下公告：

- [.NET Core 3.0 预览版 5 公告](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0-preview-5/)
- [.NET Core 3.0 预览版 4 公告](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-4/)
- [.NET Core 3.0 预览版 3 公告](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-3/)
- [.NET Core 3.0 预览版 2 公告](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)
- [.NET Core 3.0 预览版 1 公告](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)

## <a name="net-core-sdk-windows-installer"></a>.NET Core SDK Windows Installer

用于 Windows 的 MSI 安装程序已从 .NET Core 3.0 开始更改。 SDK 安装程序现在将对 SDK 功能区段版本进行就地升级。 功能区段在版本号的*补丁*部分中的*数百个*组中定义。 例如，**3.0.*101*** 和 **3.0.*201*** 是两个不同功能区段中的版本，而 **3.0.*101*** 和 **3.0.*199*** 则属于同一个功能区段。 并且，当安装 .NET Core SDK **3.0.*101*** 时，将从计算机中删除 .NET Core SDK **3.0.*100***（如果存在）。 当 .NET Core SDK **3.0.*200*** 安装在同一台计算机上时，不会删除 .NET Core SDK **3.0.*101***。

有关版本控制的详细信息，请参阅 [.NET Core 的版本控制方式概述](../versions/index.md)。

## <a name="c-80-preview"></a>C# 8.0 预览版

.NET Core 3.0 支持 C# 8 预览版。 有关 C# 8.0 功能的详细信息，请参阅 [C# 8.0 中的新增功能](../../csharp/whats-new/csharp-8.md)。

## <a name="net-standard-21"></a>.NET Standard 2.1

尽管 .NET Core 3.0 支持 **.NET Standard 2.1**，默认的 `dotnet new classlib` 模板还是会生成一个面向 **.NET Standard 2.0** 的项目。 若要面向 **.NET Standard 2.1**，请编辑项目文件并将 `TargetFramework` 属性更改为 `netstandard2.1`：

```xml
<Project Sdk="Microsoft.NET.Sdk">
 
  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>
 
</Project>
```

如果使用 Visual Studio，则需要 Visual Studio 2019，因为 Visual Studio 2017 不支持 **.NET Standard 2.1** 或 **.NET Core 3.0**。 我们强烈建议你使用 [Visual Studio 2019 Update 1 预览版](https://visualstudio.microsoft.com/vs/preview/)。

## <a name="improved-net-core-version-apis"></a>改进的 .NET Core 版本 API

从 .NET Core 3.0 开始，.NET Core 提供的版本 API 现在可以返回你预期的信息。 例如:

```csharp
System.Console.WriteLine($"Environment.Version: {System.Environment.Version}");

// Old result
//   Environment.Version: 4.0.30319.42000
//
// New result
//   Environment.Version: 3.0.0
```

```csharp
System.Console.WriteLine($"RuntimeInformation.FrameworkDescription: {System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription}");

// Old result
//   RuntimeInformation.FrameworkDescription: .NET Core 4.6.27415.71
//
// New result
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> 重大更改。 这在技术上是一个突破性的改变，因为版本控制方案已发生变化。

## <a name="net-platform-dependent-intrinsics"></a>依赖于 .NET 平台的内部函数

已添加 API，允许访问某些性能导向的 CPU 指令，例如 SIMD 或位操作指令集。 这些指令有助于在某些情况下实现显著的性能改进，例如高效地并行处理数据。 

在适当的情况下，.NET 库已开始使用这些指令来改进性能。

有关详细信息，请参阅 [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md)（依赖于 .NET 平台的内部函数）。

## <a name="default-executables"></a>默认可执行文件

.NET Core 现在默认生成[依赖于框架的可执行文件](../deploying/index.md#framework-dependent-executables-fde)。 对于使用全局安装的 .NET Core 版本的应用程序而言，这是一种新行为。 以前，仅[独立部署](../deploying/index.md#self-contained-deployments-scd)会生成可执行文件。

在 `dotnet build` 或 `dotnet publish` 期间，将创建一个与你使用的 SDK 的环境和平台相匹配的可执行文件。 和其他本机可执行文件一样，可以使用这些可执行文件执行相同操作，例如：

* 可以双击可执行文件。
* 可以直接从命令提示符启用应用程序，如 Windows 上的 `myapp.exe`，以及 Linux 和 macOS 上的 `./myapp`。

## <a name="single-file-executables"></a>单文件可执行文件

`dotnet publish` 命令支持将应用打包为特定于平台的单文件可执行文件。 该可执行文件是自提取文件，包含运行应用所需的所有依赖项（包括本机依赖项）。 首次运行应用时，应用程序将根据应用名称和生成标识符提取到目录中。 再次运行应用程序时，启动速度将变快。 除非使用新版本，否则应用程序不需要第二次提取自身。

若要发布单文件可执行文件，请使用 `dotnet publish` 命令在项目或命令行中设置 `PublishSingleFile`：

```console
dotnet publish -r win10-x64 /p:PublishSingleFile=true
```

有关单文件发布的详细信息，请参阅[单文件捆绑程序设计文档](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md)。

## <a name="tiered-compilation"></a>分层编译

.NET Core 3.0 中默认启用了[分层编译](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) (TC)。 此功能使运行时能够更适应地使用实时 (JIT) 编译器来获得更好的性能。

TC 的主要优势是使（重新）实时编译方法能够牺牲代码质量，更快地生成代码，或者以较慢的速度生成更高质量的代码。 这有助于提高应用程序在从启动到稳定状态的各个执行阶段的性能。 这与非 TC 方法完全不同，其中每种方法均以单一方式进行编译（与高质量层相同），这种方法偏向于稳定状态而不是启动性能。

若要启用快速 JIT（第 0 层实时编译的代码），请在项目文件中使用此设置：

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>true</TieredCompilationQuickJit>
</PropertyGroup>
```

若要完全禁用 TC，请在项目文件中使用此设置：

```xml
<TieredCompilation>false</TieredCompilation>
```

## <a name="build-copies-dependencies"></a>生成副本依赖项

`dotnet build` 命令现在将应用程序的 NuGet 依赖项从 NuGet 缓存复制到生成输出文件夹。 此前，依赖项仅作为 `dotnet publish` 的一部分复制。

有些操作，比如链接和 razor 页面发布仍需要发布。

## <a name="local-tools"></a>本地工具

.NET Core 3.0 引入了本地工具。 本地工具类似于[全局工具](../tools/global-tools.md)，但与磁盘上的特定位置相关联。 本地工具在全局范围内不可用，并作为 NuGet 包进行分发。

> [!WARNING]
> 如果尝试使用过 .NET Core 3.0 预览版 1 中的本地工具，例如运行 `dotnet tool restore` 或 `dotnet tool install`，请删除本地工具缓存文件夹。 否则，本地工具将无法在任何较新的版本上运行。 此文件夹位于：
>
> 在 macOS、Linux 上：`rm -r $HOME/.dotnet/toolResolverCache`
>
> 在 Windows 上：`rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`

本地工具依赖于当前目录中的清单文件名称 `dotnet-tools.json`。 此清单文件定义在该文件夹和以下文件夹中可用的工具。 你可以随代码一起分发清单文件，以确保使用代码的任何人都可以还原和使用相同的工具。

对于全局工具和本地工具，需要一个兼容的运行时版本。 目前，NuGet.org 上的许多工具都面向 .NET Core Runtime 2.1。 若要在全局范围或本地安装这些工具，仍需要安装 [NET Core 2.1 运行时](https://dotnet.microsoft.com/download/dotnet-core/2.1)。

## <a name="major-version-roll-forward"></a>主要版本前滚

.NET Core 3.0 引入了一项选择加入功能，该功能允许应用前滚到 .NET Core 最新的主要版本。 此外，还添加了一项新设置来控制如何将前滚应用于应用。 这可以通过以下方式配置：

- 项目文件属性：`RollForward`
- 运行时配置文件属性：`rollForward`
- 环境变量：`DOTNET_ROLL_FORWARD`
- 命令行参数：`--roll-forward`

必须指定以下值之一。 如果省略该设置，则默认值为“Minor”。

- **LatestPatch**\
前滚到最高补丁版本。 这会禁用次要版本前滚。
- **Minor**\
如果缺少所请求的次要版本，则前滚到最低的较高次要版本。 如果存在所请求的次要版本，则使用 **LatestPatch** 策略。
- **Major**\
如果缺少所请求的主要版本，则前滚到最低的较高主要版本和最低的次要版本。 如果存在所请求的主要版本，则使用 **Minor** 策略。
- **LatestMinor**\
即使存在所请求的次要版本，仍前滚到最高次要版本。 适用于组件托管方案。
- **LatestMajor**\
即使存在所请求的主要版本，仍前滚到最高主要版本和最高次要版本。 适用于组件托管方案。
- **Disable**\
不前滚。 仅绑定到指定的版本。 建议不要将此策略用于一般用途，因为它会禁用前滚到最新补丁的功能。 该值仅建议用于测试。

除“Disable”设置外，所有设置都将使用可用的最高补丁版本。

## <a name="windows-desktop"></a>Windows 桌面

.NET Core 3.0 支持使用 Windows Presentation Foundation (WPF) 和 Windows 窗体的 Windows 桌面应用程序。 这些框架还支持通过 [XAML 岛](/windows/uwp/xaml-platform/xaml-host-controls)从 Windows UI XAML 库 (WinUI) 使用新式控件和 Fluent 样式。

Windows 桌面部件是 Windows .NET Core 3.0 SDK 的一部分。

可以使用以下 `dotnet` 命令创建新的 WPF 或 Windows 窗体应用：

```console
dotnet new wpf
dotnet new winforms
```

Visual Studio 2019 添加了适用于 .NET Core 3.0 Windows 窗体和 WPF 的“新建项目”模板。

有关如何移植现有 .NET Framework 应用程序的详细信息，请参阅[移植 WPF 项目](../porting/wpf.md)和[移植 Windows 窗体项目](../porting/winforms.md)。

## <a name="com-callable-components---windows-desktop"></a>可调用 COM 的组件 - Windows 桌面

在 Windows 上，现在可以创建可调用 COM 的托管组件。 在将 .NET Core 与 COM 加载项模型结合使用，以及使用 .NET Framework 提供奇偶校验时，此功能至关重要。

与将 *mscoree.dll* 用作 COM 服务器的 .NET Framework 不同，.NET Core 将在生成 COM 组件时向 *bin* 目录添加本机启动程序 dll。

有关如何创建 COM 组件并使用它的示例，请参阅 [COM 演示](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo)。

## <a name="msix-deployment---windows-desktop"></a>MSIX 部署 - Windows 桌面

[MSIX](https://docs.microsoft.com/windows/msix/) 是新的 Windows 应用程序包格式。 可以使用它将 .NET Core 3.0 桌面应用程序部署到 Windows 10。

使用 Visual Studio 2019 中的 [Windows 应用打包项目](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)，可以创建包含[独立式](../deploying/index.md#self-contained-deployments-scd) .NET Core 应用的 MSIX 包。

.NET Core 项目文件必须在 `<RuntimeIdentifiers>` 属性中指定支持的运行时：

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="winforms-highdpi"></a>WinForms HighDPI

.NET Core Windows 窗体应用程序可以使用 <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType> 设置高 DPI 模式。 `SetHighDpiMode` 方法可设置相应的高 DPI 模式，除非该设置已通过其他方式（例如使用 `App.Manifest` 或在 `Application.Run` 前面使用 P/Invoke）进行设置。

由 <xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> 枚举表示的可能的 `highDpiMode` 值包括：

* `DpiUnaware`
* `SystemAware`
* `PerMonitor`
* `PerMonitorV2`
* `DpiUnawareGdiScaled`

有关高 DPI 模式的详细信息，请参阅[在 Windows 上开发高 DPI 桌面应用程序](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)。

### <a name="ranges-and-indices"></a>范围和索引

新 <xref:System.Index?displayProperty=nameWithType> 类型可用于编制索引。 可以从从开头开始计数的 `int` 中创建一个类型，也可以使用从末尾开始计数的前缀 `^` 运算符 (C#) 创建一个：

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

此外，还有 <xref:System.Range?displayProperty=nameWithType> 类型，它包含两个 `Index` 值，一个用于开头一个用于结尾，可以使用 `x..y` 范围表达式 (C#) 进行编写。 然后可以使用 `Range` 编制索引，以便生成一个切片：

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

有关详细信息，请参阅[范围和索引教程](../../csharp/tutorials/ranges-indexes.md)。

### <a name="async-streams"></a>异步流

<xref:System.Collections.Generic.IAsyncEnumerable%601> 类型是 <xref:System.Collections.Generic.IEnumerable%601> 的新异步版本。 该语言允许通过 `IAsyncEnumerable<T>` 执行 `await foreach` 操作来使用其元素，并对其使用 `yield return` 操作来生成元素。

下面的示例演示如何生成和使用异步流。 `foreach` 语句为异步语句，它本身使用 `yield return` 为调用方生成异步流。 此模式（使用 `yield return`）是生成异步流的建议模型。

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result; 
    }
}
```

除了能够 `await foreach`，还可以创建异步迭代器，例如，一个返回 `IAsyncEnumerable/IAsyncEnumerator` 的迭代器，可以在其中进行 `await` 和 `yield` 操作。 对于需要处理的对象，可以使用各种 BCL 类型（如 `Stream` 和 `Timer`）实现的 `IAsyncDisposable`。

有关详细信息，请参阅[异步流教程](../../csharp/tutorials/generate-consume-asynchronous-stream.md)。

## <a name="ieee-floating-point-improvements"></a>IEEE 浮点改进

正在更新浮点 API，以符合 [IEEE 754-2008 修订](https://en.wikipedia.org/wiki/IEEE_754-2008_revision)。 这些更改旨在公开所有**必需**操作并确保这些操作在行为上符合 IEEE 规范。有关浮点改进的详细信息，请参阅 [.NET Core 3.0 中的浮点分析和格式化改进](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/)博客文章。

分析和格式化修复包括：

* 正确分析并舍入任何输入长度。
* 正确分析并格式化负零。
* 通过执行不区分大小写的检查并允许在前面使用可选的 `+`（如果适用），正确分析 `Infinity` 和 `NaN`。

新的 <xref:System.Math?displayProperty=nameWithType> API 包括：

* <xref:System.Math.BitIncrement(System.Double)> 和 <xref:System.Math.BitDecrement(System.Double)>\
相当于 `nextUp` 和 `nextDown` IEEE 运算。 它们将返回最小的浮点数，该数字大于或小于输入值（分别）。 例如，`Math.BitIncrement(0.0)` 将返回 `double.Epsilon`。

* <xref:System.Math.MaxMagnitude(System.Double,System.Double)> 和 <xref:System.Math.MinMagnitude(System.Double,System.Double)>\
相当于 `maxNumMag` 和 `minNumMag` IEEE 运算，它们将（分别）返回大于或小于两个输入的量值的值。 例如，`Math.MaxMagnitude(2.0, -3.0)` 将返回 `-3.0`。

* <xref:System.Math.ILogB(System.Double)>\
相当于返回整数值的 `logB` IEEE 运算，它将返回输入参数的整数对数（以 2 为底）。 此方法实际上与 `floor(log2(x))` 相同，但完成后出现最小舍入错误。

* <xref:System.Math.ScaleB(System.Double,System.Int32)>\
相当于采用整数值的 `scaleB` IEEE 运算，它实际返回 `x * pow(2, n)`，但完成后出现最小舍入错误。

* <xref:System.Math.Log2(System.Double)>\
相当于返回（以 2 为底）对数的 `log2` IEEE 运算。 它会最小化舍入错误。

* <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
相当于执行乘法加法混合的 `fma` IEEE 运算。 也就是说，它以单个运算的形式执行 `(x * y) + z`，从而最小化舍入错误。 有关示例是返回 `1e308` 的 `FusedMultiplyAdd(1e308, 2.0, -1e308)`。 常规 `(1e308 * 2.0) - 1e308` 返回 `double.PositiveInfinity`。

* <xref:System.Math.CopySign(System.Double,System.Double)>\
相当于 `copySign` IEEE 运算，它返回 `x` 的值但带有符号 `y`。

## <a name="fast-built-in-json-support"></a>快速内置的 JSON 支持

.NET 用户在很大程度上依赖于 [**Json.NET**](https://www.newtonsoft.com/json) 和其他常用的 JSON 库，它们仍是很好的选择。 **Json.NET** 使用 .NET 字符串作为其基本数据类型，它实际上是 UTF-16。

新的内置 JSON 支持具有高性能、低分配的特点，并基于 `Span<byte>`。 已向 .NET Core 3.0 <xref:System.Text.Json?displayProperty=nameWithType> 命名空间添加三个新的与 JSON 相关的主类型。 这些类型*尚*不支持普通旧 CLR 对象 (POCO) 序列化和反序列化。

### <a name="utf8jsonreader"></a>Utf8JsonReader

<xref:System.Text.Json.Utf8JsonReader?displayProperty=nameWithType> 是面向 UTF-8 编码 JSON 文本的一个高性能、低分配、只进读取器，从 `ReadOnlySpan<byte>` 读取信息。 `Utf8JsonReader` 是一种基本的低级类型，可用于生成自定义分析器和反序列化程序。 使用新的 `Utf8JsonReader` 读取 JSON 有效负载要比使用 **Json.NET** 的读取器快 2 倍。 在需要将 JSON 令牌实现为 (UTF-16) 字符串之前，它不会进行分配。

下面的示例展示了如何读取 Visual Studio Code 创建的 [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) 文件：

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJson)]

[!CODE-csharp[Utf8JsonReader](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#PrintJsonCall)]

### <a name="utf8jsonwriter"></a>Utf8JsonWriter

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType> 提供了一种高性能、非缓存的只进方式，通过常见 .NET 类型（例如，`String`、`Int32` 和 `DateTime`）编写 UTF-8 编码的 JSON 文本。 与阅读器一样，编写器是一种基本的低级类型，可用于生成自定义序列化程序。 使用新的 `Utf8JsonWriter` 编写 JSON 有效负载比通过 **Json.NET** 使用编写器快 30-80%，且无需分配。

### <a name="jsondocument"></a>JsonDocument

<xref:System.Text.Json.JsonDocument?displayProperty=nameWithType> 是基于 `Utf8JsonReader` 构建的。 `JsonDocument` 可分析 JSON 数据并生成只读文档对象模型 (DOM)，可对模型进行查询，以支持随机访问和枚举。 可以通过 <xref:System.Text.Json.JsonElement> 类型（由 `JsonDocument` 公开为名为 `RootElement` 的属性）访问构成数据的 JSON 元素。 `JsonElement` 包含 JSON 数组和对象枚举器，以及用于将 JSON 文本转换为常见 .NET 类型的 API。 使用 `JsonDocument` 分析常规 JSON 有效负载并访问其所有成员比使用 **Json.NET** 快 2-3 倍，且为合理大小（即 < 1 MB）的数据所分配的量非常少。

下面是可用作起始点的 `JsonDocument` 和 `JsonElement` 的示例用法：

下面的 C# 8.0 示例展示了如何读取 Visual Studio Code 创建的 [**launch.json**](https://github.com/dotnet/samples/blob/master/snippets/core/whats-new/whats-new-in-30/cs/launch.json) 文件：

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJson)]

[!CODE-csharp[JsonDocument](~/samples/snippets/core/whats-new/whats-new-in-30/cs/program.cs#ReadJsonCall)]

### <a name="jsonserializer"></a>JsonSerializer

<xref:System.Text.Json.Serialization.JsonSerializer?displayProperty=nameWithType> 在 <xref:System.Text.Json.Utf8JsonReader> 和 <xref:System.Text.Json.Utf8JsonWriter> 的基础上生成，可在处理 JSON 文档和片段时提供快速的低内存序列化选项。

查看： https://github.com/dotnet/corefx/blob/master/src/System.Text.Json/docs/SerializerProgrammingModel.md，获取可移植到本文的示例

下面是一个将对象序列化为 JSON 的示例：

[!CODE-csharp[JsonSerializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonSerialize)]

下面是一个将 JSON 字符串反序列化为对象的示例。 可以使用上一个示例生成的 JSON 字符串：

[!CODE-csharp[JsonDeserializer](~/samples/snippets/core/whats-new/whats-new-in-30/cs/JSON.cs#JsonDeserialize)]

## <a name="interop-improvements"></a>互操作性改进

.NET Core 3.0 改进了本机 API 互操作性。

### <a name="type-nativelibrary"></a>类型：NativeLibrary

<xref:System.Runtime.InteropServices.NativeLibrary?displayProperty=nameWithType> 提供一个封装，用于加载本机库（使用与 .NET Core P/Invoke 相同的加载逻辑）并提供相关的帮助程序函数，例如 `getSymbol`。 有关代码示例，请参阅 [DLLMap 演示](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin)。

### <a name="windows-native-interop"></a>Windows 本机互操作

Windows 提供丰富的本机 API，包括平面 C API、COM 和 WinRT 的形式。 .NET Core 支持 **P/Invoke**，.NET Core 3.0 则增加了**共同创建 COM API** 和**激活 WinRT API** 的功能。 有关代码示例，请参阅 [Excel 演示](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo)。

## <a name="http2-support"></a>HTTP/2 支持

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 类型支持 HTTP/2 协议。 目前已禁用该支持，但可以在使用 <xref:System.Net.Http.HttpClient> 之前通过调用 `AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2Support", true);` 来启用。 也可以在运行应用之前通过将 `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` 环境变量设置为 `true` 来启用 HTTP/2 支持。

如果启用 HTTP/2，则将通过 TLS/ALPN 协商 HTTP 协议版本，并且仅在服务器选择使用 HTTP/2 时使用。

## <a name="tls-13--openssl-111-on-linux"></a>Linux 上的 TLS 1.3 和 OpenSSL 1.1.1

.NET Core 现在可以在给定环境中使用 [OpenSSL 1.1.1 中的 TLS 1.3 支持](https://www.openssl.org/blog/blog/2018/09/11/release111/)。 使用 TLS 1.3：

* 通过减少客户端和服务器之间所需的往返次数，提高了连接时间。
* 由于删除了各种过时和不安全的加密算法，提高了安全性。

.NET Core 3.0 在 Linux 系统上使用 **OpenSSL 1.1.1**、**OpenSSL 1.1.0** 或 **OpenSSL 1.0.2**（如果可用）。 当 **OpenSSL 1.1.1** 可用时，<xref:System.Net.Security.SslStream?displayProperty=nameWithType> 和 <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 类型都将使用 **TLS 1.3**（假定客户端和服务器都支持 **TLS 1.3**）。

>[!IMPORTANT]
>Windows 和 macOS 尚不支持 TLS 1.3。 当支持可用时，.NET Core 3.0 将在这些操作系统上支持 TLS 1.3。

下面的 C# 8.0 示例演示在 Ubuntu 18.10 上 .NET Core 3.0 如何连接到 <https://www.cloudflare.com>：

[!CODE-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

## <a name="cryptography-ciphers"></a>加密密码

.NET 3.0 增加了对 **AES-GCM** 和 **AES-CCM** 密码的支持（分别使用 <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> 和 <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType> 实现）。 这些算法都是[用于关联数据的认证加密 (AEAD) 算法](https://en.wikipedia.org/wiki/Authenticated_encryption)。

下面的代码演示了如何使用 `AesGcm` 密码加密和解密随机数据。

[!CODE-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

## <a name="cryptographic-key-importexport"></a>加密密钥导入/导出

.NET Core 3.0 支持从标准格式导入和导出非对称公钥和私钥。 你不需要使用 X.509 证书。

所有密钥类型（例如 *RSA*、*DSA*、*ECDsa* 和 *ECDiffieHellman*）都支持以下格式：

* **公钥**
  * X.509 SubjectPublicKeyInfo

* **私钥**
  * PKCS#8 PrivateKeyInfo
  * PKCS#8 EncryptedPrivateKeyInfo

RSA 密钥还支持：

* **公钥**
  * PKCS#1 RSAPublicKey

* **私钥**
  * PKCS#1 RSAPrivateKey

导出方法生成 DER 编码的二进制数据，导入方法也是如此。 如果密钥以文本友好的 PEM 格式存储，调用方需要在调用导入方法之前对内容进行 base64 解码。

[!CODE-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

可以使用 <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType> 检查 **PKCS#8** 文件，使用 <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType> 检查 **PFX/PKCS#12** 文件。 可以使用 <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType> 操作 **PFX/PKCS#12** 文件。

## <a name="serialport-for-linux"></a>适用于 Linux 的 SerialPort

.NET Core 3.0 在 Linux 上支持 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>。

以前，.NET Core 只支持在 Windows 上使用 `SerialPort`。

## <a name="docker-and-cgroup-memory-limits"></a>Docker 和 cgroup 内存限制

从预览版 3 开始，通过在 Linux 上使用 Docker 运行 .NET Core 3.0，可以更好地处理 cgroup 内存限制。 运行具有内存限制的 Docker 容器（例如使用 `docker run -m`）会更改 .NET Core 的行为方式。

* 默认垃圾回收器 (GC) 堆大小：最大为 20 MB 或容器内存限制的 75%。
* 可以将显式大小设置为绝对数或 cgroup 限制的百分比。
* 每个 GC 堆的最小保留段大小为 16 MB。 此大小可减少在计算机上创建的堆数量。

## <a name="smaller-garbage-collection-heap-sizes"></a>垃圾回收堆大小减小

垃圾回收器的默认堆大小已减小，以使 .NET Core 使用更少的内存。 此更改更符合具有现代处理器缓存大小的第 0 代分配预算。

## <a name="garbage-collection-large-page-support"></a>垃圾回收大型页面支持

大型页面（也称为 Linux 上的巨型页面）是一项功能，其中操作系统能够建立大于本机页面大小（通常为 4K）的内存区域，以提高请求这些大型页面的应用程序的性能。

现在可以使用 **GCLargePages** 设置将垃圾回收器配置为一项选择加入功能，以选择在 Windows 上分配大型页面。

## <a name="gpio-support-for-raspberry-pi"></a>对 Raspberry Pi 的 GPIO 支持

已向 NuGet 发布了两个可用于 GPIO 编程的包：

* [System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio)
* [Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings)

GPIO 包包括用于 *GPIO*、*SPI*、*I2C* 和 *PWM* 设备的 API。 IoT 绑定包包括设备绑定。 有关详细信息，请参阅[设备 GitHub 存储库](https://github.com/dotnet/iot/blob/master/src/devices/)。

## <a name="arm64-linux-support"></a>ARM64 Linux 支持

.NET Core 3.0 增加了对 ARM64 for Linux 的支持。 ARM64 的主要用例是当前的 IoT 场景。 有关详细信息，请参阅 [.NET Core ARM64 状态](https://github.com/dotnet/announcements/issues/82)。

[ARM64 上适用于 .NET Core 的 Docker 映像](https://hub.docker.com/r/microsoft/dotnet/)可用于 Alpine、Debian 和 Ubuntu。

> [!NOTE]
> **ARM64** 尚未提供 Windows 支持。
