---
title: 如何：定义使用设计器的工具栏按钮的图标
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: 2099738d5b666aa305d678c962c0b203d3ab67b2
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717734"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="b0d32-102">如何：定义使用设计器的工具栏按钮的图标</span><span class="sxs-lookup"><span data-stu-id="b0d32-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="b0d32-103">
  <xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="b0d32-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="b0d32-104"><xref:System.Windows.Forms.ToolBar> 按钮是可以由用户显示其中方便识别的图标。</span><span class="sxs-lookup"><span data-stu-id="b0d32-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="b0d32-105">这通过添加到图像<xref:System.Windows.Forms.ImageList>组件并将其与<xref:System.Windows.Forms.ToolBar>控件。</span><span class="sxs-lookup"><span data-stu-id="b0d32-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
 <span data-ttu-id="b0d32-106">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.ToolBar>控件和一个<xref:System.Windows.Forms.ImageList>组件。</span><span class="sxs-lookup"><span data-stu-id="b0d32-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="b0d32-107">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d32-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0d32-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="b0d32-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b0d32-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="b0d32-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b0d32-110">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="b0d32-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="b0d32-111">若要在设计时设置工具栏按钮的图标</span><span class="sxs-lookup"><span data-stu-id="b0d32-111">To set an icon for a toolbar button at design time</span></span>  
  
1.  <span data-ttu-id="b0d32-112">将映像添加到<xref:System.Windows.Forms.ImageList>组件。</span><span class="sxs-lookup"><span data-stu-id="b0d32-112">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="b0d32-113">有关详细信息，请参阅[如何：添加或删除 ImageList 图像与设计器](how-to-add-or-remove-imagelist-images-with-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="b0d32-113">For more information, see [How to: Add or Remove ImageList Images with the Designer](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>  
  
2.  <span data-ttu-id="b0d32-114">选择<xref:System.Windows.Forms.ToolBar>窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="b0d32-114">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>  
  
3.  <span data-ttu-id="b0d32-115">在中**属性**窗口中，将<xref:System.Windows.Forms.ToolBar>控件的<xref:System.Windows.Forms.ToolBar.ImageList%2A>属性设置为<xref:System.Windows.Forms.ImageList>组件。</span><span class="sxs-lookup"><span data-stu-id="b0d32-115">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
4.  <span data-ttu-id="b0d32-116">单击<xref:System.Windows.Forms.ToolBar>控件的<xref:System.Windows.Forms.ToolBar.Buttons%2A>属性来选择它，然后单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以打开**工具栏按钮集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="b0d32-116">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **ToolBarButton Collection Editor**.</span></span>  
  
5.  <span data-ttu-id="b0d32-117">使用**外**按钮以将按钮添加到<xref:System.Windows.Forms.ToolBar>控件。</span><span class="sxs-lookup"><span data-stu-id="b0d32-117">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
6.  <span data-ttu-id="b0d32-118">中**属性**的右侧窗格中显示的窗口**工具栏按钮集合编辑器**，将<xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A>到其中一个的值在列表中，每个工具栏按钮的属性的从映像添加到绘制<xref:System.Windows.Forms.ImageList>组件。</span><span class="sxs-lookup"><span data-stu-id="b0d32-118">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0d32-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0d32-119">See also</span></span>
- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="b0d32-120">如何：触发工具栏按钮的菜单事件</span><span class="sxs-lookup"><span data-stu-id="b0d32-120">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="b0d32-121">ToolBar 控件</span><span class="sxs-lookup"><span data-stu-id="b0d32-121">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="b0d32-122">ImageList 组件</span><span class="sxs-lookup"><span data-stu-id="b0d32-122">ImageList Component</span></span>](imagelist-component-windows-forms.md)
