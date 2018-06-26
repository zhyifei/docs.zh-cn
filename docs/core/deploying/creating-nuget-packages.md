---
title: 使用跨平台工具创建 NuGet 包
description: 了解如何使用“dotnet pack”命令创建 NuGet 包。
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.technology: dotnet-cli
ms.openlocfilehash: 6be94c2e2cef443f69b2d6df7c2d490cb1fb629d
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207761"
---
# <a name="how-to-create-a-nuget-package-with-cross-platform-tools"></a><span data-ttu-id="e928b-103">如何使用跨平台工具创建 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="e928b-103">How to Create a NuGet Package with Cross Platform Tools</span></span>

> [!NOTE]
> <span data-ttu-id="e928b-104">下例是关于使用 Unix 的命令行。</span><span class="sxs-lookup"><span data-stu-id="e928b-104">The following shows command-line samples using Unix.</span></span>  <span data-ttu-id="e928b-105">此处显示的 `dotnet pack` 命令工作方式与在 Windows 上相同。</span><span class="sxs-lookup"><span data-stu-id="e928b-105">The `dotnet pack` command as shown here works the same way on Windows.</span></span>

<span data-ttu-id="e928b-106">对于 .NET Core 1.0，所有库都应以 NuGet 包方式发布。</span><span class="sxs-lookup"><span data-stu-id="e928b-106">For .NET Core 1.0, libraries are expected to be distributed as NuGet packages.</span></span>  <span data-ttu-id="e928b-107">实际上，这是所有 .NET 标准库的发布和使用方式。</span><span class="sxs-lookup"><span data-stu-id="e928b-107">This is in fact how all of the .NET Standard libraries are distributed and consumed.</span></span>  <span data-ttu-id="e928b-108">可以使用 `dotnet pack` 命令轻松实现此操作。</span><span class="sxs-lookup"><span data-stu-id="e928b-108">This is most easily done with the `dotnet pack` command.</span></span>

<span data-ttu-id="e928b-109">假设你刚编写了一个很棒的新库，并想通过 NuGet 发布。</span><span class="sxs-lookup"><span data-stu-id="e928b-109">Imagine that you just wrote an awesome new library that you would like to distribute over NuGet.</span></span>  <span data-ttu-id="e928b-110">你就可以使用跨平台工具创建一个 NuGet 包，完全照做就行！</span><span class="sxs-lookup"><span data-stu-id="e928b-110">You can create a NuGet package with cross platform tools to do exactly that!</span></span>  <span data-ttu-id="e928b-111">下例假定使用一个名为 **SuperAwesomeLibrary** 的库，该库以 `netstandard1.0` 为目标。</span><span class="sxs-lookup"><span data-stu-id="e928b-111">The following example assumes a library called **SuperAwesomeLibrary** which targets `netstandard1.0`.</span></span>

<span data-ttu-id="e928b-112">如果存在可传递的依赖项，也就是说，如果一个项目依赖于另一个项目，在创建 NuGet 包前，则需要确保使用 `dotnet restore` 还原整个解决方案的包。</span><span class="sxs-lookup"><span data-stu-id="e928b-112">If you have transitive dependencies; that is, a project which depends on another project, you'll need to make sure to restore packages for your entire solution with the `dotnet restore` command before creating a NuGet package.</span></span>  <span data-ttu-id="e928b-113">否则将导致 `dotnet pack` 命令不能正常运行。</span><span class="sxs-lookup"><span data-stu-id="e928b-113">Failing to do so will result in the `dotnet pack` command to not work properly.</span></span>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]


<span data-ttu-id="e928b-114">确认包已还原后，可以导航到库所在的目录：</span><span class="sxs-lookup"><span data-stu-id="e928b-114">After ensuring packages are restored, you can navigate to the directory where a library lives:</span></span>

`$ cd src/SuperAwesomeLibrary`

<span data-ttu-id="e928b-115">然后，只需在命令行中输入一个命令：</span><span class="sxs-lookup"><span data-stu-id="e928b-115">Then it's just a single command from the command line:</span></span>
    
`$ dotnet pack`

<span data-ttu-id="e928b-116">`/bin/Debug` 文件夹现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="e928b-116">Your `/bin/Debug` folder will now look like this:</span></span>

```
$ ls bin/Debug

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="e928b-117">请注意，这将生成能够进行调试的包。</span><span class="sxs-lookup"><span data-stu-id="e928b-117">Note that this will produce a package which is capable of being debugged.</span></span>  <span data-ttu-id="e928b-118">如果想要生成二进制文件版本的 NuGet 包，只需添加 `-c`/`--configuration` 开关并使用 `release` 作为参数。</span><span class="sxs-lookup"><span data-stu-id="e928b-118">If you want to build a NuGet package with release binaries, all you need to do is add the `-c`/`--configuration` switch and use `release` as the argument.</span></span>

`$ dotnet pack --configuration release`

<span data-ttu-id="e928b-119">`/bin` 文件夹现在将包含一个 `release` 文件夹，后者包含的 NuGet 包为二进制文件版本：</span><span class="sxs-lookup"><span data-stu-id="e928b-119">Your `/bin` folder will now have a `release` folder containing your NuGet package with release binaries:</span></span>

```
$ ls bin/release

netstandard1.0/
SuperAwesomeLibrary.1.0.0.nupkg
SuperAwesomeLibrary.1.0.0.symbols.nupkg
```

<span data-ttu-id="e928b-120">因此，现在可以使用此必需的文件发布 NuGet 包了！</span><span class="sxs-lookup"><span data-stu-id="e928b-120">And now you have the necessary files to publish a NuGet package!</span></span>

## <a name="dont-confuse-dotnet-pack-with-dotnet-publish"></a><span data-ttu-id="e928b-121">不要混淆 `dotnet pack` 和 `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="e928b-121">Don't confuse `dotnet pack` with `dotnet publish`</span></span>

<span data-ttu-id="e928b-122">务必注意，不是任何时候都涉及 `dotnet publish` 命令。</span><span class="sxs-lookup"><span data-stu-id="e928b-122">It is important to note that at no point is the `dotnet publish` command involved.</span></span>  <span data-ttu-id="e928b-123">`dotnet publish` 命令用于在同一个包中部署具有所有依赖项的应用程序 - 而不是用于生成通过 NuGet 发布和使用的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="e928b-123">The `dotnet publish` command is for deploying applications with all of their dependencies in the same bundle -  not for generating a NuGet package to be distributed and consumed via NuGet.</span></span>
