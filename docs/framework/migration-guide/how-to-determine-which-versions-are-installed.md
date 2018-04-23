---
title: 如何：确定安装了哪些 .NET Framework 版本
ms.date: 01/24/2018
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: edf1e5a53f6f578f943cf8775a798b5681d2d9dd
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a><span data-ttu-id="8c327-102">如何：确定安装了哪些 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="8c327-102">How to: Determine which .NET Framework versions are installed</span></span>

<span data-ttu-id="8c327-103">用户可在他们的计算机上安装和运行 .NET Framework 的多个版本。</span><span class="sxs-lookup"><span data-stu-id="8c327-103">Users can install and run multiple versions of the .NET Framework on their computers.</span></span> <span data-ttu-id="8c327-104">当你开发或部署应用时，你可能需要知道用户的计算机上安装了哪些 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="8c327-104">When you develop or deploy your app, you might need to know which .NET Framework versions are installed on the user’s computer.</span></span> <span data-ttu-id="8c327-105">请注意，.NET Framework 由两个采用不同版本的主要组件构成：</span><span class="sxs-lookup"><span data-stu-id="8c327-105">Note that the .NET Framework consists of two main components, which are versioned separately:</span></span>  
  
-   <span data-ttu-id="8c327-106">一组程序集，它们是为应用提供功能的类型与资源的集合。</span><span class="sxs-lookup"><span data-stu-id="8c327-106">A set of assemblies, which are collections of types and resources that provide the functionality for your apps.</span></span> <span data-ttu-id="8c327-107">.NET Framework 和程序集使用相同的版本号。</span><span class="sxs-lookup"><span data-stu-id="8c327-107">The .NET Framework and assemblies share the same version number.</span></span>  
  
-   <span data-ttu-id="8c327-108">公共语言运行时 (CLR)，可管理并执行应用的代码。</span><span class="sxs-lookup"><span data-stu-id="8c327-108">The common language runtime (CLR), which manages and executes your app's code.</span></span> <span data-ttu-id="8c327-109">CLR 由其自己的版本号标识（请参阅[版本和依赖关系](~/docs/framework/migration-guide/versions-and-dependencies.md)）。</span><span class="sxs-lookup"><span data-stu-id="8c327-109">The CLR is identified by its own version number (see [Versions and Dependencies](~/docs/framework/migration-guide/versions-and-dependencies.md)).</span></span>  
  
 <span data-ttu-id="8c327-110">若要获取计算机上安装的 .NET Framework 版本的准确列表，你可以在代码中查看注册表或查询注册表：</span><span class="sxs-lookup"><span data-stu-id="8c327-110">To get an accurate list of the .NET Framework versions installed on a computer, you can view the registry or query the registry in code:</span></span>  
  
 [<span data-ttu-id="8c327-111">查看注册表（版本 1-4）</span><span class="sxs-lookup"><span data-stu-id="8c327-111">Viewing the registry (versions 1-4)</span></span>](#net_a)  
 [<span data-ttu-id="8c327-112">查看注册表（版本 4.5 和更高版本）</span><span class="sxs-lookup"><span data-stu-id="8c327-112">Viewing the registry (version 4.5 and later)</span></span>](#net_b)  
 [<span data-ttu-id="8c327-113">使用代码查询注册表（版本 1-4）</span><span class="sxs-lookup"><span data-stu-id="8c327-113">Using code to query the registry (versions 1-4)</span></span>](#net_c)  
 [<span data-ttu-id="8c327-114">使用代码查询注册表（版本 4.5 和更高版本）</span><span class="sxs-lookup"><span data-stu-id="8c327-114">Using code to query the registry (version 4.5 and later)</span></span>](#net_d)  
 [<span data-ttu-id="8c327-115">使用 PowerShell 查询注册表（版本 4.5 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="8c327-115">Using PowerShell to query the registry (version 4.5 and later)</span></span>](#ps_a)  
  
 <span data-ttu-id="8c327-116">若要查找 CLR 版本，你可以使用工具或代码：</span><span class="sxs-lookup"><span data-stu-id="8c327-116">To find the CLR version, you can use a tool or code:</span></span>  
  
 [<span data-ttu-id="8c327-117">使用 Clrver 工具</span><span class="sxs-lookup"><span data-stu-id="8c327-117">Using the Clrver tool</span></span>](#clr_a)  
 [<span data-ttu-id="8c327-118">使用代码查询 System.Environment 类</span><span class="sxs-lookup"><span data-stu-id="8c327-118">Using code to query the System.Environment class</span></span>](#clr_b)  
  
 <span data-ttu-id="8c327-119">有关检测每个版本 .NET Framework 所安装更新的信息，请参阅[如何：确定安装了哪些 .NET Framework 更新](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)。</span><span class="sxs-lookup"><span data-stu-id="8c327-119">For information about detecting the installed updates for each version of the .NET Framework, see [How to: Determine Which .NET Framework Updates Are Installed](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md).</span></span> <span data-ttu-id="8c327-120">若要了解如何安装 .NET Framework，请参阅[安装面向开发人员的 .NET Framework](../../../docs/framework/install/guide-for-developers.md)。</span><span class="sxs-lookup"><span data-stu-id="8c327-120">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
<a name="net_a"></a>   
## <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-1-4"></a><span data-ttu-id="8c327-121">通过查看注册表来查找 .NET Framework 版本 (.NET Framework 1-4)</span><span class="sxs-lookup"><span data-stu-id="8c327-121">To find .NET Framework versions by viewing the registry (.NET Framework 1-4)</span></span>  
  
1.  <span data-ttu-id="8c327-122">在“开始”菜单上，选择“运行”。</span><span class="sxs-lookup"><span data-stu-id="8c327-122">On the **Start** menu, choose **Run**.</span></span>  
  
2.  <span data-ttu-id="8c327-123">在“打开”框中，输入“regedit.exe”。</span><span class="sxs-lookup"><span data-stu-id="8c327-123">In the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="8c327-124">你必须具有管理凭据才能运行 regedit.exe。</span><span class="sxs-lookup"><span data-stu-id="8c327-124">You must have administrative credentials to run regedit.exe.</span></span>  
  
3.  <span data-ttu-id="8c327-125">在注册表编辑器中，打开以下子项：</span><span class="sxs-lookup"><span data-stu-id="8c327-125">In the Registry Editor, open the following subkey:</span></span>  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     <span data-ttu-id="8c327-126">安装的版本将在 NDP 子项的下方列出。</span><span class="sxs-lookup"><span data-stu-id="8c327-126">The installed versions are listed under the NDP subkey.</span></span> <span data-ttu-id="8c327-127">版本号存储在“版本”项中。</span><span class="sxs-lookup"><span data-stu-id="8c327-127">The version number is stored in the **Version** entry.</span></span> <span data-ttu-id="8c327-128">对于 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，“版本”项位于客户端或完整子项下（在 NDP 下），或在这两个子项下。</span><span class="sxs-lookup"><span data-stu-id="8c327-128">For the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] the **Version** entry is under the Client or Full subkey (under NDP), or under both subkeys.</span></span>  
  

    > [!NOTE]
    > <span data-ttu-id="8c327-129">注册表中的“NET Framework Setup”文件夹不会以句点开头。</span><span class="sxs-lookup"><span data-stu-id="8c327-129">The "NET Framework Setup" folder in the registry does not begin with a period.</span></span>

<a name="net_b"></a> 
## <a name="to-find-net-framework-versions-by-viewing-the-registry-net-framework-45-and-later"></a><span data-ttu-id="8c327-130">通过查看注册表来查找 .NET Framework 版本（.NET Framework 4.5 和更高版本）</span><span class="sxs-lookup"><span data-stu-id="8c327-130">To find .NET Framework versions by viewing the registry (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="8c327-131">在“开始”菜单上，选择“运行”。</span><span class="sxs-lookup"><span data-stu-id="8c327-131">On the **Start** menu, choose **Run**.</span></span>

2. <span data-ttu-id="8c327-132">在“打开”框中，输入“regedit.exe”。</span><span class="sxs-lookup"><span data-stu-id="8c327-132">In the **Open** box, enter **regedit.exe**.</span></span>

     <span data-ttu-id="8c327-133">你必须具有管理凭据才能运行 regedit.exe。</span><span class="sxs-lookup"><span data-stu-id="8c327-133">You must have administrative credentials to run regedit.exe.</span></span>

3. <span data-ttu-id="8c327-134">在注册表编辑器中，打开以下子项：</span><span class="sxs-lookup"><span data-stu-id="8c327-134">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     <span data-ttu-id="8c327-135">请注意，`Full` 子项的路径包括 `Net Framework` 子项，而不包括 `.NET Framework`。</span><span class="sxs-lookup"><span data-stu-id="8c327-135">Note that the path to the `Full` subkey includes the subkey `Net Framework` rather than `.NET Framework`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8c327-136">如果 `Full` 子项不存在，则表示你尚未安装 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8c327-136">If the `Full` subkey is not present, then you do not have the .NET Framework 4.5 or later installed.</span></span>

     <span data-ttu-id="8c327-137">检查名为 `Release` 的 DWORD 值。</span><span class="sxs-lookup"><span data-stu-id="8c327-137">Check for a DWORD value named `Release`.</span></span> <span data-ttu-id="8c327-138">存在 `Release` DWORD 表明该计算机上已安装 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="8c327-138">The existence of the `Release` DWORD indicates that the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or newer has been installed on that computer.</span></span>

     <span data-ttu-id="8c327-139">![.NET Framework 4.5 的注册表项。](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span><span class="sxs-lookup"><span data-stu-id="8c327-139">![The registry entry for the .NET Framework 4.5.](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")</span></span>

     <span data-ttu-id="8c327-140">`Release` DWORD 的值指示将安装的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="8c327-140">The value of the `Release` DWORD indicates which version of the .NET Framework is installed.</span></span>

    [!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

    |<span data-ttu-id="8c327-141">Release DWORD 的值</span><span class="sxs-lookup"><span data-stu-id="8c327-141">Value of the Release DWORD</span></span>|<span data-ttu-id="8c327-142">版本</span><span class="sxs-lookup"><span data-stu-id="8c327-142">Version</span></span>|
    |--------------------------------|-------------|
    |<span data-ttu-id="8c327-143">378389</span><span class="sxs-lookup"><span data-stu-id="8c327-143">378389</span></span>|<span data-ttu-id="8c327-144">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="8c327-144">.NET Framework 4.5</span></span>|
    |<span data-ttu-id="8c327-145">378675</span><span class="sxs-lookup"><span data-stu-id="8c327-145">378675</span></span>|<span data-ttu-id="8c327-146">使用 Windows 8.1 或 Windows Server 2012 R2 安装的 .NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="8c327-146">.NET Framework 4.5.1 installed with Windows 8.1 or Windows Server 2012 R2</span></span>|
    |<span data-ttu-id="8c327-147">378758</span><span class="sxs-lookup"><span data-stu-id="8c327-147">378758</span></span>|<span data-ttu-id="8c327-148">安装在 Windows 8、Windows 7 SP1 或 Windows Vista SP2 上的 .NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="8c327-148">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|
    |<span data-ttu-id="8c327-149">379893</span><span class="sxs-lookup"><span data-stu-id="8c327-149">379893</span></span>|<span data-ttu-id="8c327-150">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="8c327-150">.NET Framework 4.5.2</span></span>|
    |<span data-ttu-id="8c327-151">在 Windows 10 系统上：393295</span><span class="sxs-lookup"><span data-stu-id="8c327-151">On Windows 10 systems: 393295</span></span><br /><br /> <span data-ttu-id="8c327-152">在所有其他操作系统版本上：393297</span><span class="sxs-lookup"><span data-stu-id="8c327-152">On all other OS versions: 393297</span></span>|[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|
    |<span data-ttu-id="8c327-153">在 Windows 10 November Update 系统上：394254</span><span class="sxs-lookup"><span data-stu-id="8c327-153">On Windows 10 November Update systems: 394254</span></span><br /><br /> <span data-ttu-id="8c327-154">在所有其他操作系统版本上：394271</span><span class="sxs-lookup"><span data-stu-id="8c327-154">On all other OS versions: 394271</span></span>|[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|
    |<span data-ttu-id="8c327-155">在 Windows 10 Anniversary Update 上：394802</span><span class="sxs-lookup"><span data-stu-id="8c327-155">On Windows 10 Anniversary Update: 394802</span></span><br /><br /> <span data-ttu-id="8c327-156">在所有其他操作系统版本上：394806</span><span class="sxs-lookup"><span data-stu-id="8c327-156">On all other OS versions: 394806</span></span>|[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]| 
    |<span data-ttu-id="8c327-157">在 Windows 10 创意者更新上：460798</span><span class="sxs-lookup"><span data-stu-id="8c327-157">On Windows 10 Creators Update: 460798</span></span><br/><br/> <span data-ttu-id="8c327-158">在所有其他操作系统版本上： 460805</span><span class="sxs-lookup"><span data-stu-id="8c327-158">On all other OS versions: 460805</span></span> | <span data-ttu-id="8c327-159">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="8c327-159">.NET Framework 4.7</span></span> |
    |<span data-ttu-id="8c327-160">在 Windows 10 Fall Creators Update 中：461308</span><span class="sxs-lookup"><span data-stu-id="8c327-160">On Windows 10 Fall Creators Update: 461308</span></span><br/><br/> <span data-ttu-id="8c327-161">在所有其他操作系统版本上：461310</span><span class="sxs-lookup"><span data-stu-id="8c327-161">On all other OS versions: 461310</span></span> | <span data-ttu-id="8c327-162">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="8c327-162">.NET Framework 4.7.1</span></span> |
    
<a name="net_c"></a> 
## <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-1-4"></a><span data-ttu-id="8c327-163">通过在代码中查询注册表来查找 .NET Framework 版本 (.NET Framework 1-4)</span><span class="sxs-lookup"><span data-stu-id="8c327-163">To find .NET Framework versions by querying the registry in code (.NET Framework 1-4)</span></span>

- <span data-ttu-id="8c327-164">使用 <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> 类访问 Windows 注册表中 HKEY_LOCAL_MACHINE 下的 Software\Microsoft\NET Framework Setup\NDP\ 子项。</span><span class="sxs-lookup"><span data-stu-id="8c327-164">Use the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the Software\Microsoft\NET Framework Setup\NDP\ subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

     <span data-ttu-id="8c327-165">下面的代码显示此查询的示例。</span><span class="sxs-lookup"><span data-stu-id="8c327-165">The following code shows an example of this query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8c327-166">此代码不演示如何检测 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8c327-166">This code does not show how to detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later.</span></span> <span data-ttu-id="8c327-167">检查 `Release` DWORD 以检测这些版本，如上一节所述。</span><span class="sxs-lookup"><span data-stu-id="8c327-167">Check the `Release` DWORD to detect those versions, as described in the previous section.</span></span> <span data-ttu-id="8c327-168">有关检测 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 或更高版本的代码，请参阅本文的下一节。</span><span class="sxs-lookup"><span data-stu-id="8c327-168">For code that does detect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or later versions, see the next section in this article.</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

     <span data-ttu-id="8c327-169">该示例生成类似下面内容的输出：</span><span class="sxs-lookup"><span data-stu-id="8c327-169">The example produces output that's similar to the following:</span></span>

    ```
    v2.0.50727  2.0.50727.4016  SP2
    v3.0  3.0.30729.4037  SP2
    v3.5  3.5.30729.01  SP1
    v4
      Client  4.0.30319
      Full  4.0.30319
    ```

<a name="net_d"></a> 
## <a name="to-find-net-framework-versions-by-querying-the-registry-in-code-net-framework-45-and-later"></a><span data-ttu-id="8c327-170">通过在代码中查询注册表来查找 .NET Framework 版本（.NET Framework 4.5 和更高版本）</span><span class="sxs-lookup"><span data-stu-id="8c327-170">To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)</span></span>

1. <span data-ttu-id="8c327-171">`Release` DWORD 的存在表明该计算机上已安装 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8c327-171">The existence of the `Release` DWORD indicates that the .NET Framework 4.5 or later has been installed on a computer.</span></span> <span data-ttu-id="8c327-172">关键字的值表示已安装的版本。</span><span class="sxs-lookup"><span data-stu-id="8c327-172">The value of the keyword indicates the installed version.</span></span> <span data-ttu-id="8c327-173">要检查此关键字，请使用 <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> 类的 <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> 和 <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> 方法访问 Windows 注册表中 HKEY_LOCAL_MACHINE 下的 Software\Microsoft\NET Framework Setup\NDP\v4\Full 子项。</span><span class="sxs-lookup"><span data-stu-id="8c327-173">To check this keyword, use the <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A> and <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> methods of the <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> class to access the Software\Microsoft\NET Framework Setup\NDP\v4\Full subkey under HKEY_LOCAL_MACHINE in the Windows registry.</span></span>

2. <span data-ttu-id="8c327-174">检查 `Release` 关键字的值以确定安装的版本。</span><span class="sxs-lookup"><span data-stu-id="8c327-174">Check the value of the `Release` keyword to determine the installed version.</span></span> <span data-ttu-id="8c327-175">为了向前兼容，你可以检查是否有一个值大于或等于表中所列的值。</span><span class="sxs-lookup"><span data-stu-id="8c327-175">To be forward-compatible, you can check for a value greater than or equal to the values listed in the table.</span></span> <span data-ttu-id="8c327-176">此处是 .NET Framework 版本及相关联的 `Release` 关键字。</span><span class="sxs-lookup"><span data-stu-id="8c327-176">Here are the .NET Framework versions and associated `Release` keywords.</span></span>

    [!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

    |<span data-ttu-id="8c327-177">版本</span><span class="sxs-lookup"><span data-stu-id="8c327-177">Version</span></span>|<span data-ttu-id="8c327-178">Release DWORD 的值</span><span class="sxs-lookup"><span data-stu-id="8c327-178">Value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="8c327-179">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="8c327-179">.NET Framework 4.5</span></span>|<span data-ttu-id="8c327-180">378389</span><span class="sxs-lookup"><span data-stu-id="8c327-180">378389</span></span>|
    |<span data-ttu-id="8c327-181">使用 Windows 8.1 安装的 .NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="8c327-181">.NET Framework 4.5.1 installed with Windows 8.1</span></span>|<span data-ttu-id="8c327-182">378675</span><span class="sxs-lookup"><span data-stu-id="8c327-182">378675</span></span>|
    |<span data-ttu-id="8c327-183">安装在 Windows 8、Windows 7 SP1 或 Windows Vista SP2 上的 .NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="8c327-183">.NET Framework 4.5.1 installed on Windows 8, Windows 7 SP1, or Windows Vista SP2</span></span>|<span data-ttu-id="8c327-184">378758</span><span class="sxs-lookup"><span data-stu-id="8c327-184">378758</span></span>|
    |<span data-ttu-id="8c327-185">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="8c327-185">.NET Framework 4.5.2</span></span>|<span data-ttu-id="8c327-186">379893</span><span class="sxs-lookup"><span data-stu-id="8c327-186">379893</span></span>|
    |<span data-ttu-id="8c327-187">使用 Windows 10 安装的 .NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="8c327-187">.NET Framework 4.6 installed with Windows 10</span></span>|<span data-ttu-id="8c327-188">393295</span><span class="sxs-lookup"><span data-stu-id="8c327-188">393295</span></span>|
    |<span data-ttu-id="8c327-189">在所有其他 Windows 操作系统版本上安装的 .NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="8c327-189">.NET Framework 4.6 installed on all other Windows OS versions</span></span>|<span data-ttu-id="8c327-190">393297</span><span class="sxs-lookup"><span data-stu-id="8c327-190">393297</span></span>|
    |<span data-ttu-id="8c327-191">在 Windows 10 上安装的 .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="8c327-191">.NET Framework 4.6.1 installed on Windows 10</span></span>|<span data-ttu-id="8c327-192">394254</span><span class="sxs-lookup"><span data-stu-id="8c327-192">394254</span></span>|
    |<span data-ttu-id="8c327-193">在所有其他 Windows 操作系统版本上安装的 .NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="8c327-193">.NET Framework 4.6.1 installed on all other Windows OS versions</span></span>|<span data-ttu-id="8c327-194">394271</span><span class="sxs-lookup"><span data-stu-id="8c327-194">394271</span></span>|
    |<span data-ttu-id="8c327-195">在 Windows 10 周年更新上安装的 .NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="8c327-195">.NET Framework 4.6.2 installed on Windows 10 Anniversary Update</span></span>|<span data-ttu-id="8c327-196">394802</span><span class="sxs-lookup"><span data-stu-id="8c327-196">394802</span></span>|
    |<span data-ttu-id="8c327-197">在所有其他 Windows 操作系统版本上安装的 .NET Framework 4.6.2</span><span class="sxs-lookup"><span data-stu-id="8c327-197">.NET Framework 4.6.2 installed on all other Windows OS versions</span></span>|<span data-ttu-id="8c327-198">394806</span><span class="sxs-lookup"><span data-stu-id="8c327-198">394806</span></span>|
    |<span data-ttu-id="8c327-199">在 Windows 10 创意者更新上安装的 .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="8c327-199">.NET Framework 4.7 installed on Windows 10 Creators Update</span></span>|<span data-ttu-id="8c327-200">460798</span><span class="sxs-lookup"><span data-stu-id="8c327-200">460798</span></span>|
    |<span data-ttu-id="8c327-201">在所有其他 Windows 操作系统版本上安装的 .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="8c327-201">.NET Framework 4.7 installed on all other Windows OS versions</span></span>|<span data-ttu-id="8c327-202">460805</span><span class="sxs-lookup"><span data-stu-id="8c327-202">460805</span></span>|
    |<span data-ttu-id="8c327-203">在 Windows 10 Fall Creators Update 上安装的 .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="8c327-203">.NET Framework 4.7.1 installed on Windows 10 Fall Creators Update</span></span>|<span data-ttu-id="8c327-204">461308</span><span class="sxs-lookup"><span data-stu-id="8c327-204">461308</span></span>|
    |<span data-ttu-id="8c327-205">在所有其他 Windows 操作系统版本上安装的 .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="8c327-205">.NET Framework 4.7.1 installed on all other Windows OS versions</span></span>|<span data-ttu-id="8c327-206">461310</span><span class="sxs-lookup"><span data-stu-id="8c327-206">461310</span></span>|

     <span data-ttu-id="8c327-207">以下示例检查注册表中的 `Release` 值来确定是否已安装 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 或更高版本的 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="8c327-207">The following example checks the `Release` value in the registry to determine whether the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] or a later version of the .NET Framework is installed.</span></span>

     [!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
     [!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

     <span data-ttu-id="8c327-208">此示例遵循版本检查的建议做法：</span><span class="sxs-lookup"><span data-stu-id="8c327-208">This example follows the recommended practice for version checking:</span></span>

    - <span data-ttu-id="8c327-209">检查 `Release` 项的值是否*大于等于*已知版本键的值。</span><span class="sxs-lookup"><span data-stu-id="8c327-209">It checks whether the value of the `Release` entry is *greater than or equal to* the value of the known release keys.</span></span>

    - <span data-ttu-id="8c327-210">按从最新版本到最早版本的顺序检查。</span><span class="sxs-lookup"><span data-stu-id="8c327-210">It checks in order from most recent version to earliest version.</span></span>

<a name="ps_a"></a> 
## <a name="to-check-for-a-minimum-required-net-framework-version-by-querying-the-registry-in-powershell-net-framework-45-and-later"></a><span data-ttu-id="8c327-211">使用 PowerShell 查询注册表（NET Framework 4.5 及更高版本）以检查所需的 .NET Framework 最低版本的具体步骤</span><span class="sxs-lookup"><span data-stu-id="8c327-211">To check for a minimum-required .NET Framework version by querying the registry in PowerShell (.NET Framework 4.5 and later)</span></span>

- <span data-ttu-id="8c327-212">下面的示例检查 `Release` 关键字的值，以确定是否已安装 .NET Framework 4.6.2 或更高版本，无论 Windows OS 版本如何（如果已安装，返回 `True`；否则，返回 `False`）。</span><span class="sxs-lookup"><span data-stu-id="8c327-212">The following example checks the value of the `Release` keyword to determine whether .NET Framework 4.6.2 or higher is installed, regardless of Windows OS version (returning `True` if it is and `False` otherwise).</span></span>

    ```PowerShell
    Get-ChildItem "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\" | Get-ItemPropertyValue -Name Release | ForEach-Object { $_ -ge 394802 } 
    ```

    <span data-ttu-id="8c327-213">可以将上一示例中的 `394802` 替换为下表中的另一值，以检查另一个所需的 .NET Framework 最低版本。</span><span class="sxs-lookup"><span data-stu-id="8c327-213">You can replace `394802` in the previous example with another value from the following table to check for a different minimum-required .NET Framework version.</span></span>
  
    |<span data-ttu-id="8c327-214">版本</span><span class="sxs-lookup"><span data-stu-id="8c327-214">Version</span></span>|<span data-ttu-id="8c327-215">Release DWORD 的最小值</span><span class="sxs-lookup"><span data-stu-id="8c327-215">Minimum value of the Release DWORD</span></span>|
    |-------------|--------------------------------|
    |<span data-ttu-id="8c327-216">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="8c327-216">.NET Framework 4.5</span></span>|<span data-ttu-id="8c327-217">378389</span><span class="sxs-lookup"><span data-stu-id="8c327-217">378389</span></span>|
    |<span data-ttu-id="8c327-218">.NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="8c327-218">.NET Framework 4.5.1</span></span>|<span data-ttu-id="8c327-219">378675</span><span class="sxs-lookup"><span data-stu-id="8c327-219">378675</span></span>|
    |<span data-ttu-id="8c327-220">.NET Framework 4.5.2</span><span class="sxs-lookup"><span data-stu-id="8c327-220">.NET Framework 4.5.2</span></span>|<span data-ttu-id="8c327-221">379893</span><span class="sxs-lookup"><span data-stu-id="8c327-221">379893</span></span>|
    |[!INCLUDE[net_v46](../../../includes/net-v46-md.md)]|<span data-ttu-id="8c327-222">393295</span><span class="sxs-lookup"><span data-stu-id="8c327-222">393295</span></span>|
    |[!INCLUDE[net_v461](../../../includes/net-v461-md.md)]|<span data-ttu-id="8c327-223">394254</span><span class="sxs-lookup"><span data-stu-id="8c327-223">394254</span></span>|
    |[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]|<span data-ttu-id="8c327-224">394802</span><span class="sxs-lookup"><span data-stu-id="8c327-224">394802</span></span>|
    |<span data-ttu-id="8c327-225">.NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="8c327-225">.NET Framework 4.7</span></span>|<span data-ttu-id="8c327-226">460798</span><span class="sxs-lookup"><span data-stu-id="8c327-226">460798</span></span>|
    |<span data-ttu-id="8c327-227">.NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="8c327-227">.NET Framework 4.7.1</span></span>|<span data-ttu-id="8c327-228">461308</span><span class="sxs-lookup"><span data-stu-id="8c327-228">461308</span></span>|
    
<a name="clr_a"></a> 
## <a name="to-find-the-current-runtime-version-by-using-the-clrver-tool"></a><span data-ttu-id="8c327-229">使用 Clrver 工具查找当前运行时版本</span><span class="sxs-lookup"><span data-stu-id="8c327-229">To find the current runtime version by using the Clrver tool</span></span>

- <span data-ttu-id="8c327-230">使用 CLR 版本工具 (Clrver.exe) 决定已安装在计算机上的公共语言运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="8c327-230">Use the CLR Version Tool (Clrver.exe) to determine which versions of the common language runtime are installed on a computer.</span></span>

     <span data-ttu-id="8c327-231">从 Visual Studio 命令提示符处，输入 `clrver`。</span><span class="sxs-lookup"><span data-stu-id="8c327-231">From a Visual Studio Command Prompt, enter `clrver`.</span></span> <span data-ttu-id="8c327-232">该命令生成类似下面的输出：</span><span class="sxs-lookup"><span data-stu-id="8c327-232">This command produces output similar to the following:</span></span>

    ```
    Versions installed on the machine:
    v2.0.50727
    v4.0.30319
    ```

     <span data-ttu-id="8c327-233">有关使用此工具的详细信息，请参阅 [Clrver.exe（CLR 版本工具）](~/docs/framework/tools/clrver-exe-clr-version-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="8c327-233">For more information about using this tool, see [Clrver.exe (CLR Version Tool)](~/docs/framework/tools/clrver-exe-clr-version-tool.md).</span></span>

<a name="clr_b"></a> 
## <a name="to-find-the-current-runtime-version-by-querying-the-environment-class-in-code"></a><span data-ttu-id="8c327-234">通过在代码中查询 Environment 类来查找当前运行时版本</span><span class="sxs-lookup"><span data-stu-id="8c327-234">To find the current runtime version by querying the Environment class in code</span></span>

- <span data-ttu-id="8c327-235">查询 <xref:System.Environment.Version%2A?displayProperty=nameWithType> 属性，以检索标识当前正在执行代码的运行时版本的 <xref:System.Version> 对象。</span><span class="sxs-lookup"><span data-stu-id="8c327-235">Query the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to retrieve a <xref:System.Version> object that identifies the version of the runtime that is currently executing the code.</span></span> <span data-ttu-id="8c327-236">你可以使用 <xref:System.Version.Major%2A?displayProperty=nameWithType> 属性获取主版本标识符（例如，4.0 版的“4”），使用 <xref:System.Version.Minor%2A?displayProperty=nameWithType> 属性获取次版本标识符（例如，4.0 版的“0”），或使用 <xref:System.Object.ToString%2A?displayProperty=nameWithType> 方法获取完整版本字符串（例如“4.0.30319.18010”，如下面的代码中所示）。</span><span class="sxs-lookup"><span data-stu-id="8c327-236">You can use the <xref:System.Version.Major%2A?displayProperty=nameWithType> property to get the major release identifier (for example, "4" for version 4.0), the <xref:System.Version.Minor%2A?displayProperty=nameWithType> property to get the minor release identifier (for example, "0" for version 4.0), or the <xref:System.Object.ToString%2A?displayProperty=nameWithType> method to get the entire version string (for example, "4.0.30319.18010", as shown in the following code).</span></span> <span data-ttu-id="8c327-237">此属性返回一个值，该值反映当前正在执行代码的运行时的版本；它不返回程序集版本或可能已在计算机上安装的运行时的其他版本。</span><span class="sxs-lookup"><span data-stu-id="8c327-237">This property returns a single value that reflects the version of the runtime that is currently executing the code; it does not return assembly versions or other versions of the runtime that may have been installed on the computer.</span></span>

     <span data-ttu-id="8c327-238">对于 .NET Framework 版本 4、4.5、4.5.1 和 4.5.2，<xref:System.Environment.Version%2A?displayProperty=nameWithType> 属性返回字符串表现形式具有窗体 `4.0.30319.xxxxx` 的 <xref:System.Version> 对象。</span><span class="sxs-lookup"><span data-stu-id="8c327-238">For the .NET Framework Versions 4, 4.5, 4.5.1, and 4.5.2, the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property returns a <xref:System.Version> object whose string representation has the form `4.0.30319.xxxxx`.</span></span> <span data-ttu-id="8c327-239">对于 .NET Framework 4.6 及更高版本，形式为 `4.0.30319.42000`。</span><span class="sxs-lookup"><span data-stu-id="8c327-239">For the .NET Framework 4.6 and later, it has the form `4.0.30319.42000`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8c327-240">对于 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 和更高版本，不建议使用 <xref:System.Environment.Version%2A?displayProperty=nameWithType> 属性来检测运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="8c327-240">For the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] and later, we do not recommend using the  <xref:System.Environment.Version%2A?displayProperty=nameWithType> property to detect the version of the runtime.</span></span> <span data-ttu-id="8c327-241">相反，我们建议查询注册表，如本文前面[通过用代码查询注册表来查找 .NET Framework 版本（.NET Framework 4.5 及更高版本）](#net_d)一节所述。</span><span class="sxs-lookup"><span data-stu-id="8c327-241">Instead, we recommend that you query the registry, as described in the [To find .NET Framework versions by querying the registry in code (.NET Framework 4.5 and later)](#net_d) section earlier in this article.</span></span>

     <span data-ttu-id="8c327-242">以下是在 <xref:System.Environment.Version%2A?displayProperty=nameWithType> 属性中查询运行时版本信息的示例：</span><span class="sxs-lookup"><span data-stu-id="8c327-242">Here's an example of querying the <xref:System.Environment.Version%2A?displayProperty=nameWithType> property for runtime version information:</span></span>

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

     <span data-ttu-id="8c327-243">该示例生成类似下面内容的输出：</span><span class="sxs-lookup"><span data-stu-id="8c327-243">The example produces output that's similar to the following:</span></span>

    ```
    Version: 4.0.30319.18010
    ```

## <a name="see-also"></a><span data-ttu-id="8c327-244">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c327-244">See also</span></span>

[<span data-ttu-id="8c327-245">如何：确定安装了哪些 .NET Framework 更新</span><span class="sxs-lookup"><span data-stu-id="8c327-245">How to: Determine Which .NET Framework Updates Are Installed</span></span>](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)  
[<span data-ttu-id="8c327-246">安装面向开发者的 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8c327-246">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)  
[<span data-ttu-id="8c327-247">版本和依赖关系</span><span class="sxs-lookup"><span data-stu-id="8c327-247">Versions and Dependencies</span></span>](~/docs/framework/migration-guide/versions-and-dependencies.md)  
