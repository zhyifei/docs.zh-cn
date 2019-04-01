---
title: 如何：确定已安装的 .NET Framework 版本
ms.date: 03/18/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c4ad3ca5694457637a82a36c8db4534df43a9d7
ms.sourcegitcommit: 8258515adc6c37ab6278e5a3d102d593246f8672
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "58504426"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="7b226-102">如何：确定已安装的 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="7b226-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="7b226-103">用户可在他们的计算机上[安装](https://docs.microsoft.com/dotnet/framework/install)和运行 .NET Framework 的多个版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-103">Users can [install](https://docs.microsoft.com/dotnet/framework/install) and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="7b226-104">当你开发或部署应用时，你可能需要知道用户的计算机上安装了哪些 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> 

<span data-ttu-id="7b226-105">.NET Framework 由两个采用不同版本的主要组件构成：</span><span class="sxs-lookup"><span data-stu-id="7b226-105">The .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
- <span data-ttu-id="7b226-106">一组程序集，它们是为应用提供功能的类型与资源的集合。</span><span class="sxs-lookup"><span data-stu-id="7b226-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="7b226-107">.NET Framework 和程序集使用相同的版本号。</span><span class="sxs-lookup"><span data-stu-id="7b226-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
- <span data-ttu-id="7b226-108">公共语言运行时 (CLR)，可管理并执行应用的代码。</span><span class="sxs-lookup"><span data-stu-id="7b226-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="7b226-109">CLR 由其自己的版本号标识（请参阅[版本和依赖关系](~/docs/framework/migration-guide/versions-and-dependencies.md)）。</span><span class="sxs-lookup"><span data-stu-id="7b226-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  

> [!NOTE]
> <span data-ttu-id="7b226-110">每个新版本的 .NET Framework 都会保留早期版本中的功能并会添加新功能。</span><span class="sxs-lookup"><span data-stu-id="7b226-110">Each new version of the .NET Framework retains features from the previous versions and adds new features.</span></span> <span data-ttu-id="7b226-111">可在同一台计算机上同时加载多个版本的 .NET Framework，这意味着可安装 .NET Framework 而无需卸载以前的版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-111">You can load multiple versions of the .NET Framework on a single computer at the same time, which means that you can install the .NET Framework without having to uninstall previous versions.</span></span> <span data-ttu-id="7b226-112">通常，你不应卸载以前版本的 .NET Framework，因为你使用的应用程序可能依赖于特定版本，如果删除该版本，可能会中断。</span><span class="sxs-lookup"><span data-stu-id="7b226-112">In general, you shouldn't uninstall previous versions of the .NET Framework, because an application you use may depend on a specific version and may break if that version is removed.</span></span>
>
> <span data-ttu-id="7b226-113">.NET Framework 版本和 CLR 版本之间存在差异：</span><span class="sxs-lookup"><span data-stu-id="7b226-113">There is a difference between the .NET Framework version and the CLR version:</span></span> 
> - <span data-ttu-id="7b226-114">.NET Framework 版本基于构成 .Net Framework 类库的一组程序集。</span><span class="sxs-lookup"><span data-stu-id="7b226-114">The .NET Framework version is based on the set of assemblies that form the .NET Framework class library.</span></span> <span data-ttu-id="7b226-115">例如，.NET Framework 版本包括 4.5、4.6.1 和 4.7.2。</span><span class="sxs-lookup"><span data-stu-id="7b226-115">For example, .NET Framework versions include 4.5, 4.6.1, and 4.7.2.</span></span> 
>- <span data-ttu-id="7b226-116">CLR 版本基于 .NET Framework 应用程序执行的运行时。</span><span class="sxs-lookup"><span data-stu-id="7b226-116">The CLR version is based on the runtime on which .NET Framework applications execute.</span></span> <span data-ttu-id="7b226-117">单个 CLR 版本通常可支持多个 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-117">A single CLR version typically supports multiple .NET Framework versions.</span></span> <span data-ttu-id="7b226-118">例如，CLR 版本 4.0.30319.xxxxx 支持 .NET Framework 版本 4 到 4.5.2，而 CLR 版本 4.0.30319.42000 支持从 .NET Framework 4.6 开始的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-118">For example, CLR version 4.0.30319.*xxxxx* supports .NET Framework versions 4 through 4.5.2 and CLR version 4.0.30319.42000 supports .NET Framework versions starting with .NET Framework 4.6.</span></span> 
>
> <span data-ttu-id="7b226-119">有关版本的详细信息，请参见 [.NET Framework 版本和依赖关系](versions-and-dependencies.md)。</span><span class="sxs-lookup"><span data-stu-id="7b226-119">For more information about versions, see [.NET Framework versions and dependencies](versions-and-dependencies.md).</span></span>


<span data-ttu-id="7b226-120">若要获取计算机上安装的 .NET Framework 版本列表，请访问注册表。</span><span class="sxs-lookup"><span data-stu-id="7b226-120">To get a list of the .NET Framework versions installed on a computer, you access the registry.</span></span> <span data-ttu-id="7b226-121">可使用注册表编辑器查看注册表或使用代码进行查询：</span><span class="sxs-lookup"><span data-stu-id="7b226-121">You can either use the Registry Editor to view the registry or use code to query it:</span></span>
 
- <span data-ttu-id="7b226-122">查找较新的 .NET Framework 版本（4.5 及更高版本）：</span><span class="sxs-lookup"><span data-stu-id="7b226-122">Find newer .NET Framework versions (4.5 and later):</span></span> 
     - [<span data-ttu-id="7b226-123">使用注册表编辑器查找 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="7b226-123">Use the Registry Editor to find .NET Framework versions</span></span>](#net_b)  
     - [<span data-ttu-id="7b226-124">使用代码查询注册表以获取 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="7b226-124">Use code to query the registry for .NET Framework versions</span></span>](#net_d)  
     - [<span data-ttu-id="7b226-125">使用 PowerShell 查询注册表以获取 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="7b226-125">Use PowerShell to query the registry for .NET Framework versions</span></span>](#ps_a)
- <span data-ttu-id="7b226-126">查找较旧的 .NET Framework 版本 (1&#8211;4)：</span><span class="sxs-lookup"><span data-stu-id="7b226-126">Find older .NET Framework versions (1&#8211;4):</span></span>
     - [<span data-ttu-id="7b226-127">使用注册表编辑器查找 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="7b226-127">Use the Registry Editor to find .NET Framework versions</span></span>](#net_a)
     - [<span data-ttu-id="7b226-128">使用代码查询注册表以获取 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="7b226-128">Use code to query the registry for .NET Framework versions</span></span>](#net_c)   

<span data-ttu-id="7b226-129">若要获取计算机上安装的 CLR 版本列表，请使用工具或代码：</span><span class="sxs-lookup"><span data-stu-id="7b226-129">To get a list of the CLR versions installed on a computer, use a tool or code:</span></span>  
  
- [<span data-ttu-id="7b226-130">使用 Clrver 工具</span><span class="sxs-lookup"><span data-stu-id="7b226-130">Use the Clrver tool</span></span>](#clr_a)  
- [<span data-ttu-id="7b226-131">使用代码查询 Environment 类</span><span class="sxs-lookup"><span data-stu-id="7b226-131">Use code to query the Environment class</span></span>](#clr_b)  

<span data-ttu-id="7b226-132">有关检测安装的每个 .NET Framework 版本的更新的信息，请参阅[如何：确定已安装的 .NET Framework 更新](how-to-determine-which-net-framework-updates-are-installed.md)。</span><span class="sxs-lookup"><span data-stu-id="7b226-132">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine which .NET Framework updates are installed](how-to-determine-which-net-framework-updates-are-installed.md).</span></span> 
  

## <a name="find-newer-net-framework-versions-45-and-later"></a><span data-ttu-id="7b226-133">查找较新的 .NET Framework 版本（4.5 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="7b226-133">Find newer .NET Framework versions (4.5 and later)</span></span>

<a name="net_b"></a> 
### <a name="find-net-framework-versions-45-and-later-in-the-registry"></a><span data-ttu-id="7b226-134">在注册表中查找 .NET Framework 4.5 及更高版本</span><span class="sxs-lookup"><span data-stu-id="7b226-134">Find .NET Framework versions 4.5 and later in the registry</span></span>

1. <span data-ttu-id="7b226-135">在“开始”菜单中，选择“运行”，输入 regedit，然后选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="7b226-135">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>

     <span data-ttu-id="7b226-136">必须具有管理凭据才能运行 regedit。</span><span class="sxs-lookup"><span data-stu-id="7b226-136">You must have administrative credentials to run regedit.</span></span>

2. <span data-ttu-id="7b226-137">在注册表编辑器中，打开以下子项：**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span><span class="sxs-lookup"><span data-stu-id="7b226-137">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full**.</span></span> <span data-ttu-id="7b226-138">如果“完整”子项不存在，则表示尚未安装 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-138">If the **Full** subkey isn't present, then you don't have the .NET Framework 4.5 or later installed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7b226-139">注册表中的“.NET Framework 安装程序”文件夹不以句点开头。</span><span class="sxs-lookup"><span data-stu-id="7b226-139">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

3. <span data-ttu-id="7b226-140">请检查名为“Release”的 DWORD 条目。</span><span class="sxs-lookup"><span data-stu-id="7b226-140">Check for a DWORD entry named **Release**.</span></span> <span data-ttu-id="7b226-141">如果存在，则安装 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-141">If it exists, then you have .NET Framework 4.5 or later versions installed.</span></span> <span data-ttu-id="7b226-142">其值是对应于特定版本的 .NET Framework 的版本密钥。</span><span class="sxs-lookup"><span data-stu-id="7b226-142">Its value is a release key that corresponds to a particular version of the .NET Framework.</span></span> <span data-ttu-id="7b226-143">以下图为例，“Release”条目的值为 378389，这是 .NET Framework 4.5 的版本密钥。</span><span class="sxs-lookup"><span data-stu-id="7b226-143">In the following figure, for example, the value of the **Release** entry is *378389*, which is the release key for .NET Framework 4.5.</span></span> 

     <span data-ttu-id="7b226-144">![.NET Framework 4.5 的注册表项](media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span><span class="sxs-lookup"><span data-stu-id="7b226-144">![Registry entry for the .NET Framework 4.5](media/clr-installdir.png "Registry entry for the .NET Framework 4.5")</span></span>

<span data-ttu-id="7b226-145">下表列出每个 .NET Framework 版本“Release”条目的最小值。</span><span class="sxs-lookup"><span data-stu-id="7b226-145">The following table lists the minimum value of the **Release** entry for each .NET Framework version.</span></span> <span data-ttu-id="7b226-146">可以使用这些值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7b226-146">You can use these values as follows:</span></span>

- <span data-ttu-id="7b226-147">若要确定是否存在 .NET Framework 最低版本，测试在注册表中找到的“Release”DWORD 值是大于还是等于表中列出的值。</span><span class="sxs-lookup"><span data-stu-id="7b226-147">To determine whether a minimum .NET Framework version is present, test whether the **Release** DWORD value found in the registry is *greater than or equal to* the value listed in the table.</span></span> <span data-ttu-id="7b226-148">例如，如果应用程序需要 .NET Framework 4.7 或更高版本，则测试最小版本密钥值是否为 460798。</span><span class="sxs-lookup"><span data-stu-id="7b226-148">For example, if your application requires the .NET Framework 4.7 or later, you test for a minimum release key value of *460798*.</span></span>

- <span data-ttu-id="7b226-149">若要测试多个版本，请从最新的 .NET Framework 版本开始，然后对每个后续的早期版本进行测试。</span><span class="sxs-lookup"><span data-stu-id="7b226-149">To test for multiple versions, begin with the latest .NET Framework version, and then test for each successive earlier version.</span></span>

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

<a name="version_table"></a>

|<span data-ttu-id="7b226-150">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="7b226-150">.NET Framework version</span></span>|<span data-ttu-id="7b226-151">Release DWORD 的值</span><span class="sxs-lookup"><span data-stu-id="7b226-151">Value of the Release DWORD</span></span>|
|--------------------------------|-------------|
|<span data-ttu-id="7b226-152">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="7b226-152">.NET Framework 4.5</span></span>|<span data-ttu-id="7b226-153">378389</span><span class="sxs-lookup"><span data-stu-id="7b226-153">378389</span></span>|
|<span data-ttu-id="7b226-154">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="7b226-154">.NET Framework 4.5.1</span></span>|<span data-ttu-id="7b226-155">378675</span><span class="sxs-lookup"><span data-stu-id="7b226-155">378675</span></span>|
|<span data-ttu-id="7b226-156">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="7b226-156">.NET Framework 4.5.2</span></span>|<span data-ttu-id="7b226-157">379893</span><span class="sxs-lookup"><span data-stu-id="7b226-157">379893</span></span>|
|<span data-ttu-id="7b226-158">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="7b226-158">.NET Framework 4.6</span></span>|<span data-ttu-id="7b226-159">393295</span><span class="sxs-lookup"><span data-stu-id="7b226-159">393295</span></span>|
|<span data-ttu-id="7b226-160">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="7b226-160">.NET Framework 4.6.1</span></span>|<span data-ttu-id="7b226-161">394254</span><span class="sxs-lookup"><span data-stu-id="7b226-161">394254</span></span>|
|<span data-ttu-id="7b226-162">.NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="7b226-162">.NET Framework 4.6.2</span></span>|<span data-ttu-id="7b226-163">394802</span><span class="sxs-lookup"><span data-stu-id="7b226-163">394802</span></span>|
|<span data-ttu-id="7b226-164">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="7b226-164">.NET Framework 4.7</span></span>|<span data-ttu-id="7b226-165">460798</span><span class="sxs-lookup"><span data-stu-id="7b226-165">460798</span></span>|
|<span data-ttu-id="7b226-166">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="7b226-166">.NET Framework 4.7.1</span></span>|<span data-ttu-id="7b226-167">461308</span><span class="sxs-lookup"><span data-stu-id="7b226-167">461308</span></span>|
|<span data-ttu-id="7b226-168">.NET Framework 4.7.2</span><span class="sxs-lookup"><span data-stu-id="7b226-168">.NET Framework 4.7.2</span></span>|<span data-ttu-id="7b226-169">461808</span><span class="sxs-lookup"><span data-stu-id="7b226-169">461808</span></span>|

<span data-ttu-id="7b226-170">有关完整的适用于特定 Windows 操作系统版本的 .NET Framework 的版本密钥表，请参阅 [.NET Framework 版本密钥和 Windows 操作系统版本](release-keys-and-os-versions.md)。</span><span class="sxs-lookup"><span data-stu-id="7b226-170">For a complete table of release keys for the .NET Framework for specific Windows operating system versions, see [.NET Framework release keys and Windows operating system versions](release-keys-and-os-versions.md).</span></span>


<a name="net_d"></a> 
### <a name="find-net-framework-versions-45-and-later-with-code"></a><span data-ttu-id="7b226-171">使用代码查找 .NET Framework 4.5 及更高版本</span><span class="sxs-lookup"><span data-stu-id="7b226-171">Find .NET Framework versions 4.5 and later with code</span></span>

1. <span data-ttu-id="7b226-172">使用 <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> 和 <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> 方法访问 Windows 注册表中的“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full”子项。</span><span class="sxs-lookup"><span data-stu-id="7b226-172">Use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> methods to access the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey in the Windows registry.</span></span>

    <span data-ttu-id="7b226-173">“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full”子项中存在“Release”DWORD 条目表示已在电脑上安装 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-173">The existence of the **Release** DWORD entry in the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey indicates that the .NET Framework 4.5 or a later version is installed on a computer.</span></span> 

2. <span data-ttu-id="7b226-174">检查“Release”条目的值以确定安装的版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-174">Check the value of the **Release** entry to determine the installed version.</span></span> <span data-ttu-id="7b226-175">为了向前兼容，可检查是否有一个值大于或等于 [.NET Framework 版本表](#version_table)中所列的值。</span><span class="sxs-lookup"><span data-stu-id="7b226-175">To be forward-compatible, check for a value greater than or equal to the value listed in the [.NET Framework version table](#version_table).</span></span>

<span data-ttu-id="7b226-176">下例检查注册表中“Release”条目的值，以查找已安装的 .NET Framework 4.5 及更高版本：</span><span class="sxs-lookup"><span data-stu-id="7b226-176">The following example checks the value of the **Release** entry in the registry to find the .NET Framework 4.5 and later versions that are installed:</span></span>

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

<span data-ttu-id="7b226-177">此示例遵循版本检查的建议做法：</span><span class="sxs-lookup"><span data-stu-id="7b226-177">This example follows the recommended practice for version checking:</span></span>

- <span data-ttu-id="7b226-178">检查“Release”条目的值是否大于或等于已知版本密钥的值。</span><span class="sxs-lookup"><span data-stu-id="7b226-178">It checks whether the value of the **Release** entry is *greater than or equal to* the value of the known release keys.</span></span>

- <span data-ttu-id="7b226-179">按从最新版本到最早版本的顺序检查。</span><span class="sxs-lookup"><span data-stu-id="7b226-179">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
### <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a><span data-ttu-id="7b226-180">使用 PowerShell 检查所需的 .NET Framework 的最低版本（4.5 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="7b226-180">Check for a minimum-required .NET Framework version (4.5 and later) with PowerShell</span></span>

- <span data-ttu-id="7b226-181">使用 PowerShell 命令检查“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full”子项的“Release”条目的值。</span><span class="sxs-lookup"><span data-stu-id="7b226-181">Use PowerShell commands to check the value of the **Release** entry of the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full** subkey.</span></span>

<span data-ttu-id="7b226-182">以下示例检查“Release”条目的值，以确定是否已安装 .NET Framework 4.6.2 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-182">The following examples check the value of the **Release** entry to determine whether the .NET Framework 4.6.2 or later is installed.</span></span> <span data-ttu-id="7b226-183">如果安装了此代码，则返回 `True`，否则返回 `False`。</span><span class="sxs-lookup"><span data-stu-id="7b226-183">This code returns `True` if it's installed and `False` otherwise.</span></span>

```PowerShell
# PowerShell 5
 Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' |  Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
 ```

```PowerShell
# PowerShell 4
(Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -ge 394802
```

<span data-ttu-id="7b226-184">若要检查不同的所需最低 .NET Framework 版本，请使用 [.NET Framework 版本表](#version_table)中的“Release”值替换这些示例中的 394802。</span><span class="sxs-lookup"><span data-stu-id="7b226-184">To check for a different minimum-required .NET Framework version, replace *394802* in these examples with a **Release** value from the [.NET Framework version table](#version_table).</span></span>

## <a name="find-older-net-framework-versions-182114"></a><span data-ttu-id="7b226-185">查找较旧的 .NET Framework 版本 1&#8211;4</span><span class="sxs-lookup"><span data-stu-id="7b226-185">Find older .NET Framework versions (1&#8211;4)</span></span>

<a name="net_a"></a>
### <a name="find-net-framework-versions-182114-in-the-registry"></a><span data-ttu-id="7b226-186">在注册表中查找 .NET Framework 版本 1&#8211;4</span><span class="sxs-lookup"><span data-stu-id="7b226-186">Find .NET Framework versions 1&#8211;4 in the registry</span></span> 
  
1. <span data-ttu-id="7b226-187">在“开始”菜单中，选择“运行”，输入 regedit，然后选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="7b226-187">From the **Start** menu, choose **Run**, enter *regedit*, and then select **OK**.</span></span>
  
    <span data-ttu-id="7b226-188">必须具有管理凭据才能运行 regedit。</span><span class="sxs-lookup"><span data-stu-id="7b226-188">You must have administrative credentials to run regedit.</span></span>  

2. <span data-ttu-id="7b226-189">在注册表编辑器中，打开以下子项：**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**：</span><span class="sxs-lookup"><span data-stu-id="7b226-189">In the Registry Editor, open the following subkey: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP**:</span></span>  

    - <span data-ttu-id="7b226-190">对于 .NET Framework 1.1 到 3.5 版，每个安装的版本都在“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP”子项下列为子项。</span><span class="sxs-lookup"><span data-stu-id="7b226-190">For .NET Framework versions 1.1 through 3.5, each installed version is listed as a subkey under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP** subkey.</span></span> <span data-ttu-id="7b226-191">例如，“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5”。</span><span class="sxs-lookup"><span data-stu-id="7b226-191">For example, **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v3.5**.</span></span> <span data-ttu-id="7b226-192">版本号存储为版本子项的“Version”条目中的值。</span><span class="sxs-lookup"><span data-stu-id="7b226-192">The version number is stored as a value in the version subkey's **Version** entry.</span></span> 
     
    - <span data-ttu-id="7b226-193">对于 .NET Framework 4，“Version”条目位于“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client”或“HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full”子项下，或同时位于这两个子项下。</span><span class="sxs-lookup"><span data-stu-id="7b226-193">For .NET Framework 4, the **Version** entry is under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client** subkey, the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full** subkey, or under both subkeys.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7b226-194">注册表中的“.NET Framework 安装程序”文件夹不以句点开头。</span><span class="sxs-lookup"><span data-stu-id="7b226-194">The **NET Framework Setup** folder in the registry does not begin with a period.</span></span>

    <span data-ttu-id="7b226-195">下图显示了 .NET Framework 3.5 的子项及其“Version”条目。</span><span class="sxs-lookup"><span data-stu-id="7b226-195">The following figure shows the subkey and its **Version** entry for the .NET Framework 3.5.</span></span>

    <span data-ttu-id="7b226-196">![.NET Framework 3.5 的注册表项。](media/net-4-and-earlier.png ".NET Framework 3.5 及更早版本")</span><span class="sxs-lookup"><span data-stu-id="7b226-196">![The registry entry for the .NET Framework 3.5.](media/net-4-and-earlier.png ".NET Framework 3.5 and earlier versions")</span></span>

<a name="net_c"></a> 
### <a name="find-net-framework-versions-182114-with-code"></a><span data-ttu-id="7b226-197">使用代码查找 .NET Framework 版本 1&#8211;4</span><span class="sxs-lookup"><span data-stu-id="7b226-197">Find .NET Framework versions 1&#8211;4 with code</span></span>

- <span data-ttu-id="7b226-198">使用 <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> 类访问 Windows 注册表中的“HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP”子项。</span><span class="sxs-lookup"><span data-stu-id="7b226-198">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the **HKEY_LOCAL_MACHINE\Software\Microsoft\NET Framework Setup\NDP** subkey in the Windows registry.</span></span>

<span data-ttu-id="7b226-199">以下示例查找已安装的 .NET Framework 1-4 1&#8211;4：</span><span class="sxs-lookup"><span data-stu-id="7b226-199">The following example finds the .NET Framework 1&#8211;4 versions that are installed:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]


## <a name="find-clr-versions"></a><span data-ttu-id="7b226-200">查找 CLR 版本</span><span class="sxs-lookup"><span data-stu-id="7b226-200">Find CLR versions</span></span>
  
<a name="clr_a"></a> 
### <a name="find-the-current-clr-version-with-clrverexe"></a><span data-ttu-id="7b226-201">使用 Clrver.exe 查找当前的 CLR 版本</span><span class="sxs-lookup"><span data-stu-id="7b226-201">Find the current CLR version with Clrver.exe</span></span>

<span data-ttu-id="7b226-202">使用 [CLR 版本工具 (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) 确定计算机上安装了哪些版本的 CLR：</span><span class="sxs-lookup"><span data-stu-id="7b226-202">Use the [CLR Version tool (Clrver.exe)](../tools/clrver-exe-clr-version-tool.md) to determine which versions of the CLR are installed on a computer:</span></span>

- <span data-ttu-id="7b226-203">从 [Visual Studio 的开发人员命令提示](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs)，输入 `clrver`。</span><span class="sxs-lookup"><span data-stu-id="7b226-203">From a [Developer Command Prompt for Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs), enter `clrver`.</span></span>

    <span data-ttu-id="7b226-204">示例输出：</span><span class="sxs-lookup"><span data-stu-id="7b226-204">Sample output:</span></span>

    ```console
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

<a name="clr_b"></a> 
### <a name="find-the-current-clr-version-with-the-environment-class"></a><span data-ttu-id="7b226-205">使用 Environment 类查找当前的 CLR 版本</span><span class="sxs-lookup"><span data-stu-id="7b226-205">Find the current CLR version with the Environment class</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7b226-206">对于 .NET Framework 4.5 及更高版本，请勿使用 <xref:System.Environment.Version%2A?displayProperty=nameWithType> 属性来检测 CLR 的版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-206">For the .NET Framework 4.5 and later versions, don't use the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the CLR.</span></span> <span data-ttu-id="7b226-207">而应按照[使用代码查找 .NET Framework 4.5 及更高版本](#net_d)中所述查询注册表。</span><span class="sxs-lookup"><span data-stu-id="7b226-207">Instead, query the registry as described in [Find .NET Framework versions 4.5 and later with code](#net_d).</span></span>

1. <span data-ttu-id="7b226-208">查询 <xref:System.Environment.Version?displayProperty=nameWithType> 属性以检索 <xref:System.Version> 对象。</span><span class="sxs-lookup"><span data-stu-id="7b226-208">Query the <xref:System.Environment.Version?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object.</span></span> 

    <span data-ttu-id="7b226-209">返回的 `System.Version` 对象标识当前正在执行代码的运行时版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-209">The returned `System.Version` object identifies the version of the runtime that's currently executing the code.</span></span> <span data-ttu-id="7b226-210">它不返回计算机上可能已安装的程序集版本或运行时的其他版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-210">It doesn't return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

    <span data-ttu-id="7b226-211">对于 .NET Framework 版本 4,4.5、4.5.1 和 4.5.2，返回的 <xref:System.Version> 对象的字符串表示形式为 4.0.30319. xxxxx 。</span><span class="sxs-lookup"><span data-stu-id="7b226-211">For the .NET Framework versions 4, 4.5, 4.5.1, and 4.5.2, the string representation of the returned <xref:System.Version> object has the form 4.0.30319.*xxxxx*.</span></span> <span data-ttu-id="7b226-212">对于 .NET Framework 4.6 及更高版本，它的格式为 4.0.30319.42000。</span><span class="sxs-lookup"><span data-stu-id="7b226-212">For the .NET Framework 4.6 and later versions, it has the form 4.0.30319.42000.</span></span>    

2. <span data-ttu-id="7b226-213">获得 `Version` 对象后，按如下方式查询：</span><span class="sxs-lookup"><span data-stu-id="7b226-213">After you have the `Version` object, query it as follows:</span></span>

   - <span data-ttu-id="7b226-214">对于主要版本标识符（例如，4 表示版本 4.0），请使用 <xref:System.Version.Major%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="7b226-214">For the major release identifier (for example, *4* for version 4.0), use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="7b226-215">对于次要版本标识符（例如，0 表示版本 4.0），请使用 <xref:System.Version.Minor%2A?displayProperty=nameWithType> 属性</span><span class="sxs-lookup"><span data-stu-id="7b226-215">For the minor release identifier (for example, *0* for version 4.0), use the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property.</span></span>

   - <span data-ttu-id="7b226-216">对于整个版本字符串（例如，4.0.30319.18010），请使用 <xref:System.Version.ToString%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="7b226-216">For the entire version string (for example, *4.0.30319.18010*), use the <xref:System.Version.ToString%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7b226-217">此方法返回一个值，该值反映正在执行代码的运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-217">This method returns a single value that reflects the version of the runtime that's executing the code.</span></span> <span data-ttu-id="7b226-218">它不返回可能安装在计算机上的程序集版本或其他运行时版本。</span><span class="sxs-lookup"><span data-stu-id="7b226-218">It doesn't return assembly versions or other runtime versions that may be installed on the computer.</span></span>



<span data-ttu-id="7b226-219">以下示例使用 <xref:System.Environment.Version%2A?displayProperty=nameWithType> 属性检索 CLR 版本信息：</span><span class="sxs-lookup"><span data-stu-id="7b226-219">The following example uses the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve CLR version information:</span></span>

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a><span data-ttu-id="7b226-220">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b226-220">See also</span></span>

- [<span data-ttu-id="7b226-221">如何：确定安装了哪些 .NET Framework 更新</span><span class="sxs-lookup"><span data-stu-id="7b226-221">How to: Determine which .NET Framework updates are installed</span></span>](how-to-determine-which-net-framework-updates-are-installed.md)
- [<span data-ttu-id="7b226-222">安装面向开发者的 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7b226-222">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="7b226-223">.NET Framework 版本和依赖关系</span><span class="sxs-lookup"><span data-stu-id="7b226-223">.NET Framework versions and dependencies</span></span>](versions-and-dependencies.md)
