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
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a>如何：更改 Windows 窗体 TabControl 的外观
你可以使用属性来更改 Windows 窗体中的选项卡的外观<xref:System.Windows.Forms.TabControl>和<xref:System.Windows.Forms.TabPage>构成控件上的各个选项卡的对象。 通过设置这些属性，可以在选项卡上显示图像、 显示垂直而不是水平选项卡，显示多个数据行的选项卡，并启用或以编程方式禁用选项卡。  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a>以标签部件的选项卡上显示一个图标  
  
1.  添加<xref:System.Windows.Forms.ImageList>到窗体控件。  
  
2.  将映像添加到图像列表。  
  
     有关图像列表的详细信息，请参阅[ImageList 组件](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)和[如何： 添加或移除图像使用 Windows 窗体 ImageList 组件](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)。  
  
3.  设置<xref:System.Windows.Forms.TabControl.ImageList%2A>属性<xref:System.Windows.Forms.TabControl>到<xref:System.Windows.Forms.ImageList>控件。  
  
4.  设置<xref:System.Windows.Forms.TabPage.ImageIndex%2A>属性<xref:System.Windows.Forms.TabPage>的列表中的相应图像的索引。  
  
### <a name="to-create-multiple-rows-of-tabs"></a>若要创建多个行的选项卡  
  
1.  添加所需的选项卡页的数目。  
  
2.  设置<xref:System.Windows.Forms.TabControl.Multiline%2A>属性<xref:System.Windows.Forms.TabControl>到`true`。  
  
3.  如果选项卡已出现在多个行，设置<xref:System.Windows.Forms.Control.Width%2A>属性<xref:System.Windows.Forms.TabControl>要窄于所有选项卡。  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a>排列控件一侧的选项卡  
  
-   设置<xref:System.Windows.Forms.TabControl.Alignment%2A>属性<xref:System.Windows.Forms.TabControl>到<xref:System.Windows.Forms.TabAlignment.Left>或<xref:System.Windows.Forms.TabAlignment.Right>。  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a>若要以编程方式启用或禁用选项卡上的所有控件  
  
1.  设置<xref:System.Windows.Forms.TabPage.Enabled%2A>属性<xref:System.Windows.Forms.TabPage>到`true`或`false`。  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a>若要为按钮显示选项卡  
  
-   设置<xref:System.Windows.Forms.TabControl.Appearance%2A>属性<xref:System.Windows.Forms.TabControl>到<xref:System.Windows.Forms.TabAppearance.Buttons>或<xref:System.Windows.Forms.TabAppearance.FlatButtons>。  
  
## <a name="see-also"></a>请参阅  
 [TabControl 控件](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [TabControl 控件概述](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [如何：向选项卡页添加控件](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [如何：禁用选项卡页](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [如何：使用 Windows 窗体 TabControl 控件添加和删除选项卡](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
