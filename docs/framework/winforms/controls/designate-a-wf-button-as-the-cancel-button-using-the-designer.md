---
title: 如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
ms.openlocfilehash: faffeafc0cbe67c3b40297144ec85acd94956da9
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46698553"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮
在任何 Windows 窗体中，可以将指定<xref:System.Windows.Forms.Button>控件为取消按钮。 每当用户按 ESC 键时，无论哪个窗体上的其他控件具有焦点时，单击取消按钮。 通常，设计这样的按钮，使用户能够快速退出操作而无须执行任何操作。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-designate-the-cancel-button"></a>若要指定取消按钮  
  
1.  选择该按钮所驻留的窗体。  
  
2.  在中**属性**窗口中，将窗体的<xref:System.Windows.Forms.Form.CancelButton%2A>属性设置为<xref:System.Windows.Forms.Button>控件的名称。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [Button 控件概述](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [如何选择 Windows 窗体 Button 控件](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [如何：响应 Windows 窗体 Button 控件单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [如何：使用设计器将 Windows 窗体按钮指定为“接受”按钮](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [Button 控件](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
