---
title: 如何：将 Windows 窗体按钮指定为接受按钮使用设计器
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
ms.openlocfilehash: 477094b88c99bbe9193a6eaedb5c16d0c0e679d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709541"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a>如何：将 Windows 窗体按钮指定为接受按钮使用设计器
在任何 Windows 窗体中，可以将指定<xref:System.Windows.Forms.Button>控件成为接受按钮，也称为默认按钮。 每当用户按 ENTER 键，无论哪个窗体上的其他控件具有焦点单击默认按钮。 为以下情形时具有焦点的控件是另一个按钮的异常，将在这种情况下，单击具有焦点的按钮，或多行文本框中或捕获 ENTER 键的自定义控件。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-designate-the-accept-button"></a>若要指定接受按钮  
  
1.  选择该按钮所驻留的窗体。  
  
2.  在中**属性**窗口中，将窗体的<xref:System.Windows.Forms.Form.AcceptButton%2A>属性设置为<xref:System.Windows.Forms.Button>控件的名称。  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [Button 控件概述](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [如何选择 Windows 窗体 Button 控件](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [如何：响应 Windows 窗体按钮单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)
- [如何：将 Windows 窗体按钮指定为使用设计器的取消按钮](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)
- [Button 控件](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
