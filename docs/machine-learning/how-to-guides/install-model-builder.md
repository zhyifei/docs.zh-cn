---
title: 如何安装模型生成器
description: 了解如何安装 ML.NET 模型生成器工具
author: luisquintanilla
ms.author: luquinta
ms.date: 06/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: 54ab595c56f816517180aab48022c7df207fe84d
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410565"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="23a74-103">如何安装 ML.NET 模型生成器</span><span class="sxs-lookup"><span data-stu-id="23a74-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="23a74-104">了解如何安装 ML.NET 模型生成器以将机器学习添加到 .NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="23a74-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="23a74-105">模型生成器当前为预览版。</span><span class="sxs-lookup"><span data-stu-id="23a74-105">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="23a74-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="23a74-106">Pre-requisites</span></span>

- <span data-ttu-id="23a74-107">Visual Studio 2017 15.9.12 或更高版本 / Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="23a74-107">Visual Studio 2017 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="23a74-108">.NET Core 2.1 或更高版本的 SDK</span><span class="sxs-lookup"><span data-stu-id="23a74-108">.NET Core 2.1 or later SDK</span></span>

## <a name="limitations"></a><span data-ttu-id="23a74-109">限制</span><span class="sxs-lookup"><span data-stu-id="23a74-109">Limitations</span></span>

- <span data-ttu-id="23a74-110">ML.NET 模型生成器扩展目前仅适用于 Windows 上的 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="23a74-110">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="23a74-111">1 GB 的训练数据集限制</span><span class="sxs-lookup"><span data-stu-id="23a74-111">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="23a74-112">SQL Server 在训练用途上有 100,000 行的限制</span><span class="sxs-lookup"><span data-stu-id="23a74-112">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="23a74-113">不支持适用于 Visual Studio 2017 的 Microsoft SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="23a74-113">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="23a74-114">安装</span><span class="sxs-lookup"><span data-stu-id="23a74-114">Install</span></span>

<span data-ttu-id="23a74-115">可通过 Visual Studio Marketplace 或从 Visual Studio 中安装 ML.NET 模型生成器。</span><span class="sxs-lookup"><span data-stu-id="23a74-115">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span> 

### <a name="visual-studio-marketplace"></a><span data-ttu-id="23a74-116">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="23a74-116">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="23a74-117">在 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07) 中下载</span><span class="sxs-lookup"><span data-stu-id="23a74-117">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="23a74-118">按照提示安装到相应的 Visual Studio 版本上</span><span class="sxs-lookup"><span data-stu-id="23a74-118">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="23a74-119">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="23a74-119">Visual Studio 2017</span></span>

1. <span data-ttu-id="23a74-120">从菜单栏选择“工具” > “扩展和更新”  </span><span class="sxs-lookup"><span data-stu-id="23a74-120">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>
1. <span data-ttu-id="23a74-121">在“扩展和更新”提示符中选择“联机”节点   。</span><span class="sxs-lookup"><span data-stu-id="23a74-121">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="23a74-122">在搜索栏中搜索“ML.NET 模型生成器”，并在搜索结果中选择 ML.NET 模型搜索器（预览版） </span><span class="sxs-lookup"><span data-stu-id="23a74-122">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>
1. <span data-ttu-id="23a74-123">按照提示完成安装</span><span class="sxs-lookup"><span data-stu-id="23a74-123">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="23a74-124">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="23a74-124">Visual Studio 2019</span></span>

1. <span data-ttu-id="23a74-125">从菜单栏选择“扩展” > “管理扩展”  </span><span class="sxs-lookup"><span data-stu-id="23a74-125">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>
1. <span data-ttu-id="23a74-126">在“扩展和更新”提示符中选择“联机”节点   。</span><span class="sxs-lookup"><span data-stu-id="23a74-126">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="23a74-127">在搜索栏中键入“ML.NET 模型生成器”并选择 ML.NET 模型生成器（预览版） </span><span class="sxs-lookup"><span data-stu-id="23a74-127">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>
1. <span data-ttu-id="23a74-128">按照提示完成安装</span><span class="sxs-lookup"><span data-stu-id="23a74-128">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="23a74-129">卸载</span><span class="sxs-lookup"><span data-stu-id="23a74-129">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="23a74-130">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="23a74-130">Visual Studio 2017</span></span>

1. <span data-ttu-id="23a74-131">从菜单栏选择“工具” > “扩展和更新”  </span><span class="sxs-lookup"><span data-stu-id="23a74-131">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>
1. <span data-ttu-id="23a74-132">在“扩展和更新”提示窗口中展开“已安装”节点并选择“工具”节点   </span><span class="sxs-lookup"><span data-stu-id="23a74-132">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="23a74-133">从工具列表中选择 ML.NET 模型生成器（预览版），然后选择“卸载” </span><span class="sxs-lookup"><span data-stu-id="23a74-133">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>
1. <span data-ttu-id="23a74-134">按照提示完成卸载。</span><span class="sxs-lookup"><span data-stu-id="23a74-134">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="23a74-135">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="23a74-135">Visual Studio 2019</span></span>

1. <span data-ttu-id="23a74-136">从菜单栏选择“扩展” > “管理扩展”  </span><span class="sxs-lookup"><span data-stu-id="23a74-136">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>
1. <span data-ttu-id="23a74-137">在“扩展和更新”提示窗口中展开“已安装”节点并选择“工具”节点   </span><span class="sxs-lookup"><span data-stu-id="23a74-137">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="23a74-138">从工具列表中选择 ML.NET 模型生成器（预览版），然后选择“卸载” </span><span class="sxs-lookup"><span data-stu-id="23a74-138">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>
1. <span data-ttu-id="23a74-139">按照提示完成卸载。</span><span class="sxs-lookup"><span data-stu-id="23a74-139">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="23a74-140">Upgrade</span><span class="sxs-lookup"><span data-stu-id="23a74-140">Upgrade</span></span>

<span data-ttu-id="23a74-141">升级流程与安装流程类似。</span><span class="sxs-lookup"><span data-stu-id="23a74-141">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="23a74-142">可以从 Visual Studio Marketplace 中下载最新版本，或者使用 Visual Studio 中的扩展管理器进行升级。</span><span class="sxs-lookup"><span data-stu-id="23a74-142">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
