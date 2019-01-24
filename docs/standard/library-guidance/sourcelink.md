---
title: SourceLink 和 .NET 库
description: 有关使用 SourceLink 改进 .NET 库调试的最佳做法建议。
author: jamesnk
ms.author: mairaw
ms.date: 01/15/2019
ms.openlocfilehash: be97f868e2fcfc6c45e4bbac45b033f8914f4d99
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333533"
---
# <a name="sourcelink"></a><span data-ttu-id="5b93f-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="5b93f-103">SourceLink</span></span>

<span data-ttu-id="5b93f-104">SourceLink 是一种使开发人员可以从 NuGet 对 .NET 程序集进行源代码调试的技术。</span><span class="sxs-lookup"><span data-stu-id="5b93f-104">SourceLink is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="5b93f-105">SourceLink 在创建 NuGet 包时执行，然后将源代码管理元数据嵌入在程序集和包中。</span><span class="sxs-lookup"><span data-stu-id="5b93f-105">SourceLink executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="5b93f-106">下载包并且在 Visual Studio 中启用了 SourceLink 的开发人员可以单步执行其源代码。</span><span class="sxs-lookup"><span data-stu-id="5b93f-106">Developers who download the package and have SourceLink enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="5b93f-107">SourceLink 提供源代码管理元数据来创造出色的调试体验。</span><span class="sxs-lookup"><span data-stu-id="5b93f-107">SourceLink provides source control metadata to create a great debugging experience.</span></span>

## <a name="sourcelink-demo"></a><span data-ttu-id="5b93f-108">SourceLink 演示</span><span class="sxs-lookup"><span data-stu-id="5b93f-108">SourceLink demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a><span data-ttu-id="5b93f-109">使用 SourceLink</span><span class="sxs-lookup"><span data-stu-id="5b93f-109">Using SourceLink</span></span>

<span data-ttu-id="5b93f-110">可以在 [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub 存储库上找到有关使用 SourceLink 的说明。</span><span class="sxs-lookup"><span data-stu-id="5b93f-110">Instructions for using SourceLink can be found on the [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="5b93f-111">可以使用 [NuGet 包资源管理器](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer)以确认 SourceLink 元数据是否已成功嵌入在包中。</span><span class="sxs-lookup"><span data-stu-id="5b93f-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the SourceLink metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="5b93f-112">检查 `Repository` 元数据是否存在并具有注释标识符，以及 .pdb 文件是否与每个目标的 .dll 放置在一起。</span><span class="sxs-lookup"><span data-stu-id="5b93f-112">Check the `Repository` metadata is present with a comment identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="5b93f-113">![NuGet 包资源管理器中的 SourceLink](./media/sourcelink/nuget-package-explorer-sourcelink.png "NuGet 包资源管理器中的 SourceLink")</span><span class="sxs-lookup"><span data-stu-id="5b93f-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span></span>

<span data-ttu-id="5b93f-114">✔️ 请考虑使用 SourceLink 将源代码管理元数据添加到程序集和 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="5b93f-114">**✔️ CONSIDER** using SourceLink to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="5b93f-115">可以通过将调试器特性添加到类型来进一步增强开发人员的调试体验。</span><span class="sxs-lookup"><span data-stu-id="5b93f-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
> * <span data-ttu-id="5b93f-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> 可以自定义类或字段在调试器变量窗口中的显示方式。</span><span class="sxs-lookup"><span data-stu-id="5b93f-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="5b93f-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> 指示调试器逐行执行代码，而不是单步执行代码。</span><span class="sxs-lookup"><span data-stu-id="5b93f-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="5b93f-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> 控制成员是否会显示在调试器变量窗口中以及其显示方式。</span><span class="sxs-lookup"><span data-stu-id="5b93f-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="5b93f-119">✔️ 请考虑发布符号文件 (`*.pdb`)。</span><span class="sxs-lookup"><span data-stu-id="5b93f-119">**✔️ CONSIDER** publishing symbol files (`*.pdb`).</span></span>

> <span data-ttu-id="5b93f-120">有关符号文件和符号包的详细信息，请参阅[符号包](./nuget.md#symbol-packages)。</span><span class="sxs-lookup"><span data-stu-id="5b93f-120">For more information about symbol files and symbol packages, see [Symbol packages](./nuget.md#symbol-packages).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5b93f-121">[上一页](dependencies.md)
>[下一页](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="5b93f-121">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>
