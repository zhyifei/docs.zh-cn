---
title: Button 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
ms.openlocfilehash: 042ff7cb868b62778691348cb6c1ba464b794993
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656435"
---
# <a name="button-control-overview-windows-forms"></a>Button 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.Button> 控件允许用户通过单击来执行某项操作。 单击该按钮时，看上去它像是被按下并释放。 每当用户单击一个按钮，<xref:System.Windows.Forms.Control.Click>调用事件处理程序。 你将代码放在<xref:System.Windows.Forms.Control.Click>事件处理程序以执行所选择的任何操作。  
  
 在按钮上显示的文本包含在<xref:System.Windows.Forms.Control.Text%2A>属性。 如果您的文本超出了按钮的宽度，它将换行到下一行。 但是，它将剪辑如果控件所能容纳的窗体的整体高度。 有关详细信息，请参阅[如何：设置显示的文本的 Windows 窗体控件](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)。 <xref:System.Windows.Forms.Control.Text%2A>属性可以包含访问密钥，这样用户就可以通过按 ALT 键和访问密钥"单击"控件。 有关详细信息，请参阅[如何：Windows 窗体控件的创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)。 由控制文本的外观<xref:System.Windows.Forms.Control.Font%2A>属性和<xref:System.Windows.Forms.ButtonBase.TextAlign%2A>属性。  
  
 <xref:System.Windows.Forms.Button>控件还可以显示使用的映像<xref:System.Windows.Forms.ButtonBase.Image%2A>和<xref:System.Windows.Forms.ButtonBase.ImageList%2A>属性。 有关详细信息，请参阅[如何：设置所显示的图像的 Windows 窗体控件](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md)。  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Forms.Button>
- [如何：响应 Windows 窗体按钮单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [如何选择 Windows 窗体 Button 控件](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [如何：将 Windows 窗体按钮指定为接受按钮使用设计器](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)
- [如何：将 Windows 窗体按钮指定为使用设计器的取消按钮](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Button 控件](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
