---
title: 演练：使用 Windows 窗体控件上的智能标记执行常规任务
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 1cc854d735ba88a301d6e2f6a83fe5c8bf881380
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211422"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="d3d76-102">演练：使用 Windows 窗体控件上的智能标记执行常规任务</span><span class="sxs-lookup"><span data-stu-id="d3d76-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>

<span data-ttu-id="d3d76-103">在 Windows 窗体应用程序构造窗体和控件，如有需要反复执行的许多任务。</span><span class="sxs-lookup"><span data-stu-id="d3d76-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="d3d76-104">以下是一些你将遇到的执行常用任务：</span><span class="sxs-lookup"><span data-stu-id="d3d76-104">These are some of the commonly performed tasks you will encounter:</span></span>

- <span data-ttu-id="d3d76-105">添加或删除选项卡上<xref:System.Windows.Forms.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="d3d76-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>

- <span data-ttu-id="d3d76-106">将控件停靠到其父级。</span><span class="sxs-lookup"><span data-stu-id="d3d76-106">Docking a control to its parent.</span></span>

- <span data-ttu-id="d3d76-107">更改的方向<xref:System.Windows.Forms.SplitContainer>控件。</span><span class="sxs-lookup"><span data-stu-id="d3d76-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>

<span data-ttu-id="d3d76-108">若要加快开发速度，许多控件提供智能标记，可用于在设计时执行常见任务，比如在一个独立的上下文相关菜单。</span><span class="sxs-lookup"><span data-stu-id="d3d76-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="d3d76-109">这些任务称作*智能标记谓词*。</span><span class="sxs-lookup"><span data-stu-id="d3d76-109">These tasks are called *smart-tag verbs*.</span></span>

<span data-ttu-id="d3d76-110">智能标记的设计器中的整个生存期保持附加到一个控件实例，并始终处于可用状态。</span><span class="sxs-lookup"><span data-stu-id="d3d76-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>

<span data-ttu-id="d3d76-111">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="d3d76-111">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="d3d76-112">创建 Windows 窗体项目</span><span class="sxs-lookup"><span data-stu-id="d3d76-112">Creating a Windows Forms project</span></span>

- <span data-ttu-id="d3d76-113">使用智能标记</span><span class="sxs-lookup"><span data-stu-id="d3d76-113">Using smart tags</span></span>

- <span data-ttu-id="d3d76-114">启用和禁用智能标记</span><span class="sxs-lookup"><span data-stu-id="d3d76-114">Enabling and Disabling Smart Tags</span></span>

<span data-ttu-id="d3d76-115">完成上述操作后，你将会了解这些重要布局功能所发挥的作用。</span><span class="sxs-lookup"><span data-stu-id="d3d76-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="d3d76-116">创建项目</span><span class="sxs-lookup"><span data-stu-id="d3d76-116">Create the project</span></span>

<span data-ttu-id="d3d76-117">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="d3d76-117">The first step is to create the project and set up the form.</span></span>

1. <span data-ttu-id="d3d76-118">在 Visual Studio 中，创建一个名为"SmartTagsExample"的基于 Windows 的应用程序项目 (**文件** > **新建** > **项目** > **可视化C#** 或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="d3d76-118">In Visual Studio, create a Windows-based application project called "SmartTagsExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="d3d76-119">选择中的窗体**Windows 窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="d3d76-119">Select the form in the **Windows Forms Designer**.</span></span>

## <a name="use-smart-tags"></a><span data-ttu-id="d3d76-120">使用智能标记</span><span class="sxs-lookup"><span data-stu-id="d3d76-120">Use smart tags</span></span>

<span data-ttu-id="d3d76-121">智能标记上将其提供的控件的设计时将始终可用。</span><span class="sxs-lookup"><span data-stu-id="d3d76-121">Smart tags are always available at design time on controls that offer them.</span></span>

1. <span data-ttu-id="d3d76-122">拖动<xref:System.Windows.Forms.TabControl>从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="d3d76-122">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="d3d76-123">请注意的智能标记标志符号 (![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 旁边的显示<xref:System.Windows.Forms.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="d3d76-123">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>

2. <span data-ttu-id="d3d76-124">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="d3d76-124">Click the smart-tag glyph.</span></span> <span data-ttu-id="d3d76-125">在标志符号旁边显示的快捷菜单，选择**添加选项卡**项。</span><span class="sxs-lookup"><span data-stu-id="d3d76-125">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="d3d76-126">观察到的新选项卡页添加到<xref:System.Windows.Forms.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="d3d76-126">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>

3. <span data-ttu-id="d3d76-127">从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="d3d76-127">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

4. <span data-ttu-id="d3d76-128">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="d3d76-128">Click the smart-tag glyph.</span></span> <span data-ttu-id="d3d76-129">在标志符号旁边显示的快捷菜单，选择**添加列**项。</span><span class="sxs-lookup"><span data-stu-id="d3d76-129">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="d3d76-130">观察新列添加到<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="d3d76-130">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

5. <span data-ttu-id="d3d76-131">从 <xref:System.Windows.Forms.SplitContainer> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="d3d76-131">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>

6. <span data-ttu-id="d3d76-132">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="d3d76-132">Click the smart-tag glyph.</span></span> <span data-ttu-id="d3d76-133">在标志符号旁边显示的快捷菜单，选择**水平拆分器方向**项。</span><span class="sxs-lookup"><span data-stu-id="d3d76-133">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="d3d76-134">观察<xref:System.Windows.Forms.SplitContainer>现在是控件的分隔条水平。</span><span class="sxs-lookup"><span data-stu-id="d3d76-134">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>

## <a name="see-also"></a><span data-ttu-id="d3d76-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="d3d76-135">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- <span data-ttu-id="d3d76-136">[演练：向 Windows 窗体组件添加智能标记](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d3d76-136">[Walkthrough: Adding Smart Tags to a Windows Forms Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span></span>
