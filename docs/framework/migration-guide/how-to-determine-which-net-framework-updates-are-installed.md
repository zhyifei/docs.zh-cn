---
title: "如何： 确定安装了哪些.NET Framework 安全更新和修补程序"
description: "了解如何确定在计算机上安装了哪些.NET Framework 安全更新和修补程序。"
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c35705470a8e1b553eca2ca0c68d3b8b9b3f6fa6
ms.sourcegitcommit: a3ba258f7a8cab5c6d19a3743dd95e904ecebc44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2017
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="6fa4c-103">如何： 确定安装了哪些.NET Framework 安全更新和修补程序</span><span class="sxs-lookup"><span data-stu-id="6fa4c-103">How to: Determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="6fa4c-104">这篇文章演示如何找出哪些.NET Framework 安全更新和修补程序安装在计算机上。</span><span class="sxs-lookup"><span data-stu-id="6fa4c-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="6fa4c-105">这篇文章中所示的所有技术都需要具有管理权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="6fa4c-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="to-find-installed-updates-using-the-registry"></a><span data-ttu-id="6fa4c-106">若要查找已安装的更新使用注册表</span><span class="sxs-lookup"><span data-stu-id="6fa4c-106">To find installed updates using the registry</span></span>

<span data-ttu-id="6fa4c-107">在 Windows 注册表中列出的已安装的安全更新和每个版本的.NET Framework 的计算机上安装的修补程序。</span><span class="sxs-lookup"><span data-stu-id="6fa4c-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="6fa4c-108">你可以使用注册表编辑器 (*regedit.exe*) 程序，可以查看此信息。</span><span class="sxs-lookup"><span data-stu-id="6fa4c-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="6fa4c-109">打开程序 **regedit.exe**。</span><span class="sxs-lookup"><span data-stu-id="6fa4c-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="6fa4c-110">在 Windows 8 和更高版本中，右键单击**启动** ![Windows 徽标](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")，然后选择**运行**。</span><span class="sxs-lookup"><span data-stu-id="6fa4c-110">In Windows 8 and later versions, right-click **Start** ![Windows logo](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="6fa4c-111">在**打开**框中，输入**regedit**和选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="6fa4c-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="6fa4c-112">在注册表编辑器中，打开以下子项：</span><span class="sxs-lookup"><span data-stu-id="6fa4c-112">In the Registry Editor, open the following subkey:</span></span>

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     <span data-ttu-id="6fa4c-113">已安装的更新在标识适用的 .NET Framework 版本的子项下方列出。</span><span class="sxs-lookup"><span data-stu-id="6fa4c-113">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="6fa4c-114">每个更新均由知识库 (KB) 编号进行标识。</span><span class="sxs-lookup"><span data-stu-id="6fa4c-114">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="6fa4c-115">在注册表编辑器中，.NET Framework 版本和每个版本已安装的更新都保存在不同的子项中。</span><span class="sxs-lookup"><span data-stu-id="6fa4c-115">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="6fa4c-116">有关检测安装的版本号的信息，请参阅[如何： 确定安装了哪些.NET Framework 版本](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)。</span><span class="sxs-lookup"><span data-stu-id="6fa4c-116">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a><span data-ttu-id="6fa4c-117">若要查找已安装的更新通过在代码中查询注册表</span><span class="sxs-lookup"><span data-stu-id="6fa4c-117">To find installed updates by querying the registry in code</span></span>

<span data-ttu-id="6fa4c-118">下面的示例以编程方式确定的.NET Framework 安全更新和的计算机安装的修补程序：</span><span class="sxs-lookup"><span data-stu-id="6fa4c-118">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="6fa4c-119">该示例生成类似于以下输出：</span><span class="sxs-lookup"><span data-stu-id="6fa4c-119">The example produces an output that's similar to the following one:</span></span>

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a><span data-ttu-id="6fa4c-120">若要查找已安装的更新通过在 PowerShell 中查询注册表</span><span class="sxs-lookup"><span data-stu-id="6fa4c-120">To find installed updates by querying the registry in PowerShell</span></span>

<span data-ttu-id="6fa4c-121">下面的示例演示如何确定.NET Framework 安全更新和使用 PowerShell 的计算机安装的修补程序：</span><span class="sxs-lookup"><span data-stu-id="6fa4c-121">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

```powershell
 Get-ChildItem "HKLM:SOFTWARE\Wow6432Node\Microsoft\Updates\*" -Recurse | Where-Object {$_.name -like
 "*.NET Framework*"}
```

<span data-ttu-id="6fa4c-122">该示例生成类似于以下输出：</span><span class="sxs-lookup"><span data-stu-id="6fa4c-122">The example produces an output that's similar to the following one:</span></span>

```console
    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Client Profile


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y


    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Extended


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y
```

## <a name="see-also"></a><span data-ttu-id="6fa4c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fa4c-123">See also</span></span>

[<span data-ttu-id="6fa4c-124">如何： 确定安装了哪些.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="6fa4c-124">How to: Determine which .NET Framework versions are installed</span></span>](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[<span data-ttu-id="6fa4c-125">安装.NET Framework 为开发人员</span><span class="sxs-lookup"><span data-stu-id="6fa4c-125">Install the .NET Framework for developers</span></span>](../../../docs/framework/install/guide-for-developers.md)  
[<span data-ttu-id="6fa4c-126">版本和依赖关系</span><span class="sxs-lookup"><span data-stu-id="6fa4c-126">Versions and dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)
