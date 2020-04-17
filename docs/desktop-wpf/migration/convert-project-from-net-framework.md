---
title: 将 WPF 应用迁移到 .NET 核心 3.0
description: 了解如何将 Windows 演示文稿基础 （WPF） 应用迁移到 .NET Core 3.0。
author: mjrousos
ms.date: 09/12/2019
ms.author: mikerou
ms.openlocfilehash: f52005e7c8a6312b8c4e09a950f1f635af1894e4
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "81432592"
---
# <a name="migrating-wpf-apps-to-net-core"></a>将 WPF 应用迁移到 .NET 核心

本文介绍将 Windows 演示文稿基础 （WPF） 应用从 .NET 框架迁移到 .NET Core 3.0 所需的步骤。 如果您手头没有 WPF 应用，但希望尝试此过程，则可以使用[GitHub](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader)上可用的**Bean Trader**示例应用 。 原始应用程序（目标 .NET 框架 4.7.2）可在 NetFx_BeanTraderClient 文件夹中使用。 首先，我们将解释移植应用程序所需的步骤，然后介绍适用于**Bean Trader**示例的特定更改。

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

要迁移到 .NET 核心，必须首先：

01. 了解并更新 NuGet 依赖项：

    01. 升级 NuGet 依赖项以`<PackageReference>`使用格式。
    01. 查看 .NET 核心或 .NET 标准兼容性的顶级 NuGet 依赖项。
    01. 将 NuGet 包升级到较新版本。
    01. 使用[.NET 可移植性分析器](../../standard/analyzers/portability-analyzer.md)了解 .NET 依赖项。

01. 将项目文件迁移到新的 SDK 样式格式：

    01. 选择是同时定位 .NET 核心和 .NET 框架，还是仅定位 .NET 核心。
    01. 将相关的项目文件属性和项复制到新项目文件。

01. 修复生成问题：

    01. 添加对[Microsoft.Windows.兼容性](https://www.nuget.org/packages/Microsoft.Windows.Compatibility/)包的引用。
    01. 查找并修复 API 级别差异。
    01. 删除 或`appSettings``connectionStrings`以外的*应用.config*部分。
    01. 如有必要，重新生成生成的代码。

01. 运行时测试：

    01. 确认移植的应用按预期工作。
    01. 注意<xref:System.NotSupportedException>例外情况。

## <a name="about-the-sample"></a>关于本示例

本文引用[Bean Trader 示例应用](https://github.com/dotnet/windows-desktop/tree/master/Samples/BeanTrader)，因为它使用各种依赖项，类似于现实世界的 WPF 应用可能具有的依赖项。 该应用程序并不大，但在复杂性方面，它意味着从"你好世界"中迈出一步。 该应用程序演示了用户在移植实际应用时可能会遇到的一些问题。 该应用程序与 WCF 服务通信，因此要正常运行，您还需要运行 BeanTraderServer 项目（在同一 GitHub 存储库中可用），并确保 BeanTraderClient 配置指向正确的终结点。 （默认情况下，该示例假定服务器在 的同一台计算机上运行，*http://localhost:8090*如果您在本地启动 BeanTraderServer，则为 true。

请记住，此示例应用旨在演示 .NET Core 移植挑战和解决方案。 它不是要演示 WPF 最佳实践。 事实上，它故意包括一些反模式，以确保你在移植时至少遇到几个有趣的挑战。

## <a name="getting-ready"></a>做好准备

将 .NET Framework 应用迁移到 .NET Core 的主要挑战是其依赖项可能以不同的方式工作，或者根本不工作。 迁移比过去容易得多;许多 NuGet 软件包现在都针对 .NET 标准。 从 .NET Core 2.0 开始，.NET 框架和 .NET 核心曲面区域变得相似。 即便如此，仍然存在一些差异（在 NuGet 包和可用的 .NET API 中支持方面）。 迁移的第一步是查看应用的依赖项，并确保引用的格式易于迁移到 .NET Core。

### <a name="upgrade-to-packagereference-nuget-references"></a>升级到`<PackageReference>`NuGet 引用

较旧的 .NET 框架项目通常在*包*中列出其 NuGet 依赖项。 新的 SDK 样式的项目文件格式将 NuGet[`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files)包作为 csproj 文件本身中的元素引用，而不是在单独的配置文件中。

迁移时，使用`<PackageReference>`-style 引用有两个优点：

- 这是新的 .NET Core 项目文件所需的 NuGet 引用样式。 如果您已在使用`<PackageReference>`，则可以将这些项目文件元素直接复制并粘贴到新项目中。
- 与包.config 文件不同`<PackageReference>`，元素仅引用项目直接依赖的顶级依赖项。 所有其他传递 NuGet 包将在还原时确定，并记录在自动生成的 obj_project.assets.json 文件中。 这样可以更轻松地确定项目具有哪些依赖项，这在确定必要的依赖项是否适用于 .NET Core 上非常有用。

将 .NET Framework 应用迁移到 .NET Core 的第一步是更新它以`<PackageReference>`使用 NuGet 引用。 视觉工作室使这一点变得简单。 只需右键单击 Visual Studio**的解决方案资源管理器**中的*包.config*文件，然后选择 **"迁移包.config 到包参考**"。

![升级到包参考](./media/convert-project-from-net-framework/package-reference-migration.png)

将显示一个对话框，显示计算的顶级 NuGet 依赖项，并询问应将哪些其他 NuGet 包提升到顶级。 这些其他包都不需要是 Bean Trader 示例的顶级，因此您可以取消选中所有这些框。 然后，单击 **"确定"** 并删除*包.config*文件`<PackageReference>`，并将元素添加到项目文件中。

`<PackageReference>`-样式引用不会将 NuGet 包本地存储在包文件夹中。 相反，它们作为优化存储在全局。 迁移完成后，编辑 csproj 文件并删除引用以前来自`<Analyzer>`的分析器的任何元素 *。\包*目录。 别担心，由于您仍然具有 NuGet 包引用，因此分析器将包含在项目中。 你只需要清理旧包。 `<Analyzer>`

### <a name="review-nuget-packages"></a>查看 NuGet 包

现在，您可以看到项目所依赖的顶级 NuGet 包，您可以查看这些包是否在 .NET Core 上可用。 您可以通过查看包对[nuget.org](https://www.nuget.org/)的依赖项来确定包是否支持 .NET Core。社区创建的[fuget.org](https://www.fuget.org/)网站在包信息页面顶部醒目地显示此信息。

当定位 .NET Core 3.0 时，任何针对 .NET Core 或 .NET 标准包都应工作（因为 .NET Core 实现了 .NET 标准表面积）。 在某些情况下，所使用的包的特定版本不会针对 .NET Core 或 .NET 标准，但较新版本将面向. 在这种情况下，应考虑升级到最新版本的包。

您也可以使用针对 .NET 框架的包，但这会带来一些风险。 .NET Core 到 .NET 框架依赖项是允许的，因为 .NET Core 和 .NET 框架曲面区域足够相似，因此此类依赖项*通常*工作。 但是，如果包尝试使用 .NET Core 中不存在的 .NET API，则会遇到运行时异常。 因此，您应该仅在没有其他选项可用时引用 .NET Framework 包，并了解这样做会带来测试负担。

如果引用的包不针对 .NET Core 或 .NET 标准，则必须考虑其他备选方案：

- 是否有其他类似的软件包可以代替使用？ 有时 NuGet 作者发布单独的'。核心的库版本专门针对 .NET Core。 企业库包是社区发布的一个示例"。NetCore"替代方案。 在其他情况下，对于 .NET 标准，可用于特定服务的较新的 SDK（有时具有不同的包名）。 如果没有可用的替代方案，则可以继续使用 .NET Framework 目标包，同时请记住，在 .NET Core 上运行后，需要对其进行彻底测试。

Bean 交易者示例具有以下顶级 NuGet 依赖项：

- [**城堡.温莎，版本 4.1.1**](https://www.castleproject.org/projects/windsor/)  

  此包以 .NET 标准 1.6 为目标，因此适用于 .NET 核心。

- [**微软.代码分析.FxCopAnalyzers，版本2.6.3**](https://www.nuget.org/packages/Microsoft.CodeAnalysis.FxCopAnalyzers/2.6.3)  
  这是一个元包，因此它支持哪些平台并不立即明显，但[文档](https://github.com/dotnet/roslyn-analyzers#microsoftcodeanalysisfxcopanalyzers)表明其最新版本 （2.9.2） 将同时适用于 .NET 框架和 .NET Core。

- [**Nito.AsyncEx，版本 4.0.1**](https://www.nuget.org/packages/Nito.AsyncEx/4.0.1)  

  此包不针对 .NET Core，但较新的 5.0 版本支持. 迁移时很常见，因为许多 NuGet 包最近添加了 .NET 标准支持，但较旧的项目版本将仅针对 .NET 框架。 如果版本差异只是一个较小的版本差异，则通常很容易升级到较新版本。 由于这是一个重大版本更改，因此需要谨慎升级，因为包中可能会有重大更改。 不过，有一条前进的道路，这很好。

- [**MahApps.Metro，版本 1.6.5**](https://www.nuget.org/packages/MahApps.Metro/1.6.5)  

  此包也不针对 .NET Core，但有较新的预发行版本 （2.0-alpha）。 同样，你必须留意重大的变化，但较新的软件包是令人鼓舞的。

Bean Trader 示例的 NuGet 依赖项都针对 .NET 标准/.NET Core，或者具有较新版本，因此这里不太可能存在任何阻塞问题。

### <a name="upgrade-nuget-packages"></a>升级 NuGet 包

如果可能，最好升级仅针对 .NET Core 或 .NET 标准的任何包的版本，此时更新版本（项目仍以 .NET Framework 为目标），以便及早发现和解决任何重大更改。

如果您不希望对应用的现有 .NET Framework 版本进行任何实质性更改，则可以等到您有针对 .NET Core 的新项目文件。 但是，提前将 NuGet 包升级到 .NET Core 兼容版本，一旦创建新的项目文件并减少应用 .NET Framework 和 .NET Core 版本之间的差异，迁移过程就变得更加容易。

使用 Bean Trader 示例，所有必要的升级都可以轻松进行（使用 Visual Studio 的 NuGet 软件包管理器），但有一个例外：从**MahApps.Metro 1.6.5**升级到**2.0**揭示了与主题和重音管理 API 相关的重大更改。

理想情况下，应用将更新以使用包的较新版本（因为这更有可能适用于 .NET Core）。 然而，在某些情况下，这可能不可行。 在这些情况下，不要升级**MahApps.Metro，** 因为必要的更改是非琐碎的，本教程侧重于迁移到 .NET Core 3，而不是**MahApps.Metro 2。** 此外，这是一个低风险 .NET 框架依赖项，因为 Bean Trader 应用程序只行使**MahApps.Metro 的**一小部分。 当然，它将需要测试，以确保迁移完成后一切工作。 如果这是一个真实的场景，最好提交一个问题来跟踪工作移动到**MahApps.Metro**版本2.0，因为不做迁移现在留下一些技术债务。

将 NuGet 包更新到最新版本后，"Bean `<PackageReference>` Trader"示例的项目文件中的项目组应如下所示。

```xml
<ItemGroup>
  <PackageReference Include="Castle.Windsor">
    <Version>4.1.1</Version>
  </PackageReference>
  <PackageReference Include="MahApps.Metro">
    <Version>1.6.5</Version>
  </PackageReference>
  <PackageReference Include="Microsoft.CodeAnalysis.FxCopAnalyzers">
    <Version>2.9.2</Version>
  </PackageReference>
  <PackageReference Include="Nito.AsyncEx">
    <Version>5.0.0</Version>
  </PackageReference>
</ItemGroup>
```

### <a name="net-framework-portability-analysis"></a>.NET 框架可移植性分析

了解项目的 NuGet 依赖项的状态后，需要考虑的下一件事是 .NET Framework API 依赖项。 [.NET 可移植性分析器](../../standard/analyzers/portability-analyzer.md)工具可用于了解项目使用的 .NET API 在其他 .NET 平台上可用。

该工具作为[Visual Studio插件](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer)，[一个命令行工具](https://github.com/Microsoft/dotnet-apiport/releases)，或包装在一[个简单的GUI，](https://github.com/Microsoft/dotnet-apiport-ui)这简化了它的选项。 您可以阅读有关使用 .NET 可移植性分析器 （API 端口） 在[将桌面应用移植到 .NET Core](https://devblogs.microsoft.com/dotnet/porting-desktop-apps-to-net-core/)博客文章中的 GUI 的详细信息。 如果希望使用命令行，则必要的步骤是：

1. 如果您还没有[.NET 可移植性分析器](https://github.com/Microsoft/dotnet-apiport/releases)，请下载它。
1. 确保成功移植 .NET Framework 应用（无论在迁移之前，这是一个好主意）。
1. 使用这样的命令行运行 API 端口。

    ```console
    ApiPort.exe analyze -f <PathToBeanTraderBinaries> -r html -r excel -t ".NET Core"
    ```

    参数`-f`指定包含要分析的二进制文件的路径。 参数`-r`指定所需的输出文件格式。 参数`-t`指定要针对哪个 .NET 平台分析 API 使用情况。 在这种情况下，您需要 .NET 核心。

打开 HTML 报表时，第一部分将列出所有分析的二进制文件，以及他们使用的 .NET API 的百分比在目标平台上可用。 这个百分比本身没有意义。 更有用的是查看缺少的特定 API。 为此，请选择程序集名称或向下滚动到各个程序集的报表。

关注您拥有的源代码的程序集。 例如，在 Bean Trader ApiPort 报告中，列出了许多二进制文件，但大多数都属于 NuGet 包。 `Castle.Windsor`显示它依赖于 .NET Core 中缺少的某些 System.Web API。 这不是问题，因为您以前已验证支持`Castle.Windsor`.NET Core。 NuGet 包具有不同的二进制文件用于不同的 .NET 平台是很常见的，因此，只要包也针对 .NET`Castle.Windsor`标准或 .NET Core（它这样做），.NET 框架版本是否使用 System.Web API 都无关紧要。

使用 Bean Trader 示例时，您需要考虑的唯一二进制文件是**BeanTraderClient，** 报告显示仅缺少两个 .NET `System.ServiceModel.ClientBase<T>.Close` API：`System.ServiceModel.ClientBase<T>.Open`和 。

![豆交易客户端可移植性报告](./media/convert-project-from-net-framework/portability-report.png)

这些不太可能阻止问题，因为 WCF 客户端 API（大部分）在 .NET Core 上受支持，因此必须为这些中央 API 提供替代方案。 事实上，查看`System.ServiceModel`.NET 核心表面积（使用<https://apisof.net>），您会看到 .NET Core 中有异步替代方案。

基于此报告和以前的 NuGet 依赖项分析，似乎不应存在将 Bean Trader 示例迁移到 .NET Core 的大问题。 您已准备好下一步，在此步骤中，您将实际开始迁移。

## <a name="migrating-the-project-file"></a>迁移项目文件

如果你的应用没有使用新的[SDK 风格的项目文件格式](../../core/tools/csproj.md)，则需要一个新的项目文件来定位 .NET Core。 您可以替换现有的 csproj 文件，或者，如果您希望保持现有项目保持其当前状态不变，则可以添加针对 .NET Core 的新 csproj 文件。 您可以使用具有[多目标的](../../standard/library-guidance/cross-platform-targeting.md)单个 SDK 样式项目文件（指定多个`<TargetFrameworks>`目标）为 .NET 框架和 .NET Core 构建应用版本。

要创建新的项目文件，可以在 Visual Studio 中创建新的 WPF 项目，或者`dotnet new wpf`使用临时目录中的命令生成项目文件，然后将其复制/重命名到正确的位置。 还有一个社区创建的工具[，CsprojToVs2017，](https://github.com/hvanbakel/CsprojToVs2017)它可以自动执行一些项目文件迁移。 该工具很有用，但仍需要人工查看结果，以确保迁移的所有详细信息都正确无误。 该工具无法最好地处理的一个特定区域是从包迁移 NuGet 包 *。* 如果该工具在仍使用*包.config*文件引用 NuGet 包的项目文件上运行，它将自动迁移到`<PackageReference>`元素，但会为所有包添加`<PackageReference>`元素，而不仅仅是顶级*all*包的元素。 如果您已经迁移到`<PackageReference>`了使用 Visual Studio 的元素（如本示例中所做的那样），则该工具可以帮助完成转换的其余部分。 像斯科特·汉塞尔曼[在他的博客文章中建议迁移csproj文件](https://www.hanselman.com/blog/UpgradingAnExistingNETProjectFilesToTheLeanNewCSPROJFormatFromNETCore.aspx)，手工移植是教育性的，如果你只有几个项目移植，将提供更好的结果。 但是，如果您移植了几十个或数百个项目文件，那么像 [CprojToVs2017] 这样的工具可能是一个帮助。

要为 Bean Trader 示例创建新的项目文件，请`dotnet new wpf`运行临时目录中，并将生成的 *.csproj*文件移动到*BeanTraderClient*文件夹中，并将其重命名为**BeanTraderClient.Core.csproj**。

由于新的项目文件格式自动包括 C# 文件 *、resx*文件和 XAML 文件，它在其目录中或在其目录下找到，因此项目文件已几乎完成！ 要完成迁移，请并排打开新旧项目文件，并查看旧项目文件以查看是否需要迁移其中包含的任何信息。 在"豆交易"示例案例中，应将以下项目复制到新项目：

- 全部`<RootNamespace>`应`<AssemblyName>`复制`<ApplicationIcon>`和 属性。

- 您还需要向新项目文件添加`<GenerateAssemblyInfo>false</GenerateAssemblyInfo>`属性，因为 Bean Trader 示例在AssemblyInfo.cs文件中包含程序集级属性（如`[AssemblyTitle]`）。"属性"。 默认情况下，新的 SDK 样式项目将根据 csproj 文件中的属性自动生成这些属性。 由于在这种情况下不希望这种情况发生（自动生成的属性将与AssemblyInfo.cs的属性冲突），因此使用 禁用自动生成的属性`<GenerateAssemblyInfo>`。

- 尽管*resx*文件自动作为嵌入资源包含在内`<Resource>`，但其他项目（如图像）则不包括在内。 因此，`<Resource>`复制嵌入图像和图标文件的元素。 您可以使用新项目文件格式对 globing 模式的支持来简化对单行的 png 引用： `<Resource Include="**\*.png" />`。

- 同样，`<None>`项目会自动包含，但默认情况下不会将其复制到输出目录。 由于 Bean Trader 项目`<None>`包含*复制到*输出目录（使用`PreserveNewest`行为）的项目，因此您需要更新该文件自动填充`<None>`的项，如下所示。

  ```xml
  <None Update="BeanTrader.pfx">
    <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </None>
  ```

- Bean Trader 示例包括 XAML 文件 （Default.Accent.xaml） 作为`Content`（`Page`而不是作为 ），因为在此文件中定义的主题和重音在运行时从文件的 XAML 加载，而不是嵌入到应用本身中。 但是，新项目系统会自动将此文件作为`<Page>`，因为它是 XAML 文件。 因此，您需要同时删除 XAML 文件作为页面 （`<Page Remove="**\Default.Accent.xaml" />`）， 并将其添加为内容。

  ```xml
  <Content Include="Resources\Themes\Default.Accent.xaml">
      <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
  </Content>
  ```

- 最后，通过复制`<ItemGroup>`所有`<PackageReference>`元素来添加 NuGet 引用。 如果您以前没有将 NuGet 包升级到 .NET Core 兼容版本，则现在可以执行此操作，因为包引用位于 .NET Core 特定的项目中。

此时，应该可以将新项目添加到 BeanTrader 解决方案并在 Visual Studio 中打开它。 项目在**解决方案资源管理器**中应看起来正确，并`dotnet restore BeanTraderClient.Core.csproj`应成功还原包（与 MahApps.Metro 版本相关的两个预期警告，您使用的定位目标 .NET Framework）。

尽管可以同时保留两个项目文件（如果要保持旧项目完全按照现在的身份构建，甚至可能是可取的），但它使迁移过程复杂化（这两个项目将尝试使用相同的 bin 和 obj 文件夹），通常没有必要。 如果要同时为 .NET Core 和 .NET 框架目标生成，则可以`<TargetFramework>netcoreapp3.0</TargetFramework>``<TargetFrameworks>netcoreapp3.0;net472</TargetFrameworks>`改为替换新项目文件中的属性。 对于 Bean Trader 示例，请删除旧项目文件（BeanTraderClient.csproj），因为它不再需要。 如果您希望保留这两个项目文件，请确保将它们构建到不同的输出和中间输出路径。

## <a name="fix-build-issues"></a>修复生成问题

移植过程的第三步是生成项目。 一旦项目文件转换为 SDK 样式的项目，某些应用将成功生成。 如果你的应用如此，恭喜你！ 您可以继续执行步骤 4。 其他应用将需要一些更新，以使它们为 .NET Core 构建。 如果您尝试现在`dotnet build`运行 Bean Trader 示例项目（例如，或在 Visual Studio 中构建），将有许多错误，但很快就会修复它们。

### <a name="systemservicemodel-references-and-microsoftwindowscompatibility"></a>系统.服务模型引用和微软.Windows.兼容性

常见的错误来源是缺少可用于 .NET Core 但未自动包含在 .NET Core 应用元包中的 API 的引用。 为此，应引用该`Microsoft.Windows.Compatibility`包。 兼容性包包括 Windows 桌面应用中常见的广泛 API 集，例如 WCF 客户端、目录服务、注册表、配置、ACL API 等。

使用 Bean Trader 示例，大多数生成错误是由于缺少<xref:System.ServiceModel>类型造成的。 这些可以通过引用必要的 WCF NuGet 包来解决。 但是，WCF 客户端 API 是`Microsoft.Windows.Compatibility`包中存在的一部分，因此引用兼容性包是一个更好的解决方案（因为它还解决了与 API 相关的任何问题以及兼容性包提供的 WCF 问题的解决方案）。 在大多数`Microsoft.Windows.Compatibility`.NET Core 3.0 WPF 和 WinForms 移植方案中，该包都很有帮助。 将 NuGet 引用添加到`Microsoft.Windows.Compatibility`后，仅保留一个生成错误！

### <a name="cleaning-up-unused-files"></a>清理未使用的文件

出现一种类型的迁移问题通常与以前未包含在生成中的新 SDK 样式项目（自动包含*所有*源）的 C# 和 XAML 文件有关。

您在 Bean Trader 示例中看到的下一个生成错误是指*OldUnusedViewModel.cs*中的一个错误接口实现。 文件名是提示，但在检查时，您会发现此源文件不正确。 它以前没有引起问题，因为它未包含在原始的 .NET 框架项目中。 磁盘上存在但未包含在旧*csproj*中的源文件现在会自动包含。

对于这样的一次性问题，很容易与以前的*csproj*进行比较，以确认该文件不需要，然后`<Compile Remove="" />`要么它，要么，如果源文件不再需要任何地方，请将其删除。 在这种情况下，只需删除*OldUnusedViewModel.cs*是安全的。

如果有许多需要以这种方式排除的源文件，则可以通过在项目文件中将`<EnableDefaultCompileItems>`属性设置为 false 来禁用自动包含 C# 文件。 然后，您可以将项目从`<Compile Include>`旧项目文件复制到新项目文件，以便仅生成要包括的源。 同样，`<EnableDefaultPageItems>`可用于关闭 XAML 页面的自动包含，并且`<EnableDefaultItems>`可以使用单个属性控制这两个页面。

### <a name="a-brief-aside-on-multi-pass-compilers"></a>多通道编译器的简短旁加

从 Bean Trader 示例中删除违规文件后，您可以重新生成，并将得到四个错误。 你以前没有吗？ 为什么错误数会上升？ C# 编译器是[多通道编译器](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes)。 这意味着它遍遍每个源文件两次。 首先，编译器只查看每个源文件中的元数据和声明，并标识任何声明级问题。 这些是您修复的错误。 然后，它再次通过代码将 C# 源构建到 IL;这些是你现在看到的第二组错误。

> [!NOTE]
> C# 编译器[执行的不仅仅是两个传递](https://docs.microsoft.com/archive/blogs/ericlippert/how-many-passes)，但最终结果是，对于像这样的大型代码更改的编译器错误往往以两个波表示。

### <a name="third-party-dependency-fixes-castlewindsor"></a>第三方依赖项修复（城堡.温莎）

某些迁移方案中出现的另一类问题是依赖项 .NET Framework 和 .NET Core 版本之间的 API 差异。 即使 NuGet 包同时面向 .NET 框架和 .NET 标准或 .NET Core，也可能有不同的库可用于不同的 .NET 目标。 这允许包支持许多不同的 .NET 平台，这可能需要不同的实现。 这也意味着，当针对不同的 .NET 平台时，库中可能存在较小的 API 差异。

您将在"豆交易"示例中看到的下一组错误与`Castle.Windsor`API 相关。 .NET 核心 Bean Trader 项目使用与`Castle.Windsor`.NET Framework 目标项目 （4.1.1） 相同的版本，但这两个平台的实现略有不同。

在这种情况下，您将看到需要修复的以下问题：

1. `Castle.MicroKernel.Registration.Classes.FromThisAssembly`不在 .NET 核心上可用。 但是，有类似的`Classes.FromAssemblyContaining`API 可用，因此我们可以将 调用 的`Classes.FromThisAssembly()`两个用途替换为`Classes.FromAssemblyContaining(t)`调用`t`，其中发出调用的类型在哪里。
1. 同样，在*Bootstrapper.cs*`Castle.Windsor.Installer.FromAssembly`中。这在 .NET 核心上不可用。 相反，该调用可以替换为`FromAssembly.Containing(typeof(Bootstrapper))`。

### <a name="updating-wcf-client-usage"></a>更新 WCF 客户端使用情况

修复了`Castle.Windsor`差异后，.NET Core Bean Trader 项目中最后剩余的生成错误是`BeanTraderServiceClient`（派生自`DuplexClientBase`）没有`Open`方法。 这并不奇怪，因为这是在此迁移过程开始时由 .NET 可移植性分析器突出显示的 API。 不过，`BeanTraderServiceClient`让我们注意到一个更大的问题。 此 WCF 客户端由[Svcutil.exe](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)工具自动生成。

**Svcutil 生成的 WCF 客户端用于 .NET 框架。**

使用 svcutil 生成的 WCF 客户端的解决方案需要重新生成 .NET 标准兼容的客户端，以便与 .NET Core 一起使用。 旧客户端无法工作的主要原因之一是，它们依赖于应用配置来定义 WCF 绑定和终结点。 由于 .NET 标准 WCF API 可以跨平台工作（其中 System.配置 API 不可用），因此 .NET 核心和 .NET 标准方案的 WCF 客户端必须以编程方式定义绑定和终结点，而不是在配置中定义绑定和终结点。

事实上，任何 WCF 客户端使用依赖于`<system.serviceModel>`app.config 部分（无论是使用 Svcutil 还是手动创建的）都需要更改为在 .NET Core 上工作。

有两种方法可以自动生成与 .NET 标准兼容的 WCF 客户端：

- 该工具`dotnet-svcutil`是一个 .NET 工具，以类似于 Svcutil 以前的工作方式的方式生成 WCF 客户端。
- Visual Studio 可以使用其连接服务功能的[WCF Web 服务参考](../../core/additional-tools/wcf-web-service-reference-guide.md)选项生成 WCF 客户端。

两种方法都有效。 或者，当然，您可以自己编写 WCF 客户端代码。 对于此示例，我选择使用可视化工作室连接服务功能。 为此，请右键单击 Visual Studio 解决方案资源管理器中的*BeanTraderClient.Core*项目，然后选择"**添加** > **连接服务**"。 接下来，选择 WCF Web 服务参考提供程序。 这将弹出一个对话框，您可以在其中指定后端 Bean Trader Web 服务的地址（`localhost:8080`如果您在本地运行服务器）和生成类型的命名空间应使用（例如**BeanTrader.Service）。**

![WCF Web 服务参考连接的服务对话框](./media/convert-project-from-net-framework/connected-service-dialog.png)

选择 **"完成"** 按钮后，将添加新的"已连接服务"节点，并在该节点下添加一个Reference.cs文件，其中包含用于访问 Bean Trader 服务的新 .NET 标准 WCF 客户端。 如果查看该文件中的`GetEndpointAddress`或`GetBindingForEndpoint`方法，您将看到绑定和终结点现在以编程方式生成（而不是通过应用配置）。 "添加已连接服务"功能还可能添加对项目文件中某些 System.ServiceModel 包的引用，因为所有必需的 WCF 包都通过 Microsoft.Windows.兼容性包含在内，因此不需要这些引用。 检查 csproj 以查看是否添加了任何额外的 System.ServiceModel`<PackageReference>`项目，如果是，请删除它们。

我们的项目现在有新的WCF客户端类（*在Reference.cs），* 但它也有旧的（在BeanTrader.cs）。 此时有两个选项：

- 如果希望能够构建原始的 .NET Framework 项目（以及新的 .NET Core 目标项目），则可以使用`<Compile Remove="BeanTrader.cs" />`.NET Core 项目的 csproj 文件中的项目，以便应用程序的 .NET 框架和 .NET Core 版本使用不同的 WCF 客户端。 这样做的好处是使现有的 .NET Framework 项目保持不变，但缺点是使用生成的 WCF 客户端的代码可能需要在 .NET Core 案例中与 .NET 框架项目中的代码略有不同，因此您可能需要使用`#if`指令有条件地编译某些 WCF 客户端使用情况（例如创建客户端），以便在为 .NET Core 构建时采用单向方式工作，在为 .NET 框架构建时，可能需要另一种方式。

- 另一方面，如果现有的 .NET Framework 项目中的某些代码改动是可以接受的，则可以同时删除*BeanTrader.cs。* 由于新的 WCF 客户端是为 .NET 标准构建的，因此它将同时在 .NET Core 和 .NET 框架方案中工作。 如果要为 .NET 框架构建 .NET 框架（通过多目标或具有两个 csproj 文件），则可以对两个目标使用此新的*Reference.cs*文件。 此方法的优点是，代码不需要分叉来支持两个不同的 WCF 客户端;相同的代码将在任何地方使用。 缺点是它涉及更改 （大概稳定） .NET 框架项目。

在 Bean Trader 示例中，如果原始项目使迁移更容易，则可以对原始项目进行少量更改，因此请按照以下步骤协调 WCF 客户端使用情况：

01. 使用解决方案资源管理器中的"添加现有项目"上下文菜单将新的Reference.cs文件添加到 .NET 框架*BeanTraderClient.csproj*项目中。 请务必添加"作为链接"，以便两个项目使用相同的文件（而不是复制 C# 文件）。 如果要使用单个 csproj（使用多目标）为 .NET Core 和 .NET 框架构建，则此步骤是不必要的。

01. 删除*BeanTrader.cs*。

01. 新的 WCF 客户端与旧客户端类似，但生成的代码中的多个命名空间不同。 因此，有必要更新项目，以便 WCF 客户端类型从 BeanTrader.Service.Service（或您选择的任何命名空间名称）而不是 BeanTrader.Model 或没有命名空间使用。 构建*BeanTraderClient.Core.csproj*将有助于确定需要进行更改的位置。 在 C# 和 XAML 源文件中都需要修复。

01. 最后，您将发现*BeanTraderServiceClientFactory.cs*存在错误，因为`BeanTraderServiceClient`类型的可用构造函数已更改。 它曾经可以提供一个`InstanceContext`参数（这是使用`CallbackHandler``Castle.Windsor`IoC 容器创建的）。 新的构造函数创建新`CallbackHandler`的 s。 但是，在 基类型中`BeanTraderServiceClient`，构造函数与所需内容相匹配。 由于自动生成的 WCF 客户端代码都存在于部分类中，因此可以轻松地扩展它。 为此，请创建一个名为*BeanTraderServiceClient.cs*的新文件，然后创建具有相同名称的部分类（使用 BeanTrader.Service 命名空间）。 然后，将一个构造函数添加到部分类型，如下所示。

    ```csharp
    public BeanTraderServiceClient(System.ServiceModel.InstanceContext callbackInstance) :
        base(callbackInstance, EndpointConfiguration.NetTcpBinding_BeanTraderService)
            { }
    ```

进行这些更改后，Bean Trader 示例现在将使用新的 .NET 标准兼容的 WCF 客户端，您可以TradingService.cs改为更改`Open`调用*TradingService.cs*`await OpenAsync`的最后修复方法。

随着 WCF 问题的解决，Bean Trader 示例的 .NET 核心版本现在构建干净！

## <a name="runtime-testing"></a>运行时测试

很容易忘记，一旦项目针对 .NET Core 干净地构建，迁移工作就不会完成。 留出时间测试移植的应用程序也很重要。 成功生成内容后，请确保应用按预期运行并工作，尤其是在使用针对 .NET Framework 的任何包时。

让我们尝试启动移植的豆交易应用程序，看看会发生什么。 除了以下例外情况外，应用在失败之前不会走得太远。

```output
System.Configuration.ConfigurationErrorsException: 'Configuration system failed to initialize'

Inner Exception
ConfigurationErrorsException: Unrecognized configuration section system.serviceModel.
```

当然，这是有道理的。 请记住，WCF 不再使用应用配置，因此需要删除 app.config 文件的旧系统.serviceModel 部分。 更新后的 WCF 客户端在其代码中包含所有相同的信息，因此不再需要配置部分。 如果希望 WCF 终结点在 app.config 中可配置，则可以将其添加为应用设置，并更新 WCF 客户端代码以从配置中检索 WCF 服务终结点。

删除*app.config*的 system.serviceModel 部分后，应用启动，但在用户登录时失败，但另一个例外。

```output
System.PlatformNotSupportedException: 'Operation is not supported on this platform.'
```

不支持的 API`Func<T>.BeginInvoke`是 。 如[dotnet/corefx_5940](https://github.com/dotnet/corefx/issues/5940)中所述，.NET Core 不支持`BeginInvoke`委托`EndInvoke`类型和方法，因为存在基础的远程处理依赖关系。 此问题及其修复程序在迁移委托中进行了更详细的解释[。 BeginInvoke 调用 .NET Core](https://devblogs.microsoft.com/dotnet/migrating-delegate-begininvoke-calls-for-net-core/)博客文章，但要点是，`BeginInvoke``EndInvoke`调用应替换为`Task.Run`（或异步替代，如果可能）。 在此处应用常规解决方案，`BeginInvoke`呼叫可以替换为 由`Invoke``Task.Run`启动的呼叫。

```csharp
Task.Run(() =>
{
    return userInfoRetriever.Invoke();
}).ContinueWith(result =>
{
    // BeginInvoke's callback is replaced with ContinueWith
    var task = result.ConfigureAwait(false);
    CurrentTrader = task.GetAwaiter().GetResult();
}, TaskScheduler.Default);
```

删除`BeginInvoke`使用后，豆交易者应用程序在 .NET 核心上成功运行！

![在 .NET 核心上运行的豆交易者](./media/convert-project-from-net-framework/running-on-core.png)

所有应用都不同，因此将您自己的应用迁移到 .NET Core 所需的特定步骤会有所不同。 但希望 Bean Trader 示例演示了常规工作流和可以预期的问题类型。 而且，尽管本文的长度，豆交易者样本中所需的实际更改，使其在 .NET Core 上工作相当有限。 许多应用以同样方式迁移到 .NET Core;需要有限甚至无需更改代码。
