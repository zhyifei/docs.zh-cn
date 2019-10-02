---
title: 如何安装模型生成器
description: 了解如何安装 ML.NET 模型生成器工具
author: luisquintanilla
ms.author: luquinta
ms.date: 06/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: b0d45ab7807bf84b98c58e85580d5aa04d0c5f7d
ms.sourcegitcommit: 1e72e2990220b3635cebc39586828af9deb72d8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2019
ms.locfileid: "71306330"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="c89ac-103">如何安装 ML.NET 模型生成器</span><span class="sxs-lookup"><span data-stu-id="c89ac-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="c89ac-104">了解如何安装 ML.NET 模型生成器以将机器学习添加到 .NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c89ac-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="c89ac-105">模型生成器当前为预览版。</span><span class="sxs-lookup"><span data-stu-id="c89ac-105">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="c89ac-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="c89ac-106">Pre-requisites</span></span>

- <span data-ttu-id="c89ac-107">Visual Studio 2017 15.9.12 或更高版本 / Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c89ac-107">Visual Studio 2017 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="c89ac-108">.NET Core 2.1 或更高版本的 SDK</span><span class="sxs-lookup"><span data-stu-id="c89ac-108">.NET Core 2.1 or later SDK</span></span>

## <a name="limitations"></a><span data-ttu-id="c89ac-109">限制</span><span class="sxs-lookup"><span data-stu-id="c89ac-109">Limitations</span></span>

- <span data-ttu-id="c89ac-110">ML.NET 模型生成器扩展目前仅适用于 Windows 上的 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="c89ac-110">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="c89ac-111">1 GB 的训练数据集限制</span><span class="sxs-lookup"><span data-stu-id="c89ac-111">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="c89ac-112">SQL Server 在训练用途上有 100,000 行的限制</span><span class="sxs-lookup"><span data-stu-id="c89ac-112">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="c89ac-113">不支持适用于 Visual Studio 2017 的 Microsoft SQL Server Data Tools</span><span class="sxs-lookup"><span data-stu-id="c89ac-113">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="c89ac-114">安装</span><span class="sxs-lookup"><span data-stu-id="c89ac-114">Install</span></span>

<span data-ttu-id="c89ac-115">可通过 Visual Studio Marketplace 或从 Visual Studio 中安装 ML.NET 模型生成器。</span><span class="sxs-lookup"><span data-stu-id="c89ac-115">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span> 

### <a name="visual-studio-marketplace"></a><span data-ttu-id="c89ac-116">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="c89ac-116">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="c89ac-117">在 [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07) 中下载</span><span class="sxs-lookup"><span data-stu-id="c89ac-117">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="c89ac-118">按照提示安装到相应的 Visual Studio 版本上</span><span class="sxs-lookup"><span data-stu-id="c89ac-118">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="c89ac-119">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="c89ac-119">Visual Studio 2017</span></span>

1. <span data-ttu-id="c89ac-120">从菜单栏选择“工具” > “扩展和更新”  </span><span class="sxs-lookup"><span data-stu-id="c89ac-120">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017 打开“扩展管理器”对话框](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="c89ac-122">在“扩展和更新”提示符中选择“联机”节点   。</span><span class="sxs-lookup"><span data-stu-id="c89ac-122">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="c89ac-123">在搜索栏中搜索“ML.NET 模型生成器”，并在搜索结果中选择 ML.NET 模型搜索器（预览版） </span><span class="sxs-lookup"><span data-stu-id="c89ac-123">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>

    ![VS2017 从“扩展管理器”对话框中搜索并安装“模型生成器”扩展](./media/install-model-builder/vs2017-install-model-builder.png)

1. <span data-ttu-id="c89ac-125">按照提示完成安装</span><span class="sxs-lookup"><span data-stu-id="c89ac-125">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="c89ac-126">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c89ac-126">Visual Studio 2019</span></span>

1. <span data-ttu-id="c89ac-127">从菜单栏选择“扩展” > “管理扩展”  </span><span class="sxs-lookup"><span data-stu-id="c89ac-127">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019 打开“扩展管理器”对话框](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="c89ac-129">在“扩展和更新”提示符中选择“联机”节点   。</span><span class="sxs-lookup"><span data-stu-id="c89ac-129">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="c89ac-130">在搜索栏中键入“ML.NET 模型生成器”并选择 ML.NET 模型生成器（预览版） </span><span class="sxs-lookup"><span data-stu-id="c89ac-130">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>

    ![VS2019 从“扩展管理器”对话框中搜索并安装“模型生成器”扩展](./media/install-model-builder/vs2019-install-model-builder.png)

1. <span data-ttu-id="c89ac-132">按照提示完成安装</span><span class="sxs-lookup"><span data-stu-id="c89ac-132">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="c89ac-133">卸载</span><span class="sxs-lookup"><span data-stu-id="c89ac-133">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="c89ac-134">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="c89ac-134">Visual Studio 2017</span></span>

1. <span data-ttu-id="c89ac-135">从菜单栏选择“工具” > “扩展和更新”  </span><span class="sxs-lookup"><span data-stu-id="c89ac-135">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017 打开“管理扩展”对话框](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="c89ac-137">在“扩展和更新”提示窗口中展开“已安装”节点并选择“工具”节点   </span><span class="sxs-lookup"><span data-stu-id="c89ac-137">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="c89ac-138">从工具列表中选择 ML.NET 模型生成器（预览版），然后选择“卸载” </span><span class="sxs-lookup"><span data-stu-id="c89ac-138">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2017 从“扩展管理器”对话框中搜索并卸载“模型生成器”扩展](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. <span data-ttu-id="c89ac-140">按照提示完成卸载。</span><span class="sxs-lookup"><span data-stu-id="c89ac-140">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="c89ac-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="c89ac-141">Visual Studio 2019</span></span>

1. <span data-ttu-id="c89ac-142">从菜单栏选择“扩展” > “管理扩展”  </span><span class="sxs-lookup"><span data-stu-id="c89ac-142">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019 打开“管理扩展”对话框](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="c89ac-144">在“扩展和更新”提示窗口中展开“已安装”节点并选择“工具”节点   </span><span class="sxs-lookup"><span data-stu-id="c89ac-144">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="c89ac-145">从工具列表中选择 ML.NET 模型生成器（预览版），然后选择“卸载” </span><span class="sxs-lookup"><span data-stu-id="c89ac-145">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2019 从“扩展管理器”对话框中搜索并卸载“模型生成器”扩展](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. <span data-ttu-id="c89ac-147">按照提示完成卸载。</span><span class="sxs-lookup"><span data-stu-id="c89ac-147">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="c89ac-148">Upgrade</span><span class="sxs-lookup"><span data-stu-id="c89ac-148">Upgrade</span></span>

<span data-ttu-id="c89ac-149">升级流程与安装流程类似。</span><span class="sxs-lookup"><span data-stu-id="c89ac-149">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="c89ac-150">可以从 Visual Studio Marketplace 中下载最新版本，或者使用 Visual Studio 中的扩展管理器进行升级。</span><span class="sxs-lookup"><span data-stu-id="c89ac-150">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
