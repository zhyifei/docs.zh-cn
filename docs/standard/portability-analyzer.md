---
title: ".NET 可移植性分析器 - .NET | Microsoft Docs"
description: "了解如何使用 .NET 可移植性分析器工具来评估代码在各种 .NET 实现中的可移植性。"
keywords: ".NET、.NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 07/26/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 0375250f-5704-4993-a6d5-e21c499cea1e
ms.translationtype: HT
ms.sourcegitcommit: 3155295489e1188640dae5aa5bf9fdceb7480ed6
ms.openlocfilehash: adb1971c14c8ff8c147dba378ae0e9a5bc0fb5ad
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---

# <a name="the-net-portability-analyzer"></a><span data-ttu-id="2a789-104">.NET 可移植性分析器</span><span class="sxs-lookup"><span data-stu-id="2a789-104">The .NET Portability Analyzer</span></span>

<span data-ttu-id="2a789-105">想要让你的库在多个平台上使用？</span><span class="sxs-lookup"><span data-stu-id="2a789-105">Want to make your libraries multi-platform?</span></span> <span data-ttu-id="2a789-106">想要了解使应用程序与其他 .NET 实现兼容需要花费多大的精力？</span><span class="sxs-lookup"><span data-stu-id="2a789-106">Want to see how much work is required to make your application compatible with other .NET implementations?</span></span> <span data-ttu-id="2a789-107">[.NET 可移植性分析器](http://go.microsoft.com/fwlink/?LinkID=507467)工具可通过分析程序集，详细报告程序在各种 .NET 实现上的灵活性。</span><span class="sxs-lookup"><span data-stu-id="2a789-107">The [.NET Portability Analyzer](http://go.microsoft.com/fwlink/?LinkID=507467) is a tool that provides you with a detailed report on how flexible your program is across .NET implementations by analyzing assemblies.</span></span> <span data-ttu-id="2a789-108">可移植性分析器以 Visual Studio 扩展和控制台应用的形式提供。</span><span class="sxs-lookup"><span data-stu-id="2a789-108">The Portability Analyzer is offered as a Visual Studio Extension and as a console app.</span></span>

## <a name="new-targets"></a><span data-ttu-id="2a789-109">新目标</span><span class="sxs-lookup"><span data-stu-id="2a789-109">New targets</span></span>

* <span data-ttu-id="2a789-110">[.NET Core](https://dotnetfoundation.org/net-core)：采用模块化设计，可并行工作，面向跨平台方案。</span><span class="sxs-lookup"><span data-stu-id="2a789-110">[.NET Core](https://dotnetfoundation.org/net-core): Has a modular design, employs side-by-side, and targets cross-platform scenarios.</span></span> <span data-ttu-id="2a789-111">可并行工作意味着无需破坏其他应用即可采用新的 .NET Core 版本。</span><span class="sxs-lookup"><span data-stu-id="2a789-111">Side-by-side allows you to adopt new .NET Core versions without breaking other apps.</span></span>
* <span data-ttu-id="2a789-112">[ASP.NET Core](https://dotnetfoundation.org/asp-net-core)：构建在 .NET Core 基础之上的新型 Web 框架，为开发人员提供与 .NET Core 相同的优势。</span><span class="sxs-lookup"><span data-stu-id="2a789-112">[ASP.NET Core](https://dotnetfoundation.org/asp-net-core): is a modern web-framework built on .NET Core thus giving developers the same benefits.</span></span>
* <span data-ttu-id="2a789-113">[通用 Windows 平台](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance)：使用 .NET Native 的静态编译，提高 x64 和 ARM 计算机上运行的 Windows 应用商店应用的性能。</span><span class="sxs-lookup"><span data-stu-id="2a789-113">[Universal Windows Platform](https://blogs.msdn.microsoft.com/dotnet/2014/04/24/net-native-performance): Improve performance of your Windows Store apps that run on x64 and ARM machines by using .NET Native’s static compilation.</span></span> 
* <span data-ttu-id="2a789-114">.NET Core + 平台扩展：除 WCF、ASP.NET Core、FSharp 和 Azure 等 .NET 生态系统中的其他 API 外还包括 .NET Core API。</span><span class="sxs-lookup"><span data-stu-id="2a789-114">.NET Core + Platform Extensions: Includes the .NET Core APIs in addition to other APIs in the .NET ecosystem such as WCF, ASP.NET Core, FSharp, and Azure.</span></span>
* <span data-ttu-id="2a789-115">.NET Standard + 平台扩展：除 WCF、ASP.NET Core、FSharp 和 Azure 等 .NET 生态系统中的其他 API 外还包括 .NET Standard API。</span><span class="sxs-lookup"><span data-stu-id="2a789-115">.NET Standard + Platform Extensions: Includes the .NET Standard APIs in addition to other .NET ecosystem such as WCF, ASP.NET Core, FSharp, and Azure.</span></span>

## <a name="how-to-use-portability-analyzer"></a><span data-ttu-id="2a789-116">如何使用可移植性分析器</span><span class="sxs-lookup"><span data-stu-id="2a789-116">How to use Portability Analyzer</span></span>

<span data-ttu-id="2a789-117">若要开始使用 .NET 可移植性分析器，首先需要从 [Visual Studio 库](http://go.microsoft.com/fwlink/?LinkID=507467)下载相应的扩展。</span><span class="sxs-lookup"><span data-stu-id="2a789-117">To begin using the .NET Portability Analyzer, you first need to download and install the extension from the [Visual Studio Gallery](http://go.microsoft.com/fwlink/?LinkID=507467).</span></span> <span data-ttu-id="2a789-118">它适用于 Visual Studio 2015 和 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="2a789-118">It works on Visual Studio 2015 and Visual Studio 2017.</span></span> <span data-ttu-id="2a789-119">可以在 Visual Studio 中转到“分析” > “可移植性分析器设置”并选择目标平台，对可移植性分析器进行配置。</span><span class="sxs-lookup"><span data-stu-id="2a789-119">You can configure it in Visual Studio via **Analyze** > **Portability Analyzer Settings** and select your Target Platforms.</span></span>

![可移植性屏幕截图](./media/portability-analyzer/portability-screenshot.png)

<span data-ttu-id="2a789-121">若要分析整个项目，请在“解决方案资源管理器”中右键单击该项目，然后选择“分析程序集可移植性”。</span><span class="sxs-lookup"><span data-stu-id="2a789-121">To analyze your entire project, right-click on your project in **Solution Explorer** and select **Analyze Assembly Portability**.</span></span> <span data-ttu-id="2a789-122">也可以转到“分析”菜单，选择“分析程序集可移植性”。</span><span class="sxs-lookup"><span data-stu-id="2a789-122">Otherwise, go to the **Analyze** menu and select **Analyze Assembly Portability**.</span></span> <span data-ttu-id="2a789-123">在该位置选择项目的可执行文件或 DLL。</span><span class="sxs-lookup"><span data-stu-id="2a789-123">From there, select your project’s executable or DLL.</span></span>

![可移植性解决方案资源管理器](./media/portability-analyzer/portability-solution-explorer.png)

<span data-ttu-id="2a789-125">运行分析后，可以看到 .NET 可移植性报告。</span><span class="sxs-lookup"><span data-stu-id="2a789-125">After running the analysis, you will see your .NET Portability Report.</span></span> <span data-ttu-id="2a789-126">只有不受目标平台支持的类型才显示在列表中，可在“错误列表”的“消息”选项卡中查看建议。</span><span class="sxs-lookup"><span data-stu-id="2a789-126">Only types that are unsupported by a target platform appear in the list and you can review recommendations in the **Messages** tab in the **Error List**.</span></span> <span data-ttu-id="2a789-127">还可以直接从“消息”选项卡跳转到问题区域。</span><span class="sxs-lookup"><span data-stu-id="2a789-127">You can also jump to problem areas directly from the **Messages** tab.</span></span>

![可移植性报告](./media/portability-analyzer/portability-report.png)

<span data-ttu-id="2a789-129">不想使用 Visual Studio？</span><span class="sxs-lookup"><span data-stu-id="2a789-129">Don’t want to use Visual Studio?</span></span> <span data-ttu-id="2a789-130">还可以从命令提示符使用可移植性分析器。</span><span class="sxs-lookup"><span data-stu-id="2a789-130">You can also use the Portability Analyzer from the command prompt.</span></span> <span data-ttu-id="2a789-131">仅下载 [API 可移植性分析器](http://www.microsoft.com/download/details.aspx?id=42678)。</span><span class="sxs-lookup"><span data-stu-id="2a789-131">Just download the [API Portability Analyzer](http://www.microsoft.com/download/details.aspx?id=42678).</span></span>

*   <span data-ttu-id="2a789-132">键入以下命令即可分析当前目录：`\...\ApiPort.exe analyze -f .`</span><span class="sxs-lookup"><span data-stu-id="2a789-132">Type the following command to analyze the current directory: `\...\ApiPort.exe analyze -f .`</span></span>
*   <span data-ttu-id="2a789-133">若要分析特定的 .dll 文件列表，请键入以下命令：`\...\ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`</span><span class="sxs-lookup"><span data-stu-id="2a789-133">To analyze a specific list of .dll files, type the following command: `\...\ApiPort.exe analyze -f first.dll -f second.dll -f third.dll`</span></span>

<span data-ttu-id="2a789-134">.NET 可移植性报告以 Excel 文件 (.xlsx) 格式保存在当前目录中。</span><span class="sxs-lookup"><span data-stu-id="2a789-134">Your .NET Portability Report is saved as an Excel file (*.xlsx*) in your current directory.</span></span> <span data-ttu-id="2a789-135">Excel 工作簿中的“详细信息”选项卡包含详细信息。</span><span class="sxs-lookup"><span data-stu-id="2a789-135">The **Details** tab in the Excel Workbook contains more information.</span></span>

<span data-ttu-id="2a789-136">有关 .NET 可移植性分析器的详细信息，请访问 [GitHub 文档](https://github.com/Microsoft/dotnet-apiport#documentation)和[简要了解 .NET 可移植性分析器](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer)第 9 频道视频。</span><span class="sxs-lookup"><span data-stu-id="2a789-136">For more information on the .NET Portability Analyzer, visit the [GitHub documentation](https://github.com/Microsoft/dotnet-apiport#documentation) and [A Brief Look at the .NET Portability Analyzer](https://channel9.msdn.com/Blogs/Seth-Juarez/A-Brief-Look-at-the-NET-Portability-Analyzer) Channel 9 video.</span></span>

