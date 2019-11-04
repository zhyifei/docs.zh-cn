---
title: 演练：使用 Windows 窗体控件上的智能标记执行常规任务
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 07fb43a711ae8b1e2e375b17b136c07f35b1cf39
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459574"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a><span data-ttu-id="e539c-102">演练：使用智能标记执行常规任务</span><span class="sxs-lookup"><span data-stu-id="e539c-102">Walkthrough: Perform Common Tasks Using Smart Tags</span></span>

<span data-ttu-id="e539c-103">当你为 Windows 窗体应用程序构造窗体和控件时，将重复执行许多任务。</span><span class="sxs-lookup"><span data-stu-id="e539c-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="e539c-104">以下是你将会遇到的一些常见任务：</span><span class="sxs-lookup"><span data-stu-id="e539c-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="e539c-105">添加或删除 <xref:System.Windows.Forms.TabControl>上的选项卡。</span><span class="sxs-lookup"><span data-stu-id="e539c-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="e539c-106">将控件停靠到其父控件。</span><span class="sxs-lookup"><span data-stu-id="e539c-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="e539c-107">更改 <xref:System.Windows.Forms.SplitContainer> 控件的方向。</span><span class="sxs-lookup"><span data-stu-id="e539c-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="e539c-108">为了加快开发速度，许多控件都提供智能标记，这是一个上下文相关菜单，可用于在设计时在单个手势中执行类似这些任务的常见任务。</span><span class="sxs-lookup"><span data-stu-id="e539c-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="e539c-109">这些任务称为*智能标记谓词*。</span><span class="sxs-lookup"><span data-stu-id="e539c-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="e539c-110">智能标记在设计器的生存期内保持附加到控件实例，并且始终可用。</span><span class="sxs-lookup"><span data-stu-id="e539c-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="e539c-111">创建项目</span><span class="sxs-lookup"><span data-stu-id="e539c-111">Create the project</span></span>

<span data-ttu-id="e539c-112">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="e539c-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="e539c-113">在 Visual Studio 中，创建一个名为**SmartTagsExample**的基于 Windows 的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="e539c-113">In Visual Studio, create a Windows-based application project called **SmartTagsExample**.</span></span>

2. <span data-ttu-id="e539c-114">在**Windows 窗体设计器**中选择窗体。</span><span class="sxs-lookup"><span data-stu-id="e539c-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="e539c-115">使用智能标记</span><span class="sxs-lookup"><span data-stu-id="e539c-115">Use smart tags</span></span>

<span data-ttu-id="e539c-116">智能标记在设计时在提供这些标记的控件上始终可用。</span><span class="sxs-lookup"><span data-stu-id="e539c-116">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="e539c-117">将 <xref:System.Windows.Forms.TabControl> 从 "**工具箱**" 拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="e539c-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="e539c-118">请注意，在 <xref:System.Windows.Forms.TabControl>的一侧会出现智能标记标志符号（![智能标记标志符号](./media/vs-winformsmttagglyph.gif)）。</span><span class="sxs-lookup"><span data-stu-id="e539c-118">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="e539c-119">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="e539c-119">Click the smart-tag glyph.</span></span> <span data-ttu-id="e539c-120">在标志符号旁边显示的快捷菜单中，选择 "**添加" 选项卡**项。</span><span class="sxs-lookup"><span data-stu-id="e539c-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="e539c-121">请注意，新的选项卡页已添加到 <xref:System.Windows.Forms.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="e539c-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="e539c-122">从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="e539c-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="e539c-123">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="e539c-123">Click the smart-tag glyph.</span></span> <span data-ttu-id="e539c-124">在出现标志符号旁边的快捷菜单中，选择 "**添加列**" 项。</span><span class="sxs-lookup"><span data-stu-id="e539c-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="e539c-125">请注意，新列已添加到 <xref:System.Windows.Forms.TableLayoutPanel> 控件。</span><span class="sxs-lookup"><span data-stu-id="e539c-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="e539c-126">从 <xref:System.Windows.Forms.SplitContainer> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="e539c-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="e539c-127">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="e539c-127">Click the smart-tag glyph.</span></span> <span data-ttu-id="e539c-128">在标志符号旁边显示的快捷菜单中，选择 "**水平拆分器方向**" 项。</span><span class="sxs-lookup"><span data-stu-id="e539c-128">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="e539c-129">请注意，<xref:System.Windows.Forms.SplitContainer> 控件的拆分条现在为水平方向。</span><span class="sxs-lookup"><span data-stu-id="e539c-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="e539c-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="e539c-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
