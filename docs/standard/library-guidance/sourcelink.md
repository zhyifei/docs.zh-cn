---
title: SourceLink 和.NET 库
description: 有关使用 SourceLink 提高调试.NET 库的最佳做法建议。
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: fa4af47eaa5dd1510640c2bf0ebb2187b56efae0
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49369796"
---
# <a name="sourcelink"></a><span data-ttu-id="cb195-103">SourceLink</span><span class="sxs-lookup"><span data-stu-id="cb195-103">SourceLink</span></span>

<span data-ttu-id="cb195-104">SourceLink 是一种允许从 NuGet 由开发人员的.NET 程序集的源代码调试技术。</span><span class="sxs-lookup"><span data-stu-id="cb195-104">SourceLink is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="cb195-105">SourceLink 执行时创建 NuGet 包，然后将嵌入在程序集和包的源控件元数据。</span><span class="sxs-lookup"><span data-stu-id="cb195-105">SourceLink executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="cb195-106">下载包，并具有 SourceLink 在 Visual Studio 中启用开发人员可以单步执行它的源代码。</span><span class="sxs-lookup"><span data-stu-id="cb195-106">Developers who download the package and have SourceLink enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="cb195-107">SourceLink 提供源控件元数据来创建出色的调试体验。</span><span class="sxs-lookup"><span data-stu-id="cb195-107">SourceLink provides source control metadata to create a great debugging experience.</span></span>

## <a name="sourcelink-demo"></a><span data-ttu-id="cb195-108">SourceLink 演示</span><span class="sxs-lookup"><span data-stu-id="cb195-108">SourceLink demo</span></span>

> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-sourcelink"></a><span data-ttu-id="cb195-109">使用 SourceLink</span><span class="sxs-lookup"><span data-stu-id="cb195-109">Using SourceLink</span></span>

<span data-ttu-id="cb195-110">可以上找到用于使用 SourceLink 说明[dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="cb195-110">Instructions for using SourceLink can be found on the [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="cb195-111">可以使用[NuGet 包资源管理器](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer)确认 SourceLink 元数据已成功嵌入包中。</span><span class="sxs-lookup"><span data-stu-id="cb195-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the SourceLink metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="cb195-112">检查`Repository`元数据是否存在具有注释标识符和.pdb 文件位于与每个目标的.dll。</span><span class="sxs-lookup"><span data-stu-id="cb195-112">Check the `Repository` metadata is present with a comment identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="cb195-113">![在 NuGet 包资源管理器的 SourceLink](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink 在 NuGet 包资源管理器")</span><span class="sxs-lookup"><span data-stu-id="cb195-113">![SourceLink in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "SourceLink in NuGet Package Explorer")</span></span>

<span data-ttu-id="cb195-114">**请考虑 ✔️**使用 SourceLink 将源控件元数据添加到你的程序集和 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="cb195-114">**✔️ CONSIDER** using SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

<span data-ttu-id="cb195-115">**请考虑 ✔️**包括 NuGet 包中的 PDB 文件。</span><span class="sxs-lookup"><span data-stu-id="cb195-115">**✔️ CONSIDER** including PDB files in the NuGet package.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="cb195-116">[上一页](./dependencies.md)
[下一页](./publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="cb195-116">[Previous](./dependencies.md)
[Next](./publish-nuget-package.md)</span></span>
