---
title: "如何：确定安装了哪些 .NET Framework 更新"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
caps.latest.revision: 6
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b29b402e859688dcced6bd4429b18298070fb5e4
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-determine-which-net-framework-updates-are-installed"></a><span data-ttu-id="02607-102">如何：确定安装了哪些 .NET Framework 更新</span><span class="sxs-lookup"><span data-stu-id="02607-102">How to: Determine Which .NET Framework Updates Are Installed</span></span>
<span data-ttu-id="02607-103">安装在计算机上的各个版本 .NET Framework 已安装的更新都列在 Windows 注册表中。</span><span class="sxs-lookup"><span data-stu-id="02607-103">The installed updates for each version of the .NET Framework installed on a computer are listed in the Windows registry.</span></span> <span data-ttu-id="02607-104">可以使用注册表编辑器 (regedit.exe) 查看此信息。</span><span class="sxs-lookup"><span data-stu-id="02607-104">You can use the Registry Editor (regedit.exe) to view this information.</span></span>  
  
 <span data-ttu-id="02607-105">在注册表编辑器中，.NET Framework 版本和每个版本已安装的更新都保存在不同的子项中。</span><span class="sxs-lookup"><span data-stu-id="02607-105">In the Registry Editor, the .NET Framework versions and installed updates for each version are stored in different subkeys.</span></span> <span data-ttu-id="02607-106">若要了解如何检测已安装的版本号，请参阅[如何：确定安装了哪些 .NET Framework 版本](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)。</span><span class="sxs-lookup"><span data-stu-id="02607-106">For information about detecting the installed version numbers, see [How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md).</span></span> <span data-ttu-id="02607-107">若要了解如何安装 .NET Framework，请参阅[安装面向开发人员的 .NET Framework](../../../docs/framework/install/guide-for-developers.md)。</span><span class="sxs-lookup"><span data-stu-id="02607-107">For information about installing the .NET Framework, see [Install the .NET Framework for developers](../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
### <a name="to-find-installed-updates"></a><span data-ttu-id="02607-108">若要查找已安装的更新</span><span class="sxs-lookup"><span data-stu-id="02607-108">To find installed updates</span></span>  
  
1.  <span data-ttu-id="02607-109">打开程序 **regedit.exe**。</span><span class="sxs-lookup"><span data-stu-id="02607-109">Open the program **regedit.exe**.</span></span> <span data-ttu-id="02607-110">在 Windows 8 和更高版本上打开“开始”屏幕，并键入的名称。</span><span class="sxs-lookup"><span data-stu-id="02607-110">In Windows 8 and higher open the Start screen and type the name.</span></span> <span data-ttu-id="02607-111">在旧版 Windows 中，选择“开始”菜单上的“运行”，然后在“打开”框中输入“regedit.exe”。</span><span class="sxs-lookup"><span data-stu-id="02607-111">In earlier versions of Windows, on the **Start** menu, choose **Run** and then, in the **Open** box, enter **regedit.exe**.</span></span>  
  
     <span data-ttu-id="02607-112">你必须具有管理凭据才能运行 regedit.exe。</span><span class="sxs-lookup"><span data-stu-id="02607-112">You must have administrative credentials to run regedit.exe.</span></span>  
  
2.  <span data-ttu-id="02607-113">在注册表编辑器中，打开以下子项：</span><span class="sxs-lookup"><span data-stu-id="02607-113">In the Registry Editor, open the following subkey:</span></span>  
  
     <span data-ttu-id="02607-114">HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates</span><span class="sxs-lookup"><span data-stu-id="02607-114">HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates</span></span>  
  
     <span data-ttu-id="02607-115">已安装的更新在标识适用的 .NET Framework 版本的子项下方列出。</span><span class="sxs-lookup"><span data-stu-id="02607-115">The installed updates are listed under subkeys that identify the .NET Framework version they apply to.</span></span> <span data-ttu-id="02607-116">每个更新均由知识库 (KB) 编号进行标识。</span><span class="sxs-lookup"><span data-stu-id="02607-116">Each update is identified by a Knowledge Base (KB) number.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02607-117">示例</span><span class="sxs-lookup"><span data-stu-id="02607-117">Example</span></span>  
 <span data-ttu-id="02607-118">以下代码以编程方式确定已安装在计算机上的 .NET Framework 更新。</span><span class="sxs-lookup"><span data-stu-id="02607-118">The following code programmatically determines the .NET Framework updates that are installed on a computer.</span></span> <span data-ttu-id="02607-119">你必须具有管理凭据才能运行此示例。</span><span class="sxs-lookup"><span data-stu-id="02607-119">You must have administrative credentials to run this example.</span></span>  
  
 <span data-ttu-id="02607-120">[!code-csharp[ListUpdates#1](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs#1)] [!code-vb[ListUpdates#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="02607-120">[!code-csharp[ListUpdates#1](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs#1)] [!code-vb[ListUpdates#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb#1)]</span></span>  
  
 <span data-ttu-id="02607-121">该示例生成类似下面内容的输出：</span><span class="sxs-lookup"><span data-stu-id="02607-121">The example produces output that's similar to the following:</span></span>  
  
```  
Microsoft .NET Framework 3.5 SP1  
  KB953595  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB953595)  
  SP1  
    KB2657424  Security Update for Microsoft .NET Framework 3.5 SP1 (KB2657424)  
    KB958484  Hotfix for Microsoft .NET Framework 3.5 SP1 (KB958484)  
    KB963707  Update for Microsoft .NET Framework 3.5 SP1 (KB963707)  
Microsoft .NET Framework 4 Client Profile  
  KB2160841  Security Update for Microsoft .NET Framework 4 Client Profile (KB2160841)  
  KB2446708  Security Update for Microsoft .NET Framework 4 Client Profile (KB2446708)  
  KB2468871  Update for Microsoft .NET Framework 4 Client Profile (KB2468871)  
  KB2478663  Security Update for Microsoft .NET Framework 4 Client Profile (KB2478663)  
  KB2518870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2518870)  
  KB2533523  Update for Microsoft .NET Framework 4 Client Profile (KB2533523)  
  KB2539636  Security Update for Microsoft .NET Framework 4 Client Profile (KB2539636)  
  KB2572078  Security Update for Microsoft .NET Framework 4 Client Profile (KB2572078)  
  KB2633870  Security Update for Microsoft .NET Framework 4 Client Profile (KB2633870)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Client Profile (KB2656351)  
Microsoft .NET Framework 4 Extended  
  KB2416472  Security Update for Microsoft .NET Framework 4 Extended (KB2416472)  
  KB2468871  Update for Microsoft .NET Framework 4 Extended (KB2468871)  
  KB2487367  Security Update for Microsoft .NET Framework 4 Extended (KB2487367)  
  KB2533523  Update for Microsoft .NET Framework 4 Extended (KB2533523)  
  KB2656351  Security Update for Microsoft .NET Framework 4 Extended (KB2656351)  
```  
  
## <a name="see-also"></a><span data-ttu-id="02607-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="02607-122">See also</span></span>

<span data-ttu-id="02607-123">[如何：确定安装了哪些 .NET Framework 版本](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) </span><span class="sxs-lookup"><span data-stu-id="02607-123">[How to: Determine Which .NET Framework Versions Are Installed](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md) </span></span>  
<span data-ttu-id="02607-124">[安装 .NET Framework](../../../docs/framework/install/guide-for-developers.md) </span><span class="sxs-lookup"><span data-stu-id="02607-124">[Installing the .NET Framework](../../../docs/framework/install/guide-for-developers.md) </span></span>  
[<span data-ttu-id="02607-125">版本和依赖关系</span><span class="sxs-lookup"><span data-stu-id="02607-125">Versions and Dependencies</span></span>](../../../docs/framework/migration-guide/versions-and-dependencies.md)

