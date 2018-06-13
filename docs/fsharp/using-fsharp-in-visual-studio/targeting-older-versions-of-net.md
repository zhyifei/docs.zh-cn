---
title: 面向 Windows 8 中的 .NET Framework 2.0
description: '了解如何使用 F # 时以旧版本的.NET Framework 为目标。'
ms.date: 05/16/2016
ms.openlocfilehash: 9b08cced63b46778a5081d4de710991a6299fd29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566960"
---
# <a name="targeting-older-versions-of-net"></a><span data-ttu-id="1ac27-103">面向 .NET 的较旧版本</span><span class="sxs-lookup"><span data-stu-id="1ac27-103">Targeting Older Versions of .NET</span></span>

> [!NOTE]
<span data-ttu-id="1ac27-104">本文不是最新的 Visual Studio 最新的。</span><span class="sxs-lookup"><span data-stu-id="1ac27-104">This article is not up to date with the latest Visual Studio.</span></span>  <span data-ttu-id="1ac27-105">它将会更新。</span><span class="sxs-lookup"><span data-stu-id="1ac27-105">It will be updated.</span></span>

<span data-ttu-id="1ac27-106">如果你尝试面向.NET Framework 2.0，3.0 或 3.5 中的 F # 项目时在 Windows 8.1 上安装 Visual Studio 可能会出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="1ac27-106">The following error might appear if you try to target the .NET Framework 2.0, 3.0, or 3.5 in an F# project when Visual Studio is installed on Windows 8.1:</span></span> 

```
This project requires the 2.0 F# runtime, but that runtime is not installed.
```

<span data-ttu-id="1ac27-107">此错误是已知在以下条件的组合下出现：</span><span class="sxs-lookup"><span data-stu-id="1ac27-107">This error is known to occur under the following combination of conditions:</span></span>


- <span data-ttu-id="1ac27-108">在 Windows 8.1 上安装了 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="1ac27-108">You installed Visual Studio on Windows 8.1.</span></span>
<br />

- <span data-ttu-id="1ac27-109">在安装 Visual Studio 之前，未启用.NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="1ac27-109">You didn’t enable the .NET Framework 3.5 before you installed Visual Studio.</span></span>
<br />

- <span data-ttu-id="1ac27-110">你的项目面向.NET Framework 2.0、 3.0 或 3.5。</span><span class="sxs-lookup"><span data-stu-id="1ac27-110">Your project targets the .NET Framework 2.0, 3.0, or 3.5.</span></span>
<br />

<span data-ttu-id="1ac27-111">在安装 Visual Studio 时，它检测到已安装的.NET Framework 版本，并安装 F # 2.0 运行时，仅当安装并启用.NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="1ac27-111">When you install Visual Studio, it detects the installed versions of the .NET Framework and installs the F# 2.0 Runtime only if the .NET Framework 3.5 is installed and enabled.</span></span>


## <a name="resolving-the-error"></a><span data-ttu-id="1ac27-112">解决错误</span><span class="sxs-lookup"><span data-stu-id="1ac27-112">Resolving the Error</span></span>
<span data-ttu-id="1ac27-113">若要解决此错误，你可以任一目标.NET Framework 中，较新版本，或您可以启用 Windows 8.1 上的.NET Framework 3.5，然后安装 F # 2.0 运行时通过运行使用 Visual Studio 的安装程序**修复**选项。</span><span class="sxs-lookup"><span data-stu-id="1ac27-113">To resolve this error, you can either target a newer version of the .NET Framework, or you can enable the .NET Framework 3.5 on Windows 8.1 and then install the F# 2.0 runtime by running the setup program for Visual Studio with the **Repair** option.</span></span>


#### <a name="to-enable-the-net-framework-35-on-windows-81"></a><span data-ttu-id="1ac27-114">若要启用 Windows 8.1 上的.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="1ac27-114">To enable the .NET Framework 3.5 on Windows 8.1</span></span>

1. <span data-ttu-id="1ac27-115">上**启动**屏幕上，开始输入**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="1ac27-115">On the **Start** screen, start to enter **Control Panel**.</span></span>
<br />  <span data-ttu-id="1ac27-116">该名称时，输入时**控制面板**图标显示在**应用**标题。</span><span class="sxs-lookup"><span data-stu-id="1ac27-116">As you enter that name, the **Control Panel** icon appears under the **Apps** heading.</span></span>
<br />

2. <span data-ttu-id="1ac27-117">选择**控制面板**图标，选择**程序**图标，然后选择**打开或关闭 Windows 功能**链接。</span><span class="sxs-lookup"><span data-stu-id="1ac27-117">Choose the **Control Panel** icon, choose the **Programs** icon, and then choose the **Turn Windows features on or off** link.</span></span>
<br />

3. <span data-ttu-id="1ac27-118">请确保 **.NET Framework 3.5 （包括.NET 2.0 和 3.0）** 复选框被选中，并且然后选择**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="1ac27-118">Make sure that the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box is selected, and then choose the **OK** button.</span></span>
<br />  <span data-ttu-id="1ac27-119">你不需要选择对应的.NET framework 的可选组件的任何子节点的复选框。</span><span class="sxs-lookup"><span data-stu-id="1ac27-119">You don’t need to select the check boxes for any child nodes for optional components of the .NET Framework.</span></span>
<br />  <span data-ttu-id="1ac27-120">如果尚未，启用.NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="1ac27-120">The .NET Framework 3.5 is enabled if it wasn't already.</span></span>
<br />


#### <a name="to-install-the-f-20-runtime"></a><span data-ttu-id="1ac27-121">若要安装 F # 2.0 运行时</span><span class="sxs-lookup"><span data-stu-id="1ac27-121">To install the F# 2.0 runtime</span></span>

1. <span data-ttu-id="1ac27-122">在控制面板中，选择**程序**链接，然后再选择**程序和功能**链接。</span><span class="sxs-lookup"><span data-stu-id="1ac27-122">In the Control Panel, choose the **Programs** link, and then choose the **Programs and Features** link.</span></span>
<br />

2. <span data-ttu-id="1ac27-123">在已安装的程序列表中，选择版本的 Visual Studio 的安装，然后依次**更改**按钮。</span><span class="sxs-lookup"><span data-stu-id="1ac27-123">In the list of installed programs, choose the edition of Visual Studio that you installed, and then choose the **Change** button.</span></span>
<br />

3. <span data-ttu-id="1ac27-124">安装程序启动后，请选择**修复**按钮。</span><span class="sxs-lookup"><span data-stu-id="1ac27-124">After setup starts, choose the **Repair** button.</span></span>
<br />  <span data-ttu-id="1ac27-125">有关详细信息，请参阅[安装 Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1ac27-125">For more information, see [Installing Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span></span>
<br />
## <a name="see-also"></a><span data-ttu-id="1ac27-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ac27-126">See Also</span></span>
[<span data-ttu-id="1ac27-127">Visual F#</span><span class="sxs-lookup"><span data-stu-id="1ac27-127">Visual F#</span></span>](../index.md)
