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
ms.openlocfilehash: 5de7645ecbf2123df849046a152643cd629b4898
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038227"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a><span data-ttu-id="55013-102">如何：使用设计器定义工具栏按钮的图标</span><span class="sxs-lookup"><span data-stu-id="55013-102">How to: Define an Icon for a ToolBar Button Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="55013-103"><xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="55013-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>

<span data-ttu-id="55013-104"><xref:System.Windows.Forms.ToolBar>按钮能够显示它们中的图标, 用户可以轻松识别。</span><span class="sxs-lookup"><span data-stu-id="55013-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="55013-105">这是通过向<xref:System.Windows.Forms.ImageList>组件添加图像并将其<xref:System.Windows.Forms.ToolBar>与控件相关联实现的。</span><span class="sxs-lookup"><span data-stu-id="55013-105">This is achieved through adding images to the <xref:System.Windows.Forms.ImageList> component and associating it with the <xref:System.Windows.Forms.ToolBar> control.</span></span>

<span data-ttu-id="55013-106">下面的过程需要一个**Windows 应用程序**项目, 该项目具有<xref:System.Windows.Forms.ToolBar>包含控件和<xref:System.Windows.Forms.ImageList>组件的窗体。</span><span class="sxs-lookup"><span data-stu-id="55013-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ToolBar> control and an <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="55013-107">有关设置此类项目的信息, 请参阅[如何:创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)以及[如何:将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="55013-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>


### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a><span data-ttu-id="55013-108">在设计时设置工具栏按钮的图标</span><span class="sxs-lookup"><span data-stu-id="55013-108">To set an icon for a toolbar button at design time</span></span>

1. <span data-ttu-id="55013-109">向<xref:System.Windows.Forms.ImageList>组件添加映像。</span><span class="sxs-lookup"><span data-stu-id="55013-109">Add images to the <xref:System.Windows.Forms.ImageList> component.</span></span> <span data-ttu-id="55013-110">有关详细信息，请参阅[如何：在设计器](how-to-add-or-remove-imagelist-images-with-the-designer.md)中添加或删除 ImageList 映像。</span><span class="sxs-lookup"><span data-stu-id="55013-110">For more information, see [How to: Add or Remove ImageList Images with the Designer](how-to-add-or-remove-imagelist-images-with-the-designer.md).</span></span>

2. <span data-ttu-id="55013-111">选择窗<xref:System.Windows.Forms.ToolBar>体上的控件。</span><span class="sxs-lookup"><span data-stu-id="55013-111">Select the <xref:System.Windows.Forms.ToolBar> control on your form.</span></span>

3. <span data-ttu-id="55013-112">在 "**属性**" 窗口中, <xref:System.Windows.Forms.ToolBar>将控件<xref:System.Windows.Forms.ToolBar.ImageList%2A> <xref:System.Windows.Forms.ImageList>的属性设置为组件。</span><span class="sxs-lookup"><span data-stu-id="55013-112">In the **Properties** window, set the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.ImageList%2A> property to the <xref:System.Windows.Forms.ImageList> component.</span></span>

4. <span data-ttu-id="55013-113"><xref:System.Windows.Forms.ToolBar.Buttons%2A> ![](./media/visual-studio-ellipsis-button.png)单击控件的属性以将其选中, 然后单击省略号 ("Visual Studio" 的属性窗口中的省略号按钮 (...), 以打开 " **ToolBarButton 集合编辑器**"。 <xref:System.Windows.Forms.ToolBar></span><span class="sxs-lookup"><span data-stu-id="55013-113">Click the <xref:System.Windows.Forms.ToolBar> control's <xref:System.Windows.Forms.ToolBar.Buttons%2A> property to select it, and click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **ToolBarButton Collection Editor**.</span></span>

5. <span data-ttu-id="55013-114">使用 "**添加**" 按钮可将按钮添加<xref:System.Windows.Forms.ToolBar>到控件。</span><span class="sxs-lookup"><span data-stu-id="55013-114">Use the **Add** button to add buttons to the <xref:System.Windows.Forms.ToolBar> control.</span></span>

6. <span data-ttu-id="55013-115">在**ToolBarButton 集合编辑器**右侧窗格中显示的 " <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> **属性**" 窗口中, 将每个工具栏按钮的属性设置为列表中的值之一, 此列表中的值从添加到<xref:System.Windows.Forms.ImageList>组件。</span><span class="sxs-lookup"><span data-stu-id="55013-115">In the **Properties** window that appears in the pane on the right side of the **ToolBarButton Collection Editor**, set the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of each toolbar button to one of the values in the list, which is drawn from the images you added to the <xref:System.Windows.Forms.ImageList> component.</span></span>

## <a name="see-also"></a><span data-ttu-id="55013-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="55013-116">See also</span></span>

- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="55013-117">如何：工具栏按钮的触发器菜单事件</span><span class="sxs-lookup"><span data-stu-id="55013-117">How to: Trigger Menu Events for Toolbar Buttons</span></span>](how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="55013-118">ToolBar 控件</span><span class="sxs-lookup"><span data-stu-id="55013-118">ToolBar Control</span></span>](toolbar-control-windows-forms.md)
- [<span data-ttu-id="55013-119">ImageList 组件</span><span class="sxs-lookup"><span data-stu-id="55013-119">ImageList Component</span></span>](imagelist-component-windows-forms.md)
