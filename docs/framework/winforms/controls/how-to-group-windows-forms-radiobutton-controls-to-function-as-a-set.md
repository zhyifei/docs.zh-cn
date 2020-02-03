---
title: 将单选按钮控件作为一个集进行分组
ms.date: 03/30/2017
helpviewer_keywords:
- radio buttons [Windows Forms], grouping
- controls [Windows Forms], grouping
- Windows Forms controls, grouping
- RadioButton control [Windows Forms], grouping
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
ms.openlocfilehash: c4b37c84bf0f93837b91c743c7681d39fd83a659
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732950"
---
# <a name="how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set"></a>如何：按功能分组 Windows 窗体 RadioButton 控件
Windows 窗体 <xref:System.Windows.Forms.RadioButton> 控件旨在为用户选择两个或多个设置，其中只有一个设置可以分配给过程或对象。 例如，一组 <xref:System.Windows.Forms.RadioButton> 控件可能会针对订单显示包托架的选择，但将仅使用其中一个运营商。 因此，一次只能选择一个 <xref:System.Windows.Forms.RadioButton>，即使它是功能组的一部分也是如此。  
  
 可以通过在容器（如 <xref:System.Windows.Forms.Panel> 控件、<xref:System.Windows.Forms.GroupBox> 控件或窗体）中绘制单选按钮来对其进行分组。 直接添加到窗体中的所有单选按钮都将成为一个组。 若要添加单独的组，则必须将它们放在面板或组框中。 有关面板或分组框的详细信息，请参阅[Panel 控件概述](panel-control-overview-windows-forms.md)或[分组框控件概述](groupbox-control-overview-windows-forms.md)。  
  
### <a name="to-group-radiobutton-controls-as-a-set-to-function-independently-of-other-sets"></a>将单选按钮控件分组为独立于其他集的功能  
  
1. 将 <xref:System.Windows.Forms.GroupBox> 或 <xref:System.Windows.Forms.Panel> 控件从**工具箱**上的 " **Windows 窗体**" 选项卡拖到窗体上。  
  
2. 在 <xref:System.Windows.Forms.GroupBox> 或 <xref:System.Windows.Forms.Panel> 控件上绘制 <xref:System.Windows.Forms.RadioButton> 控件。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.RadioButton>
- [RadioButton 控件概述](radiobutton-control-overview-windows-forms.md)
- [Panel 控件概述](panel-control-overview-windows-forms.md)
- [GroupBox 控件概述](groupbox-control-overview-windows-forms.md)
- [CheckBox 控件概述](checkbox-control-overview-windows-forms.md)
- [RadioButton 控件](radiobutton-control-windows-forms.md)
