---
title: 确定已安装的 .NET Framework 版本
ms.date: 04/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
ms.openlocfilehash: b860aac01780acb67c53e822eff478b78198996b
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738188"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="e9c34-102">如何：确定已安装的 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="e9c34-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="e9c34-103">用户可在他们的计算机上[安装](../install/index.md)和运行 .NET Framework 的多个版本。</span><span class="sxs-lookup"><span data-stu-id="e9c34-103">Users can [install](../install/index.md) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="e9c34-104">当你开发或部署应用时，你可能需要知道用户的计算机上安装了哪些 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="e9c34-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span>

<span data-ttu-id="e9c34-105">.NET Framework 由两个采用不同版本的主要组件构成：</span><span class="sxs-lookup"><span data-stu-id="e9c34-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>

- <span data-ttu-id="e9c34-106">一组程序集，它们是为应用提供功能的类型与资源的集合。</span><span class="sxs-lookup"><span data-stu-id="e9c34-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="e9c34-107">.NET Framework 和程序集使用相同的版本号。</span><span class="sxs-lookup"><span data-stu-id="e9c34-107">The .NET Framework and assemblies share the same version number.</span></span>

- <span data-ttu-id="e9c34-108">公共语言运行时 (CLR)，可管理并执行应用的代码。</span><span class="sxs-lookup"><span data-stu-id="e9c34-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="e9c34-109">CLR 按其自己的版本号标识（请参阅[版本和依赖关系](versions-and-dependencies.md)）。</span><span class="sxs-lookup"><span data-stu-id="e9c34-109">The CLR is identified by its own version number (see [Versions and dependencies](versions-and-dependencies.md)).</span></span>

> [!NOTE]
> <span data-ttu-id="e9c34-110">每个新版本的 .NET Framework 都会保留早期版本中的功能并会添加新功能。</span><span class="sxs-lookup"><span data-stu-id="e9c34-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="e9c34-111">可在同一台计算机上同时加载多个版本的 .NET Framework，这意味着可安装 .NET Framework 而无需卸载以前的版本。</span><span class="sxs-lookup"><span data-stu-id="e9c34-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="e9c34-112">通常，你不应卸载以前版本的 .NET Framework，因为你使用的应用程序可能依赖于特定版本，如果删除该版本，可能会中断。</span><span class="sxs-lookup"><span data-stu-id="e9c34-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="e9c34-113">.NET Framework 版本和 CLR 版本之间存在差异：</span><span class="sxs-lookup"><span data-stu-id="e9c34-113">There is a difference between the .NET Framework version and the CLR version:</span></span>
>
> - <span data-ttu-id="e9c34-114">.NET Framework 版本基于构成 .Net Framework 类库的一组程序集。</span><span class="sxs-lookup"><span data-stu-id="e9c34-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="e9c34-115">例如，.NET Framework 版本包括 4.5、4.6.1 和 4.7.2。</span><span class="sxs-lookup"><span data-stu-id="e9c34-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span>
> - <span data-ttu-id="e9c34-116">CLR 版本基于 .NET Framework 应用程序执行的运行时。</span><span class="sxs-lookup"><span data-stu-id="e9c34-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="e9c34-117">单个 CLR 版本通常可支持多个 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="e9c34-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="e9c34-118">例如，CLR 版本 4.0.30319.*xxxxx* 支持 .NET Framework 版本 4 到 4.5.2（其中 *xxxxx* 小于 42000），而 CLR 版本 4.0.30319.42000 支持从 .NET Framework 4.6 开始的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="e9c34-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2, where *xxxxx* is less than 42000, and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span>
>
> <span data-ttu-id="e9c34-119">有关版本的详细信息，请参见 [.NET Framework 版本和依赖关系](versions-and-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="e9c34-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>

<span data-ttu-id="e9c34-120">注册表包含计算机上安装的 .NET Framework 版本列表。</span><span class="sxs-lookup"><span data-stu-id="e9c34-120">The registry contains a list of the .NET Framework versions installed on a computer.</span></span> <span data-ttu-id="e9c34-121">可使用注册表编辑器查看注册表或使用代码进行查询：</span><span class="sxs-lookup"><span data-stu-id="e9c34-121">You can either use the Registry Editor to view the registry or query it with code:</span></span>

- <span data-ttu-id="e9c34-122">查找较新的 .NET Framework 版本（4.5 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="e9c34-122">Find newer .NET Framework versions (4.5 and later):</span></span>

  - [<span data-ttu-id="e9c34-123">使用注册表编辑器查找 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="e9c34-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)
  - [<span data-ttu-id="e9c34-124">使用代码查询注册表以获取 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="e9c34-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)
  - [<span data-ttu-id="e9c34-125">使用 PowerShell 查询注册表以获取 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="e9c34-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)

- <span data-ttu-id="e9c34-126">查找较旧的 .NET Framework 版本 (1-4)：</span><span class="sxs-lookup"><span data-stu-id="e9c34-126">Find older .NET Framework versions (1 through 4):</span></span>

  - [<span data-ttu-id="e9c34-127">使用注册表编辑器查找 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="e9c34-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
  - [<span data-ttu-id="e9c34-128">使用代码查询注册表以获取 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="e9c34-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)

<span data-ttu-id="e9c34-129">若要获取计算机上安装的 CLR 版本列表，请使用工具或代码：</span><span class="sxs-lookup"><span data-stu-id="e9c34-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>

- [<span data-ttu-id="e9c34-130">使用 Clrver 工具</span><span class="sxs-lookup"><span data-stu-id="e9c34-130">Use the Clrver tool</span></span>](#clr_a)
- [<span data-ttu-id="e9c34-131">使用代码查询 Environment 类</span><span class="sxs-lookup"><span data-stu-id="e9c34-131">Use code to query the Environment class</span></span>](#clr_b)

<span data-ttu-id="e9c34-132">有关检测安装的每个 .NET Framework 版本的更新的信息，请参阅[如何：确定已安装的 .NET Framework 更新](how-to-determine-which-net-framework-updates-are-installed.md)。</span><span class="sxs-lookup"><span data-stu-id="e9c34-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span>

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="e9c34-133">查找较新的 .NET Framework 版本（4.5 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="e9c34-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<span data-ttu-id="e9c34-134">可使用注册表编辑器在注册表中查找版本信息，也可以通过编程方式查询注册表。</span><span class="sxs-lookup"><span data-stu-id="e9c34-134">You can use Registry Editor to find version information in the registry, or you can query the registry programmatically.</span></span>

<a name="net_b"></a>

### <a name="use-registry-editor"></a><span data-ttu-id="e9c34-135">使用注册表编辑器</span><span class="sxs-lookup"><span data-stu-id="e9c34-135">Use Registry Editor</span></span>

1. <span data-ttu-id="e9c34-136">在“开始”菜单中，选择“运行”，输入 regedit，然后选择“确定”     。</span><span class="sxs-lookup"><span data-stu-id="e9c34-136">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="e9c34-137">必须具有管理凭据才能运行 regedit。</span><span class="sxs-lookup"><span data-stu-id="e9c34-137">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="e9c34-138">在注册表编辑器中，打开以下子项：**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="e9c34-138">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="e9c34-139">如果“完整”子项不存在，则表示尚未安装 .NET Framework 4.5 或更高版本  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-139">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e9c34-140">注册表中的“.NET Framework 安装程序”  文件夹不以句点开头  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-140">The **NET Framework Setup** folder in the registry does *not* begin with a period.</span></span>

3. <span data-ttu-id="e9c34-141">请检查名为“Release”的 DWORD 条目  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-141">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="e9c34-142">如果存在，则安装 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e9c34-142">If it exists, then you have .NET Framework 4.5 or later installed.</span></span> <span data-ttu-id="e9c34-143">其值是对应于特定版本的 .NET Framework 的版本密钥。</span><span class="sxs-lookup"><span data-stu-id="e9c34-143">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="e9c34-144">以下图为例，“Release”条目的值为 378389，这是 .NET Framework 4.5 的版本密钥  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-144">In the following figure, for example, the value of the **Release** entry is 378389, which is the release key for .NET Framework 4.5.</span></span>

   <span data-ttu-id="e9c34-145">![.NET Framework 4.5 的注册表项](./media/clr-installdir.png ".NET Framework 4.5 的注册表项")</span><span class="sxs-lookup"><span data-stu-id="e9c34-145">![Registry entry for the .NET Framework 4.5](./media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="e9c34-146">下表列出了 .NET Framework 4.5 及更高版本的独立操作系统的  Release DWORD 的值。</span><span class="sxs-lookup"><span data-stu-id="e9c34-146">The following table lists the value of the **Release** DWORD on individual operating systems for .NET Framework 4.5 and later versions.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="e9c34-147">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="e9c34-147">.NET Framework version</span></span>|<span data-ttu-id="e9c34-148">Release DWORD 的值</span><span class="sxs-lookup"><span data-stu-id="e9c34-148">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="e9c34-149">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="e9c34-149">.NET Framework 4.5</span></span>|<span data-ttu-id="e9c34-150">所有 Windows 操作系统：378389</span><span class="sxs-lookup"><span data-stu-id="e9c34-150">All Windows operating systems: 378389</span></span>|
|<span data-ttu-id="e9c34-151">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="e9c34-151">.NET Framework 4.5.1</span></span>|<span data-ttu-id="e9c34-152">在 Windows 8.1 和 Windows Server 2012 R2 上：378675</span><span class="sxs-lookup"><span data-stu-id="e9c34-152">On Windows 8.1 and Windows Server 2012 R2: 378675</span></span><br /><span data-ttu-id="e9c34-153">在所有其他 Windows 操作系统上：378758</span><span class="sxs-lookup"><span data-stu-id="e9c34-153">On all other Windows operating systems: 378758</span></span>|
|<span data-ttu-id="e9c34-154">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="e9c34-154">.NET Framework 4.5.2</span></span>|<span data-ttu-id="e9c34-155">所有 Windows 操作系统：379893</span><span class="sxs-lookup"><span data-stu-id="e9c34-155">All Windows operating systems: 379893</span></span>|
|<span data-ttu-id="e9c34-156">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="e9c34-156">.NET Framework 4.6</span></span>|<span data-ttu-id="e9c34-157">在 Windows 10 上：393295</span><span class="sxs-lookup"><span data-stu-id="e9c34-157">On Windows 10: 393295</span></span><br /><span data-ttu-id="e9c34-158">在所有其他 Windows 操作系统上：393297</span><span class="sxs-lookup"><span data-stu-id="e9c34-158">On all other Windows operating systems: 393297</span></span>|
|<span data-ttu-id="e9c34-159">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="e9c34-159">.NET Framework 4.6.1</span></span>|<span data-ttu-id="e9c34-160">在 Windows 10 11 月更新系统上：394254</span><span class="sxs-lookup"><span data-stu-id="e9c34-160">On Windows 10 November Update systems: 394254</span></span><br /><span data-ttu-id="e9c34-161">在所有其他 Windows 操作系统（包括 Windows 10）上：394271</span><span class="sxs-lookup"><span data-stu-id="e9c34-161">On all other Windows operating systems (including Windows 10): 394271</span></span>|
|<span data-ttu-id="e9c34-162">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="e9c34-162">.NET Framework 4.6.2</span></span>|<span data-ttu-id="e9c34-163">在 Windows 10 周年更新和 Windows Server 2016 上：394802</span><span class="sxs-lookup"><span data-stu-id="e9c34-163">On Windows 10 Anniversary Update and Windows Server 2016: 394802</span></span><br /><span data-ttu-id="e9c34-164">在所有其他 Windows 操作系统（包括其他 Windows 10 操作系统）上：394806</span><span class="sxs-lookup"><span data-stu-id="e9c34-164">On all other Windows operating systems (including other Windows 10 operating systems): 394806</span></span>|
|<span data-ttu-id="e9c34-165">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="e9c34-165">.NET Framework 4.7</span></span>|<span data-ttu-id="e9c34-166">在 Windows 10 创意者更新上：460798</span><span class="sxs-lookup"><span data-stu-id="e9c34-166">On Windows 10 Creators Update: 460798</span></span><br /><span data-ttu-id="e9c34-167">在所有其他 Windows 操作系统（包括其他 Windows 10 操作系统）上：460805</span><span class="sxs-lookup"><span data-stu-id="e9c34-167">On all other Windows operating systems (including other Windows 10 operating systems): 460805</span></span>|
|<span data-ttu-id="e9c34-168">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="e9c34-168">.NET Framework 4.7.1</span></span>|<span data-ttu-id="e9c34-169">在 Windows 10 Fall Creators Update 和 Windows Server 版本 1709 上：461308</span><span class="sxs-lookup"><span data-stu-id="e9c34-169">On Windows 10 Fall Creators Update and Windows Server, version 1709: 461308</span></span><br/><span data-ttu-id="e9c34-170">在所有其他 Windows 操作系统（包括其他 Windows 10 操作系统）上：461310</span><span class="sxs-lookup"><span data-stu-id="e9c34-170">On all other Windows operating systems (including other Windows 10 operating systems): 461310</span></span>|
|<span data-ttu-id="e9c34-171">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="e9c34-171">.NET Framework 4.7.2</span></span>|<span data-ttu-id="e9c34-172">在 Windows 10 2018 年 4 月更新和 Windows Server 版本 1803 上：461808</span><span class="sxs-lookup"><span data-stu-id="e9c34-172">On Windows 10 April 2018 Update and Windows Server, version 1803: 461808</span></span><br/><span data-ttu-id="e9c34-173">在除 Windows 10 2018 年 4 月更新和 Windows Server 版本 1803 之外的所有 Windows 操作系统上：461814</span><span class="sxs-lookup"><span data-stu-id="e9c34-173">On all Windows operating systems other than Windows 10 April 2018 Update and Windows Server, version 1803: 461814</span></span>|
|<span data-ttu-id="e9c34-174">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="e9c34-174">.NET Framework 4.8</span></span>|<span data-ttu-id="e9c34-175">在 Windows 10 2019 年 5 月更新和 Windows 10 2019 年 11 月更新上：528040</span><span class="sxs-lookup"><span data-stu-id="e9c34-175">On Windows 10 May 2019 Update and Windows 10 November 2019 Update: 528040</span></span><br/><span data-ttu-id="e9c34-176">在所有其他 Windows 操作系统（包括其他 Windows 10 操作系统）上：528049</span><span class="sxs-lookup"><span data-stu-id="e9c34-176">On all other Windows operating systems (including other Windows 10 operating systems): 528049</span></span>|

#### <a name="specific-version"></a><span data-ttu-id="e9c34-177">特定版本</span><span class="sxs-lookup"><span data-stu-id="e9c34-177">Specific version</span></span>

<span data-ttu-id="e9c34-178">若要确定特定 Windows 操作系统版本上是否安装了特定版本的 .NET Framework，请测试 Release DWORD 值是否等于表中列出的值    。</span><span class="sxs-lookup"><span data-stu-id="e9c34-178">To determine whether a *specific* version of the .NET Framework is installed on a particular version of the Windows operating system, test whether the **Release** DWORD value is *equal to* the value listed in the table.</span></span> <span data-ttu-id="e9c34-179">例如，若要确定 Windows 10 系统上是否安装了 .NET Framework 4.6，请测试 Release 值是否等于  393295  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-179">For example, to determine whether .NET Framework 4.6 is present on a Windows 10 system, test for the a **Release** value that is *equal to* 393295.</span></span>

#### <a name="minimum-version"></a><span data-ttu-id="e9c34-180">最低版本</span><span class="sxs-lookup"><span data-stu-id="e9c34-180">Minimum version</span></span>

<span data-ttu-id="e9c34-181">若要确定是否安装了最低版本的 .NET Framework，请对该版本使用上个表中最小的 RELEASE DWORD 值   。</span><span class="sxs-lookup"><span data-stu-id="e9c34-181">To determine whether a *minimum* version of the .NET Framework is present, use the smallest **RELEASE** DWORD value for that version from the previous table.</span></span> <span data-ttu-id="e9c34-182">（为方便起见，后续表中也列出了最小值。）</span><span class="sxs-lookup"><span data-stu-id="e9c34-182">(For convenience, the minimum values are also listed in the table that follows.)</span></span>

<span data-ttu-id="e9c34-183">例如，如果应用程序在 .NET Framework 4.8 或更高版本下运行，请测试 RELEASE DWORD 值是否大于或等于 528040   。</span><span class="sxs-lookup"><span data-stu-id="e9c34-183">For example, if your application runs under .NET Framework 4.8 or a later version, test for a **RELEASE** DWORD value that is *greater than or equal to* 528040.</span></span>

|<span data-ttu-id="e9c34-184">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="e9c34-184">.NET Framework version</span></span>|<span data-ttu-id="e9c34-185">Release DWORD 的最小值</span><span class="sxs-lookup"><span data-stu-id="e9c34-185">Minimum value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="e9c34-186">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="e9c34-186">.NET Framework 4.5</span></span>|<span data-ttu-id="e9c34-187">378389</span><span class="sxs-lookup"><span data-stu-id="e9c34-187">378389</span></span>|
|<span data-ttu-id="e9c34-188">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="e9c34-188">.NET Framework 4.5.1</span></span>|<span data-ttu-id="e9c34-189">378675</span><span class="sxs-lookup"><span data-stu-id="e9c34-189">378675</span></span>|
|<span data-ttu-id="e9c34-190">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="e9c34-190">.NET Framework 4.5.2</span></span>|<span data-ttu-id="e9c34-191">379893</span><span class="sxs-lookup"><span data-stu-id="e9c34-191">379893</span></span>|
|<span data-ttu-id="e9c34-192">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="e9c34-192">.NET Framework 4.6</span></span>|<span data-ttu-id="e9c34-193">393295</span><span class="sxs-lookup"><span data-stu-id="e9c34-193">393295</span></span>|
|<span data-ttu-id="e9c34-194">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="e9c34-194">.NET Framework 4.6.1</span></span>|<span data-ttu-id="e9c34-195">394254</span><span class="sxs-lookup"><span data-stu-id="e9c34-195">394254</span></span>|
|<span data-ttu-id="e9c34-196">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="e9c34-196">.NET Framework 4.6.2</span></span>|<span data-ttu-id="e9c34-197">394802</span><span class="sxs-lookup"><span data-stu-id="e9c34-197">394802</span></span>|
|<span data-ttu-id="e9c34-198">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="e9c34-198">.NET Framework 4.7</span></span>|<span data-ttu-id="e9c34-199">460798</span><span class="sxs-lookup"><span data-stu-id="e9c34-199">460798</span></span>|
|<span data-ttu-id="e9c34-200">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="e9c34-200">.NET Framework 4.7.1</span></span>|<span data-ttu-id="e9c34-201">461308</span><span class="sxs-lookup"><span data-stu-id="e9c34-201">461308</span></span>|
|<span data-ttu-id="e9c34-202">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="e9c34-202">.NET Framework 4.7.2</span></span>|<span data-ttu-id="e9c34-203">461808</span><span class="sxs-lookup"><span data-stu-id="e9c34-203">461808</span></span>|
|<span data-ttu-id="e9c34-204">.NET Framework 4.8</span><span class="sxs-lookup"><span data-stu-id="e9c34-204">.NET Framework 4.8</span></span>|<span data-ttu-id="e9c34-205">528040</span><span class="sxs-lookup"><span data-stu-id="e9c34-205">528040</span></span>|

#### <a name="multiple-versions"></a><span data-ttu-id="e9c34-206">多个版本</span><span class="sxs-lookup"><span data-stu-id="e9c34-206">Multiple versions</span></span>

<span data-ttu-id="e9c34-207">若要测试多个版本，请先测试值是否大于或等于最新 .NET Framework 版本的较小 DWORD 值，然后将该值与每个连续较旧版本的较小 DWORD 值进行比较  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-207">To test for multiple versions, begin by testing for a value that is *greater than or equal to* the smaller DWORD value for the latest .NET Framework version, and then compare the value with the smaller DWORD value for each successive earlier version.</span></span> <span data-ttu-id="e9c34-208">例如，如果应用程序需要 .NET Framework 4.7 或更高版本，且你希望确定是否安装了特定版本的 .NET Framework，请先测试 RELEASE DWORD 值是否大于或等于 461808   （.NET Framework 4.7.2 的较小 DWORD 值）。</span><span class="sxs-lookup"><span data-stu-id="e9c34-208">For example, if your application requires .NET Framework 4.7 or later and you want to determine the specific version of .NET Framework present, start by testing for a **RELEASE** DWORD value that is *great than or equal to* to 461808 (the smaller DWORD value for .NET Framework 4.7.2).</span></span> <span data-ttu-id="e9c34-209">然后，将 RELEASE  DWORD 值与每个更新版本的 .NET Framework 的较小值进行比较。</span><span class="sxs-lookup"><span data-stu-id="e9c34-209">Then compare the **RELEASE** DWORD value with the smaller value for each later .NET Framework version.</span></span>

<a name="net_d"></a>

### <a name="query-the-registry-using-code"></a><span data-ttu-id="e9c34-210">使用代码查询注册表</span><span class="sxs-lookup"><span data-stu-id="e9c34-210">Query the registry using code</span></span>

1. <span data-ttu-id="e9c34-211">使用 <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> 和 <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> 方法访问 Windows 注册表中的“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full”子项  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-211">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

   <span data-ttu-id="e9c34-212">“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full”子项中存在“Release”DWORD 条目表示已在电脑上安装 .NET Framework 4.5 或更高版本   。</span><span class="sxs-lookup"><span data-stu-id="e9c34-212">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span>

2. <span data-ttu-id="e9c34-213">检查“Release”条目的值以确定安装的版本  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-213">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="e9c34-214">为了向前兼容，可检查是否有一个值大于或等于 [.NET Framework 版本表](#version_table)中所列的值。</span><span class="sxs-lookup"><span data-stu-id="e9c34-214">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="e9c34-215">下例检查注册表中“Release”条目的值，以查找已安装的 .NET Framework 4.5 及更高版本  ：</span><span class="sxs-lookup"><span data-stu-id="e9c34-215">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="e9c34-216">此示例遵循版本检查的建议做法：</span><span class="sxs-lookup"><span data-stu-id="e9c34-216">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="e9c34-217">检查“Release”条目的值是否大于或等于已知版本密钥的值   。</span><span class="sxs-lookup"><span data-stu-id="e9c34-217">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="e9c34-218">按从最新版本到最早版本的顺序检查。</span><span class="sxs-lookup"><span data-stu-id="e9c34-218">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a>

### <a name="use-powershell-to-check-for-a-minimum-required-version"></a><span data-ttu-id="e9c34-219">使用 PowerShell 检查要求的最低版本</span><span class="sxs-lookup"><span data-stu-id="e9c34-219">Use PowerShell to check for a minimum-required version</span></span>

<span data-ttu-id="e9c34-220">使用 PowerShell 命令检查“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full”子项的“Release”条目的值   。</span><span class="sxs-lookup"><span data-stu-id="e9c34-220">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="e9c34-221">以下示例检查“Release”条目的值，以确定是否已安装 .NET Framework 4.6.2 或更高版本  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-221">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="e9c34-222">如果安装了此代码，则返回 `True`，否则返回 `False`。</span><span class="sxs-lookup"><span data-stu-id="e9c34-222">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="e9c34-223">若要检查其他要求的最低 .NET Framework 版本，请使用 [.NET Framework 版本表](#version_table)中的值替换 `394802`。</span><span class="sxs-lookup"><span data-stu-id="e9c34-223">To check for a different minimum-required .NET Framework version, replace `394802` in the example with a value from the [.NET Framework version table](#version_table).</span></span> <span data-ttu-id="e9c34-224">使用所示的该版本的最小值。</span><span class="sxs-lookup"><span data-stu-id="e9c34-224">Use the smallest value shown for that version.</span></span>

## <a name="find-older-net-framework-versions-1-through-4"></a><span data-ttu-id="e9c34-225">查找较旧的 .NET Framework 版本 (1-4)</span><span class="sxs-lookup"><span data-stu-id="e9c34-225">Find older .NET Framework versions (1 through 4)</span></span>

<a name="net_a"></a>

### <a name="use-registry-editor-older-framework-versions"></a><span data-ttu-id="e9c34-226">使用注册表编辑器（较旧的框架版本）</span><span class="sxs-lookup"><span data-stu-id="e9c34-226">Use Registry Editor (older framework versions)</span></span>

1. <span data-ttu-id="e9c34-227">在“开始”菜单中，选择“运行”，输入 regedit，然后选择“确定”     。</span><span class="sxs-lookup"><span data-stu-id="e9c34-227">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

    <span data-ttu-id="e9c34-228">必须具有管理凭据才能运行 regedit。</span><span class="sxs-lookup"><span data-stu-id="e9c34-228">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="e9c34-229">在注册表编辑器中，打开以下子项：**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**：</span><span class="sxs-lookup"><span data-stu-id="e9c34-229">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>

    - <span data-ttu-id="e9c34-230">对于 .NET Framework 1.1 到 3.5 版，每个安装的版本都在“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP”子项下列为子项  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-230">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="e9c34-231">例如，“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5”  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-231">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="e9c34-232">版本号存储为版本子项的“Version”条目中的值  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-232">The version number is stored as a value in the version subkey's **Version** entry.</span></span>

    - <span data-ttu-id="e9c34-233">对于 .NET Framework 4，“Version”条目位于“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client”或“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full”子项下，或同时位于这两个子项下    。</span><span class="sxs-lookup"><span data-stu-id="e9c34-233">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e9c34-234">注册表中的“.NET Framework 安装程序”文件夹不以句点开头  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-234">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="e9c34-235">下图显示了 .NET Framework 3.5 的子项及其“Version”条目  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-235">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="e9c34-236">![.NET Framework 3.5 的注册表项。](./media/net-4-and-earlier.png ".NET Framework 3.5 及早期版本")</span><span class="sxs-lookup"><span data-stu-id="e9c34-236">![The registry entry for the .NET Framework 3.5.](./media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a>

### <a name="query-the-registry-using-code-older-framework-versions"></a><span data-ttu-id="e9c34-237">使用代码查询注册表（较旧的框架版本）</span><span class="sxs-lookup"><span data-stu-id="e9c34-237">Query the registry using code (older framework versions)</span></span>

<span data-ttu-id="e9c34-238">使用 <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> 类访问 Windows 注册表中的“HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP”子项  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-238">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="e9c34-239">以下示例查找已安装的 .NET Framework 1-4 版本：</span><span class="sxs-lookup"><span data-stu-id="e9c34-239">The following example finds the .NET Framework 1 through 4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

## <a name="find-clr-versions"></a><span data-ttu-id="e9c34-240">查找 CLR 版本</span><span class="sxs-lookup"><span data-stu-id="e9c34-240">Find CLR versions</span></span>

<a name="clr_a"></a>

### <a name="use-clrverexe"></a><span data-ttu-id="e9c34-241">使用 Clrver.exe</span><span class="sxs-lookup"><span data-stu-id="e9c34-241">Use Clrver.exe</span></span>

<span data-ttu-id="e9c34-242">使用 [CLR 版本工具 (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) 确定计算机上安装了哪些版本的 CLR：</span><span class="sxs-lookup"><span data-stu-id="e9c34-242">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="e9c34-243">从 [Visual Studio 的开发人员命令提示](../tools/developer-command-prompt-for-vs.md)，输入 `clrver`。</span><span class="sxs-lookup"><span data-stu-id="e9c34-243">From a [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), enter `clrver`.</span></span>

    <span data-ttu-id="e9c34-244">示例输出：</span><span class="sxs-lookup"><span data-stu-id="e9c34-244">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a>

### <a name="use-the-environment-class"></a><span data-ttu-id="e9c34-245">使用 Environment 类</span><span class="sxs-lookup"><span data-stu-id="e9c34-245">Use the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e9c34-246">对于 .NET Framework 4.5 及更高版本，请勿使用 <xref:System.Environment.Version%2A?displayProperty=nameWithType> 属性来检测 CLR 的版本。</span><span class="sxs-lookup"><span data-stu-id="e9c34-246">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="e9c34-247">而应按照[使用代码查找 .NET Framework 4.5 及更高版本](#net_d)中所述查询注册表。</span><span class="sxs-lookup"><span data-stu-id="e9c34-247">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="e9c34-248">查询 <xref:System.Environment.Version?displayProperty=nameWithType> 属性以检索 <xref:System.Version> 对象。</span><span class="sxs-lookup"><span data-stu-id="e9c34-248">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span>

    <span data-ttu-id="e9c34-249">返回的 `System.Version` 对象标识当前正在执行代码的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="e9c34-249">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="e9c34-250">它不返回计算机上可能已安装的程序集版本或运行时的其他版本。</span><span class="sxs-lookup"><span data-stu-id="e9c34-250">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="e9c34-251">对于 .NET Framework 版本 4、4.5、4.5.1 和 4.5.2，返回的 <xref:System.Version> 对象的字符串表示形式为 4.0.30319. *xxxxx*（其中 *xxxxx* 小于 42000）。</span><span class="sxs-lookup"><span data-stu-id="e9c34-251">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*, where *xxxxx* is less than 42000.</span></span> <span data-ttu-id="e9c34-252">对于 .NET Framework 4.6 及更高版本，它的格式为 4.0.30319.42000。</span><span class="sxs-lookup"><span data-stu-id="e9c34-252">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>

2. <span data-ttu-id="e9c34-253">获得 `Version` 对象后，按如下方式查询：</span><span class="sxs-lookup"><span data-stu-id="e9c34-253">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="e9c34-254">对于主要版本标识符（例如，4 表示版本 4.0），请使用 <xref:System.Version.Major%2A?displayProperty=nameWithType> 属性  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-254">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="e9c34-255">对于次要版本标识符（例如，0 表示版本 4.0），请使用 <xref:System.Version.Minor%2A?displayProperty=nameWithType> 属性 </span><span class="sxs-lookup"><span data-stu-id="e9c34-255">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="e9c34-256">对于整个版本字符串（例如，4.0.30319.18010），请使用 <xref:System.Version.ToString%2A?displayProperty=nameWithType> 方法  。</span><span class="sxs-lookup"><span data-stu-id="e9c34-256">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e9c34-257">此方法返回一个值，该值反映正在执行代码的运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="e9c34-257">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="e9c34-258">它不返回可能安装在计算机上的程序集版本或其他运行时版本。</span><span class="sxs-lookup"><span data-stu-id="e9c34-258">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>

<span data-ttu-id="e9c34-259">以下示例使用 <xref:System.Environment.Version%2A?displayProperty=nameWithType> 属性检索 CLR 版本信息：</span><span class="sxs-lookup"><span data-stu-id="e9c34-259">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="e9c34-260">请参阅</span><span class="sxs-lookup"><span data-stu-id="e9c34-260">See also</span></span>

- [<span data-ttu-id="e9c34-261">如何：确定安装了哪些 .NET Framework 更新</span><span class="sxs-lookup"><span data-stu-id="e9c34-261">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="e9c34-262">安装面向开发者的 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e9c34-262">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="e9c34-263">.NET Framework 版本和依赖关系</span><span class="sxs-lookup"><span data-stu-id="e9c34-263">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)
