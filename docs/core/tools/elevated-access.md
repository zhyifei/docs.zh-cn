---
title: 提升的 Dotnet 命令访问权限
description: 了解需要提升访问权限的 dotnet 命令的最佳做法。
author: wli3
ms.date: 06/26/2019
ms.openlocfilehash: 3d874a76eadbf5330c4e5efe4e86bfeca0a9b504
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410625"
---
# <a name="elevated-access-for-dotnet-commands"></a><span data-ttu-id="b2197-103">提升的 Dotnet 命令访问权限</span><span class="sxs-lookup"><span data-stu-id="b2197-103">Elevated access for dotnet commands</span></span>

<span data-ttu-id="b2197-104">开发人员可根据软件开发最佳做法来编写需要最少权限的软件。</span><span class="sxs-lookup"><span data-stu-id="b2197-104">Software development best practices guide developers to writing software that requires the least amount of privilege.</span></span> <span data-ttu-id="b2197-105">但是，某些软件（如性能监视工具）由于操作系统规则，需要管理员权限。</span><span class="sxs-lookup"><span data-stu-id="b2197-105">However, some software, like performance monitoring tools, requires admin permission because of operating system rules.</span></span> <span data-ttu-id="b2197-106">以下指南介绍使用 .NET Core 编写此类软件的适用方案。</span><span class="sxs-lookup"><span data-stu-id="b2197-106">The following guidance describes supported scenarios for writing such software with .NET Core.</span></span> 

<span data-ttu-id="b2197-107">可以运行以下提升的命令：</span><span class="sxs-lookup"><span data-stu-id="b2197-107">The following commands can be run elevated:</span></span>

- <span data-ttu-id="b2197-108">`dotnet tool` 命令，如 [dotnet tool install](dotnet-tool-install.md)。</span><span class="sxs-lookup"><span data-stu-id="b2197-108">`dotnet tool` commands, such as [dotnet tool install](dotnet-tool-install.md).</span></span>
- `dotnet run --no-build`

<span data-ttu-id="b2197-109">不建议运行其他提升的命令。</span><span class="sxs-lookup"><span data-stu-id="b2197-109">We don't recommend running other commands elevated.</span></span> <span data-ttu-id="b2197-110">具体而言，不建议为使用 MSBuild（例如，[dotnet restore](dotnet-restore.md)、[dotnet build](dotnet-build.md) 和 [dotnet run](dotnet-run.md)）的命令提升访问权限。</span><span class="sxs-lookup"><span data-stu-id="b2197-110">In particular, we don't recommend elevation with commands that use MSBuild, such as [dotnet restore](dotnet-restore.md), [dotnet build](dotnet-build.md), and [dotnet run](dotnet-run.md).</span></span> <span data-ttu-id="b2197-111">主要问题是用户在发出 dotnet 命令后在根帐户和受限帐户之间来回切换时存在权限管理问题。</span><span class="sxs-lookup"><span data-stu-id="b2197-111">The primary issue is permission management problems when a user transitions back and forth between root and a restricted account after issuing dotnet commands.</span></span> <span data-ttu-id="b2197-112">受限用户可能会发现自己无法访问根用户构建的文件。</span><span class="sxs-lookup"><span data-stu-id="b2197-112">You may find as a restricted user that you don't have access to the file built by a root user.</span></span> <span data-ttu-id="b2197-113">有办法可以解决这种情况，但不一定要使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="b2197-113">There are ways to resolve this situation, but they're unnecessary to get into in the first place.</span></span>

<span data-ttu-id="b2197-114">只要不在根帐户和受限帐户之间来回切换，就可以根帐户的身份运行命令。</span><span class="sxs-lookup"><span data-stu-id="b2197-114">You can run commands as root as long as you don’t transition back and forth between root and a restricted account.</span></span> <span data-ttu-id="b2197-115">例如，Docker 容器默认以根帐户身份运行，因此它们具有此特性。</span><span class="sxs-lookup"><span data-stu-id="b2197-115">For example, Docker containers run as root by default, so they have this characteristic.</span></span>

## <a name="global-tool-installation"></a><span data-ttu-id="b2197-116">全局工具安装</span><span class="sxs-lookup"><span data-stu-id="b2197-116">Global tool installation</span></span>

<span data-ttu-id="b2197-117">以下说明展示了执行下述操作的推荐方法：安装、运行和卸载需要提升权限才能执行的 .NET Core 工具。</span><span class="sxs-lookup"><span data-stu-id="b2197-117">The following instructions demonstrate the recommended way to install, run, and uninstall .NET Core tools that require elevated permissions to execute.</span></span>

# <a name="windowstabwindows"></a>[<span data-ttu-id="b2197-118">Windows</span><span class="sxs-lookup"><span data-stu-id="b2197-118">Windows</span></span>](#tab/windows)

### <a name="install-the-global-tool"></a><span data-ttu-id="b2197-119">安装全局工具</span><span class="sxs-lookup"><span data-stu-id="b2197-119">Install the global tool</span></span>

<span data-ttu-id="b2197-120">如果文件夹 `%ProgramFiles%\dotnet-tools` 已存在，请执行以下操作以检查“用户”组是否有写入或修改该目录的权限：</span><span class="sxs-lookup"><span data-stu-id="b2197-120">If the folder `%ProgramFiles%\dotnet-tools` already exists, do the following to check whether the "Users" group has permission to write or modify that directory:</span></span>

* <span data-ttu-id="b2197-121">右键单击 `%ProgramFiles%\dotnet-tools` 文件夹并选择“属性”  。</span><span class="sxs-lookup"><span data-stu-id="b2197-121">Right-click the `%ProgramFiles%\dotnet-tools` folder and select **Properties**.</span></span> <span data-ttu-id="b2197-122">随即打开“常用属性”对话框  。</span><span class="sxs-lookup"><span data-stu-id="b2197-122">The **Common Properties** dialog box opens.</span></span> 
* <span data-ttu-id="b2197-123">选择“安全性”选项卡  。在“组或用户名”下，检查“用户”组是否具有写入或修改目录的权限  。</span><span class="sxs-lookup"><span data-stu-id="b2197-123">Select the **Security** tab. Under **Group or user names**, check whether the “Users” group has permission to write or modify the directory.</span></span> 
* <span data-ttu-id="b2197-124">如果“用户”组可以写入或修改目录，则在安装工具时使用其他目录名，而不使用 dotnet-tools  。</span><span class="sxs-lookup"><span data-stu-id="b2197-124">If the "Users" group can write or modify the directory, use a different directory name when installing the tools rather than *dotnet-tools*.</span></span>

<span data-ttu-id="b2197-125">要安装工具，请在提升的提示符下运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="b2197-125">To install tools, run the following command in elevated prompt.</span></span> <span data-ttu-id="b2197-126">此操作将在安装期间创建 dotnet-tools 文件夹  。</span><span class="sxs-lookup"><span data-stu-id="b2197-126">It will create the *dotnet-tools* folder during the installation.</span></span>

```cmd
dotnet tool install PACKAGEID --tool-path "%ProgramFiles%\dotnet-tools".
```

### <a name="run-the-global-tool"></a><span data-ttu-id="b2197-127">运行全局工具</span><span class="sxs-lookup"><span data-stu-id="b2197-127">Run the global tool</span></span>

<span data-ttu-id="b2197-128">**选项 1** 在提升的提示符中使用完整路径：</span><span class="sxs-lookup"><span data-stu-id="b2197-128">**Option 1** Use the full path with elevated prompt:</span></span>

```cmd
"%ProgramFiles%\dotnet-tools\TOOLCOMMAND"
```

<span data-ttu-id="b2197-129">**选项 2** 将新创建的文件夹添加到 `%Path%`。</span><span class="sxs-lookup"><span data-stu-id="b2197-129">**Option 2** Add the newly created folder to `%Path%`.</span></span> <span data-ttu-id="b2197-130">只需执行此操作一次。</span><span class="sxs-lookup"><span data-stu-id="b2197-130">You only need to do this operation once.</span></span>

```cmd
setx Path "%Path%;%ProgramFiles%\dotnet-tools\"
```

<span data-ttu-id="b2197-131">然后使用以下命令运行：</span><span class="sxs-lookup"><span data-stu-id="b2197-131">And run with:</span></span>

```cmd
TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a><span data-ttu-id="b2197-132">卸载全局工具</span><span class="sxs-lookup"><span data-stu-id="b2197-132">Uninstall the global tool</span></span>

<span data-ttu-id="b2197-133">在提升的提示符处，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="b2197-133">In an elevated prompt, type the following command:</span></span>

```cmd
dotnet tool uninstall PACKAGEID --tool-path "%ProgramFiles%\dotnet-tools"
```

# <a name="linuxtablinux"></a>[<span data-ttu-id="b2197-134">Linux</span><span class="sxs-lookup"><span data-stu-id="b2197-134">Linux</span></span>](#tab/linux)

[!INCLUDE [elevated-access-unix](../../../includes/elevated-access-unix.md)]

# <a name="macostabmacos"></a>[<span data-ttu-id="b2197-135">macOS</span><span class="sxs-lookup"><span data-stu-id="b2197-135">macOS</span></span>](#tab/macos)

[!INCLUDE [elevated-access-unix](../../../includes/elevated-access-unix.md)]

---

## <a name="local-tools"></a><span data-ttu-id="b2197-136">本地工具</span><span class="sxs-lookup"><span data-stu-id="b2197-136">Local tools</span></span>

<span data-ttu-id="b2197-137">本地工具的作用域按用户和个子目录树来限定。</span><span class="sxs-lookup"><span data-stu-id="b2197-137">Local tools are scoped per subdirectory tree, per user.</span></span> <span data-ttu-id="b2197-138">执行特权运行后，本地工具将受限的用户环境共享给提升的环境。</span><span class="sxs-lookup"><span data-stu-id="b2197-138">When run elevated, local tools share a restricted user environment to the elevated environment.</span></span> <span data-ttu-id="b2197-139">在 Linux 和 macOS 中，这会导致将文件设置为仅限根用户访问。</span><span class="sxs-lookup"><span data-stu-id="b2197-139">In Linux and macOS, this results in files being set with root user-only access.</span></span> <span data-ttu-id="b2197-140">如果用户切换回受限帐户，则用户无法再访问或写入文件。</span><span class="sxs-lookup"><span data-stu-id="b2197-140">If the user switches back to a restricted account, the user can no longer access or write to the files.</span></span> <span data-ttu-id="b2197-141">因此，不建议将必须提升的工具安装为本地工具。</span><span class="sxs-lookup"><span data-stu-id="b2197-141">So installing tools that require elevation as local tools isn't recommended.</span></span> <span data-ttu-id="b2197-142">建议使用 `--tool-path` 选项和上述全局工具指南。</span><span class="sxs-lookup"><span data-stu-id="b2197-142">Instead, use the `--tool-path` option and the previous guidelines for global tools.</span></span>

## <a name="elevation-during-development"></a><span data-ttu-id="b2197-143">开发过程中的提升</span><span class="sxs-lookup"><span data-stu-id="b2197-143">Elevation during development</span></span>

<span data-ttu-id="b2197-144">在开发过程中，可能需要提升访问权限才能测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="b2197-144">During development, you may need elevated access to test your application.</span></span> <span data-ttu-id="b2197-145">（例如）IoT 应用就常存在这种情况。</span><span class="sxs-lookup"><span data-stu-id="b2197-145">This scenario is common for IoT apps, for example.</span></span> <span data-ttu-id="b2197-146">建议在构建应用程序时不要进行提升，而是在运行时使用提升。</span><span class="sxs-lookup"><span data-stu-id="b2197-146">We recommend that you build the application without elevation and then run it with elevation.</span></span> <span data-ttu-id="b2197-147">有几种模式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b2197-147">There are a few patterns, as follows:</span></span>

- <span data-ttu-id="b2197-148">使用生成的可执行文件（它提供最佳的启动性能）：</span><span class="sxs-lookup"><span data-stu-id="b2197-148">Using generated executable (it provides the best startup performance):</span></span>

   ```bash
   dotnet build
   sudo ./bin/Debug/netcoreapp3.0/APPLICATIONNAME
   ```
    
- <span data-ttu-id="b2197-149">使用 [dotnet run](dotnet-run.md) 命令与 `—no-build` 标志，以避免生成新的二进制文件：</span><span class="sxs-lookup"><span data-stu-id="b2197-149">Using the [dotnet run](dotnet-run.md) command with the `—no-build` flag to avoid generating new binaries:</span></span>

   ```bash
   dotnet build
   sudo dotnet run --no-build
   ```

## <a name="see-also"></a><span data-ttu-id="b2197-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2197-150">See also</span></span>

* [<span data-ttu-id="b2197-151">.NET Core 全局工具概述</span><span class="sxs-lookup"><span data-stu-id="b2197-151">.NET Core Global Tools overview</span></span>](global-tools.md)
