---
title: 卸载工具
description: .NET Core 卸载工具概述，它是一种可实现 .NET Core SDK 和运行时的受控清理的引导式工具。
author: sfoslund
ms.date: 01/06/2020
ms.openlocfilehash: 4944c983cbd02b456c3a09a1b03bc28ba6e458cc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714544"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="1d298-103">.NET Core 卸载工具</span><span class="sxs-lookup"><span data-stu-id="1d298-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="1d298-104">[.NET Core 卸载工具](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) 使你可以从系统中删除 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-104">The [.NET Core Uninstall Tool](https://github.com/dotnet/cli-lab/releases) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="1d298-105">可使用选项集合来指定要卸载的版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="1d298-106">该工具支持 Windows 和 macOS。</span><span class="sxs-lookup"><span data-stu-id="1d298-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="1d298-107">目前不支持 Linux。</span><span class="sxs-lookup"><span data-stu-id="1d298-107">Linux is currently not supported.</span></span>

<span data-ttu-id="1d298-108">在 Windows 上，该工具只能卸载使用以下安装程序之一安装的 SDK 和运行时：</span><span class="sxs-lookup"><span data-stu-id="1d298-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="1d298-109">.NET Core SDK 和运行时安装程序。</span><span class="sxs-lookup"><span data-stu-id="1d298-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="1d298-110">Visual studio 安装程序的版本早于 Visual Studio 2019 版本 16.3。</span><span class="sxs-lookup"><span data-stu-id="1d298-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="1d298-111">在 macOS 上，该工具只能卸载位于 /usr/local/share/dotnet  文件夹中的 SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="1d298-112">由于这些限制，该工具可能无法卸载计算机上的所有 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="1d298-113">可以使用 `dotnet --info` 命令来查找所有安装的 .NET Core SDK 和运行时，包括此工具无法删除的 SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="1d298-114">`dotnet-core-uninstall list` 命令显示可以通过该工具卸载的 SDK。</span><span class="sxs-lookup"><span data-stu-id="1d298-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="1d298-115">安装工具</span><span class="sxs-lookup"><span data-stu-id="1d298-115">Install the tool</span></span>

<span data-ttu-id="1d298-116">可以从 [dotnet/cli-lab](https://github.com/dotnet/cli-lab/releases) GitHub 存储库下载 .NET Core 卸载工具。</span><span class="sxs-lookup"><span data-stu-id="1d298-116">You can download the .NET Core Uninstall Tool from the [dotnet/cli-lab](https://github.com/dotnet/cli-lab/releases) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="1d298-117">此工具需要提升才能卸载 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="1d298-118">因此，应将其安装在写入保护的目录中，如 Windows 上的 C:\Program Files  或 macOS 上的 /usr/local/bin  。</span><span class="sxs-lookup"><span data-stu-id="1d298-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="1d298-119">另请参阅[提升的 Dotnet 命令访问权限](../tools/elevated-access.md)。</span><span class="sxs-lookup"><span data-stu-id="1d298-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="1d298-120">[GitHub 版本页](https://github.com/dotnet/cli-lab/releases)上提供了详细的安装说明。</span><span class="sxs-lookup"><span data-stu-id="1d298-120">Detailed installation instructions are available on the [GitHub Releases page](https://github.com/dotnet/cli-lab/releases).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="1d298-121">运行该工具</span><span class="sxs-lookup"><span data-stu-id="1d298-121">Run the tool</span></span>

<span data-ttu-id="1d298-122">以下步骤说明了运行卸载工具的建议方法：</span><span class="sxs-lookup"><span data-stu-id="1d298-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="1d298-123">步骤 1 - 显示已安装的 .NET Core Sdk 和运行时</span><span class="sxs-lookup"><span data-stu-id="1d298-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="1d298-124">步骤 2 - 执行试运行</span><span class="sxs-lookup"><span data-stu-id="1d298-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="1d298-125">步骤 3 - 卸载 .NET Core SDK 和运行时</span><span class="sxs-lookup"><span data-stu-id="1d298-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="1d298-126">步骤 4 - 删除 NuGet 回退文件夹（可选）</span><span class="sxs-lookup"><span data-stu-id="1d298-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="1d298-127">步骤 1 - 显示安装的 .NET Core SDK 和运行时</span><span class="sxs-lookup"><span data-stu-id="1d298-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="1d298-128">`dotnet-core-uninstall list` 命令列出了已安装的 .NET Core SDK 和运行时，可以通过此工具将其删除。</span><span class="sxs-lookup"><span data-stu-id="1d298-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="1d298-129">Visual Studio 可能需要某些 SDK 和运行时，它们将显示出来，并说明为何不建议将其卸载。</span><span class="sxs-lookup"><span data-stu-id="1d298-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

<span data-ttu-id="1d298-130">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="1d298-130">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="1d298-131">摘要</span><span class="sxs-lookup"><span data-stu-id="1d298-131">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="1d298-132">选项</span><span class="sxs-lookup"><span data-stu-id="1d298-132">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="1d298-133">Windows</span><span class="sxs-lookup"><span data-stu-id="1d298-133">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="1d298-134">列出可通过此工具卸载的所有 ASP.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-134">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="1d298-135">列出可通过此工具卸载的所有 .NET Core 运行时和托管捆绑包。</span><span class="sxs-lookup"><span data-stu-id="1d298-135">Lists all the .NET Core runtime and hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="1d298-136">列出可通过此工具卸载的所有 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-136">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="1d298-137">列出可通过此工具卸载的所有 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="1d298-137">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="1d298-138">设置详细程度。</span><span class="sxs-lookup"><span data-stu-id="1d298-138">Sets the verbosity level.</span></span> <span data-ttu-id="1d298-139">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="1d298-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1d298-140">默认值为 `normal`。</span><span class="sxs-lookup"><span data-stu-id="1d298-140">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="1d298-141">列出可通过此工具卸载的所有 x64 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-141">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="1d298-142">列出可通过此工具卸载的所有 x86 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-142">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="1d298-143">macOS</span><span class="sxs-lookup"><span data-stu-id="1d298-143">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="1d298-144">列出可通过此工具卸载的所有 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-144">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="1d298-145">列出可通过此工具卸载的所有 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="1d298-145">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="1d298-146">设置详细程度。</span><span class="sxs-lookup"><span data-stu-id="1d298-146">Sets the verbosity level.</span></span> <span data-ttu-id="1d298-147">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="1d298-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1d298-148">默认值为 `normal`。</span><span class="sxs-lookup"><span data-stu-id="1d298-148">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="1d298-149">示例</span><span class="sxs-lookup"><span data-stu-id="1d298-149">Examples</span></span>

* <span data-ttu-id="1d298-150">列出可通过此工具删除的所有 .NET Core SDK 和运行时：</span><span class="sxs-lookup"><span data-stu-id="1d298-150">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="1d298-151">列出所有 x64 .NET Core SDK 和运行时：</span><span class="sxs-lookup"><span data-stu-id="1d298-151">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="1d298-152">列出所有 x86 .NET Core SDK：</span><span class="sxs-lookup"><span data-stu-id="1d298-152">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="1d298-153">步骤 2 - 执行试运行</span><span class="sxs-lookup"><span data-stu-id="1d298-153">Step 2 - Do a dry run</span></span>

<span data-ttu-id="1d298-154">`dotnet-core-uninstall dry-run` 和 `dotnet-core-uninstall whatif` 命令显示将根据提供的选项删除的 .NET Core SDK 和运行时，而无需执行卸载。</span><span class="sxs-lookup"><span data-stu-id="1d298-154">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="1d298-155">这些命令是同义词。</span><span class="sxs-lookup"><span data-stu-id="1d298-155">These commands are synonyms.</span></span>

<span data-ttu-id="1d298-156">**dotnet-core-uninstall dry-run 和 dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="1d298-156">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="1d298-157">摘要</span><span class="sxs-lookup"><span data-stu-id="1d298-157">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="1d298-158">自变量</span><span class="sxs-lookup"><span data-stu-id="1d298-158">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="1d298-159">要卸载的指定版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-159">The specified version to uninstall.</span></span> <span data-ttu-id="1d298-160">可以逐一列出多个版本，用空格分隔。</span><span class="sxs-lookup"><span data-stu-id="1d298-160">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="1d298-161">此外还支持响应文件。</span><span class="sxs-lookup"><span data-stu-id="1d298-161">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="1d298-162">响应文件是在命令行上放置所有版本的替代方法。</span><span class="sxs-lookup"><span data-stu-id="1d298-162">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="1d298-163">它们是文本文件，通常具有 \*.rsp 扩展名，每个版本都在单独的行上列出。</span><span class="sxs-lookup"><span data-stu-id="1d298-163">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="1d298-164">若要为 `VERSION` 参数指定响应文件，请使用后面紧跟响应文件名的 \@ 字符。</span><span class="sxs-lookup"><span data-stu-id="1d298-164">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="1d298-165">选项</span><span class="sxs-lookup"><span data-stu-id="1d298-165">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="1d298-166">Windows</span><span class="sxs-lookup"><span data-stu-id="1d298-166">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="1d298-167">删除所有 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-167">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="1d298-168">仅删除版本小于指定版本的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-168">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="1d298-169">仍安装指定版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-169">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="1d298-170">除了那些指定版本外，删除所有 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-170">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="1d298-171">删除 .NET Core SDK 和运行时（最高版本除外）。</span><span class="sxs-lookup"><span data-stu-id="1d298-171">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="1d298-172">删除由较高版本的修补程序取代的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-172">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="1d298-173">此选项保护 global.json。</span><span class="sxs-lookup"><span data-stu-id="1d298-173">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="1d298-174">删除标记为预览的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-174">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="1d298-175">删除标记为预览的 .NET Core SDK 和运行时（最高预览版除外）。</span><span class="sxs-lookup"><span data-stu-id="1d298-175">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="1d298-176">仅删除 ASP.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-176">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="1d298-177">仅删除 .NET Core 运行时和托管绑定。</span><span class="sxs-lookup"><span data-stu-id="1d298-177">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="1d298-178">删除与指定 `major.minor` 版本相匹配的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-178">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="1d298-179">仅删除 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-179">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="1d298-180">仅删除 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="1d298-180">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="1d298-181">设置详细程度。</span><span class="sxs-lookup"><span data-stu-id="1d298-181">Sets the verbosity level.</span></span> <span data-ttu-id="1d298-182">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="1d298-182">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1d298-183">默认值为 `normal`。</span><span class="sxs-lookup"><span data-stu-id="1d298-183">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="1d298-184">必须与 `--sdk`、`--runtime` 和 `--aspnet-runtime` 结合使用才能删除 x64 SDK 或运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-184">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="1d298-185">必须与 `--sdk`、`--runtime` 和 `--aspnet-runtime` 结合使用才能删除 x86 SDK 或运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-185">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="1d298-186">`--force`  强制删除可能由 Visual Studio 使用的版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-186">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="1d298-187">注意：</span><span class="sxs-lookup"><span data-stu-id="1d298-187">Notes:</span></span>

1. <span data-ttu-id="1d298-188">只需 `--sdk`、`--runtime`、`--aspnet-runtime` 和 `--hosting-bundle` 中的一个。</span><span class="sxs-lookup"><span data-stu-id="1d298-188">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="1d298-189">`--all`、`--all-below`、`--all-but`、`--all-but-latest`、`--all-lower-patches`、`--all-previews`、`--all-previews-but-latest`、`--major-minor` 和 `[<VERSION>...]` 除外。</span><span class="sxs-lookup"><span data-stu-id="1d298-189">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="1d298-190">如果未指定 `--x64` 或 `--x86`，则同时删除 x64 和 x86。</span><span class="sxs-lookup"><span data-stu-id="1d298-190">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="1d298-191">macOS</span><span class="sxs-lookup"><span data-stu-id="1d298-191">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="1d298-192">删除所有 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-192">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="1d298-193">删除低于指定版本的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-193">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="1d298-194">将保留指定的版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-194">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="1d298-195">删除 .NET Core SDK 和运行时（指定版本除外）。</span><span class="sxs-lookup"><span data-stu-id="1d298-195">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="1d298-196">删除 .NET Core SDK 和运行时（最高版本除外）。</span><span class="sxs-lookup"><span data-stu-id="1d298-196">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="1d298-197">删除由较高版本的修补程序取代的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-197">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="1d298-198">此选项保护 global.json。</span><span class="sxs-lookup"><span data-stu-id="1d298-198">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="1d298-199">删除标记为预览的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-199">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="1d298-200">删除标记为预览的 .NET Core SDK 和运行时（最高预览版除外）。</span><span class="sxs-lookup"><span data-stu-id="1d298-200">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="1d298-201">删除与指定 `major.minor` 版本相匹配的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-201">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="1d298-202">仅删除 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-202">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="1d298-203">仅删除 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="1d298-203">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="1d298-204">设置详细程度。</span><span class="sxs-lookup"><span data-stu-id="1d298-204">Sets the verbosity level.</span></span> <span data-ttu-id="1d298-205">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="1d298-205">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1d298-206">默认值为 `normal`。</span><span class="sxs-lookup"><span data-stu-id="1d298-206">The default value is `normal`.</span></span>
  
* <span data-ttu-id="1d298-207">`--force`  强制删除可能由 Visual Studio 或 SDK 使用的版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-207">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="1d298-208">注意：</span><span class="sxs-lookup"><span data-stu-id="1d298-208">Notes:</span></span>

1. <span data-ttu-id="1d298-209">只需 `--sdk` 和 `--runtime` 中的一个。</span><span class="sxs-lookup"><span data-stu-id="1d298-209">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="1d298-210">`--all`、`--all-below`、`--all-but`、`--all-but-latest`、`--all-lower-patches`、`--all-previews`、`--all-previews-but-latest`、`--major-minor` 和 `[<VERSION>...]` 除外。</span><span class="sxs-lookup"><span data-stu-id="1d298-210">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="1d298-211">示例</span><span class="sxs-lookup"><span data-stu-id="1d298-211">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="1d298-212">默认情况下，Visual Studio 或其他 SDK 可能需要的 .NET Core SDK 和运行时不会包含在 `dotnet-core-uninstall dry-run` 输出中。</span><span class="sxs-lookup"><span data-stu-id="1d298-212">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="1d298-213">在下面的示例中，某些指定的 SDK 和运行时可能不会包含在输出中，具体取决于计算机的状态。</span><span class="sxs-lookup"><span data-stu-id="1d298-213">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="1d298-214">若要包括所有 SDK 和运行时，请将它们显式列出为参数或使用 `--force` 选项。</span><span class="sxs-lookup"><span data-stu-id="1d298-214">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="1d298-215">试运行删除已被较高版本的修补程序取代的所有 .NET Core 运行时：</span><span class="sxs-lookup"><span data-stu-id="1d298-215">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="1d298-216">试运行删除低于版本 `2.2.301` 的所有 .NET Core SDK：</span><span class="sxs-lookup"><span data-stu-id="1d298-216">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="1d298-217">步骤 3 - 卸载 .NET Core SDK 和运行时</span><span class="sxs-lookup"><span data-stu-id="1d298-217">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="1d298-218">`dotnet-core-uninstall remove` 卸载由选项集合指定的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-218">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="1d298-219">该工具不能用于卸载版本 5.0 或更高版本的 SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-219">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="1d298-220">由于此工具具有破坏性行为，因此强烈  建议在运行 remove 命令之前执行试运行。</span><span class="sxs-lookup"><span data-stu-id="1d298-220">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="1d298-221">使用 `remove` 命令时，试运行将显示要删除的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-221">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="1d298-222">请参阅[是否应删除版本？](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version)了解哪些 SDK 和运行时可以安全删除。</span><span class="sxs-lookup"><span data-stu-id="1d298-222">Refer to [Should I remove a version?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="1d298-223">请记住以下注意事项：</span><span class="sxs-lookup"><span data-stu-id="1d298-223">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="1d298-224">此工具可以卸载计算机上 `global.json` 文件所需的 .NET Core SDK 版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-224">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="1d298-225">可以从[下载 .NET Core](https://dotnet.microsoft.com/download/dotnet-core) 页面重新安装 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="1d298-225">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="1d298-226">此工具可以卸载计算机上依赖于框架的应用程序所需的 .NET Core 运行时版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-226">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="1d298-227">可以从[下载 .NET Core](https://dotnet.microsoft.com/download/dotnet-core) 页面重新安装 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-227">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="1d298-228">此工具可以卸载 Visual Studio 所依赖的 .NET Core SDK 和运行时版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-228">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="1d298-229">如果中断 Visual Studio 安装，请在 Visual Studio 安装程序中运行“修复”以返回到工作状态。</span><span class="sxs-lookup"><span data-stu-id="1d298-229">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="1d298-230">默认情况下，所有命令都将保留 Visual Studio 或其他 SDK 可能需要的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-230">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="1d298-231">可以通过将这些 SDK 和运行时显式列出为参数或使用 `--force` 选项来卸载这些 SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-231">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="1d298-232">此工具需要提升才能卸载 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-232">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="1d298-233">在 Windows 上的管理员命令提示符中运行此工具，在 macOS 上则通过 `sudo` 运行。</span><span class="sxs-lookup"><span data-stu-id="1d298-233">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="1d298-234">`dry-run` 和 `whatif` 命令不需要提升。</span><span class="sxs-lookup"><span data-stu-id="1d298-234">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="1d298-235">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="1d298-235">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="1d298-236">摘要</span><span class="sxs-lookup"><span data-stu-id="1d298-236">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="1d298-237">自变量</span><span class="sxs-lookup"><span data-stu-id="1d298-237">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="1d298-238">要卸载的指定版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-238">The specified version to uninstall.</span></span> <span data-ttu-id="1d298-239">可以逐一列出多个版本，用空格分隔。</span><span class="sxs-lookup"><span data-stu-id="1d298-239">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="1d298-240">此外还支持响应文件。</span><span class="sxs-lookup"><span data-stu-id="1d298-240">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="1d298-241">响应文件是在命令行上放置所有版本的替代方法。</span><span class="sxs-lookup"><span data-stu-id="1d298-241">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="1d298-242">它们是文本文件，通常具有 \*.rsp 扩展名，每个版本都在单独的行上列出。</span><span class="sxs-lookup"><span data-stu-id="1d298-242">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="1d298-243">若要为 `VERSION` 参数指定响应文件，请使用后面紧跟响应文件名的 \@ 字符。</span><span class="sxs-lookup"><span data-stu-id="1d298-243">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="1d298-244">选项</span><span class="sxs-lookup"><span data-stu-id="1d298-244">Options</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="1d298-245">Windows</span><span class="sxs-lookup"><span data-stu-id="1d298-245">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="1d298-246">删除所有 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-246">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="1d298-247">仅删除版本小于指定版本的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-247">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="1d298-248">仍安装指定版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-248">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="1d298-249">除了那些指定版本外，删除所有 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-249">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="1d298-250">删除 .NET Core SDK 和运行时（最高版本除外）。</span><span class="sxs-lookup"><span data-stu-id="1d298-250">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="1d298-251">删除由较高版本的修补程序取代的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-251">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="1d298-252">此选项保护 global.json。</span><span class="sxs-lookup"><span data-stu-id="1d298-252">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="1d298-253">删除标记为预览的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-253">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="1d298-254">删除标记为预览的 .NET Core SDK 和运行时（最高预览版除外）。</span><span class="sxs-lookup"><span data-stu-id="1d298-254">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="1d298-255">仅删除 ASP.NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-255">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="1d298-256">仅删除 .NET Core 运行时和托管绑定。</span><span class="sxs-lookup"><span data-stu-id="1d298-256">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="1d298-257">删除与指定 `major.minor` 版本相匹配的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-257">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="1d298-258">仅删除 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-258">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="1d298-259">仅删除 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="1d298-259">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="1d298-260">设置详细程度。</span><span class="sxs-lookup"><span data-stu-id="1d298-260">Sets the verbosity level.</span></span> <span data-ttu-id="1d298-261">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="1d298-261">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1d298-262">默认值为 `normal`。</span><span class="sxs-lookup"><span data-stu-id="1d298-262">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="1d298-263">必须与 `--sdk`、`--runtime` 和 `--aspnet-runtime` 结合使用才能删除 x64 SDK 或运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-263">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="1d298-264">必须与 `--sdk`、`--runtime` 和 `--aspnet-runtime` 结合使用才能删除 x86 SDK 或运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-264">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="1d298-265">`-y, --yes`  执行命令而不需要进行是或否确认。</span><span class="sxs-lookup"><span data-stu-id="1d298-265">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="1d298-266">`--force`  强制删除可能由 Visual Studio 使用的版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-266">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="1d298-267">注意：</span><span class="sxs-lookup"><span data-stu-id="1d298-267">Notes:</span></span>

1. <span data-ttu-id="1d298-268">只需 `--sdk`、`--runtime`、`--aspnet-runtime` 和 `--hosting-bundle` 中的一个。</span><span class="sxs-lookup"><span data-stu-id="1d298-268">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="1d298-269">`--all`、`--all-below`、`--all-but`、`--all-but-latest`、`--all-lower-patches`、`--all-previews`、`--all-previews-but-latest`、`--major-minor` 和 `[<VERSION>...]` 除外。</span><span class="sxs-lookup"><span data-stu-id="1d298-269">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="1d298-270">如果未指定 `--x64` 或 `--x86`，则同时删除 x64 和 x86。</span><span class="sxs-lookup"><span data-stu-id="1d298-270">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="1d298-271">macOS</span><span class="sxs-lookup"><span data-stu-id="1d298-271">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="1d298-272">删除所有 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-272">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="1d298-273">删除低于指定版本的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-273">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="1d298-274">将保留指定的版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-274">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="1d298-275">删除 .NET Core SDK 和运行时（指定版本除外）。</span><span class="sxs-lookup"><span data-stu-id="1d298-275">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="1d298-276">删除 .NET Core SDK 和运行时（最高版本除外）。</span><span class="sxs-lookup"><span data-stu-id="1d298-276">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="1d298-277">删除由较高版本的修补程序取代的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-277">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="1d298-278">此选项保护 global.json。</span><span class="sxs-lookup"><span data-stu-id="1d298-278">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="1d298-279">删除标记为预览的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-279">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="1d298-280">删除标记为预览的 .NET Core SDK 和运行时（最高预览版除外）。</span><span class="sxs-lookup"><span data-stu-id="1d298-280">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="1d298-281">删除与指定 `major.minor` 版本相匹配的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-281">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="1d298-282">仅删除 .NET Core 运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-282">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="1d298-283">仅删除 .NET Core SDK。</span><span class="sxs-lookup"><span data-stu-id="1d298-283">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="1d298-284">设置详细程度。</span><span class="sxs-lookup"><span data-stu-id="1d298-284">Sets the verbosity level.</span></span> <span data-ttu-id="1d298-285">允许使用的值为 `q[uiet]`、`m[inimal]`、`n[ormal]`、`d[etailed]` 和 `diag[nostic]`。</span><span class="sxs-lookup"><span data-stu-id="1d298-285">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="1d298-286">默认值为 `normal`。</span><span class="sxs-lookup"><span data-stu-id="1d298-286">The default value is `normal`.</span></span>

* <span data-ttu-id="1d298-287">`-y, --yes`  执行命令而不需要进行 Y/N 确认。</span><span class="sxs-lookup"><span data-stu-id="1d298-287">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="1d298-288">`--force`  强制删除可能由 Visual Studio 或 SDK 使用的版本。</span><span class="sxs-lookup"><span data-stu-id="1d298-288">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="1d298-289">注意：</span><span class="sxs-lookup"><span data-stu-id="1d298-289">Notes:</span></span>

1. <span data-ttu-id="1d298-290">只需 `--sdk` 和 `--runtime` 中的一个。</span><span class="sxs-lookup"><span data-stu-id="1d298-290">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="1d298-291">`--all`、`--all-below`、`--all-but`、`--all-but-latest`、`--all-lower-patches`、`--all-previews`、`--all-previews-but-latest`、`--major-minor` 和 `[<VERSION>...]` 除外。</span><span class="sxs-lookup"><span data-stu-id="1d298-291">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="1d298-292">示例</span><span class="sxs-lookup"><span data-stu-id="1d298-292">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="1d298-293">默认情况下，将保留 Visual Studio 或其他 SDK 可能需要的 .NET Core SDK 和运行时。</span><span class="sxs-lookup"><span data-stu-id="1d298-293">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="1d298-294">在下面的示例中，可能保留某些指定的 SDK 和运行时，具体取决于计算机的状态。</span><span class="sxs-lookup"><span data-stu-id="1d298-294">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="1d298-295">若要删除所有 SDK 和运行时，请将它们显式列出为参数或使用 `--force` 选项。</span><span class="sxs-lookup"><span data-stu-id="1d298-295">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="1d298-296">删除除版本 `3.0.0-preview6-27804-01` 之外的所有 .NET Core 运行时，无需进行 Y/N 确认：</span><span class="sxs-lookup"><span data-stu-id="1d298-296">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="1d298-297">删除所有 .NET Core 1.1 SDK，无需进行 Y/N 确认：</span><span class="sxs-lookup"><span data-stu-id="1d298-297">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="1d298-298">删除没有控制台输出的 .NET Core 1.1.11 SDK：</span><span class="sxs-lookup"><span data-stu-id="1d298-298">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="1d298-299">删除可由此工具安全删除的所有 .NET Core SDK：</span><span class="sxs-lookup"><span data-stu-id="1d298-299">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="1d298-300">删除此工具可删除的所有 .NET Core SDK，包括 Visual Studio 可能需要的 SDK（不推荐）：</span><span class="sxs-lookup"><span data-stu-id="1d298-300">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="1d298-301">删除响应文件 `versions.rsp` 中指定的所有 .NET Core SDK</span><span class="sxs-lookup"><span data-stu-id="1d298-301">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="1d298-302">versions.rsp  的内容如下所示：</span><span class="sxs-lookup"><span data-stu-id="1d298-302">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="1d298-303">步骤 4 - 删除 NuGet 回退文件夹（可选）</span><span class="sxs-lookup"><span data-stu-id="1d298-303">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="1d298-304">在某些情况下，你不再需要 `NuGetFallbackFolder`，可能希望将其删除。</span><span class="sxs-lookup"><span data-stu-id="1d298-304">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="1d298-305">有关删除此文件夹的详细信息，请参阅[删除 NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder)。</span><span class="sxs-lookup"><span data-stu-id="1d298-305">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="1d298-306">卸载工具</span><span class="sxs-lookup"><span data-stu-id="1d298-306">Uninstall the tool</span></span>

## <a name="windowstabwindows"></a>[<span data-ttu-id="1d298-307">Windows</span><span class="sxs-lookup"><span data-stu-id="1d298-307">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="1d298-308">打开“添加或删除程序”  。</span><span class="sxs-lookup"><span data-stu-id="1d298-308">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="1d298-309">搜索 `Microsoft .NET Core SDK Uninstall Tool`。</span><span class="sxs-lookup"><span data-stu-id="1d298-309">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="1d298-310">选择“卸载”  。</span><span class="sxs-lookup"><span data-stu-id="1d298-310">Select **Uninstall**.</span></span>

## <a name="macostabmacos"></a>[<span data-ttu-id="1d298-311">macOS</span><span class="sxs-lookup"><span data-stu-id="1d298-311">macOS</span></span>](#tab/macos)

<span data-ttu-id="1d298-312">从安装目录中删除已下载的 dotnet-core-uninstall.tar.gz  文件。</span><span class="sxs-lookup"><span data-stu-id="1d298-312">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="1d298-313">如果将此文件的内容解压缩到其他目录中，请务必同时删除该内容。</span><span class="sxs-lookup"><span data-stu-id="1d298-313">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
