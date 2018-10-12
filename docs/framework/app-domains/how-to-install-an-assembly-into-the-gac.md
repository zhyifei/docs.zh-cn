---
title: 将程序集安装到 GAC 中
ms.date: 09/20/2018
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- global assembly cache, installing assemblies
- Global Assembly Cache tool
- windows installer, global assembly cache
ms.assetid: a7e6f091-d02c-49ba-b736-7295cb0eb743
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d365ac77fe6cd7fc4fca36705729ec12b06d6830
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2018
ms.locfileid: "46584576"
---
# <a name="how-to-install-an-assembly-into-the-global-assembly-cache"></a><span data-ttu-id="201ae-102">如何：将程序集安装到全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="201ae-102">How to: Install an assembly into the global assembly cache</span></span>

<span data-ttu-id="201ae-103">可通过两种方法将强名称程序集安装到全局程序集缓存 (GAC) 中。</span><span class="sxs-lookup"><span data-stu-id="201ae-103">There are two ways to install a strong-named assembly into the global assembly cache (GAC).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="201ae-104">仅强名称程序集可安装到 GAC 中。</span><span class="sxs-lookup"><span data-stu-id="201ae-104">Only strong-named assemblies can be installed into the GAC.</span></span> <span data-ttu-id="201ae-105">若要了解如何创建强名称程序集，请参阅[如何：使用强名称为程序集签名](how-to-sign-an-assembly-with-a-strong-name.md)。</span><span class="sxs-lookup"><span data-stu-id="201ae-105">For information about how to create a strong-named assembly, see [How to: Sign an Assembly with a Strong Name](how-to-sign-an-assembly-with-a-strong-name.md).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="201ae-106">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="201ae-106">Windows Installer</span></span>

<span data-ttu-id="201ae-107">建议使用 [Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache)（即 Windows 安装引擎）将程序集添加到全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="201ae-107">[Windows Installer](/windows/desktop/Msi/installation-of-assemblies-to-the-global-assembly-cache), the Windows installation engine, is the recommended way to add assemblies to the global assembly cache.</span></span> <span data-ttu-id="201ae-108">Windows Installer 可提供全局程序集缓存中程序集的引用计数，还具有其他优点。</span><span class="sxs-lookup"><span data-stu-id="201ae-108">Windows Installer provides reference counting of assemblies in the global assembly cache and other benefits.</span></span> <span data-ttu-id="201ae-109">你可以使用[适用于 Visual Studio 2017 的 WiX 工具集扩展](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension)为 Windows Installer 创建安装程序包。</span><span class="sxs-lookup"><span data-stu-id="201ae-109">You can use the [WiX Toolset extension for Visual Studio 2017](https://marketplace.visualstudio.com/items?itemName=RobMensching.WixToolsetVisualStudio2017Extension) to create an installer package for Windows Installer.</span></span>

## <a name="global-assembly-cache-tool"></a><span data-ttu-id="201ae-110">全局程序集缓存工具</span><span class="sxs-lookup"><span data-stu-id="201ae-110">Global assembly cache tool</span></span>

<span data-ttu-id="201ae-111">你可以使用[全局程序集缓存工具 (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) 将强名称程序集添加到全局程序集缓存，并查看全局程序集缓存的内容。</span><span class="sxs-lookup"><span data-stu-id="201ae-111">You can use the [Global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to add strong-named assemblies to the global assembly cache and to view the contents of the global assembly cache.</span></span>

   > [!NOTE]
   > <span data-ttu-id="201ae-112">Gacutil.exe 只用于开发，不应用于将产品程序集安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="201ae-112">Gacutil.exe is only for development purposes and should not be used to install production assemblies into the global assembly cache.</span></span>

<span data-ttu-id="201ae-113">gacutil 的语法如下：</span><span class="sxs-lookup"><span data-stu-id="201ae-113">The syntax for gacutil is as follows:</span></span>

```shell
gacutil -i <assembly name>
```

<span data-ttu-id="201ae-114">在此命令中，“assembly name”是要在全局程序集缓存中安装的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="201ae-114">In this command, *assembly name* is the name of the assembly to install in the global assembly cache.</span></span>

<span data-ttu-id="201ae-115">下面的示例将文件名为 `hello.dll` 的程序集安装到全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="201ae-115">The following example installs an assembly with the file name `hello.dll` into the global assembly cache.</span></span>

```shell
gacutil -i hello.dll
```

> [!NOTE]
> <span data-ttu-id="201ae-116">在 .NET Framework 的早期版本中，可以使用 Shfusion.dll Windows 外壳扩展通过将程序集拖到文件资源管理器中来安装这些程序集。</span><span class="sxs-lookup"><span data-stu-id="201ae-116">In earlier versions of the .NET Framework, the Shfusion.dll Windows shell extension enabled you to install assemblies by dragging them in **File Explorer**.</span></span> <span data-ttu-id="201ae-117">从 .NET Framework 4 开始，Shfusion.dll 已淘汰。</span><span class="sxs-lookup"><span data-stu-id="201ae-117">Beginning with the .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="201ae-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="201ae-118">See also</span></span>

- [<span data-ttu-id="201ae-119">使用程序集和全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="201ae-119">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="201ae-120">如何：从全局程序集缓存中删除程序集</span><span class="sxs-lookup"><span data-stu-id="201ae-120">How to: Remove an Assembly from the Global Assembly Cache</span></span>](how-to-remove-an-assembly-from-the-gac.md)
- [<span data-ttu-id="201ae-121">Gacutil.exe（全局程序集缓存工具）</span><span class="sxs-lookup"><span data-stu-id="201ae-121">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
- [<span data-ttu-id="201ae-122">如何：使用强名称为程序集签名</span><span class="sxs-lookup"><span data-stu-id="201ae-122">How to: Sign an Assembly with a Strong Name</span></span>](how-to-sign-an-assembly-with-a-strong-name.md)