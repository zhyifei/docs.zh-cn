---
title: "如何：在 Windows 窗体上创建 Windows 资源管理器样式的界面"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26a91052586843f87c04adf1a31025991d9973db
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="27469-102">如何：在 Windows 窗体上创建 Windows 资源管理器样式的界面</span><span class="sxs-lookup"><span data-stu-id="27469-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="27469-103">Windows 资源管理器因其比较熟悉的应用程序的常见用户界面选择。</span><span class="sxs-lookup"><span data-stu-id="27469-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>  
  
 <span data-ttu-id="27469-104">Windows 资源管理器是，从根本上来说，<xref:System.Windows.Forms.TreeView>控件和<xref:System.Windows.Forms.ListView>在不同面板上的控件。</span><span class="sxs-lookup"><span data-stu-id="27469-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="27469-105">可调整大小面板进行的拆分。</span><span class="sxs-lookup"><span data-stu-id="27469-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="27469-106">此类控件排列是对于显示和浏览信息非常有效。</span><span class="sxs-lookup"><span data-stu-id="27469-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>  
  
 <span data-ttu-id="27469-107">以下步骤显示如何排列 Windows 资源管理器类似的窗体中的控件。</span><span class="sxs-lookup"><span data-stu-id="27469-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="27469-108">它们不显示如何添加的 Windows 资源管理器应用程序的文件浏览功能。</span><span class="sxs-lookup"><span data-stu-id="27469-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="27469-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="27469-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="27469-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="27469-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="27469-111">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="27469-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="27469-112">若要创建 Windows 资源管理器样式 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="27469-112">To create a Windows Explorer-style Windows Form</span></span>  
  
1.  <span data-ttu-id="27469-113">创建新的 Windows 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="27469-113">Create a new Windows Application project.</span></span> <span data-ttu-id="27469-114">有关详细信息，请参阅[如何：创建一个 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)。</span><span class="sxs-lookup"><span data-stu-id="27469-114">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="27469-115">从**工具箱**:</span><span class="sxs-lookup"><span data-stu-id="27469-115">From the **Toolbox**:</span></span>  
  
    1.  <span data-ttu-id="27469-116">拖动<xref:System.Windows.Forms.SplitContainer>拖动到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="27469-116">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>  
  
    2.  <span data-ttu-id="27469-117">拖动<xref:System.Windows.Forms.TreeView>控制**SplitterPanel1** (的面板<xref:System.Windows.Forms.SplitContainer>控件标记**Panel1**)。</span><span class="sxs-lookup"><span data-stu-id="27469-117">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>  
  
    3.  <span data-ttu-id="27469-118">拖动<xref:System.Windows.Forms.ListView>控制**SplitterPanel2** (的面板<xref:System.Windows.Forms.SplitContainer>控件标记**面板 2**)。</span><span class="sxs-lookup"><span data-stu-id="27469-118">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>  
  
3.  <span data-ttu-id="27469-119">通过按住 CTRL 键并单击它们反过来选择所有三个控件。</span><span class="sxs-lookup"><span data-stu-id="27469-119">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="27469-120">当选择<xref:System.Windows.Forms.SplitContainer>控件中，单击拆分栏中，而不是面板。</span><span class="sxs-lookup"><span data-stu-id="27469-120">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27469-121">不要使用**选择所有**命令**编辑**菜单。</span><span class="sxs-lookup"><span data-stu-id="27469-121">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="27469-122">如果这样做，在下一步所需的属性不会出现在**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="27469-122">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>  
  
4.  <span data-ttu-id="27469-123">在**属性**窗口中，设置<xref:System.Windows.Forms.SplitContainer.Dock%2A>属性<xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="27469-123">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5.  <span data-ttu-id="27469-124">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="27469-124">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="27469-125">窗体显示两个部分构成用户界面，类似于 Windows 资源管理器。</span><span class="sxs-lookup"><span data-stu-id="27469-125">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27469-126">当拆分器拖动时，面板将调整大小。</span><span class="sxs-lookup"><span data-stu-id="27469-126">When you drag the splitter, the panels resize themselves.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27469-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="27469-127">See Also</span></span>  
 <xref:System.Windows.Forms.SplitContainer>  
 [<span data-ttu-id="27469-128">如何：使用 Windows 窗体创建多窗格用户界面</span><span class="sxs-lookup"><span data-stu-id="27469-128">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 [<span data-ttu-id="27469-129">如何：定义拆分窗口中的重设大小和定位行为</span><span class="sxs-lookup"><span data-stu-id="27469-129">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 [<span data-ttu-id="27469-130">如何：水平拆分窗口</span><span class="sxs-lookup"><span data-stu-id="27469-130">How to: Split a Window Horizontally</span></span>](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 [<span data-ttu-id="27469-131">SplitContainer 控件</span><span class="sxs-lookup"><span data-stu-id="27469-131">SplitContainer Control</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
