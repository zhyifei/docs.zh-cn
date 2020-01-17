---
title: 请查看安装的 .NET Framework 安全更新和修补程序
description: 了解如何确定计算机上安装了哪些 .NET Framework 安全更新和修补程序。
ms.date: 11/27/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
ms.openlocfilehash: 087519048b412798ef7495d250dc2538ee5c2fd0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716256"
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a><span data-ttu-id="023dd-103">如何确定安装了哪些 .NET Framework 安全更新和修补程序</span><span class="sxs-lookup"><span data-stu-id="023dd-103">How to determine which .NET Framework security updates and hotfixes are installed</span></span>

<span data-ttu-id="023dd-104">本文介绍如何找出计算机上安装了哪些 .NET Framework 安全更新和修补程序。</span><span class="sxs-lookup"><span data-stu-id="023dd-104">This article shows you how to find out which .NET Framework security updates and hotfixes are installed on a computer.</span></span>

> [!NOTE]
> <span data-ttu-id="023dd-105">本文中介绍的所有方法均需要具有管理权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="023dd-105">All the techniques shown in this article require an account with administrative privileges.</span></span>

## <a name="use-registry-editor"></a><span data-ttu-id="023dd-106">使用注册表编辑器</span><span class="sxs-lookup"><span data-stu-id="023dd-106">Use Registry Editor</span></span>

<span data-ttu-id="023dd-107">安装在计算机上的各个版本 .NET Framework 的已安装安全更新和修补程序都列在 Windows 注册表中。</span><span class="sxs-lookup"><span data-stu-id="023dd-107">The installed security updates and hotfixes for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="023dd-108">可以使用注册表编辑器 (regedit.exe) 程序查看此信息  。</span><span class="sxs-lookup"><span data-stu-id="023dd-108">You can use the Registry Editor (*regedit.exe*) program to view this information.</span></span>

1. <span data-ttu-id="023dd-109">打开程序 **regedit.exe**。</span><span class="sxs-lookup"><span data-stu-id="023dd-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="023dd-110">在 Windows 8 和更高版本中，右键单击“开始”  ![Windows 键徽标的屏幕截图](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo")，然后选择“运行”  。</span><span class="sxs-lookup"><span data-stu-id="023dd-110">In Windows 8 and later versions, right-click **Start** ![Screenshot of the Windows key logo.](./media/how-to-determine-which-net-framework-updates-are-installed/windows-keyboard-logo.png "Windowskeyboardlogo"), then select **Run**.</span></span> <span data-ttu-id="023dd-111">在“打开”对话框中，输入“regedit.exe”并选择“确定”    。</span><span class="sxs-lookup"><span data-stu-id="023dd-111">In the **Open** box, enter **regedit** and select **OK**.</span></span>

2. <span data-ttu-id="023dd-112">在注册表编辑器中，打开以下子项：</span><span class="sxs-lookup"><span data-stu-id="023dd-112">In the Registry Editor, open the following subkey:</span></span>

     <span data-ttu-id="023dd-113">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates**</span><span class="sxs-lookup"><span data-stu-id="023dd-113">**HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates**</span></span>

     <span data-ttu-id="023dd-114">已安装的更新在标识适用的 .NET Framework 版本的子项下方列出。</span><span class="sxs-lookup"><span data-stu-id="023dd-114">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="023dd-115">每个更新均由知识库 (KB) 编号进行标识。</span><span class="sxs-lookup"><span data-stu-id="023dd-115">Each update is identified by a Knowledge Base (KB) number.</span></span>

<span data-ttu-id="023dd-116">在注册表编辑器中，.NET Framework 版本和每个版本已安装的更新都保存在不同的子项中。</span><span class="sxs-lookup"><span data-stu-id="023dd-116">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="023dd-117">有关检测已安装版本号的信息，请参阅[如何：确定已安装的 .NET Framework 版本](how-to-determine-which-versions-are-installed.md)。</span><span class="sxs-lookup"><span data-stu-id="023dd-117">For information about detecting the installed version numbers, see [How to: Determine which .NET Framework versions are installed](how-to-determine-which-versions-are-installed.md).</span></span>

## <a name="query-the-registry-using-code"></a><span data-ttu-id="023dd-118">使用代码查询注册表</span><span class="sxs-lookup"><span data-stu-id="023dd-118">Query the registry using code</span></span>

<span data-ttu-id="023dd-119">以下示例以编程方式确定已安装在计算机上的 .NET Framework 安全更新和修补程序：</span><span class="sxs-lookup"><span data-stu-id="023dd-119">The following example programmatically determines the .NET Framework security updates and hotfixes that are installed on a computer:</span></span>

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

<span data-ttu-id="023dd-120">该示例生成类似下面内容的输出：</span><span class="sxs-lookup"><span data-stu-id="023dd-120">The example produces an output that's similar to the following one:</span></span>

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

## <a name="use-powershell-to-query-the-registry"></a><span data-ttu-id="023dd-121">使用 PowerShell 查询注册表</span><span class="sxs-lookup"><span data-stu-id="023dd-121">Use PowerShell to query the registry</span></span>

<span data-ttu-id="023dd-122">以下示例介绍如何使用 PowerShell 确定已安装在计算机上的 .NET Framework 安全更新和修补程序：</span><span class="sxs-lookup"><span data-stu-id="023dd-122">The following example shows how to determine the .NET Framework security updates and hotfixes that are installed on a computer using PowerShell:</span></span>

```powershell
$DotNetVersions = Get-ChildItem HKLM:\SOFTWARE\WOW6432Node\Microsoft\Updates | Where-Object {$_.name -like
 "*.NET Framework*"}

ForEach($Version in $DotNetVersions){
    
   $Updates = Get-ChildItem $Version.PSPath
    $Version.PSChildName
    ForEach ($Update in $Updates){
       $Update.PSChildName
       }
}
```

<span data-ttu-id="023dd-123">该示例生成类似下面内容的输出：</span><span class="sxs-lookup"><span data-stu-id="023dd-123">The example produces an output that's similar to the following one:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="023dd-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="023dd-124">See also</span></span>

- [<span data-ttu-id="023dd-125">如何：确定已安装的 .NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="023dd-125">How to: Determine which .NET Framework versions are installed</span></span>](how-to-determine-which-versions-are-installed.md)
- [<span data-ttu-id="023dd-126">安装面向开发者的 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="023dd-126">Install the .NET Framework for developers</span></span>](../install/guide-for-developers.md)
- [<span data-ttu-id="023dd-127">版本和依赖关系</span><span class="sxs-lookup"><span data-stu-id="023dd-127">Versions and dependencies</span></span>](versions-and-dependencies.md)
