---
title: .NET 可移植性分析器 - .NET
description: 了解如何使用 .NET 可移植性分析器工具，评估代码在各种 .NET 实现（包括 .NET Core、.NET Standard、UWP 和 Xamarin）间的可移植性。
ms.date: 07/18/2019
ms.technology: dotnet-standard
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.openlocfilehash: 433936480aa1181370a6ebc2bd2ba9914a50dfa2
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331744"
---
# <a name="the-net-portability-analyzer"></a>.NET 可移植性分析器

想让库支持多平台吗？ 想要了解让应用与其他 .NET 实现和配置文件（包括 .NET Core、.NET Standard、UWP 以及适用于 iOS、Android 和 Mac 的 Xamarin）兼容所需的工作量？ [.NET 可移植性分析器](https://github.com/microsoft/dotnet-apiport)工具可通过分析程序集，详细报告程序在各种 .NET 实现上的灵活性。 可移植性分析器作为 [Visual Studio Extension](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) 提供，用于分析每个项目的程序集；也可以作为 [ApiPort 控制台应用](https://aka.ms/apiportdownload)提供，用于按指定文件或目录分析程序集。

## <a name="common-targets"></a>常用对象

* [.NET Core](../../core/index.md)：采用模块化设计，可并行工作，面向跨平台方案。 可并行工作意味着无需破坏其他应用即可采用新的 .NET Core 版本。 如果目标是将应用移植到支持跨平台的 .NET Core，则建议使用此对象。 
* .[NET Standard](../../standard/net-standard.md)：包括所有 .NET 实现上提供的 .NET Standard API。 如果目标是使自己的库能够在所有 .NET 支持的平台上运行，则建议使用此对象。  
* [ASP.NET Core](/aspnet/core)：在 .NET Core 基础上构建的现代 Web 框架。 如果目标是将 Web 应用移植到 .NET Core 以支持多个平台，则建议使用此对象。
* .NET Core + [平台扩展](../../core/porting/windows-compat-pack.md)：除 Windows 兼容包之外，还包括 .NET Core API，后者提供了许多可用的 .NET Framework 技术。 这是推荐的对象，用于将 Windows 上的应用从 .NET Framework 移植到 .NET Core。
* .NET Standard + [平台扩展](../../core/porting/windows-compat-pack.md)：除 Windows 兼容包之外，还包括 .NET Standard API，后者提供了许多可用的 .NET Framework 技术。 这是推荐的对象，用于将 Windows 上的库从 .NET Framework 移植到 .NET Core。

## <a name="how-to-use-the-net-portability-analyzer"></a>如何使用 .NET 可移植性分析器

若要开始在 Visual Studio 中使用 .NET 可移植性分析器，必须先从 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) 下载扩展并进行安装。 它适用于 Visual Studio 2017 及更高版本。 可以通过 Visual Studio 中的“分析” > “可移植性分析器设置”对其进行配置，并选择目标平台，即选择 .NET 平台/版本，用于评估与当前程序集构建的平台/版本相比的可移植性差距   。

![可移植性屏幕截图](./media/portability-analyzer/portability-screenshot.png)

还可以使用 ApiPort 控制台应用程序，可从 [ApiPort 存储库](http://aka.ms/apiportdownload)进行下载。 可以使用 `listTargets` 命令选项以显示可用的目标列表，然后通过指定 `-t` 或 `--target` 命令选项来选择目标平台。 

### <a name="analyze-portability"></a>分析可移植性
若要在 Visual Studio 中分析整个项目，请在“解决方案资源管理器”中右键单击该项目，然后选择“分析程序集可移植性”   。 也可以转到“分析”菜单，选择“分析程序集可移植性”。   在该位置选择项目的可执行文件或 DLL。

![解决方案资源管理器中的可移植性分析器](./media/portability-analyzer/portability-solution-explorer.png)

还可以使用 [ApiPort 控制台应用](https://aka.ms/apiportdownload)。 

* 键入以下命令即可分析当前目录：`ApiPort.exe analyze -f .`
* 若要分析特定的 .dll 文件列表，请键入以下命令：`ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`
* 运行 `ApiPort.exe -?` 以获取更多帮助

建议包含自己拥有的且要移植的所有相关 exe 和 dll 文件，并且排除应用所依赖的，但你既不拥有又无法移植的文件。 这将为你提供最相关的可移植性报表。  

### <a name="view-and-interpret-portability-result"></a>查看和解释可移植性结果

报表中仅显示目标平台不支持的 API。 在 Visual Studio 中运行分析后，你将看到弹出的 .NET 可移植性报表文件链接。 如果使用的是 [ApiPort 控制台应用](https://aka.ms/apiportdownload)，.NET 可移植性报表将以指定的格式保存为文件。 默认位于当前目录中的 Excel 文件 (.xlsx) 中  。

#### <a name="portability-summary"></a>可移植性摘要 

![可移植性摘要](./media/portability-analyzer/portabilitysummary.png)

报表的“可移植性摘要”部分显示运行中包含的每个程序集的可移植性百分比。 在上述示例中，`svcutil` 应用中使用的 71.24% 的 .NET Framework API 在 .NET Core + Platform Extensions 中可用。 如果针对多个程序集运行 .NET 可移植性分析器工具，则每个程序集在“可移植性摘要”报表中都应有一行。

#### <a name="details"></a>详细信息

![可移植性详细信息](./media/portability-analyzer/portabilitydetails.png)

报表的“详细信息”部分列出了其中某个目标平台缺少的 API。 

- 目标类型：该类型具有目标平台缺少的 API 
- 目标成员：目标平台缺少的方法 
- 程序集名称：缺少的 API 所在的 .NET Framework 程序集。 
- 每个选定的目标平台都是一列，例如“.NET Core”：“不支持”值表示此目标平台不支持 API。 
- 建议的更改：要进行更改的推荐 API 或技术。 对于许多 API，此字段当前为空或已过时。 由于 API 数量众多，在维护 API 方面，我们面临着巨大的挑战。 我们致力于提供备用解决方案，以便为客户提供有用的信息。

#### <a name="missing-assemblies"></a>缺少程序集

![可移植性详细信息](./media/portability-analyzer/missingassemblies.png)

可以在报表中找到“缺少程序集”部分。 它告诉你，此程序集列表由分析的程序集引用，但不对其进行分析。 如果它是你自己拥有的程序集，请将其包含在 API 可移植性分析器运行过程中，以便你可以获得 API 级别的详细可移植性报表。 如果它是第三方库，则查找是否有支持自己的目标平台的最新版本。 如果有，请考虑转而使用最新版本。 最终，你希望此列表包含应用所依赖的所有第三方程序集，并确认其具有支持自己的目标平台的版本。  

有关 .NET 可移植性分析器的详细信息，请访问 [GitHub 文档](https://github.com/Microsoft/dotnet-apiport#documentation)和[简要了解 .NET 可移植性分析器](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer)第 9 频道视频。
