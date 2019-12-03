---
title: 如何安装模型生成器
description: 了解如何安装 ML.NET 模型生成器工具
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: b87f712ad7a8b2229c1d42db4bad1fe511475ac7
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552944"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="0dceb-103">如何安装 ML.NET 模型生成器</span><span class="sxs-lookup"><span data-stu-id="0dceb-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="0dceb-104">了解如何安装 ML.NET 模型生成器以将机器学习添加到 .NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0dceb-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="0dceb-105">模型生成器当前为预览版。</span><span class="sxs-lookup"><span data-stu-id="0dceb-105">Model Builder is currently in Preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0dceb-106">系统必备</span><span class="sxs-lookup"><span data-stu-id="0dceb-106">Prerequisites</span></span>

- <span data-ttu-id="0dceb-107">Visual Studio 2017 版本 15.9.12 或更高版本/Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0dceb-107">Visual Studio 2017 version 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="0dceb-108">.NET Core 2.1 SDK 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="0dceb-108">.NET Core 2.1 SDK or later.</span></span>

> [!NOTE]
> <span data-ttu-id="0dceb-109">暂不支持 .NET Core 3.0 SDK。</span><span class="sxs-lookup"><span data-stu-id="0dceb-109">.NET Core 3.0 SDK is not currently supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="0dceb-110">限制</span><span class="sxs-lookup"><span data-stu-id="0dceb-110">Limitations</span></span>

- <span data-ttu-id="0dceb-111">ML.NET 模型生成器扩展目前仅适用于 Windows 上的 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="0dceb-111">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="0dceb-112">1 GB 的训练数据集限制</span><span class="sxs-lookup"><span data-stu-id="0dceb-112">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="0dceb-113">SQL Server 在训练用途上有 100,000 行的限制</span><span class="sxs-lookup"><span data-stu-id="0dceb-113">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="0dceb-114">不支持适用于 Visual Studio 2017 的 Microsoft SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="0dceb-114">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="0dceb-115">安装</span><span class="sxs-lookup"><span data-stu-id="0dceb-115">Install</span></span>

<span data-ttu-id="0dceb-116">可通过 Visual Studio Marketplace 或从 Visual Studio 中安装 ML.NET 模型生成器。</span><span class="sxs-lookup"><span data-stu-id="0dceb-116">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span>

### <a name="visual-studio-marketplace"></a><span data-ttu-id="0dceb-117">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="0dceb-117">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="0dceb-118">在 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07) 中下载</span><span class="sxs-lookup"><span data-stu-id="0dceb-118">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="0dceb-119">按照提示安装到相应的 Visual Studio 版本上</span><span class="sxs-lookup"><span data-stu-id="0dceb-119">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="0dceb-120">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0dceb-120">Visual Studio 2017</span></span>

1. <span data-ttu-id="0dceb-121">从菜单栏选择“工具” > “扩展和更新”  </span><span class="sxs-lookup"><span data-stu-id="0dceb-121">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017 打开“扩展管理器”对话框](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="0dceb-123">在“扩展和更新”提示符中选择“联机”节点   。</span><span class="sxs-lookup"><span data-stu-id="0dceb-123">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="0dceb-124">在搜索栏中搜索“ML.NET 模型生成器”，并在搜索结果中选择 ML.NET 模型搜索器（预览版） </span><span class="sxs-lookup"><span data-stu-id="0dceb-124">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>

    ![VS2017 从“扩展管理器”对话框中搜索并安装“模型生成器”扩展](./media/install-model-builder/vs2017-install-model-builder.png)

1. <span data-ttu-id="0dceb-126">按照提示完成安装</span><span class="sxs-lookup"><span data-stu-id="0dceb-126">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="0dceb-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0dceb-127">Visual Studio 2019</span></span>

1. <span data-ttu-id="0dceb-128">从菜单栏选择“扩展” > “管理扩展”  </span><span class="sxs-lookup"><span data-stu-id="0dceb-128">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019 打开“扩展管理器”对话框](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="0dceb-130">在“扩展和更新”提示符中选择“联机”节点   。</span><span class="sxs-lookup"><span data-stu-id="0dceb-130">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="0dceb-131">在搜索栏中键入“ML.NET 模型生成器”并选择 ML.NET 模型生成器（预览版） </span><span class="sxs-lookup"><span data-stu-id="0dceb-131">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>

    ![VS2019 从“扩展管理器”对话框中搜索并安装“模型生成器”扩展](./media/install-model-builder/vs2019-install-model-builder.png)

1. <span data-ttu-id="0dceb-133">按照提示完成安装</span><span class="sxs-lookup"><span data-stu-id="0dceb-133">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="0dceb-134">卸载</span><span class="sxs-lookup"><span data-stu-id="0dceb-134">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="0dceb-135">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="0dceb-135">Visual Studio 2017</span></span>

1. <span data-ttu-id="0dceb-136">从菜单栏选择“工具” > “扩展和更新”  </span><span class="sxs-lookup"><span data-stu-id="0dceb-136">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017 打开“管理扩展”对话框](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="0dceb-138">在“扩展和更新”提示窗口中展开“已安装”节点并选择“工具”节点   </span><span class="sxs-lookup"><span data-stu-id="0dceb-138">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="0dceb-139">从工具列表中选择 ML.NET 模型生成器（预览版），然后选择“卸载” </span><span class="sxs-lookup"><span data-stu-id="0dceb-139">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2017 从“扩展管理器”对话框中搜索并卸载“模型生成器”扩展](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. <span data-ttu-id="0dceb-141">按照提示完成卸载。</span><span class="sxs-lookup"><span data-stu-id="0dceb-141">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="0dceb-142">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="0dceb-142">Visual Studio 2019</span></span>

1. <span data-ttu-id="0dceb-143">从菜单栏选择“扩展” > “管理扩展”  </span><span class="sxs-lookup"><span data-stu-id="0dceb-143">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019 打开“管理扩展”对话框](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="0dceb-145">在“扩展和更新”提示窗口中展开“已安装”节点并选择“工具”节点   </span><span class="sxs-lookup"><span data-stu-id="0dceb-145">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="0dceb-146">从工具列表中选择 ML.NET 模型生成器（预览版），然后选择“卸载” </span><span class="sxs-lookup"><span data-stu-id="0dceb-146">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2019 从“扩展管理器”对话框中搜索并卸载“模型生成器”扩展](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. <span data-ttu-id="0dceb-148">按照提示完成卸载。</span><span class="sxs-lookup"><span data-stu-id="0dceb-148">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="0dceb-149">Upgrade</span><span class="sxs-lookup"><span data-stu-id="0dceb-149">Upgrade</span></span>

<span data-ttu-id="0dceb-150">升级流程与安装流程类似。</span><span class="sxs-lookup"><span data-stu-id="0dceb-150">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="0dceb-151">可以从 Visual Studio Marketplace 中下载最新版本，或者使用 Visual Studio 中的扩展管理器进行升级。</span><span class="sxs-lookup"><span data-stu-id="0dceb-151">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
