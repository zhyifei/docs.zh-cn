---
title: 如何：在 Windows 窗体上创建 Windows 资源管理器样式的界面
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 578fdf8e24803db0e0d80ff22aa5cebebbc2663e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64616002"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="c00ef-102">如何：在 Windows 窗体上创建 Windows 资源管理器样式的界面</span><span class="sxs-lookup"><span data-stu-id="c00ef-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="c00ef-103">Windows 资源管理器是由于其比较熟悉的应用程序的一个常见用户界面选择。</span><span class="sxs-lookup"><span data-stu-id="c00ef-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>  
  
 <span data-ttu-id="c00ef-104">从根本上来说，Windows 资源管理器是<xref:System.Windows.Forms.TreeView>控件和一个<xref:System.Windows.Forms.ListView>上单独的面板的控件。</span><span class="sxs-lookup"><span data-stu-id="c00ef-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="c00ef-105">通过拆分器，面板进行可调整大小。</span><span class="sxs-lookup"><span data-stu-id="c00ef-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="c00ef-106">此类控件排列是用于显示和浏览信息非常有效。</span><span class="sxs-lookup"><span data-stu-id="c00ef-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>  
  
 <span data-ttu-id="c00ef-107">以下步骤说明如何在 Windows 资源管理器类似的窗体中排列控件。</span><span class="sxs-lookup"><span data-stu-id="c00ef-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="c00ef-108">它们不显示如何添加 Windows 资源管理器应用程序的文件浏览功能。</span><span class="sxs-lookup"><span data-stu-id="c00ef-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c00ef-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="c00ef-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c00ef-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="c00ef-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c00ef-111">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="c00ef-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="c00ef-112">若要创建 Windows 资源管理器样式 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="c00ef-112">To create a Windows Explorer-style Windows Form</span></span>  
  
1. <span data-ttu-id="c00ef-113">创建新的 Windows 应用程序项目 (**文件** > **新建** > **项目** > **Visual C#** 或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="c00ef-113">Create a new Windows Application project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
2. <span data-ttu-id="c00ef-114">从**工具箱**:</span><span class="sxs-lookup"><span data-stu-id="c00ef-114">From the **Toolbox**:</span></span>  
  
    1. <span data-ttu-id="c00ef-115">拖动<xref:System.Windows.Forms.SplitContainer>控件拖到窗体上的。</span><span class="sxs-lookup"><span data-stu-id="c00ef-115">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>  
  
    2. <span data-ttu-id="c00ef-116">拖动<xref:System.Windows.Forms.TreeView>控制**SplitterPanel1** (的面板<xref:System.Windows.Forms.SplitContainer>控制标记**Panel1**)。</span><span class="sxs-lookup"><span data-stu-id="c00ef-116">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>  
  
    3. <span data-ttu-id="c00ef-117">拖动<xref:System.Windows.Forms.ListView>控制**SplitterPanel2** (的面板<xref:System.Windows.Forms.SplitContainer>控制标记**Panel2**)。</span><span class="sxs-lookup"><span data-stu-id="c00ef-117">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>  
  
3. <span data-ttu-id="c00ef-118">通过按 CTRL 键并依次单击选择所有三个控件。</span><span class="sxs-lookup"><span data-stu-id="c00ef-118">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="c00ef-119">当选择<xref:System.Windows.Forms.SplitContainer>控件中，单击拆分条中，而不是面板。</span><span class="sxs-lookup"><span data-stu-id="c00ef-119">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c00ef-120">不要使用**全**命令**编辑**菜单。</span><span class="sxs-lookup"><span data-stu-id="c00ef-120">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="c00ef-121">如果这样做下, 一步中所需的属性不会出现在**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="c00ef-121">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>  
  
4. <span data-ttu-id="c00ef-122">在“属性”  窗口中，将 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="c00ef-122">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5. <span data-ttu-id="c00ef-123">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c00ef-123">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="c00ef-124">窗体显示类似于在 Windows 资源管理器的两部分组成用户界面。</span><span class="sxs-lookup"><span data-stu-id="c00ef-124">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c00ef-125">当拖动拆分器时，面板调整自身大小。</span><span class="sxs-lookup"><span data-stu-id="c00ef-125">When you drag the splitter, the panels resize themselves.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c00ef-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="c00ef-126">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="c00ef-127">如何：用 Windows 窗体创建多窗格用户界面</span><span class="sxs-lookup"><span data-stu-id="c00ef-127">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [<span data-ttu-id="c00ef-128">如何：定义大小调整和拆分窗口中定位行为</span><span class="sxs-lookup"><span data-stu-id="c00ef-128">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [<span data-ttu-id="c00ef-129">如何：水平拆分窗口</span><span class="sxs-lookup"><span data-stu-id="c00ef-129">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)
- [<span data-ttu-id="c00ef-130">SplitContainer 控件</span><span class="sxs-lookup"><span data-stu-id="c00ef-130">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
