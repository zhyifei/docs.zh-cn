---
title: 如何：使用设计器定义工具栏按钮的图标
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: f26e21d824420fc4ff0480de21f260309c5c2e11
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856603"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="3c5f7-102">如何：使用设计器定义工具栏按钮的图标</span><span class="sxs-lookup"><span data-stu-id="3c5f7-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="3c5f7-103"><xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="3c5f7-104"><xref:System.Windows.Forms.ToolBar> 按钮是可以由用户显示其中方便识别的图标。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="3c5f7-105">这通过添加到图像<xref:System.Windows.Forms.ImageList>组件并将其与<xref:System.Windows.Forms.ToolBar>控件。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
 <span data-ttu-id="3c5f7-106">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.ToolBar>控件和一个<xref:System.Windows.Forms.ImageList>组件。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="3c5f7-107">有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)并[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-107">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c5f7-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3c5f7-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3c5f7-110">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="3c5f7-111">若要在设计时设置工具栏按钮的图标</span><span class="sxs-lookup"><span data-stu-id="3c5f7-111">To set an icon for a toolbar button at design time</span></span>  
  
1.  <span data-ttu-id="3c5f7-112">将映像添加到<xref:System.Windows.Forms.ImageList>组件。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-112">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="3c5f7-113">有关详细信息，请参阅[如何： 添加或删除 ImageList 图像与设计器](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-113">For more information, see [How to: Add or Remove ImageList Images with the Designer](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>  
  
2.  <span data-ttu-id="3c5f7-114">选择<xref:System.Windows.Forms.ToolBar>窗体上的控件。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-114">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>  
  
3.  <span data-ttu-id="3c5f7-115">在中**属性**窗口中，将<xref:System.Windows.Forms.ToolBar>控件的<xref:System.Windows.Forms.ToolBar.ImageList%2A>属性设置为<xref:System.Windows.Forms.ImageList>组件。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-115">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
4.  <span data-ttu-id="3c5f7-116">单击<xref:System.Windows.Forms.ToolBar>控件的<xref:System.Windows.Forms.ToolBar.Buttons%2A>属性来选择它，然后单击省略号 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮以打开**工具栏按钮集合编辑器**。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-116">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **ToolBarButton Collection Editor**.</span></span>  
  
5.  <span data-ttu-id="3c5f7-117">使用**外**按钮以将按钮添加到<xref:System.Windows.Forms.ToolBar>控件。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-117">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
6.  <span data-ttu-id="3c5f7-118">中**属性**的右侧窗格中显示的窗口**工具栏按钮集合编辑器**，将<xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A>到其中一个的值在列表中，每个工具栏按钮的属性的从映像添加到绘制<xref:System.Windows.Forms.ImageList>组件。</span><span class="sxs-lookup"><span data-stu-id="3c5f7-118">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c5f7-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c5f7-119">See Also</span></span>  
 <xref:System.Windows.Forms.ToolBar>  
 [<span data-ttu-id="3c5f7-120">如何：触发工具栏按钮的菜单事件</span><span class="sxs-lookup"><span data-stu-id="3c5f7-120">How to: Trigger Menu Events for Toolbar Buttons</span></span>](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [<span data-ttu-id="3c5f7-121">ToolBar 控件</span><span class="sxs-lookup"><span data-stu-id="3c5f7-121">ToolBar Control</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [<span data-ttu-id="3c5f7-122">ImageList 组件</span><span class="sxs-lookup"><span data-stu-id="3c5f7-122">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
