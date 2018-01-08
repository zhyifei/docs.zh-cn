---
title: "如何：将程序集安装到全局程序集缓存"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47867a82432ec6abe2245a0421d800c242d92b2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="33e44-102">如何：将程序集安装到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="33e44-102">How to: Install an Assembly into the Global Assembly Cache</span></span>
<span data-ttu-id="33e44-103">可通过两种方法将强名称程序集安装到全局程序集缓存 (GAC) 中：</span><span class="sxs-lookup"><span data-stu-id="33e44-103">There are two ways to install a strong-named assembly into the global assembly cache (GAC):</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33e44-104">仅强名称程序集可安装到 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="33e44-104">Only strong-named assemblies can be installed into the GAC.</span></span> <span data-ttu-id="33e44-105">若要了解如何创建强名称程序集，请参阅[如何：使用强名称为程序集签名](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)。</span><span class="sxs-lookup"><span data-stu-id="33e44-105">For information about how to create a strong-named assembly, see [How to: Sign an Assembly with a Strong Name](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
-   <span data-ttu-id="33e44-106">使用 [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx)。</span><span class="sxs-lookup"><span data-stu-id="33e44-106">Using [Windows Installer](http://msdn.microsoft.com/library/windows/desktop/cc185688.aspx).</span></span>  
  
     <span data-ttu-id="33e44-107">通过创建 InstallShield Limited Edition 项目可在 Visual Studio 2012 和 Visual Studio 2013 中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="33e44-107">You do this in Visual Studio 2012 and Visual Studio 2013 by creating an InstallShield Limited Edition Project.</span></span>  
  
     <span data-ttu-id="33e44-108">这是将程序集添加到全局程序集缓存的最常用方法，建议采用。</span><span class="sxs-lookup"><span data-stu-id="33e44-108">This is the recommended and most common way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="33e44-109">此安装程序可提供全局程序集缓存中程序集的引用计数，还具有其他优点。</span><span class="sxs-lookup"><span data-stu-id="33e44-109">The installer provides reference counting of assemblies in the global assembly cache, plus other benefits.</span></span>  
  
-   <span data-ttu-id="33e44-110">使用[全局程序集缓存工具 (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="33e44-110">Using the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span>  
  
     <span data-ttu-id="33e44-111">你可以使用 Gacutil.exe 将强名称程序集添加到全局程序集缓存，并查看全局程序集缓存的内容。</span><span class="sxs-lookup"><span data-stu-id="33e44-111">You can use Gacutil.exe to add strong-named assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33e44-112">Gacutil.exe 只用于开发，不应用于将产品程序集安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="33e44-112">Gacutil.exe is only for development purposes and should not be used to install production assemblies into the global assembly cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33e44-113">在 .NET Framework 的早期版本中，可以使用 Shfusion.dll Windows 外壳扩展通过将程序集拖到文件资源管理器中来安装这些程序集。</span><span class="sxs-lookup"><span data-stu-id="33e44-113">In earlier versions of the .NET Framework, the Shfusion.dll Windows shell extension enabled you to install assemblies by dragging them in File Explorer.</span></span> <span data-ttu-id="33e44-114">从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]开始，Shfusion.dll 已过时。</span><span class="sxs-lookup"><span data-stu-id="33e44-114">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
### <a name="to-use-the-global-assembly-cache-tool-gacutilexe"></a><span data-ttu-id="33e44-115">使用全局程序集缓存工具 (Gacutil.exe)</span><span class="sxs-lookup"><span data-stu-id="33e44-115">To use the Global Assembly Cache tool (Gacutil.exe)</span></span>  
  
1.  <span data-ttu-id="33e44-116">在命令提示符处，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="33e44-116">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="33e44-117">gacutil -i \<assembly name></span><span class="sxs-lookup"><span data-stu-id="33e44-117">**gacutil -i** \<*assembly name*></span></span>  
  
     <span data-ttu-id="33e44-118">在此命令中，“assembly name”是要在全局程序集缓存中安装的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="33e44-118">In this command, *assembly name* is the name of the assembly to install in the global assembly cache.</span></span>  
  
 <span data-ttu-id="33e44-119">下面的示例将文件名为 `hello.dll` 的程序集安装到全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="33e44-119">The following example installs an assembly with the file name `hello.dll` into the global assembly cache.</span></span>  
  
```  
gacutil -i hello.dll  
```  
  
 <span data-ttu-id="33e44-120">有关详细信息，请参阅[全局程序集缓存工具 (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="33e44-120">For more information, see [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span>  
  
### <a name="to-use-an-installshield-limited-edition-project"></a><span data-ttu-id="33e44-121">使用 InstallShield Limited Edition 项目</span><span class="sxs-lookup"><span data-stu-id="33e44-121">To use an InstallShield Limited Edition Project</span></span>  
  
1.  <span data-ttu-id="33e44-122">通过以下方式将安装程序和部署包添加到解决方案：打开解决方案的快捷菜单，然后选择“添加”、“新建项目”。</span><span class="sxs-lookup"><span data-stu-id="33e44-122">Add a setup and deployment package to your solution by opening the shortcut menu for your solution, and then choosing **Add**, **New Project**.</span></span>  
  
2.  <span data-ttu-id="33e44-123">在“添加新项目”对话框的“已安装”文件夹中，选择“其他项目类型”、“安装和部署”和“InstallShield Limited Edition”，并为项目指定名称。</span><span class="sxs-lookup"><span data-stu-id="33e44-123">In the **Add New Project** dialog box, in the **Installed** folder, choose **Other Project Types**,  **Setup and Deployment**, **InstallShield Limited Edition**, and give your project a name.</span></span> <span data-ttu-id="33e44-124">（如果出现提示，下载、安装并激活 InstallShield。）</span><span class="sxs-lookup"><span data-stu-id="33e44-124">(If prompted, download, install, and activate InstallShield.)</span></span>  
  
3.  <span data-ttu-id="33e44-125">通过使用“解决方案资源管理器”中的“项目助手”或通过选择“解决方案资源管理器”中已编号步骤的子步骤，执行安装和部署项目的常规配置。如果未将程序集添加到 GAC，则按需配置设置。</span><span class="sxs-lookup"><span data-stu-id="33e44-125">Perform the general configuration of your setup and deployment project either by using the Project Assistant in **Solution Explorer**, or by choosing the substeps of the numbered steps in the **Solution Explorer**.Configure your setup as you would if you were not adding assemblies to the GAC.</span></span>  
  
4.  <span data-ttu-id="33e44-126">若要开始将程序集添加到 GAC 的过程，请选择“文件”（位于“解决方案资源管理器”中“指定应用程序数据”步骤的下方）。</span><span class="sxs-lookup"><span data-stu-id="33e44-126">To begin the process of adding an assembly to the GAC, choose **Files**, which is under the **Specify Application Data** step in **Solution Explorer**.</span></span>  
  
5.  <span data-ttu-id="33e44-127">在“目标计算机的文件夹”窗格中，打开“目标计算机”的快捷菜单，再选择“显示预定义的文件夹”、“[GlobalAssemblyCache]”。</span><span class="sxs-lookup"><span data-stu-id="33e44-127">In the **Destination computer's folders** pane, open the shortcut menu for **Destination Computer**, and then choose **Show Predefined Folder**, **[GlobalAssemblyCache]**.</span></span>  
  
6.  <span data-ttu-id="33e44-128">对于包含要安装到全局程序集缓存中的程序集的解决方案中的每个项目：</span><span class="sxs-lookup"><span data-stu-id="33e44-128">For each project in the solution that contains an assembly that you want to install in the global assembly cache:</span></span>  
  
    1.  <span data-ttu-id="33e44-129">在“源计算机的文件夹”窗格中，选择此项目。</span><span class="sxs-lookup"><span data-stu-id="33e44-129">In the **Source computer's folders** pane, choose the project.</span></span>  
  
    2.  <span data-ttu-id="33e44-130">在“目标计算机的文件夹”窗格中，选择“[GlobalAssemblyCache]”。</span><span class="sxs-lookup"><span data-stu-id="33e44-130">In the **Destination computer's folders** pane, choose **[GlobalAssemblyCache]**.</span></span>  
  
    3.  <span data-ttu-id="33e44-131">在“源计算机的文件”窗格中，选择“主输出来源”<project_name>。</span><span class="sxs-lookup"><span data-stu-id="33e44-131">In the **Source computer's files** pane, choose **Primary output from** *<project_name>*.</span></span>  
  
    4.  <span data-ttu-id="33e44-132">将步骤 c 中的文件拖动到“目标计算机的文件”窗格（或使用文件快捷菜单上的“复制”和“粘贴”命令）。</span><span class="sxs-lookup"><span data-stu-id="33e44-132">Drag the file in step c to the **Destination computer's files** pane (or use the **Copy** and **Paste** commands from the file's shortcut menu).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33e44-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="33e44-133">See Also</span></span>  
 [<span data-ttu-id="33e44-134">使用程序集和全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="33e44-134">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="33e44-135">如何：从全局程序集缓存中删除程序集</span><span class="sxs-lookup"><span data-stu-id="33e44-135">How to: Remove an Assembly from the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-remove-an-assembly-from-the-gac.md)  
 [<span data-ttu-id="33e44-136">Gacutil.exe（全局程序集缓存工具）</span><span class="sxs-lookup"><span data-stu-id="33e44-136">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)  
 [<span data-ttu-id="33e44-137">如何：使用强名称为程序集签名</span><span class="sxs-lookup"><span data-stu-id="33e44-137">How to: Sign an Assembly with a Strong Name</span></span>](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="33e44-138">Windows Installer 部署</span><span class="sxs-lookup"><span data-stu-id="33e44-138">Windows Installer Deployment</span></span>](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)
