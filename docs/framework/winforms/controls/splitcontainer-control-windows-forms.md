---
title: SplitContainer 控件（Windows 窗体）
ms.date: 03/30/2017
helpviewer_keywords:
- splitter windows
- SplitContainer control [Windows Forms]
ms.assetid: 2e36f17f-5c39-4fb4-bb09-7ce3ef823402
ms.openlocfilehash: 63b1a4b9b2483d017a686819573f91744d8a565a
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518802"
---
# <a name="splitcontainer-control-windows-forms"></a><span data-ttu-id="54c36-102">SplitContainer 控件（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="54c36-102">SplitContainer Control (Windows Forms)</span></span>
<span data-ttu-id="54c36-103">Windows 窗体 `SplitContainer` 控件可视为一个复合控件；它是由可移动条隔开的两个面板。</span><span class="sxs-lookup"><span data-stu-id="54c36-103">The Windows Forms `SplitContainer` control can be thought of as a composite; it is two panels separated by a movable bar.</span></span> <span data-ttu-id="54c36-104">当鼠标指针位于条上方时，指针将改变形状以表示条可移动。</span><span class="sxs-lookup"><span data-stu-id="54c36-104">When the mouse pointer is over the bar, the pointer changes shape to show that the bar is movable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54c36-105">在中**工具箱**，则此控件替代<xref:System.Windows.Forms.Splitter>以前版本的 Visual Studio 中的控件。</span><span class="sxs-lookup"><span data-stu-id="54c36-105">In the **Toolbox**, this control replaces the <xref:System.Windows.Forms.Splitter> control that was there in the previous version of Visual Studio.</span></span> <span data-ttu-id="54c36-106">相较于 <xref:System.Windows.Forms.Splitter> 控件，优先选择 `SplitContainer` 控件。</span><span class="sxs-lookup"><span data-stu-id="54c36-106">The `SplitContainer` control is much preferred over the <xref:System.Windows.Forms.Splitter> control.</span></span> <span data-ttu-id="54c36-107"><xref:System.Windows.Forms.Splitter> 类仍包含在 .NET Framework 中，以便与现有应用程序兼容，但我们强烈建议为新项目使用 `SplitContainer` 控件。</span><span class="sxs-lookup"><span data-stu-id="54c36-107">The <xref:System.Windows.Forms.Splitter> class is still included in the .NET Framework for compatibility with existing applications, but we strongly encourage you to use the `SplitContainer` control for new projects.</span></span>  
  
 <span data-ttu-id="54c36-108">`SplitContainer` 控件允许你创建复杂的用户界面；通常情况下，在一个面板中的选择将决定显示在另一个面板中的对象。</span><span class="sxs-lookup"><span data-stu-id="54c36-108">The `SplitContainer` control lets you create complex user interfaces; often, a selection in one panel determines what objects are shown in the other panel.</span></span> <span data-ttu-id="54c36-109">这种安排对于显示和浏览信息非常有效。</span><span class="sxs-lookup"><span data-stu-id="54c36-109">This arrangement is very effective for displaying and browsing information.</span></span> <span data-ttu-id="54c36-110">拥有两个面板使你能够在区域、条或“拆分器”中聚合信息，使用户可轻松地调整面板大小。</span><span class="sxs-lookup"><span data-stu-id="54c36-110">Having two panels allow you to aggregate information in areas, and the bar, or "splitter," makes it easy for users to resize the panels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="54c36-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="54c36-111">In This Section</span></span>  
 [<span data-ttu-id="54c36-112">SplitContainer 控件概述</span><span class="sxs-lookup"><span data-stu-id="54c36-112">SplitContainer Control Overview</span></span>](../../../../docs/framework/winforms/controls/splitcontainer-control-overview-windows-forms.md)  
 <span data-ttu-id="54c36-113">介绍 `SplitContainer` 控件并描述常用的属性、方法和事件。</span><span class="sxs-lookup"><span data-stu-id="54c36-113">Introduces the `SplitContainer` control and describes the commonly used properties, methods, and events.</span></span>  
  
 [<span data-ttu-id="54c36-114">如何：定义拆分窗口中的重设大小和定位行为</span><span class="sxs-lookup"><span data-stu-id="54c36-114">How to: Define Resize and Positioning Behavior in a Split Window</span></span>](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 <span data-ttu-id="54c36-115">描述如何在 `SplitContainer` 控件中控制拆分器。</span><span class="sxs-lookup"><span data-stu-id="54c36-115">Describes how to control the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="54c36-116">如何：水平拆分窗口</span><span class="sxs-lookup"><span data-stu-id="54c36-116">How to: Split a Window Horizontally</span></span>](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 <span data-ttu-id="54c36-117">描述如何在 `SplitContainer` 控件中控制拆分器的方向。</span><span class="sxs-lookup"><span data-stu-id="54c36-117">Describes how to control the orientation of the splitter within the `SplitContainer` control.</span></span>  
  
 [<span data-ttu-id="54c36-118">如何：使用 Windows 窗体创建多窗格用户界面</span><span class="sxs-lookup"><span data-stu-id="54c36-118">How to: Create a Multipane User Interface with Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 <span data-ttu-id="54c36-119">创建一个与 Microsoft Outlook 中使用的多窗格用户界面相似的多窗格用户界面。</span><span class="sxs-lookup"><span data-stu-id="54c36-119">Creates a multi-pane user interface that is similar to the one used in Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="54c36-120">另请参阅[如何： 拆分窗口水平使用设计器](how-to-split-a-window-horizontally-using-the-designer.md)，[如何： 在 Windows 窗体上创建一个 Windows 资源管理器样式界面](https://msdn.microsoft.com/library/zh2fe5a5\(v=vs.110\))，[如何： 创建一个具有用户界面，Multipane使用设计器的 Windows 窗体](create-a-multipane-user-interface-with-wf-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="54c36-120">Also see [How to: Split a Window Horizontally Using the Designer](how-to-split-a-window-horizontally-using-the-designer.md), [How to: Create a Windows Explorer–Style Interface on a Windows Form](https://msdn.microsoft.com/library/zh2fe5a5\(v=vs.110\)), [How to: Create a Multipane User Interface with Windows Forms Using the Designer](create-a-multipane-user-interface-with-wf-using-the-designer.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="54c36-121">参考</span><span class="sxs-lookup"><span data-stu-id="54c36-121">Reference</span></span>  
 <span data-ttu-id="54c36-122"><xref:System.Windows.Forms.SplitContainer> 类</span><span class="sxs-lookup"><span data-stu-id="54c36-122"><xref:System.Windows.Forms.SplitContainer> class</span></span>  
 <span data-ttu-id="54c36-123">对此类进行描述，并提供指向其所有成员的链接。</span><span class="sxs-lookup"><span data-stu-id="54c36-123">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="54c36-124">相关章节</span><span class="sxs-lookup"><span data-stu-id="54c36-124">Related Sections</span></span>  
 [<span data-ttu-id="54c36-125">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="54c36-125">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 <span data-ttu-id="54c36-126">提供指向有关专用于使用 Windows 窗体的控件的主题链接。</span><span class="sxs-lookup"><span data-stu-id="54c36-126">Provides links to topics about the controls designed specifically to work with Windows Forms.</span></span>  
  
 [<span data-ttu-id="54c36-127">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="54c36-127">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="54c36-128">提供 Windows 窗体控件的完整列表，附带其使用情况相关信息的链接。</span><span class="sxs-lookup"><span data-stu-id="54c36-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
