---
title: "运行时包存储区"
description: "本主题介绍了 .NET Core 使用的运行时包存储区和目标清单。"
keywords: ".NET, .NET Core, dotnet store, 运行时包存储区"
author: bleroy
ms.author: mairaw
ms.date: 08/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 9521d8b4-25fc-412b-a65b-4c975ebf6bfd
ms.workload: dotnetcore
ms.openlocfilehash: de1aa4d29abae6bc6c26c0686bafe9bd9cc10ee1
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="runtime-package-store"></a><span data-ttu-id="db548-104">运行时包存储区</span><span class="sxs-lookup"><span data-stu-id="db548-104">Runtime package store</span></span>

<span data-ttu-id="db548-105">自 .NET Core 2.0 起，可以根据目标环境中已知的一组包来打包和部署应用程序。</span><span class="sxs-lookup"><span data-stu-id="db548-105">Starting with .NET Core 2.0, it's possible to package and deploy apps against a known set of packages that exist in the target environment.</span></span> <span data-ttu-id="db548-106">优点是部署速度更快、磁盘空间占用少，并可以在某些情况下提升启动性能。</span><span class="sxs-lookup"><span data-stu-id="db548-106">The benefits are faster deployments, lower disk space use, and improved startup performance in some cases.</span></span>

<span data-ttu-id="db548-107">此功能实现为运行时包存储区，这是包在磁盘上的存储目录（通常情况下，在 macOS/Linux 上是 /usr/local/share/dotnet/store，在 Windows 上是 C:/Program Files/dotnet/store）。</span><span class="sxs-lookup"><span data-stu-id="db548-107">This feature is implemented as a *runtime package store*, which is a directory on disk where packages are stored (typically at */usr/local/share/dotnet/store* on macOS/Linux and *C:/Program Files/dotnet/store* on Windows).</span></span> <span data-ttu-id="db548-108">此目录下有各个体系结构和[目标框架](../../standard/frameworks.md)的子目录。</span><span class="sxs-lookup"><span data-stu-id="db548-108">Under this directory, there are subdirectories for architectures and [target frameworks](../../standard/frameworks.md).</span></span> <span data-ttu-id="db548-109">文件布局类似于[磁盘上的 NuGet 资产布局](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure)：</span><span class="sxs-lookup"><span data-stu-id="db548-109">The file layout is similar to the way that [NuGet assets are laid out on disk](/nuget/create-packages/supporting-multiple-target-frameworks#framework-version-folder-structure):</span></span>

<span data-ttu-id="db548-110">\dotnet</span><span class="sxs-lookup"><span data-stu-id="db548-110">\dotnet</span></span>   
<span data-ttu-id="db548-111">&nbsp;&nbsp;\store</span><span class="sxs-lookup"><span data-stu-id="db548-111">&nbsp;&nbsp;\store</span></span>   
<span data-ttu-id="db548-112">&nbsp;&nbsp;&nbsp;&nbsp;\x64</span><span class="sxs-lookup"><span data-stu-id="db548-112">&nbsp;&nbsp;&nbsp;&nbsp;\x64</span></span>   
<span data-ttu-id="db548-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="db548-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span></span>   
<span data-ttu-id="db548-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span><span class="sxs-lookup"><span data-stu-id="db548-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span></span>   
<span data-ttu-id="db548-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span><span class="sxs-lookup"><span data-stu-id="db548-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span></span>   
<span data-ttu-id="db548-116">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span><span class="sxs-lookup"><span data-stu-id="db548-116">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span></span>   
<span data-ttu-id="db548-117">&nbsp;&nbsp;&nbsp;&nbsp;\x86</span><span class="sxs-lookup"><span data-stu-id="db548-117">&nbsp;&nbsp;&nbsp;&nbsp;\x86</span></span>   
<span data-ttu-id="db548-118">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span><span class="sxs-lookup"><span data-stu-id="db548-118">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\netcoreapp2.0</span></span>   
<span data-ttu-id="db548-119">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span><span class="sxs-lookup"><span data-stu-id="db548-119">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.applicationinsights</span></span>   
<span data-ttu-id="db548-120">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span><span class="sxs-lookup"><span data-stu-id="db548-120">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\microsoft.aspnetcore</span></span>   
<span data-ttu-id="db548-121">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span><span class="sxs-lookup"><span data-stu-id="db548-121">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;...</span></span>   

<span data-ttu-id="db548-122">目标清单文件列出了运行时包存储区中的包。</span><span class="sxs-lookup"><span data-stu-id="db548-122">A *target manifest* file lists the packages in the runtime package store.</span></span> <span data-ttu-id="db548-123">开发者可以在发布应用程序时以此清单为目标。</span><span class="sxs-lookup"><span data-stu-id="db548-123">Developers can target this manifest when publishing their app.</span></span> <span data-ttu-id="db548-124">目标清单通常是由目标生产环境的所有者提供。</span><span class="sxs-lookup"><span data-stu-id="db548-124">The target manifest is typically provided by the owner of the targeted production environment.</span></span>

## <a name="preparing-a-runtime-environment"></a><span data-ttu-id="db548-125">准备运行时环境</span><span class="sxs-lookup"><span data-stu-id="db548-125">Preparing a runtime environment</span></span>

<span data-ttu-id="db548-126">运行时环境管理员可以生成运行时包存储区和相应的目标清单，从而优化应用程序，以加快部署速度并释放磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="db548-126">The administrator of a runtime environment can optimize apps for faster deployments and lower disk space use by building a runtime package store and the corresponding target manifest.</span></span>

<span data-ttu-id="db548-127">第一步是创建包存储区清单，用于列出运行时包存储区中的包。</span><span class="sxs-lookup"><span data-stu-id="db548-127">The first step is to create a *package store manifest* that lists the packages that compose the runtime package store.</span></span> <span data-ttu-id="db548-128">此文件格式与项目文件格式 (csproj) 兼容。</span><span class="sxs-lookup"><span data-stu-id="db548-128">This file format is compatible with the project file format (*csproj*).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="<NUGET_PACKAGE>" Version="<VERSION>" />
    <!-- Include additional packages here -->
  </ItemGroup>
</Project>
```

<span data-ttu-id="db548-129">**示例**</span><span class="sxs-lookup"><span data-stu-id="db548-129">**Example**</span></span>

<span data-ttu-id="db548-130">下面的示例包存储区清单 (packages.csproj) 用于将 [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) 和 [`Moq`](https://www.nuget.org/packages/moq/) 添加到运行时包存储区：</span><span class="sxs-lookup"><span data-stu-id="db548-130">The following example package store manifest (*packages.csproj*) is used to add [`Newtonsoft.Json`](https://www.nuget.org/packages/Newtonsoft.Json/) and [`Moq`](https://www.nuget.org/packages/moq/) to a runtime package store:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.3" />
    <PackageReference Include="Moq" Version="4.7.63" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="db548-131">通过执行 `dotnet store` 并指定包存储区清单、运行时和框架，预配运行时包存储区：</span><span class="sxs-lookup"><span data-stu-id="db548-131">Provision the runtime package store by executing `dotnet store` with the package store manifest, runtime, and framework:</span></span>

```console
dotnet store --manifest <PATH_TO_MANIFEST_FILE> --runtime <RUNTIME_IDENTIFIER> --framework <FRAMEWORK>
```

<span data-ttu-id="db548-132">**示例**</span><span class="sxs-lookup"><span data-stu-id="db548-132">**Example**</span></span>

```console
dotnet store --manifest packages.csproj --runtime win10-x64 --framework netcoreapp2.0 --framework-version 2.0.0
```

<span data-ttu-id="db548-133">可以将多个目标包存储区清单路径传递到一个 [`dotnet store`](../tools/dotnet-store.md) 命令，具体方法是在此命令中重复指定选项和路径。</span><span class="sxs-lookup"><span data-stu-id="db548-133">You can pass multiple target package store manifest paths to a single [`dotnet store`](../tools/dotnet-store.md) command by repeating the option and path in the command.</span></span>

<span data-ttu-id="db548-134">默认情况下，命令输出是在用户配置文件的 .dotnet/store 子目录下生成包存储区。</span><span class="sxs-lookup"><span data-stu-id="db548-134">By default, the output of the command is a package store under the *.dotnet/store* subdirectory of the user's profile.</span></span> <span data-ttu-id="db548-135">可以使用 `--output <OUTPUT_DIRECTORY>` 选项指定其他位置。</span><span class="sxs-lookup"><span data-stu-id="db548-135">You can specify a different location using the `--output <OUTPUT_DIRECTORY>` option.</span></span> <span data-ttu-id="db548-136">存储区的根目录包含目标清单 artifact.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="db548-136">The root directory of the store contains a target manifest *artifact.xml* file.</span></span> <span data-ttu-id="db548-137">此文件可供下载。如果应用程序创建者在发布时以这个存储区为目标，可以使用此文件。</span><span class="sxs-lookup"><span data-stu-id="db548-137">This file can be made available for download and be used by app authors who want to target this store when publishing.</span></span>

<span data-ttu-id="db548-138">**示例**</span><span class="sxs-lookup"><span data-stu-id="db548-138">**Example**</span></span>

<span data-ttu-id="db548-139">运行上一示例后生成以下 artifact.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="db548-139">The following *artifact.xml* file is produced after running the previous example.</span></span> <span data-ttu-id="db548-140">请注意，由于 [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) 是 `Moq` 的依赖项，因此 artifacts.xml 清单文件会自动包含并显示它。</span><span class="sxs-lookup"><span data-stu-id="db548-140">Note that [`Castle.Core`](https://www.nuget.org/packages/Castle.Core/) is a dependency of `Moq`, so it's included automatically and appears in the *artifacts.xml* manifest file.</span></span>

```xml
<StoreArtifacts>
  <Package Id="Newtonsoft.Json" Version="10.0.3" />
  <Package Id="Castle.Core" Version="4.1.0" />
  <Package Id="Moq" Version="4.7.63" />
</StoreArtifacts>
```

## <a name="publishing-an-app-against-a-target-manifest"></a><span data-ttu-id="db548-141">根据目标清单发布应用程序</span><span class="sxs-lookup"><span data-stu-id="db548-141">Publishing an app against a target manifest</span></span>

<span data-ttu-id="db548-142">如果磁盘上有目标清单文件，请在使用 [`dotnet publish`](../tools/dotnet-publish.md) 命令发布应用程序时指定此文件的路径：</span><span class="sxs-lookup"><span data-stu-id="db548-142">If you have a target manifest file on disk, you specify the path to the file when publishing your app with the [`dotnet publish`](../tools/dotnet-publish.md) command:</span></span>

```console
dotnet publish --manifest <PATH_TO_MANIFEST_FILE>
```

<span data-ttu-id="db548-143">**示例**</span><span class="sxs-lookup"><span data-stu-id="db548-143">**Example**</span></span>

```console
dotnet publish --manifest manifest.xml
```

<span data-ttu-id="db548-144">将生成的已发布应用程序部署到包含目标清单中所述包的环境内。</span><span class="sxs-lookup"><span data-stu-id="db548-144">You deploy the resulting published app to an environment that has the packages described in the target manifest.</span></span> <span data-ttu-id="db548-145">如果不这样做，应用程序便无法启动。</span><span class="sxs-lookup"><span data-stu-id="db548-145">Failing to do so results in the app failing to start.</span></span>

<span data-ttu-id="db548-146">发布应用程序时，通过重复指定选项和路径（例如，`--manifest manifest1.xml --manifest manifest2.xml`），可以指定多个目标清单。</span><span class="sxs-lookup"><span data-stu-id="db548-146">Specify multiple target manifests when publishing an app by repeating the option and path (for example, `--manifest manifest1.xml --manifest manifest2.xml`).</span></span> <span data-ttu-id="db548-147">这样，应用程序会进行剪裁，依据为提供给命令的目标清单文件中指定的包并集。</span><span class="sxs-lookup"><span data-stu-id="db548-147">When you do so, the app is trimmed for the union of packages specified in the target manifest files provided to the command.</span></span>

## <a name="specifying-target-manifests-in-the-project-file"></a><span data-ttu-id="db548-148">在项目文件中指定目标清单</span><span class="sxs-lookup"><span data-stu-id="db548-148">Specifying target manifests in the project file</span></span>

<span data-ttu-id="db548-149">除了使用 [`dotnet publish`](../tools/dotnet-publish.md) 命令指定目标清单之外，还可以在项目文件中将目标清单指定为 \<TargetManifestFiles> 标记下的路径分号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="db548-149">An alternative to specifying target manifests with the [`dotnet publish`](../tools/dotnet-publish.md) command is to specify them in the project file as a semicolon-separated list of paths under a **\<TargetManifestFiles>** tag.</span></span>

```xml
<PropertyGroup>
  <TargetManifestFiles>manifest1.xml;manifest2.xml</TargetManifestFiles>
</PropertyGroup>
```

<span data-ttu-id="db548-150">仅在应用程序的目标环境已知的情况下（如 .NET Core 项目），才在项目文件中指定目标清单。</span><span class="sxs-lookup"><span data-stu-id="db548-150">Specify the target manifests in the project file only when the target environment for the app is well-known, such as for .NET Core projects.</span></span> <span data-ttu-id="db548-151">开放源代码项目的情况有所不同。</span><span class="sxs-lookup"><span data-stu-id="db548-151">This isn't the case for open-source projects.</span></span> <span data-ttu-id="db548-152">开放源代码项目的用户通常将项目部署到不同的生产环境。</span><span class="sxs-lookup"><span data-stu-id="db548-152">The users of an open-source project typically deploy it to different production environments.</span></span> <span data-ttu-id="db548-153">这些生产环境通常都预安装了各组不同的包。</span><span class="sxs-lookup"><span data-stu-id="db548-153">These production environments generally have different sets of packages pre-installed.</span></span> <span data-ttu-id="db548-154">在这样的环境中，不能对目标清单作出假设，所以应使用 [`dotnet publish`](../tools/dotnet-publish.md) 的 `--manifest` 选项。</span><span class="sxs-lookup"><span data-stu-id="db548-154">You can't make assumptions about the target manifest in such environments, so you should use the `--manifest` option of [`dotnet publish`](../tools/dotnet-publish.md).</span></span>

## <a name="aspnet-core-implicit-store"></a><span data-ttu-id="db548-155">ASP.NET Core 隐式存储区</span><span class="sxs-lookup"><span data-stu-id="db548-155">ASP.NET Core implicit store</span></span>

<span data-ttu-id="db548-156">当 ASP.NET Core 应用程序部署为[从属框架部署 (FDD)](index.md#framework-dependent-deployments-fdd) 应用程序时，应用程序会隐式使用运行时包存储区功能。</span><span class="sxs-lookup"><span data-stu-id="db548-156">The runtime package store feature is used implicitly by an ASP.NET Core app when the app is deployed as a [framework-dependent deployment (FDD)](index.md#framework-dependent-deployments-fdd) app.</span></span> <span data-ttu-id="db548-157">[`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) 中的目标包括引用目标系统上的隐式包存储区的清单。</span><span class="sxs-lookup"><span data-stu-id="db548-157">The targets in [`Microsoft.NET.Sdk.Web`](https://github.com/aspnet/websdk) include manifests referencing the implicit package store on the target system.</span></span> <span data-ttu-id="db548-158">此外，如果 FDD 应用程序依赖 `Microsoft.AspNetCore.All` 包，则会生成仅包含应用程序及其资产的已发布应用程序，而不是 `Microsoft.AspNetCore.All` 元包中列出的包。</span><span class="sxs-lookup"><span data-stu-id="db548-158">Additionally, any FDD app that depends on the `Microsoft.AspNetCore.All` package results in a published app that contains only the app and its assets and not the packages listed in the `Microsoft.AspNetCore.All` metapackage.</span></span> <span data-ttu-id="db548-159">假定这些包都位于目标系统上。</span><span class="sxs-lookup"><span data-stu-id="db548-159">It's assumed that those packages are present on the target system.</span></span>

<span data-ttu-id="db548-160">安装 .NET Core SDK 后，便会在主机上安装运行时包存储区。</span><span class="sxs-lookup"><span data-stu-id="db548-160">The runtime package store is installed on the host when the .NET Core SDK is installed.</span></span> <span data-ttu-id="db548-161">其他安装程序可能会提供运行时包存储区，包括 .NET Core SDK 的 Zip/tarball 安装、`apt-get`、Red Hat Yum、.NET Core Windows Server Hosting 捆绑包和手动运行时包存储区安装。</span><span class="sxs-lookup"><span data-stu-id="db548-161">Other installers may provide the runtime package store, including Zip/tarball installations of the .NET Core SDK, `apt-get`, Red Hat Yum, the .NET Core Windows Server Hosting bundle, and manual runtime package store installations.</span></span>

<span data-ttu-id="db548-162">部署[从属框架部署 (FDD)](index.md#framework-dependent-deployments-fdd) 应用程序时，请确保目标环境中已安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="db548-162">When deploying a [framework-dependent deployment (FDD)](index.md#framework-dependent-deployments-fdd) app, make sure that the target environment has the .NET Core SDK installed.</span></span> <span data-ttu-id="db548-163">如果应用程序部署环境中未安装 ASP.NET Core，可以在项目文件中指定将 \<PublishWithAspNetCoreTargetManifest> 设置为 `false`，从而选择退出隐式存储区，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="db548-163">If the app is deployed to an environment that doesn't include ASP.NET Core, you can opt out of the implicit store by specifying  **\<PublishWithAspNetCoreTargetManifest>** set to `false` in the project file as in the following example:</span></span>

```xml
<PropertyGroup>
  <PublishWithAspNetCoreTargetManifest>false</PublishWithAspNetCoreTargetManifest>
</PropertyGroup>
```

> [!NOTE] 
> <span data-ttu-id="db548-164">对于[独立部署 (SCD)](index.md#self-contained-deployments-scd) 应用程序，假定目标系统不一定包含所需的清单包。</span><span class="sxs-lookup"><span data-stu-id="db548-164">For [self-contained deployment (SCD)](index.md#self-contained-deployments-scd) apps, it's assumed that the target system doesn't necessarily contain the required manifest packages.</span></span> <span data-ttu-id="db548-165">因此，对于 SCD 应用程序，不能将 \<PublishWithAspNetCoreTargetManifest> 设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="db548-165">Therefore, **\<PublishWithAspNetCoreTargetManifest>** cannot be set to `true` for an SCD app.</span></span>

<span data-ttu-id="db548-166">如果使用部署中的清单依赖项（程序集位于 bin 文件夹中）部署应用程序，运行时包存储区不会在主机上用于相应程序集。</span><span class="sxs-lookup"><span data-stu-id="db548-166">If you deploy an application with a manifest dependency that's present in the deployment (the assembly is present in the *bin* folder), the runtime package store *isn't used* on the host for that assembly.</span></span> <span data-ttu-id="db548-167">将使用 bin 文件夹程序集，无论它是否位于主机上的运行时包存储区中。</span><span class="sxs-lookup"><span data-stu-id="db548-167">The *bin* folder assembly is used regardless of its presence in the runtime package store on the host.</span></span>

<span data-ttu-id="db548-168">清单中指明的依赖项版本必须与运行时包存储区中的依赖项版本一致。</span><span class="sxs-lookup"><span data-stu-id="db548-168">The version of the dependency indicated in the manifest must match the version of the dependency in the runtime package store.</span></span> <span data-ttu-id="db548-169">如果目标清单与运行时包存储区中的依赖项版本不一致，并且应用程序的部署中没有包的相应版本，那么应用程序将无法启动。</span><span class="sxs-lookup"><span data-stu-id="db548-169">If you have a version mismatch between the dependency in the target manifest and the version that exists in the runtime package store and the app doesn't include the required version of the package in its deployment, the app fails to start.</span></span> <span data-ttu-id="db548-170">例外情况包括，为运行时包存储区程序集调用的目标清单名称，这有助于排查不一致问题。</span><span class="sxs-lookup"><span data-stu-id="db548-170">The exception includes the name of the target manifest that called for the runtime package store assembly, which helps you troubleshoot the mismatch.</span></span>

<span data-ttu-id="db548-171">如果在发布时部署发生剪裁，只有指明的特定版本清单包，才不会出现在已发布的输出中。</span><span class="sxs-lookup"><span data-stu-id="db548-171">When the deployment is *trimmed* on publish, only the specific versions of the manifest packages you indicate are withheld from the published output.</span></span> <span data-ttu-id="db548-172">主机上必须有指明的包版本，应用程序才能启动。</span><span class="sxs-lookup"><span data-stu-id="db548-172">The packages at the versions indicated must be present on the host for the app to start.</span></span>

## <a name="see-also"></a><span data-ttu-id="db548-173">请参阅</span><span class="sxs-lookup"><span data-stu-id="db548-173">See also</span></span>
 [<span data-ttu-id="db548-174">dotnet-publish</span><span class="sxs-lookup"><span data-stu-id="db548-174">dotnet-publish</span></span>](../tools/dotnet-publish.md)  
 [<span data-ttu-id="db548-175">dotnet-store</span><span class="sxs-lookup"><span data-stu-id="db548-175">dotnet-store</span></span>](../tools/dotnet-store.md)  
