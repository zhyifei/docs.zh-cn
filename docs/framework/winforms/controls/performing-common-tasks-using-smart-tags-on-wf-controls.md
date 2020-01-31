---
title: 使用控件上的智能标记 Performi 常见任务
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 826313d0a89410f62c034a5fba4dee32e90a1750
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744256"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a><span data-ttu-id="cb235-102">演练：使用智能标记执行常规任务</span><span class="sxs-lookup"><span data-stu-id="cb235-102">Walkthrough: Perform Common Tasks Using Smart Tags</span></span>

<span data-ttu-id="cb235-103">当你为 Windows 窗体应用程序构造窗体和控件时，将重复执行许多任务。</span><span class="sxs-lookup"><span data-stu-id="cb235-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="cb235-104">以下是你将会遇到的一些常见任务：</span><span class="sxs-lookup"><span data-stu-id="cb235-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="cb235-105">添加或删除 <xref:System.Windows.Forms.TabControl>上的选项卡。</span><span class="sxs-lookup"><span data-stu-id="cb235-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="cb235-106">将控件停靠到其父控件。</span><span class="sxs-lookup"><span data-stu-id="cb235-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="cb235-107">更改 <xref:System.Windows.Forms.SplitContainer> 控件的方向。</span><span class="sxs-lookup"><span data-stu-id="cb235-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="cb235-108">为了加快开发速度，许多控件都提供智能标记，这是一个上下文相关菜单，可用于在设计时在单个手势中执行类似这些任务的常见任务。</span><span class="sxs-lookup"><span data-stu-id="cb235-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="cb235-109">这些任务称为*智能标记谓词*。</span><span class="sxs-lookup"><span data-stu-id="cb235-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="cb235-110">智能标记在设计器的生存期内保持附加到控件实例，并且始终可用。</span><span class="sxs-lookup"><span data-stu-id="cb235-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="cb235-111">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cb235-111">Create the project</span></span>

<span data-ttu-id="cb235-112">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cb235-112">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="cb235-113">在 Visual Studio 中，创建一个名为**SmartTagsExample**的基于 Windows 的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="cb235-113">In Visual Studio, create a Windows-based application project called **SmartTagsExample**.</span></span>

2. <span data-ttu-id="cb235-114">在**Windows 窗体设计器**中选择窗体。</span><span class="sxs-lookup"><span data-stu-id="cb235-114">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="cb235-115">使用智能标记</span><span class="sxs-lookup"><span data-stu-id="cb235-115">Use smart tags</span></span>

<span data-ttu-id="cb235-116">智能标记在设计时在提供这些标记的控件上始终可用。</span><span class="sxs-lookup"><span data-stu-id="cb235-116">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="cb235-117">将 <xref:System.Windows.Forms.TabControl> 从 "**工具箱**" 拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="cb235-117">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="cb235-118">请注意，在 <xref:System.Windows.Forms.TabControl>的一侧会出现智能标记标志符号（![智能标记标志符号](./media/vs-winformsmttagglyph.gif)）。</span><span class="sxs-lookup"><span data-stu-id="cb235-118">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif)) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="cb235-119">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="cb235-119">Click the smart-tag glyph.</span></span> <span data-ttu-id="cb235-120">在标志符号旁边显示的快捷菜单中，选择 "**添加" 选项卡**项。</span><span class="sxs-lookup"><span data-stu-id="cb235-120">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="cb235-121">请注意，新的选项卡页已添加到 <xref:System.Windows.Forms.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="cb235-121">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="cb235-122"><xref:System.Windows.Forms.TableLayoutPanel> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="cb235-122">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="cb235-123">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="cb235-123">Click the smart-tag glyph.</span></span> <span data-ttu-id="cb235-124">在出现标志符号旁边的快捷菜单中，选择 "**添加列**" 项。</span><span class="sxs-lookup"><span data-stu-id="cb235-124">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="cb235-125">请注意，新列已添加到 <xref:System.Windows.Forms.TableLayoutPanel> 控件。</span><span class="sxs-lookup"><span data-stu-id="cb235-125">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="cb235-126"><xref:System.Windows.Forms.SplitContainer> 도구 상자 **에서** 컨트롤을 폼으로 끌어다 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="cb235-126">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="cb235-127">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="cb235-127">Click the smart-tag glyph.</span></span> <span data-ttu-id="cb235-128">在标志符号旁边显示的快捷菜单中，选择 "**水平拆分器方向**" 项。</span><span class="sxs-lookup"><span data-stu-id="cb235-128">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="cb235-129">请注意，<xref:System.Windows.Forms.SplitContainer> 控件的拆分条现在为水平方向。</span><span class="sxs-lookup"><span data-stu-id="cb235-129">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="cb235-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb235-130">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
