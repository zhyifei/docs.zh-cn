---
title: 剪裁独立应用程序
description: 了解如何剪裁独立应用以减小其大小。 .NET Core 将运行时与独立发布的应用捆绑在一起，通常包含比所需更多的运行时。
author: jamshedd
ms.author: jamshedd
ms.date: 01/23/2020
ms.openlocfilehash: 5206ca255c500b382402ac4e7dd3300b7face1cf
ms.sourcegitcommit: 45cced471d59d5dac3f0c92abc9d4849716098a2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2020
ms.locfileid: "80665619"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="b0789-104">剪裁独立部署和可执行文件</span><span class="sxs-lookup"><span data-stu-id="b0789-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="b0789-105">当发布独立应用程序时，.NET Core 运行时会与该应用程序捆绑在一起。</span><span class="sxs-lookup"><span data-stu-id="b0789-105">When publishing an application self-contained, the .NET Core runtime is bundled together with the application.</span></span> <span data-ttu-id="b0789-106">此捆绑包向打包的应用程序添加了大量内容。</span><span class="sxs-lookup"><span data-stu-id="b0789-106">This bundling adds a significant amount of content to your packaged application.</span></span>

<span data-ttu-id="b0789-107">在涉及到应用程序部署时，大小通常是一个重要因素。</span><span class="sxs-lookup"><span data-stu-id="b0789-107">When it comes to deploying your application, size is often an important factor.</span></span> <span data-ttu-id="b0789-108">使包应用程序的大小尽可能小通常是应用程序开发者的目标。</span><span class="sxs-lookup"><span data-stu-id="b0789-108">Keeping the size of the package application as small as possible is typically a goal for application developers.</span></span>

<span data-ttu-id="b0789-109">根据应用程序的复杂性，运行应用程序只需要运行时的子集。</span><span class="sxs-lookup"><span data-stu-id="b0789-109">Depending on the complexity of the application, only a subset of the runtime is required to run the application.</span></span> <span data-ttu-id="b0789-110">不需要这些未使用的运行时部分，可以从打包的应用程序中进行剪裁。</span><span class="sxs-lookup"><span data-stu-id="b0789-110">These unused parts of the runtime are unnecessary and can be trimmed from the packaged application.</span></span>

> [!NOTE]
> <span data-ttu-id="b0789-111">剪裁是 .NET Core 3.1 中的实验性功能，只能用于独立发布的应用程序  。</span><span class="sxs-lookup"><span data-stu-id="b0789-111">Trimming is an experimental feature in .NET Core 3.1 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="trim-your-application"></a><span data-ttu-id="b0789-112">剪裁应用程序</span><span class="sxs-lookup"><span data-stu-id="b0789-112">Trim your application</span></span>

<span data-ttu-id="b0789-113">下面的示例演示如何使用 [dotnet publish](../tools/dotnet-publish.md) 命令剪裁应用程序：</span><span class="sxs-lookup"><span data-stu-id="b0789-113">The following example shows how to trim your application using the [dotnet publish](../tools/dotnet-publish.md) command:</span></span>

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true /p:PublishSingleFile=false /p:PublishTrimmed=true
```

<span data-ttu-id="b0789-114">剪裁功能的工作方式是检查应用程序二进制文件，以发现和生成所需运行时程序集的关系图。</span><span class="sxs-lookup"><span data-stu-id="b0789-114">The trimming feature works by examining the application binaries to discover and build a graph of the required runtime assemblies.</span></span> <span data-ttu-id="b0789-115">未引用的其余运行时程序集会被剪裁。</span><span class="sxs-lookup"><span data-stu-id="b0789-115">The remaining runtime assemblies that aren't referenced are trimmed.</span></span>

## <a name="trimming-issues-when-using-reflection"></a><span data-ttu-id="b0789-116">使用反射时的剪裁问题</span><span class="sxs-lookup"><span data-stu-id="b0789-116">Trimming issues when using reflection</span></span>

<span data-ttu-id="b0789-117">在某些情况下，剪裁功能无法检测到引用。</span><span class="sxs-lookup"><span data-stu-id="b0789-117">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="b0789-118">例如，使用反射的应用程序可能会遇到此问题，因为只有在运行时才知道程序集的依赖项。</span><span class="sxs-lookup"><span data-stu-id="b0789-118">For example, an application that uses reflection could run into this issue because the dependency on the assembly will only be known at run time.</span></span>

<span data-ttu-id="b0789-119">仅当反射使用依赖于未直接引用的运行时程序集时，剪裁才会成为问题。</span><span class="sxs-lookup"><span data-stu-id="b0789-119">Trimming is only a problem if the reflection usage depends on a runtime assembly that isn't referenced directly.</span></span> <span data-ttu-id="b0789-120">请记住，应用程序代码可能未直接使用反射，但是所引用的第三方程序集可能在使用反射。</span><span class="sxs-lookup"><span data-stu-id="b0789-120">Keep in mind that your application code may not be using reflection directly, but a third-party assembly you're referencing may be using it.</span></span>

<span data-ttu-id="b0789-121">当代码通过反射引用某个 API，而你不希望链接器剪裁包含该 API 的程序集时，可以修改项目文件以从剪裁过程中排除该程序集。</span><span class="sxs-lookup"><span data-stu-id="b0789-121">When the code is referencing an API through reflection and you don't want the linker to trim the assembly that contains that API, you can modify your project file to exclude the assembly from the trimming process.</span></span> <span data-ttu-id="b0789-122">下面的示例演示如何防止剪裁名为 `System.Security` 的程序集：</span><span class="sxs-lookup"><span data-stu-id="b0789-122">The following example shows how to prevent an assembly called `System.Security` from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="see-also"></a><span data-ttu-id="b0789-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0789-123">See also</span></span>

- [<span data-ttu-id="b0789-124">.NET Core 应用程序部署</span><span class="sxs-lookup"><span data-stu-id="b0789-124">.NET Core application deployment</span></span>](index.md)
