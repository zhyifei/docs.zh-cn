---
title: "如何：设置 Windows 窗体上的 Tab 键顺序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de52a4d7784eb4508d5cf5026b394b7b63ecc56e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>如何：设置 Windows 窗体上的 Tab 键顺序
Tab 键顺序是在其中用户焦点从一个控件移到另一个通过按 TAB 键顺序。 每个窗体具有其自己的 tab 键顺序。 默认情况下，tab 键顺序是创建控件的顺序相同。 Tab 键顺序编号从 0 开始。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-set-the-tab-order-of-a-control"></a>若要设置控件的 tab 键次序  
  
1.  上**视图**菜单上，单击**tab 键顺序**。  
  
     这将激活窗体上的 tab 键顺序选择模式。 一个数字 (表示<xref:System.Windows.Forms.Control.TabIndex%2A>属性) 显示在每个控件的左上角。  
  
2.  单击的控件按顺序建立所需的选项卡顺序。  
  
    > [!NOTE]
    >  大于或等于 0，在选项卡顺序内的控件的位置可以设置为任何值。 当出现重复时，计算的两个控件的 z 顺序，并位于上面的控件为第一个选项卡式。 （z 顺序是沿窗体的 z 轴 [深度] 窗体上控件的可视化分层。 Z 顺序确定哪些控件位于其他控件的前面。）Z 顺序的详细信息，请参阅[Windows 窗体上的分层对象](../../../../docs/framework/winforms/controls/how-to-layer-objects-on-windows-forms.md)。  
  
3.  完成后，单击**tab 键顺序**上**视图**菜单再次离开 tab 键顺序模式。  
  
    > [!NOTE]
    >  无法获得焦点的控件，以及禁用，并且不可见控件没有<xref:System.Windows.Forms.Control.TabIndex%2A>属性，也不包括的 tab 键顺序。 当用户按 TAB 键，则跳过这些控件。  
  
 或者，可以在属性窗口中使用设置 tab 键顺序<xref:System.Windows.Forms.Control.TabIndex%2A>属性。 <xref:System.Windows.Forms.Control.TabIndex%2A>控件的属性确定的 tab 键顺序的放置位置。 默认情况下，第一个控件绘制具有<xref:System.Windows.Forms.Control.TabIndex%2A>值为 0，第二个具有<xref:System.Windows.Forms.Control.TabIndex%2A>为 1，依次类推。  
  
 此外，默认情况下，<xref:System.Windows.Forms.GroupBox>控件具有其自己<xref:System.Windows.Forms.Control.TabIndex%2A>值，该值是一个整数。 A<xref:System.Windows.Forms.GroupBox>控件本身不能在运行时具有焦点。 因此，在每个控件<xref:System.Windows.Forms.GroupBox>具有其自己的十进制<xref:System.Windows.Forms.Control.TabIndex%2A>值，开头.0。 当然，作为<xref:System.Windows.Forms.Control.TabIndex%2A>的<xref:System.Windows.Forms.GroupBox>控件即会递增，其中的控件将相应递增。 如果你更改<xref:System.Windows.Forms.Control.TabIndex%2A>介于 5 和 6，值<xref:System.Windows.Forms.Control.TabIndex%2A>在其组的第一个控件的值自动更改为 6.0 中，依次类推。  
  
 最后，任何控件的窗体上多可以跳过的 tab 键顺序。 通常情况下，连续按 tab 键在运行的时选择每个控件的 tab 键顺序。 通过关闭<xref:System.Windows.Forms.Control.TabStop%2A>属性，可以使控件通过传递窗体的 tab 键顺序。  
  
#### <a name="to-remove-a-control-from-the-tab-order"></a>若要从 tab 键顺序中移除控件  
  
1.  设置控件的<xref:System.Windows.Forms.Control.TabStop%2A>属性`false`属性窗口中。  
  
     一个控件<xref:System.Windows.Forms.Control.TabStop%2A>属性已设置为`false`仍保持 tab 键顺序中，其位置，即使控件循环使用 TAB 键时，控件将跳过。  
  
    > [!NOTE]
    >  单选按钮组具有一个制表位运行时。 所选的按钮 (即，具有的按钮其<xref:System.Windows.Forms.RadioButton.Checked%2A>属性设置为`true`) 具有其<xref:System.Windows.Forms.Control.TabStop%2A>属性自动设置为`true`，而其他按钮拥有其<xref:System.Windows.Forms.Control.TabStop%2A>属性设置为`false`。 有关更多信息分组<xref:System.Windows.Forms.RadioButton>控件，请参阅[分组用作一组 Windows 窗体 RadioButton 控件](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)  
 [在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [按功能列出的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
