---
title: 如何：更改 Windows 窗体 TabControl 的外观
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
ms.openlocfilehash: 1ea2208229d790f69e517d55e2de5ee042bdfb03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531035"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="ff3e4-102">如何：更改 Windows 窗体 TabControl 的外观</span><span class="sxs-lookup"><span data-stu-id="ff3e4-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="ff3e4-103">你可以使用属性来更改 Windows 窗体中的选项卡的外观<xref:System.Windows.Forms.TabControl>和<xref:System.Windows.Forms.TabPage>构成控件上的各个选项卡的对象。</span><span class="sxs-lookup"><span data-stu-id="ff3e4-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="ff3e4-104">通过设置这些属性，可以在选项卡上显示图像、 显示垂直而不是水平选项卡，显示多个数据行的选项卡，并启用或以编程方式禁用选项卡。</span><span class="sxs-lookup"><span data-stu-id="ff3e4-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="ff3e4-105">以标签部件的选项卡上显示一个图标</span><span class="sxs-lookup"><span data-stu-id="ff3e4-105">To display an icon on the label part of a tab</span></span>  
  
1.  <span data-ttu-id="ff3e4-106">添加<xref:System.Windows.Forms.ImageList>到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="ff3e4-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2.  <span data-ttu-id="ff3e4-107">将映像添加到图像列表。</span><span class="sxs-lookup"><span data-stu-id="ff3e4-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="ff3e4-108">有关图像列表的详细信息，请参阅[ImageList 组件](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)和[如何： 添加或移除图像使用 Windows 窗体 ImageList 组件](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。</span><span class="sxs-lookup"><span data-stu-id="ff3e4-108">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3.  <span data-ttu-id="ff3e4-109">设置<xref:System.Windows.Forms.TabControl.ImageList%2A>属性<xref:System.Windows.Forms.TabControl>到<xref:System.Windows.Forms.ImageList>控件。</span><span class="sxs-lookup"><span data-stu-id="ff3e4-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4.  <span data-ttu-id="ff3e4-110">设置<xref:System.Windows.Forms.TabPage.ImageIndex%2A>属性<xref:System.Windows.Forms.TabPage>的列表中的相应图像的索引。</span><span class="sxs-lookup"><span data-stu-id="ff3e4-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="ff3e4-111">若要创建多个行的选项卡</span><span class="sxs-lookup"><span data-stu-id="ff3e4-111">To create multiple rows of tabs</span></span>  
  
1.  <span data-ttu-id="ff3e4-112">添加所需的选项卡页的数目。</span><span class="sxs-lookup"><span data-stu-id="ff3e4-112">Add the number of tab pages you want.</span></span>  
  
2.  <span data-ttu-id="ff3e4-113">设置<xref:System.Windows.Forms.TabControl.Multiline%2A>属性<xref:System.Windows.Forms.TabControl>到`true`。</span><span class="sxs-lookup"><span data-stu-id="ff3e4-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3.  <span data-ttu-id="ff3e4-114">如果选项卡已出现在多个行，设置<xref:System.Windows.Forms.Control.Width%2A>属性<xref:System.Windows.Forms.TabControl>要窄于所有选项卡。</span><span class="sxs-lookup"><span data-stu-id="ff3e4-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="ff3e4-115">排列控件一侧的选项卡</span><span class="sxs-lookup"><span data-stu-id="ff3e4-115">To arrange tabs on the side of the control</span></span>  
  
-   <span data-ttu-id="ff3e4-116">设置<xref:System.Windows.Forms.TabControl.Alignment%2A>属性<xref:System.Windows.Forms.TabControl>到<xref:System.Windows.Forms.TabAlignment.Left>或<xref:System.Windows.Forms.TabAlignment.Right>。</span><span class="sxs-lookup"><span data-stu-id="ff3e4-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="ff3e4-117">若要以编程方式启用或禁用选项卡上的所有控件</span><span class="sxs-lookup"><span data-stu-id="ff3e4-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1.  <span data-ttu-id="ff3e4-118">设置<xref:System.Windows.Forms.TabPage.Enabled%2A>属性<xref:System.Windows.Forms.TabPage>到`true`或`false`。</span><span class="sxs-lookup"><span data-stu-id="ff3e4-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="ff3e4-119">若要为按钮显示选项卡</span><span class="sxs-lookup"><span data-stu-id="ff3e4-119">To display tabs as buttons</span></span>  
  
-   <span data-ttu-id="ff3e4-120">设置<xref:System.Windows.Forms.TabControl.Appearance%2A>属性<xref:System.Windows.Forms.TabControl>到<xref:System.Windows.Forms.TabAppearance.Buttons>或<xref:System.Windows.Forms.TabAppearance.FlatButtons>。</span><span class="sxs-lookup"><span data-stu-id="ff3e4-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff3e4-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff3e4-121">See Also</span></span>  
 [<span data-ttu-id="ff3e4-122">TabControl 控件</span><span class="sxs-lookup"><span data-stu-id="ff3e4-122">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="ff3e4-123">TabControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="ff3e4-123">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="ff3e4-124">如何：向选项卡页添加控件</span><span class="sxs-lookup"><span data-stu-id="ff3e4-124">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="ff3e4-125">如何：禁用选项卡页</span><span class="sxs-lookup"><span data-stu-id="ff3e4-125">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="ff3e4-126">如何：使用 Windows 窗体 TabControl 控件添加和删除选项卡</span><span class="sxs-lookup"><span data-stu-id="ff3e4-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
