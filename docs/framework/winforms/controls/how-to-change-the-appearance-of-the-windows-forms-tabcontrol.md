---
title: 更改 TabControl 的外观
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
ms.openlocfilehash: 056070177e6bbaba0c93c7b94f5adfd7887be6a8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746610"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="a4359-102">如何：更改 Windows 窗体 TabControl 的外观</span><span class="sxs-lookup"><span data-stu-id="a4359-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="a4359-103">您可以通过使用 <xref:System.Windows.Forms.TabControl> 的属性和组成控件上各个选项卡的 <xref:System.Windows.Forms.TabPage> 对象，更改 Windows 窗体中选项卡的外观。</span><span class="sxs-lookup"><span data-stu-id="a4359-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="a4359-104">通过设置这些属性，可以在选项卡上显示图像，垂直显示选项卡，而不是水平显示，显示多行选项卡，并以编程方式启用或禁用选项卡。</span><span class="sxs-lookup"><span data-stu-id="a4359-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="a4359-105">在选项卡的标签部分显示图标</span><span class="sxs-lookup"><span data-stu-id="a4359-105">To display an icon on the label part of a tab</span></span>  
  
1. <span data-ttu-id="a4359-106">向窗体添加 <xref:System.Windows.Forms.ImageList> 控件。</span><span class="sxs-lookup"><span data-stu-id="a4359-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2. <span data-ttu-id="a4359-107">向图像列表添加图像。</span><span class="sxs-lookup"><span data-stu-id="a4359-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="a4359-108">有关图像列表的详细信息，请参阅[Imagelist 组件](imagelist-component-windows-forms.md)和[如何：通过 Windows 窗体 ImageList 组件添加或删除图像](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。</span><span class="sxs-lookup"><span data-stu-id="a4359-108">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3. <span data-ttu-id="a4359-109">将 <xref:System.Windows.Forms.TabControl> 的 <xref:System.Windows.Forms.TabControl.ImageList%2A> 属性设置为 <xref:System.Windows.Forms.ImageList> 控件。</span><span class="sxs-lookup"><span data-stu-id="a4359-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4. <span data-ttu-id="a4359-110">将 <xref:System.Windows.Forms.TabPage> 的 <xref:System.Windows.Forms.TabPage.ImageIndex%2A> 属性设置为列表中相应图像的索引。</span><span class="sxs-lookup"><span data-stu-id="a4359-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="a4359-111">创建多行选项卡</span><span class="sxs-lookup"><span data-stu-id="a4359-111">To create multiple rows of tabs</span></span>  
  
1. <span data-ttu-id="a4359-112">添加所需的选项卡页的数目。</span><span class="sxs-lookup"><span data-stu-id="a4359-112">Add the number of tab pages you want.</span></span>  
  
2. <span data-ttu-id="a4359-113">将 <xref:System.Windows.Forms.TabControl> 的 <xref:System.Windows.Forms.TabControl.Multiline%2A> 属性设置为 "`true`"。</span><span class="sxs-lookup"><span data-stu-id="a4359-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3. <span data-ttu-id="a4359-114">如果选项卡尚未出现在多个行中，请将 <xref:System.Windows.Forms.TabControl> 的 <xref:System.Windows.Forms.Control.Width%2A> 属性设置为比所有选项卡都窄。</span><span class="sxs-lookup"><span data-stu-id="a4359-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="a4359-115">排列控件一侧的选项卡</span><span class="sxs-lookup"><span data-stu-id="a4359-115">To arrange tabs on the side of the control</span></span>  
  
- <span data-ttu-id="a4359-116">将 <xref:System.Windows.Forms.TabControl> 的 <xref:System.Windows.Forms.TabControl.Alignment%2A> 属性设置为 <xref:System.Windows.Forms.TabAlignment.Left> 或 <xref:System.Windows.Forms.TabAlignment.Right>。</span><span class="sxs-lookup"><span data-stu-id="a4359-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="a4359-117">以编程方式启用或禁用选项卡上的所有控件</span><span class="sxs-lookup"><span data-stu-id="a4359-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1. <span data-ttu-id="a4359-118">将 <xref:System.Windows.Forms.TabPage> 的 <xref:System.Windows.Forms.TabPage.Enabled%2A> 属性设置为 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="a4359-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="a4359-119">将选项卡显示为按钮</span><span class="sxs-lookup"><span data-stu-id="a4359-119">To display tabs as buttons</span></span>  
  
- <span data-ttu-id="a4359-120">将 <xref:System.Windows.Forms.TabControl> 的 <xref:System.Windows.Forms.TabControl.Appearance%2A> 属性设置为 <xref:System.Windows.Forms.TabAppearance.Buttons> 或 <xref:System.Windows.Forms.TabAppearance.FlatButtons>。</span><span class="sxs-lookup"><span data-stu-id="a4359-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4359-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4359-121">See also</span></span>

- [<span data-ttu-id="a4359-122">TabControl 控件</span><span class="sxs-lookup"><span data-stu-id="a4359-122">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="a4359-123">TabControl 控件概述</span><span class="sxs-lookup"><span data-stu-id="a4359-123">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="a4359-124">如何：向选项卡页添加控件</span><span class="sxs-lookup"><span data-stu-id="a4359-124">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="a4359-125">如何：禁用选项卡页</span><span class="sxs-lookup"><span data-stu-id="a4359-125">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="a4359-126">如何：使用 Windows 窗体 TabControl 控件添加和删除选项卡</span><span class="sxs-lookup"><span data-stu-id="a4359-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
