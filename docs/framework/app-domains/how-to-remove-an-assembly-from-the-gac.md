---
title: 如何：从全局程序集缓存中删除程序集
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- global assembly cache, removing assemblies
- strong-named assemblies, global assembly cache
- removing assemblies from global assembly cache
- deleting assemblies in global assembly cache
- Global Assembly Cache tool
- GAC (global assembly cache), removing assemblies
ms.assetid: acdcc588-b458-436d-876c-726de68244c1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4a8077125ac99fa1d8f5b22ac3864fcc17213fa6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54639623"
---
# <a name="how-to-remove-an-assembly-from-the-global-assembly-cache"></a><span data-ttu-id="c1b34-102">如何：从全局程序集缓存中删除程序集</span><span class="sxs-lookup"><span data-stu-id="c1b34-102">How to: Remove an Assembly from the Global Assembly Cache</span></span>
<span data-ttu-id="c1b34-103">有两种方法可以从全局程序集缓存 (GAC) 中移除程序集：</span><span class="sxs-lookup"><span data-stu-id="c1b34-103">There are two ways to remove an assembly from the global assembly cache (GAC):</span></span>  
  
-   <span data-ttu-id="c1b34-104">通过使用[全局程序集缓存工具 (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="c1b34-104">By using the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md).</span></span> <span data-ttu-id="c1b34-105">可以使用此选项卸载开发和测试期间已放置在 GAC 中的程序集。</span><span class="sxs-lookup"><span data-stu-id="c1b34-105">You can use this option to uninstall assemblies that you've placed in the GAC during development and testing.</span></span>  
  
-   <span data-ttu-id="c1b34-106">通过使用 [Windows Installer](/windows/desktop/Msi/windows-installer-portal)。</span><span class="sxs-lookup"><span data-stu-id="c1b34-106">By using [Windows Installer](/windows/desktop/Msi/windows-installer-portal).</span></span> <span data-ttu-id="c1b34-107">应使用此选项在测试安装包期间卸载程序集，并将其用于生产系统。</span><span class="sxs-lookup"><span data-stu-id="c1b34-107">You should use this option to uninstall assemblies when testing installation packages and for production systems.</span></span>  
  
### <a name="removing-an-assembly-with-gacutilexe"></a><span data-ttu-id="c1b34-108">使用 Gacutil.exe 删除程序集</span><span class="sxs-lookup"><span data-stu-id="c1b34-108">Removing an assembly with Gacutil.exe</span></span>  
  
1.  <span data-ttu-id="c1b34-109">在命令提示符处，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="c1b34-109">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="c1b34-110">gacutil –u \<assembly name></span><span class="sxs-lookup"><span data-stu-id="c1b34-110">**gacutil –u** \<*assembly name*></span></span>  
  
     <span data-ttu-id="c1b34-111">在此命令中，“assembly name”是要从全局程序集缓存中删除的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="c1b34-111">In this command, *assembly name* is the name of the assembly to remove from the global assembly cache.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="c1b34-112">不应使用 Gacutil.exe 来移除生产系统上的程序集，因为一些应用程序可能仍需要该程序集。</span><span class="sxs-lookup"><span data-stu-id="c1b34-112">You should not use Gacutil.exe to remove assemblies on production systems because of the possibility that the assembly may still be required by some application.</span></span> <span data-ttu-id="c1b34-113">应改为使用 Windows Installer，它保留了它在 GAC 中安装的每个程序集的引用计数。</span><span class="sxs-lookup"><span data-stu-id="c1b34-113">Instead, you should use the Windows Installer, which maintains a reference count for each assembly it installs in the GAC.</span></span>  
  
 <span data-ttu-id="c1b34-114">以下示例从全局程序集缓存中删除名为 `hello.dll` 的程序集。</span><span class="sxs-lookup"><span data-stu-id="c1b34-114">The following example removes an assembly named `hello.dll` from the global assembly cache.</span></span>  
  
```  
gacutil -u hello  
```  
  
### <a name="removing-an-assembly-with-windows-installer"></a><span data-ttu-id="c1b34-115">使用 Windows Installer 移除程序集</span><span class="sxs-lookup"><span data-stu-id="c1b34-115">Removing an assembly with Windows Installer</span></span>  
  
1.  <span data-ttu-id="c1b34-116">在“控制面板”的“程序和功能”应用中，选择要卸载的应用。</span><span class="sxs-lookup"><span data-stu-id="c1b34-116">From the **Programs and Features** app in **Control Panel**, select the app that you want to uninstall.</span></span> <span data-ttu-id="c1b34-117">如果安装包将程序集放入 GAC，在没有其他应用程序使用这些程序集的情况下，Windows Installer 将移除它们。</span><span class="sxs-lookup"><span data-stu-id="c1b34-117">If the installation package placed assemblies in the GAC, Windows Installer will remove them if they are not used by another application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c1b34-118">Windows Installer 保留了安装在 GAC 中的程序集的引用计数。</span><span class="sxs-lookup"><span data-stu-id="c1b34-118">Windows Installer maintains a reference count for assemblies installed in the GAC.</span></span> <span data-ttu-id="c1b34-119">仅当程序集的引用计数为零时才可将其从 GAC 移除，计数为零时意味着它没有被任何 Windows Installer 包安装的应用程序所使用。</span><span class="sxs-lookup"><span data-stu-id="c1b34-119">An assembly is removed from the GAC only when its reference count reaches zero, which indicates that it is not used by any application installed by a Windows Installer package.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1b34-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1b34-120">See also</span></span>
- [<span data-ttu-id="c1b34-121">使用程序集和全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="c1b34-121">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="c1b34-122">如何：将程序集安装到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="c1b34-122">How to: Install an Assembly into the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)
- [<span data-ttu-id="c1b34-123">Gacutil.exe（全局程序集缓存工具）</span><span class="sxs-lookup"><span data-stu-id="c1b34-123">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
