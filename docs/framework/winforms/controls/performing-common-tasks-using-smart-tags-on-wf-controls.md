---
title: "演练：使用 Windows 窗体控件上的智能标记执行常规任务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e2fb4e8bf710e55be0a817a4154dfbce114db191
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="47426-102">演练：使用 Windows 窗体控件上的智能标记执行常规任务</span><span class="sxs-lookup"><span data-stu-id="47426-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>
<span data-ttu-id="47426-103">为 Windows 窗体应用程序中构造窗体和控件，如有需要反复执行的许多任务。</span><span class="sxs-lookup"><span data-stu-id="47426-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="47426-104">以下是一些常执行的任务，则会遇到：</span><span class="sxs-lookup"><span data-stu-id="47426-104">These are some of the commonly performed tasks you will encounter:</span></span>  
  
-   <span data-ttu-id="47426-105">添加或删除选项卡上<xref:System.Windows.Forms.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="47426-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>  
  
-   <span data-ttu-id="47426-106">将控件停靠到其父级。</span><span class="sxs-lookup"><span data-stu-id="47426-106">Docking a control to its parent.</span></span>  
  
-   <span data-ttu-id="47426-107">更改的方向<xref:System.Windows.Forms.SplitContainer>控件。</span><span class="sxs-lookup"><span data-stu-id="47426-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>  
  
 <span data-ttu-id="47426-108">为了加快开发速度，许多控件提供了智能标记，它们是可用于在设计时执行常见任务，比如这些中的单个笔势的上下文相关菜单。</span><span class="sxs-lookup"><span data-stu-id="47426-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="47426-109">这些任务称作*智能标记谓词*。</span><span class="sxs-lookup"><span data-stu-id="47426-109">These tasks are called *smart-tag verbs*.</span></span>  
  
 <span data-ttu-id="47426-110">智能标记的设计器中的整个生存期保持附加到控件实例并且始终可用。</span><span class="sxs-lookup"><span data-stu-id="47426-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>  
  
 <span data-ttu-id="47426-111">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="47426-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="47426-112">创建 Windows 窗体项目</span><span class="sxs-lookup"><span data-stu-id="47426-112">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="47426-113">使用智能标记</span><span class="sxs-lookup"><span data-stu-id="47426-113">Using smart tags</span></span>  
  
-   <span data-ttu-id="47426-114">启用和禁用智能标记</span><span class="sxs-lookup"><span data-stu-id="47426-114">Enabling and Disabling Smart Tags</span></span>  
  
 <span data-ttu-id="47426-115">完成上述操作后，你将会了解这些重要布局功能所发挥的作用。</span><span class="sxs-lookup"><span data-stu-id="47426-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47426-116">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="47426-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="47426-117">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="47426-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="47426-118">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="47426-118">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="47426-119">创建项目</span><span class="sxs-lookup"><span data-stu-id="47426-119">Creating the Project</span></span>  
 <span data-ttu-id="47426-120">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="47426-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="47426-121">要创建项目</span><span class="sxs-lookup"><span data-stu-id="47426-121">To create the project</span></span>  
  
1.  <span data-ttu-id="47426-122">创建一个名为"SmartTagsExample"的基于 Windows 的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="47426-122">Create a Windows-based application project called "SmartTagsExample".</span></span> <span data-ttu-id="47426-123">有关详细信息，请参阅[如何：创建一个 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)。</span><span class="sxs-lookup"><span data-stu-id="47426-123">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="47426-124">选择的窗体中**Windows 窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="47426-124">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="using-smart-tags"></a><span data-ttu-id="47426-125">使用智能标记</span><span class="sxs-lookup"><span data-stu-id="47426-125">Using Smart Tags</span></span>  
 <span data-ttu-id="47426-126">在设计时为他们提供的控件上都可以使用智能标记。</span><span class="sxs-lookup"><span data-stu-id="47426-126">Smart tags are always available at design time on controls that offer them.</span></span>  
  
#### <a name="to-use-smart-tags"></a><span data-ttu-id="47426-127">若要使用智能标记</span><span class="sxs-lookup"><span data-stu-id="47426-127">To use smart tags</span></span>  
  
1.  <span data-ttu-id="47426-128">拖动<xref:System.Windows.Forms.TabControl>从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="47426-128">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="47426-129">请注意的智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 旁边的显示<xref:System.Windows.Forms.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="47426-129">Note the smart-tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
2.  <span data-ttu-id="47426-130">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="47426-130">Click the smart-tag glyph.</span></span> <span data-ttu-id="47426-131">在出现旁边标志符号的快捷菜单，选择**添加选项卡**项。</span><span class="sxs-lookup"><span data-stu-id="47426-131">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="47426-132">观察新的选项卡页添加到<xref:System.Windows.Forms.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="47426-132">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
3.  <span data-ttu-id="47426-133">拖动<xref:System.Windows.Forms.TableLayoutPanel>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="47426-133">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="47426-134">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="47426-134">Click the smart-tag glyph.</span></span> <span data-ttu-id="47426-135">在出现旁边标志符号的快捷菜单，选择**添加列**项。</span><span class="sxs-lookup"><span data-stu-id="47426-135">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="47426-136">观察新列添加到<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="47426-136">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
5.  <span data-ttu-id="47426-137">拖动<xref:System.Windows.Forms.SplitContainer>控件从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="47426-137">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>  
  
6.  <span data-ttu-id="47426-138">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="47426-138">Click the smart-tag glyph.</span></span> <span data-ttu-id="47426-139">在出现旁边标志符号的快捷菜单，选择**水平拆分器方向**项。</span><span class="sxs-lookup"><span data-stu-id="47426-139">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="47426-140">注意，<xref:System.Windows.Forms.SplitContainer>控件的拆分栏现在处于水平放置。</span><span class="sxs-lookup"><span data-stu-id="47426-140">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47426-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="47426-141">See Also</span></span>  
 <xref:System.Windows.Forms.TextBox>  
 <xref:System.Windows.Forms.TabControl>  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.ComponentModel.Design.DesignerActionList>  
 [<span data-ttu-id="47426-142">演练： 将智能标记添加到 Windows 窗体组件</span><span class="sxs-lookup"><span data-stu-id="47426-142">Walkthrough: Adding Smart Tags to a Windows Forms Component</span></span>](http://msdn.microsoft.com/library/a6814169-fa7d-4527-808c-637ca5c95f63)
