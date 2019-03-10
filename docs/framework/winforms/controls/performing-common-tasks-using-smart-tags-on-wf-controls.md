---
title: 演练：使用 Windows 窗体控件上的智能标记执行常规任务
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
ms.openlocfilehash: 2805ebc66be5908c333e9a5db41076518ad77c1a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705852"
---
# <a name="walkthrough-performing-common-tasks-using-smart-tags-on-windows-forms-controls"></a><span data-ttu-id="b155a-102">演练：使用 Windows 窗体控件上的智能标记执行常规任务</span><span class="sxs-lookup"><span data-stu-id="b155a-102">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>
<span data-ttu-id="b155a-103">在 Windows 窗体应用程序构造窗体和控件，如有需要反复执行的许多任务。</span><span class="sxs-lookup"><span data-stu-id="b155a-103">As you construct forms and controls for your Windows Forms application, there are many tasks you will perform repeatedly.</span></span> <span data-ttu-id="b155a-104">以下是一些你将遇到的执行常用任务：</span><span class="sxs-lookup"><span data-stu-id="b155a-104">These are some of the commonly performed tasks you will encounter:</span></span>  
  
-   <span data-ttu-id="b155a-105">添加或删除选项卡上<xref:System.Windows.Forms.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="b155a-105">Adding or removing a tab on a <xref:System.Windows.Forms.TabControl>.</span></span>  
  
-   <span data-ttu-id="b155a-106">将控件停靠到其父级。</span><span class="sxs-lookup"><span data-stu-id="b155a-106">Docking a control to its parent.</span></span>  
  
-   <span data-ttu-id="b155a-107">更改的方向<xref:System.Windows.Forms.SplitContainer>控件。</span><span class="sxs-lookup"><span data-stu-id="b155a-107">Changing the orientation of a <xref:System.Windows.Forms.SplitContainer> control.</span></span>  
  
 <span data-ttu-id="b155a-108">若要加快开发速度，许多控件提供智能标记，可用于在设计时执行常见任务，比如在一个独立的上下文相关菜单。</span><span class="sxs-lookup"><span data-stu-id="b155a-108">To speed development, many controls offer smart tags, which are context-sensitive menus that allow you to perform common tasks like these in a single gesture at design time.</span></span> <span data-ttu-id="b155a-109">这些任务称作*智能标记谓词*。</span><span class="sxs-lookup"><span data-stu-id="b155a-109">These tasks are called *smart-tag verbs*.</span></span>  
  
 <span data-ttu-id="b155a-110">智能标记的设计器中的整个生存期保持附加到一个控件实例，并始终处于可用状态。</span><span class="sxs-lookup"><span data-stu-id="b155a-110">Smart tags remain attached to a control instance for its lifetime in the designer and are always available.</span></span>  
  
 <span data-ttu-id="b155a-111">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="b155a-111">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="b155a-112">创建 Windows 窗体项目</span><span class="sxs-lookup"><span data-stu-id="b155a-112">Creating a Windows Forms project</span></span>  
  
-   <span data-ttu-id="b155a-113">使用智能标记</span><span class="sxs-lookup"><span data-stu-id="b155a-113">Using smart tags</span></span>  
  
-   <span data-ttu-id="b155a-114">启用和禁用智能标记</span><span class="sxs-lookup"><span data-stu-id="b155a-114">Enabling and Disabling Smart Tags</span></span>  
  
 <span data-ttu-id="b155a-115">完成上述操作后，你将会了解这些重要布局功能所发挥的作用。</span><span class="sxs-lookup"><span data-stu-id="b155a-115">When you are finished, you will have an understanding of the role played by these important layout features.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b155a-116">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="b155a-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b155a-117">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="b155a-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b155a-118">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="b155a-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="b155a-119">创建项目</span><span class="sxs-lookup"><span data-stu-id="b155a-119">Creating the Project</span></span>  
 <span data-ttu-id="b155a-120">第一步是创建项目并设置窗体。</span><span class="sxs-lookup"><span data-stu-id="b155a-120">The first step is to create the project and set up the form.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="b155a-121">要创建项目</span><span class="sxs-lookup"><span data-stu-id="b155a-121">To create the project</span></span>  
  
1.  <span data-ttu-id="b155a-122">创建一个名为"SmartTagsExample"的基于 Windows 的应用程序项目 (**文件** > **新建** > **项目** >  **Visual C#** 或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="b155a-122">Create a Windows-based application project called "SmartTagsExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2.  <span data-ttu-id="b155a-123">选择中的窗体**Windows 窗体设计器**。</span><span class="sxs-lookup"><span data-stu-id="b155a-123">Select the form in the **Windows Forms Designer**.</span></span>  
  
## <a name="using-smart-tags"></a><span data-ttu-id="b155a-124">使用智能标记</span><span class="sxs-lookup"><span data-stu-id="b155a-124">Using Smart Tags</span></span>  
 <span data-ttu-id="b155a-125">智能标记上将其提供的控件的设计时将始终可用。</span><span class="sxs-lookup"><span data-stu-id="b155a-125">Smart tags are always available at design time on controls that offer them.</span></span>  
  
#### <a name="to-use-smart-tags"></a><span data-ttu-id="b155a-126">若要使用智能标记</span><span class="sxs-lookup"><span data-stu-id="b155a-126">To use smart tags</span></span>  
  
1.  <span data-ttu-id="b155a-127">拖动<xref:System.Windows.Forms.TabControl>从**工具箱**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="b155a-127">Drag a <xref:System.Windows.Forms.TabControl> from the **Toolbox** onto your form.</span></span> <span data-ttu-id="b155a-128">请注意的智能标记标志符号 (![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 旁边的显示<xref:System.Windows.Forms.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="b155a-128">Note the smart-tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) that appears on the side of the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
2.  <span data-ttu-id="b155a-129">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="b155a-129">Click the smart-tag glyph.</span></span> <span data-ttu-id="b155a-130">在标志符号旁边显示的快捷菜单，选择**添加选项卡**项。</span><span class="sxs-lookup"><span data-stu-id="b155a-130">In the shortcut menu that appears next to the glyph, select the **Add Tab** item.</span></span> <span data-ttu-id="b155a-131">观察到的新选项卡页添加到<xref:System.Windows.Forms.TabControl>。</span><span class="sxs-lookup"><span data-stu-id="b155a-131">Observe that a new tab page is added to the <xref:System.Windows.Forms.TabControl>.</span></span>  
  
3.  <span data-ttu-id="b155a-132">从 <xref:System.Windows.Forms.TableLayoutPanel> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="b155a-132">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>  
  
4.  <span data-ttu-id="b155a-133">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="b155a-133">Click the smart-tag glyph.</span></span> <span data-ttu-id="b155a-134">在标志符号旁边显示的快捷菜单，选择**添加列**项。</span><span class="sxs-lookup"><span data-stu-id="b155a-134">In the shortcut menu that appears next to the glyph, select the **Add Column** item.</span></span> <span data-ttu-id="b155a-135">观察新列添加到<xref:System.Windows.Forms.TableLayoutPanel>控件。</span><span class="sxs-lookup"><span data-stu-id="b155a-135">Observe that a new column is added to the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
5.  <span data-ttu-id="b155a-136">从 <xref:System.Windows.Forms.SplitContainer> “工具箱” **将** 控件拖到你的窗体上。</span><span class="sxs-lookup"><span data-stu-id="b155a-136">Drag a <xref:System.Windows.Forms.SplitContainer> control from the **Toolbox** onto your form.</span></span>  
  
6.  <span data-ttu-id="b155a-137">单击智能标记标志符号。</span><span class="sxs-lookup"><span data-stu-id="b155a-137">Click the smart-tag glyph.</span></span> <span data-ttu-id="b155a-138">在标志符号旁边显示的快捷菜单，选择**水平拆分器方向**项。</span><span class="sxs-lookup"><span data-stu-id="b155a-138">In the shortcut menu that appears next to the glyph, select the **Horizontal splitter orientation** item.</span></span> <span data-ttu-id="b155a-139">观察<xref:System.Windows.Forms.SplitContainer>现在是控件的分隔条水平。</span><span class="sxs-lookup"><span data-stu-id="b155a-139">Observe that the <xref:System.Windows.Forms.SplitContainer> control's splitter bar is now oriented horizontally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b155a-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="b155a-140">See also</span></span>
- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
- <span data-ttu-id="b155a-141">[演练：向 Windows 窗体组件添加智能标记](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="b155a-141">[Walkthrough: Adding Smart Tags to a Windows Forms Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171829(v=vs.120))</span></span>
