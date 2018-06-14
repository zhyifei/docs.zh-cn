---
title: 如何：使用 Windows 窗体 Label 控件创建访问键
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- Label control [Windows Forms], creating access keys
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- Windows Forms controls, access keys
- UseMnemonic property [Windows Forms], Label control
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
ms.assetid: 5ee8f823-80be-4a4f-96a4-412671e2e306
ms.openlocfilehash: fc9592981f3d926b2b5b85b6869da13dc644e7a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530798"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>如何：使用 Windows 窗体 Label 控件创建访问键
Windows 窗体<xref:System.Windows.Forms.Label>控件可以用于定义其他控件的访问密钥。 当标签控件中定义的访问密钥时，用户可以按 ALT 键加你指定要将焦点移到控件的 tab 键顺序将它后面的字符。 因为标签不能接收焦点，焦点将自动移动到下一个控件的 tab 键顺序。 使用此方法将访问密钥分配到文本框、 组合框、 列表框和数据网格。  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>要分配给了标签控件的访问密钥  
  
1.  首先，绘制标签，然后绘制另一个控件。  
  
     -或-  
  
     按任意顺序绘制控件，并设置<xref:System.Windows.Forms.Control.TabIndex%2A>属性为一个小于另一个控件的标签。  
  
2.  设置标签的<xref:System.Windows.Forms.Label.UseMnemonic%2A>属性`true`。  
  
3.  使用与号 (&) 中的标签<xref:System.Windows.Forms.Label.Text%2A>要分配标签的访问密钥属性。 有关详细信息，请参阅[为 Windows 窗体控件创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)。  
  
    > [!NOTE]
    >  你可能想要显示的标签控件，在与符号，而不是使用它们来创建访问键。 这可能是如果你将一个标签控件绑定到其中的数据包括 & 在记录集中的字段。 若要显示的标签控件中的 &，请设置<xref:System.Windows.Forms.Label.UseMnemonic%2A>属性`false`。 如果你想要显示与符号，并且还具有的访问密钥，设置<xref:System.Windows.Forms.Label.UseMnemonic%2A>属性`true`并指示访问密钥与一个 & 号 (&) 和连字符来显示两个 & 号。  
  
    ```vb  
    Label1.UseMnemonic = True  
    Label1.Text = "&Print"  
    Label2.UseMnemonic = True  
    Label2.Text = "&Copy && Paste"  
    ```  
  
    ```csharp  
    label1.UseMnemonic = true;  
    label1.Text = "&Print";  
    label2.UseMnemonic = true;  
    label2.Text = "&Copy && Paste";  
    ```  
  
    ```cpp  
    label1->UseMnemonic = true;  
    label1->Text = "&Print";  
    label2->UseMnemonic = true;  
    label2->Text = "&Copy && Paste";  
    ```  
  
## <a name="see-also"></a>请参阅  
 [如何：重设 Windows 窗体 Label 控件大小以适应其内容](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)  
 [Label 控件概述](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)  
 [Label 控件](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
