---
title: 如何：在 Windows 窗体上创建 Windows 资源管理器样式的界面
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 34a5cd735c350688d9e83003806668e213932c85
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960625"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a><span data-ttu-id="113c7-102">如何：在 Windows 窗体上创建 Windows 资源管理器样式的界面</span><span class="sxs-lookup"><span data-stu-id="113c7-102">How to: Create a Windows Explorer–Style Interface on a Windows Form</span></span>
<span data-ttu-id="113c7-103">Windows 资源管理器是应用程序的一个常见用户界面选项, 因为它已做好了准备。</span><span class="sxs-lookup"><span data-stu-id="113c7-103">Windows Explorer is a common user-interface choice for applications because of its ready familiarity.</span></span>

 <span data-ttu-id="113c7-104">Windows 资源管理器本质<xref:System.Windows.Forms.TreeView>上是控件<xref:System.Windows.Forms.ListView>和控件在单独的面板上。</span><span class="sxs-lookup"><span data-stu-id="113c7-104">Windows Explorer is, essentially, a <xref:System.Windows.Forms.TreeView> control and a <xref:System.Windows.Forms.ListView> control on separate panels.</span></span> <span data-ttu-id="113c7-105">可以通过拆分器调整面板的大小。</span><span class="sxs-lookup"><span data-stu-id="113c7-105">The panels are made resizable by a splitter.</span></span> <span data-ttu-id="113c7-106">这种控件排列对于显示和浏览信息非常有效。</span><span class="sxs-lookup"><span data-stu-id="113c7-106">This arrangement of controls is very effective for displaying and browsing information.</span></span>

 <span data-ttu-id="113c7-107">以下步骤演示如何在类似 Windows 资源管理器的窗体中排列控件。</span><span class="sxs-lookup"><span data-stu-id="113c7-107">The following steps show how to arrange controls in a Windows Explorer-like form.</span></span> <span data-ttu-id="113c7-108">它们不显示如何添加 Windows 资源管理器应用程序的文件浏览功能。</span><span class="sxs-lookup"><span data-stu-id="113c7-108">They do not show how to add the file-browsing functionality of the Windows Explorer application.</span></span>

## <a name="to-create-a-windows-explorer-style-windows-form"></a><span data-ttu-id="113c7-109">创建 Windows 资源管理器样式的 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="113c7-109">To create a Windows Explorer-style Windows Form</span></span>

1. <span data-ttu-id="113c7-110">创建新的 Windows 应用程序项目 **(文件** > **新** > **项目** > **视觉C#对象**或**Visual Basic** > **经典桌面** >  **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="113c7-110">Create a new Windows Application project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

2. <span data-ttu-id="113c7-111">从**工具箱**:</span><span class="sxs-lookup"><span data-stu-id="113c7-111">From the **Toolbox**:</span></span>

    1. <span data-ttu-id="113c7-112"><xref:System.Windows.Forms.SplitContainer>将控件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="113c7-112">Drag a <xref:System.Windows.Forms.SplitContainer> control onto your form.</span></span>

    2. <span data-ttu-id="113c7-113">将控件拖动到**SplitterPanel1** ( <xref:System.Windows.Forms.SplitContainer>控件的面板中标记为**Panel1**)。 <xref:System.Windows.Forms.TreeView></span><span class="sxs-lookup"><span data-stu-id="113c7-113">Drag a <xref:System.Windows.Forms.TreeView> control into **SplitterPanel1** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel1**).</span></span>

    3. <span data-ttu-id="113c7-114">将控件拖动到**SplitterPanel2** ( <xref:System.Windows.Forms.SplitContainer>控件的面板中标记为**Panel2**)。 <xref:System.Windows.Forms.ListView></span><span class="sxs-lookup"><span data-stu-id="113c7-114">Drag a <xref:System.Windows.Forms.ListView> control into **SplitterPanel2** (the panel of the <xref:System.Windows.Forms.SplitContainer> control marked **Panel2**).</span></span>

3. <span data-ttu-id="113c7-115">按住 CTRL 键并依次单击所有三个控件以将其选中。</span><span class="sxs-lookup"><span data-stu-id="113c7-115">Select all three controls by pressing the CTRL key and clicking them in turn.</span></span> <span data-ttu-id="113c7-116">选择<xref:System.Windows.Forms.SplitContainer>控件时, 请单击拆分条, 而不是面板。</span><span class="sxs-lookup"><span data-stu-id="113c7-116">When you select the <xref:System.Windows.Forms.SplitContainer> control, click the splitter bar, rather than the panels.</span></span>

    > [!NOTE]
    > <span data-ttu-id="113c7-117">不要使用 "**编辑**" 菜单上的 "**全选**" 命令。</span><span class="sxs-lookup"><span data-stu-id="113c7-117">Do not use the **Select All** command on the **Edit** menu.</span></span> <span data-ttu-id="113c7-118">如果这样做, 下一步中所需的属性将不会显示在 "**属性**" 窗口中。</span><span class="sxs-lookup"><span data-stu-id="113c7-118">If you do so, the property needed in the next step will not appear in the **Properties** window.</span></span>

4. <span data-ttu-id="113c7-119">在“属性” 窗口中，将 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="113c7-119">In the **Properties** window, set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="113c7-120">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="113c7-120">Press F5 to run the application.</span></span>

     <span data-ttu-id="113c7-121">该窗体显示两个部分的用户界面, 与 Windows 资源管理器类似。</span><span class="sxs-lookup"><span data-stu-id="113c7-121">The form displays a two-part user interface, similar to that of the Windows Explorer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="113c7-122">拖动拆分器时, 面板会调整其自身大小。</span><span class="sxs-lookup"><span data-stu-id="113c7-122">When you drag the splitter, the panels resize themselves.</span></span>

## <a name="see-also"></a><span data-ttu-id="113c7-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="113c7-123">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="113c7-124">如何：使用 Windows 窗体创建多窗格用户界面</span><span class="sxs-lookup"><span data-stu-id="113c7-124">How to: Create a Multipane User Interface with Windows Forms</span></span>](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [<span data-ttu-id="113c7-125">如何：定义拆分窗口中的大小调整和定位行为</span><span class="sxs-lookup"><span data-stu-id="113c7-125">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [<span data-ttu-id="113c7-126">如何：水平拆分窗口</span><span class="sxs-lookup"><span data-stu-id="113c7-126">How to: Split a Window Horizontally</span></span>](how-to-split-a-window-horizontally.md)
- [<span data-ttu-id="113c7-127">SplitContainer 控件</span><span class="sxs-lookup"><span data-stu-id="113c7-127">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
