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
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a>如何：更改 Windows 窗体 TabControl 的外观
您可以通过使用 <xref:System.Windows.Forms.TabControl> 的属性和组成控件上各个选项卡的 <xref:System.Windows.Forms.TabPage> 对象，更改 Windows 窗体中选项卡的外观。 通过设置这些属性，可以在选项卡上显示图像，垂直显示选项卡，而不是水平显示，显示多行选项卡，并以编程方式启用或禁用选项卡。  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a>在选项卡的标签部分显示图标  
  
1. 向窗体添加 <xref:System.Windows.Forms.ImageList> 控件。  
  
2. 向图像列表添加图像。  
  
     有关图像列表的详细信息，请参阅[Imagelist 组件](imagelist-component-windows-forms.md)和[如何：通过 Windows 窗体 ImageList 组件添加或删除图像](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。  
  
3. 将 <xref:System.Windows.Forms.TabControl> 的 <xref:System.Windows.Forms.TabControl.ImageList%2A> 属性设置为 <xref:System.Windows.Forms.ImageList> 控件。  
  
4. 将 <xref:System.Windows.Forms.TabPage> 的 <xref:System.Windows.Forms.TabPage.ImageIndex%2A> 属性设置为列表中相应图像的索引。  
  
### <a name="to-create-multiple-rows-of-tabs"></a>创建多行选项卡  
  
1. 添加所需的选项卡页的数目。  
  
2. 将 <xref:System.Windows.Forms.TabControl> 的 <xref:System.Windows.Forms.TabControl.Multiline%2A> 属性设置为 "`true`"。  
  
3. 如果选项卡尚未出现在多个行中，请将 <xref:System.Windows.Forms.TabControl> 的 <xref:System.Windows.Forms.Control.Width%2A> 属性设置为比所有选项卡都窄。  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a>排列控件一侧的选项卡  
  
- 将 <xref:System.Windows.Forms.TabControl> 的 <xref:System.Windows.Forms.TabControl.Alignment%2A> 属性设置为 <xref:System.Windows.Forms.TabAlignment.Left> 或 <xref:System.Windows.Forms.TabAlignment.Right>。  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a>以编程方式启用或禁用选项卡上的所有控件  
  
1. 将 <xref:System.Windows.Forms.TabPage> 的 <xref:System.Windows.Forms.TabPage.Enabled%2A> 属性设置为 `true` 或 `false`。  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a>将选项卡显示为按钮  
  
- 将 <xref:System.Windows.Forms.TabControl> 的 <xref:System.Windows.Forms.TabControl.Appearance%2A> 属性设置为 <xref:System.Windows.Forms.TabAppearance.Buttons> 或 <xref:System.Windows.Forms.TabAppearance.FlatButtons>。  
  
## <a name="see-also"></a>另请参阅

- [TabControl 控件](tabcontrol-control-windows-forms.md)
- [TabControl 控件概述](tabcontrol-control-overview-windows-forms.md)
- [如何：向选项卡页添加控件](how-to-add-a-control-to-a-tab-page.md)
- [如何：禁用选项卡页](how-to-disable-tab-pages.md)
- [如何：使用 Windows 窗体 TabControl 控件添加和删除选项卡](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
