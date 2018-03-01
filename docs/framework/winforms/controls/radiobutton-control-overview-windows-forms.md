---
title: "RadioButton 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- RadioButton
helpviewer_keywords:
- RadioButton control [Windows Forms], about RadioButton control
- RadioButton control [Windows Forms], determining state
- radio buttons [Windows Forms], determining state
- radio buttons [Windows Forms], about radio buttons
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 67befd973dec38628f97a0d3153c399d48c18305
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="radiobutton-control-overview-windows-forms"></a>RadioButton 控件概述（Windows 窗体）
Windows 窗体<xref:System.Windows.Forms.RadioButton>控件向用户显示一组两个或多个互相排斥的选择。 尽管单选按钮和复选框可能看起来作用类似，但还有一项重大差异： 当用户选择一个单选按钮时，不能也选择同一组中的其他单选按钮。 与此相反，可以选择任意数量的复选框。 定义单选按钮组将告诉用户:"这是一组选项，您可以从中选择一个且只有一个。"  
  
## <a name="using-the-control"></a>使用控件  
 当<xref:System.Windows.Forms.RadioButton>单击控件时，其<xref:System.Windows.Forms.RadioButton.Checked%2A>属性设置为`true`和<xref:System.Windows.Forms.Control.Click>调用事件处理程序。 <xref:System.Windows.Forms.RadioButton.CheckedChanged>引发事件时的值<xref:System.Windows.Forms.RadioButton.Checked%2A>属性更改。 如果<xref:System.Windows.Forms.RadioButton.AutoCheck%2A>属性设置为`true`（默认值），当选择单选按钮组中的所有其他会自动清除。 此属性通常是只将设置为`false`验证代码用于确保单选按钮处于选中状态的时是允许的选项。 设置控件中显示的文本<xref:System.Windows.Forms.Control.Text%2A>属性，它可以包含访问键快捷方式。 访问密钥使用户可以通过按 ALT 键和访问密钥"单击"的控件。 有关详细信息，请参阅[如何： 为 Windows 窗体控件创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)和[如何： 设置 Windows 窗体控件显示的文本](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)。  
  
 <xref:System.Windows.Forms.RadioButton>控件可以显示类似于命令按钮，它看起来已按下，如果选择，如果<xref:System.Windows.Forms.RadioButton.Appearance%2A>属性设置为<xref:System.Windows.Forms.Appearance.Button>。 单选按钮还可以显示使用的图像<xref:System.Windows.Forms.ButtonBase.Image%2A>和<xref:System.Windows.Forms.ButtonBase.ImageList%2A>属性。 有关详细信息，请参阅[如何： 设置 Windows 窗体控件显示的图像](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.RadioButton>  
 [Panel 控件概述](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)  
 [GroupBox 控件概述](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)  
 [CheckBox 控件概述](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)  
 [如何：创建 Windows 窗体控件的访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)  
 [如何：设置 Windows 窗体控件显示的文本](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [如何：按功能分组 Windows 窗体 RadioButton 控件](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)  
 [RadioButton 控件](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)
