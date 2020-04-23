---
title: 剪裁独立应用程序
description: 了解如何剪裁独立应用以减小其大小。 .NET Core 将运行时与独立发布的应用捆绑在一起，通常包含比所需更多的运行时。
author: jamshedd
ms.author: jamshedd
ms.date: 04/03/2020
ms.openlocfilehash: bb8ac88c5e16b7fd20a7670e4ad76dbe4b44da1b
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242892"
---
# <a name="trim-self-contained-deployments-and-executables"></a><span data-ttu-id="7fc95-104">剪裁独立部署和可执行文件</span><span class="sxs-lookup"><span data-stu-id="7fc95-104">Trim self-contained deployments and executables</span></span>

<span data-ttu-id="7fc95-105">当发布独立应用程序时，.NET Core 运行时会与该应用程序捆绑在一起。</span><span class="sxs-lookup"><span data-stu-id="7fc95-105">When publishing an application self-contained, the .NET Core runtime is bundled together with the application.</span></span> <span data-ttu-id="7fc95-106">此捆绑包向打包的应用程序添加了大量内容。</span><span class="sxs-lookup"><span data-stu-id="7fc95-106">This bundling adds a significant amount of content to your packaged application.</span></span> <span data-ttu-id="7fc95-107">在涉及到应用程序部署时，大小通常是一个重要因素。</span><span class="sxs-lookup"><span data-stu-id="7fc95-107">When it comes to deploying your application, size is often an important factor.</span></span> <span data-ttu-id="7fc95-108">使包应用程序的大小尽可能小通常是应用程序开发者的目标。</span><span class="sxs-lookup"><span data-stu-id="7fc95-108">Keeping the size of the package application as small as possible is typically a goal for application developers.</span></span>

<span data-ttu-id="7fc95-109">根据应用程序的复杂性，运行应用程序只需要运行时的子集。</span><span class="sxs-lookup"><span data-stu-id="7fc95-109">Depending on the complexity of the application, only a subset of the runtime is required to run the application.</span></span> <span data-ttu-id="7fc95-110">不需要这些未使用的运行时部分，可以从打包的应用程序中进行剪裁。</span><span class="sxs-lookup"><span data-stu-id="7fc95-110">These unused parts of the runtime are unnecessary and can be trimmed from the packaged application.</span></span>

<span data-ttu-id="7fc95-111">剪裁功能的工作方式是检查应用程序二进制文件，以发现和生成所需运行时程序集的关系图。</span><span class="sxs-lookup"><span data-stu-id="7fc95-111">The trimming feature works by examining the application binaries to discover and build a graph of the required runtime assemblies.</span></span> <span data-ttu-id="7fc95-112">未引用的其余运行时程序集会被排除。</span><span class="sxs-lookup"><span data-stu-id="7fc95-112">The remaining runtime assemblies that aren't referenced are excluded.</span></span>

> [!NOTE]
> <span data-ttu-id="7fc95-113">剪裁是 .NET Core 3.1 中的实验性功能，只能用于独立发布的应用程序  。</span><span class="sxs-lookup"><span data-stu-id="7fc95-113">Trimming is an experimental feature in .NET Core 3.1 and is _only_ available to applications that are published self-contained.</span></span>

## <a name="prevent-assemblies-from-being-trimmed"></a><span data-ttu-id="7fc95-114">防止剪裁程序集</span><span class="sxs-lookup"><span data-stu-id="7fc95-114">Prevent assemblies from being trimmed</span></span>

<span data-ttu-id="7fc95-115">在某些情况下，剪裁功能无法检测到引用。</span><span class="sxs-lookup"><span data-stu-id="7fc95-115">There are scenarios in which the trimming functionality will fail to detect references.</span></span> <span data-ttu-id="7fc95-116">例如，当应用程序或应用程序引用的库在运行时程序集上使用反射时，都不会直接引用该程序集。</span><span class="sxs-lookup"><span data-stu-id="7fc95-116">For example, when reflection is used on a runtime assembly, either by your application or a library that is referenced by your application, the assembly isn't directly referenced.</span></span> <span data-ttu-id="7fc95-117">剪裁不知道这些间接引用，并将从已发布文件夹中排除库。</span><span class="sxs-lookup"><span data-stu-id="7fc95-117">Trimming is unaware of these indirect references and would exclude the library from the published folder.</span></span>

<span data-ttu-id="7fc95-118">当代码通过反射间接引用程序集时，可以防止使用 `<TrimmerRootAssembly>` 设置剪裁该程序集。</span><span class="sxs-lookup"><span data-stu-id="7fc95-118">When the code is indirectly referencing an assembly through reflection, you can prevent the assembly from being trimmed with the `<TrimmerRootAssembly>` setting.</span></span> <span data-ttu-id="7fc95-119">下面的示例演示如何防止剪裁名为 `System.Security` 程序集的程序集：</span><span class="sxs-lookup"><span data-stu-id="7fc95-119">The following example shows how to prevent an assembly called `System.Security` assembly from being trimmed:</span></span>

```xml
<ItemGroup>
    <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="trim-your-app---cli"></a><span data-ttu-id="7fc95-120">剪裁应用 - CLI</span><span class="sxs-lookup"><span data-stu-id="7fc95-120">Trim your app - CLI</span></span>

<span data-ttu-id="7fc95-121">使用 [dotnet publish](../tools/dotnet-publish.md) 命令剪裁应用程序。</span><span class="sxs-lookup"><span data-stu-id="7fc95-121">Trim your application using the [dotnet publish](../tools/dotnet-publish.md) command.</span></span> <span data-ttu-id="7fc95-122">发布应用时，请设定以下三个设置：</span><span class="sxs-lookup"><span data-stu-id="7fc95-122">When you publish your app, set the following three settings:</span></span>

- <span data-ttu-id="7fc95-123">发布为自包含：`--self-contained true`</span><span class="sxs-lookup"><span data-stu-id="7fc95-123">Publish as self-contained: `--self-contained true`</span></span>
- <span data-ttu-id="7fc95-124">禁用单个文件发布：`-p:PublishSingleFile=false`</span><span class="sxs-lookup"><span data-stu-id="7fc95-124">Disable single-file publishing: `-p:PublishSingleFile=false`</span></span>
- <span data-ttu-id="7fc95-125">启用剪裁：`p:PublishTrimmed=true`</span><span class="sxs-lookup"><span data-stu-id="7fc95-125">Enable trimming: `p:PublishTrimmed=true`</span></span>

<span data-ttu-id="7fc95-126">以下示例将 Windows 10 应用发布为自包含，并剪裁输出。</span><span class="sxs-lookup"><span data-stu-id="7fc95-126">The following example publishes an app for Windows 10 as self-contained and trims the output.</span></span>

```dotnetcli
dotnet publish -c Release -r win10-x64 --self-contained true -p:PublishSingleFile=false -p:PublishTrimmed=true
```

<span data-ttu-id="7fc95-127">有关详细信息，请参阅[使用 .NET Core CLI 发布 .NET Core 应用](deploy-with-cli.md)。</span><span class="sxs-lookup"><span data-stu-id="7fc95-127">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="trim-your-app---visual-studio"></a><span data-ttu-id="7fc95-128">剪裁应用 - Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7fc95-128">Trim your app - Visual Studio</span></span>

<span data-ttu-id="7fc95-129">Visual Studio 创建可重用的发布配置文件，用于控制应用程序的发布方式。</span><span class="sxs-lookup"><span data-stu-id="7fc95-129">Visual Studio creates reusable publishing profiles that control how your application is published.</span></span>

01. <span data-ttu-id="7fc95-130">在“解决方案资源管理器”窗格中，右键单击要发布的项目  。</span><span class="sxs-lookup"><span data-stu-id="7fc95-130">On the **Solution Explorer** pane, right-click on the project you want to publish.</span></span> <span data-ttu-id="7fc95-131">选择“发布…”  。</span><span class="sxs-lookup"><span data-stu-id="7fc95-131">Select **Publish...**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-solution-explorer.png" alt-text="解决方案资源管理器，其中右键单击菜单突出显示了“发布”选项。":::

    <span data-ttu-id="7fc95-133">如果还没有发布配置文件，请按照说明创建一个并选择“文件夹”目标类型  。</span><span class="sxs-lookup"><span data-stu-id="7fc95-133">If you don't already have a publishing profile, follow the instructions to create one and choose the **Folder** target-type.</span></span>

01. <span data-ttu-id="7fc95-134">选择“编辑”  。</span><span class="sxs-lookup"><span data-stu-id="7fc95-134">Choose **Edit**.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-edit-settings.png" alt-text="带有“编辑”按钮的 Visual Studio 发布配置文件。":::

01. <span data-ttu-id="7fc95-136">在“配置文件设置”对话框中，设置以下选项  ：</span><span class="sxs-lookup"><span data-stu-id="7fc95-136">In the **Profile settings** dialog, set the following options:</span></span>

    - <span data-ttu-id="7fc95-137">将“部署模式”设置为“自包含”   。</span><span class="sxs-lookup"><span data-stu-id="7fc95-137">Set **Deployment mode** to **Self-contained**.</span></span>
    - <span data-ttu-id="7fc95-138">将“目标运行时”设置为要发布到的平台  。</span><span class="sxs-lookup"><span data-stu-id="7fc95-138">Set **Target runtime** to the platform you want to publish to.</span></span>
    - <span data-ttu-id="7fc95-139">选择“剪裁未使用的程序集(预览版)”  。</span><span class="sxs-lookup"><span data-stu-id="7fc95-139">Select **Trim unused assemblies (in preview)**.</span></span>

    <span data-ttu-id="7fc95-140">选择“保存”保存设置并返回到“发布”对话框   。</span><span class="sxs-lookup"><span data-stu-id="7fc95-140">Choose **Save** to save the settings and return to the **Publish** dialog.</span></span>

    :::image type="content" source="media/trim-self-contained/visual-studio-publish-properties.png" alt-text="“配置文件设置”对话框，其中突出显示了“部署模式”、“目标运行时”和“剪裁未使用的程序集”选项。":::

01. <span data-ttu-id="7fc95-142">选择“发布”以发布剪裁过的应用  。</span><span class="sxs-lookup"><span data-stu-id="7fc95-142">Choose **Publish** to publish your app trimmed.</span></span>

<span data-ttu-id="7fc95-143">有关详细信息，请参阅[使用 Visual Studio 发布 .NET Core 应用](deploy-with-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="7fc95-143">For more information, see [Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>

## <a name="trim-your-app---visual-studio-for-mac"></a><span data-ttu-id="7fc95-144">剪裁应用 - Visual Studio for Mac</span><span class="sxs-lookup"><span data-stu-id="7fc95-144">Trim your app - Visual Studio for Mac</span></span>

<span data-ttu-id="7fc95-145">Visual Studio for Mac 不提供在发布期间剪裁应用的选项。</span><span class="sxs-lookup"><span data-stu-id="7fc95-145">Visual Studio for Mac doesn't provide options to trim your app during publish.</span></span> <span data-ttu-id="7fc95-146">你需要按照[剪裁应用 - CLI](#trim-your-app---cli) 部分的说明手动发布。</span><span class="sxs-lookup"><span data-stu-id="7fc95-146">You'll need to publish manually by following the instructions from the [Trim your app - CLI](#trim-your-app---cli) section.</span></span> <span data-ttu-id="7fc95-147">有关详细信息，请参阅[使用 .NET Core CLI 发布 .NET Core 应用](deploy-with-cli.md)。</span><span class="sxs-lookup"><span data-stu-id="7fc95-147">For more information, see [Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7fc95-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="7fc95-148">See also</span></span>

- <span data-ttu-id="7fc95-149">[.NET Core 应用程序部署](index.md)。</span><span class="sxs-lookup"><span data-stu-id="7fc95-149">[.NET Core application deployment](index.md).</span></span>
- <span data-ttu-id="7fc95-150">[使用 .NET Core CLI 发布 .NET Core 应用](deploy-with-cli.md)。</span><span class="sxs-lookup"><span data-stu-id="7fc95-150">[Publish .NET Core apps with .NET Core CLI](deploy-with-cli.md).</span></span>
- <span data-ttu-id="7fc95-151">[使用 Visual Studio 发布 .NET Core 应用](deploy-with-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="7fc95-151">[Publish .NET Core apps with Visual Studio](deploy-with-vs.md).</span></span>
- <span data-ttu-id="7fc95-152">[dotnet publish 命令](../tools/dotnet-publish.md)。</span><span class="sxs-lookup"><span data-stu-id="7fc95-152">[dotnet publish command](../tools/dotnet-publish.md).</span></span>
