---
title: "面向 Windows 8 中的 .NET Framework 2.0"
description: "了解如何使用 F # 时以旧版本的.NET Framework 为目标。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63989543-95c3-4ab7-81f3-3834a8b15010
ms.openlocfilehash: 2c0191267da5bee7b844c11cdee168ccfb3321c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="targeting-older-versions-of-net"></a><span data-ttu-id="34f05-104">面向 .NET 的较旧版本</span><span class="sxs-lookup"><span data-stu-id="34f05-104">Targeting Older Versions of .NET</span></span>

> [!NOTE]
<span data-ttu-id="34f05-105">本文不是最新的 Visual Studio 最新的。</span><span class="sxs-lookup"><span data-stu-id="34f05-105">This article is not up to date with the latest Visual Studio.</span></span>  <span data-ttu-id="34f05-106">它将会更新。</span><span class="sxs-lookup"><span data-stu-id="34f05-106">It will be updated.</span></span>

<span data-ttu-id="34f05-107">如果你尝试面向.NET Framework 2.0，3.0 或 3.5 中的 F # 项目时在 Windows 8.1 上安装 Visual Studio 可能会出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="34f05-107">The following error might appear if you try to target the .NET Framework 2.0, 3.0, or 3.5 in an F# project when Visual Studio is installed on Windows 8.1:</span></span> 

```
This project requires the 2.0 F# runtime, but that runtime is not installed.
```

<span data-ttu-id="34f05-108">此错误是已知在以下条件的组合下出现：</span><span class="sxs-lookup"><span data-stu-id="34f05-108">This error is known to occur under the following combination of conditions:</span></span>


- <span data-ttu-id="34f05-109">在 Windows 8.1 上安装了 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="34f05-109">You installed Visual Studio on Windows 8.1.</span></span>
<br />

- <span data-ttu-id="34f05-110">在安装 Visual Studio 之前，未启用.NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="34f05-110">You didn’t enable the .NET Framework 3.5 before you installed Visual Studio.</span></span>
<br />

- <span data-ttu-id="34f05-111">你的项目面向.NET Framework 2.0、 3.0 或 3.5。</span><span class="sxs-lookup"><span data-stu-id="34f05-111">Your project targets the .NET Framework 2.0, 3.0, or 3.5.</span></span>
<br />

<span data-ttu-id="34f05-112">在安装 Visual Studio 时，它检测到已安装的.NET Framework 版本，并安装 F # 2.0 运行时，仅当安装并启用.NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="34f05-112">When you install Visual Studio, it detects the installed versions of the .NET Framework and installs the F# 2.0 Runtime only if the .NET Framework 3.5 is installed and enabled.</span></span>


## <a name="resolving-the-error"></a><span data-ttu-id="34f05-113">解决错误</span><span class="sxs-lookup"><span data-stu-id="34f05-113">Resolving the Error</span></span>
<span data-ttu-id="34f05-114">若要解决此错误，你可以任一目标.NET Framework 中，较新版本，或您可以启用 Windows 8.1 上的.NET Framework 3.5，然后安装 F # 2.0 运行时通过运行使用 Visual Studio 的安装程序**修复**选项。</span><span class="sxs-lookup"><span data-stu-id="34f05-114">To resolve this error, you can either target a newer version of the .NET Framework, or you can enable the .NET Framework 3.5 on Windows 8.1 and then install the F# 2.0 runtime by running the setup program for Visual Studio with the **Repair** option.</span></span>


#### <a name="to-enable-the-net-framework-35-on-windows-81"></a><span data-ttu-id="34f05-115">若要启用 Windows 8.1 上的.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="34f05-115">To enable the .NET Framework 3.5 on Windows 8.1</span></span>

1. <span data-ttu-id="34f05-116">上**启动**屏幕上，开始输入**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="34f05-116">On the **Start** screen, start to enter **Control Panel**.</span></span>
<br />  <span data-ttu-id="34f05-117">该名称时，输入时**控制面板**图标显示在**应用**标题。</span><span class="sxs-lookup"><span data-stu-id="34f05-117">As you enter that name, the **Control Panel** icon appears under the **Apps** heading.</span></span>
<br />

2. <span data-ttu-id="34f05-118">选择**控制面板**图标，选择**程序**图标，然后选择**打开或关闭 Windows 功能**链接。</span><span class="sxs-lookup"><span data-stu-id="34f05-118">Choose the **Control Panel** icon, choose the **Programs** icon, and then choose the **Turn Windows features on or off** link.</span></span>
<br />

3. <span data-ttu-id="34f05-119">请确保**.NET Framework 3.5 （包括.NET 2.0 和 3.0）**复选框被选中，并且然后选择**确定**按钮。</span><span class="sxs-lookup"><span data-stu-id="34f05-119">Make sure that the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box is selected, and then choose the **OK** button.</span></span>
<br />  <span data-ttu-id="34f05-120">你不需要选择对应的.NET framework 的可选组件的任何子节点的复选框。</span><span class="sxs-lookup"><span data-stu-id="34f05-120">You don’t need to select the check boxes for any child nodes for optional components of the .NET Framework.</span></span>
<br />  <span data-ttu-id="34f05-121">如果尚未，启用.NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="34f05-121">The .NET Framework 3.5 is enabled if it wasn't already.</span></span>
<br />


#### <a name="to-install-the-f-20-runtime"></a><span data-ttu-id="34f05-122">若要安装 F # 2.0 运行时</span><span class="sxs-lookup"><span data-stu-id="34f05-122">To install the F# 2.0 runtime</span></span>

1. <span data-ttu-id="34f05-123">在控制面板中，选择**程序**链接，然后再选择**程序和功能**链接。</span><span class="sxs-lookup"><span data-stu-id="34f05-123">In the Control Panel, choose the **Programs** link, and then choose the **Programs and Features** link.</span></span>
<br />

2. <span data-ttu-id="34f05-124">在已安装的程序列表中，选择版本的 Visual Studio 的安装，然后依次**更改**按钮。</span><span class="sxs-lookup"><span data-stu-id="34f05-124">In the list of installed programs, choose the edition of Visual Studio that you installed, and then choose the **Change** button.</span></span>
<br />

3. <span data-ttu-id="34f05-125">安装程序启动后，请选择**修复**按钮。</span><span class="sxs-lookup"><span data-stu-id="34f05-125">After setup starts, choose the **Repair** button.</span></span>
<br />  <span data-ttu-id="34f05-126">有关详细信息，请参阅[安装 Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx)。</span><span class="sxs-lookup"><span data-stu-id="34f05-126">For more information, see [Installing Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span></span>
<br />
## <a name="see-also"></a><span data-ttu-id="34f05-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34f05-127">See Also</span></span>
[<span data-ttu-id="34f05-128">Visual F#</span><span class="sxs-lookup"><span data-stu-id="34f05-128">Visual F#</span></span>](../index.md)
