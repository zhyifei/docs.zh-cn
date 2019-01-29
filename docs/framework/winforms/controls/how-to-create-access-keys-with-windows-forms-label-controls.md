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
ms.openlocfilehash: a1317f34b39c5689e285f8822fff9bfcc42db1d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680312"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>如何：使用 Windows 窗体 Label 控件创建访问键
Windows 窗体<xref:System.Windows.Forms.Label>控件可用于定义其他控件的访问键。 当标签控件中定义的访问键时，用户可以按 ALT 键的同时指定要将焦点移到控件的 tab 键顺序后面的字符。 因为标签不能接收焦点，焦点将自动移动到下一个控件的 tab 键顺序。 使用此方法将访问键分配给文本框、 组合框、 列表框和数据网格。  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>若要向使用标签控件分配访问键  
  
1.  首先，绘制标签并画出另一个控件。  
  
     或  
  
     按任意顺序绘制控件，并设置<xref:System.Windows.Forms.Control.TabIndex%2A>标签为一个小于另一个控件的属性。  
  
2.  设置的标签<xref:System.Windows.Forms.Label.UseMnemonic%2A>属性设置为`true`。  
  
3.  使用与号 (&) 中标签的<xref:System.Windows.Forms.Label.Text%2A>要分配为标签的访问键属性。 有关详细信息，请参阅[的 Windows 窗体控件创建访问密钥](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)。  
  
    > [!NOTE]
    >  您可能想要显示与号中的标签控件，而不使用它们来创建访问键。 如果将标签控件绑定到其中的数据包括与号在记录集中的字段，这可能会出现。 若要在标签控件中显示与号，请设置<xref:System.Windows.Forms.Label.UseMnemonic%2A>属性设置为`false`。 如果你想要显示与号，并且还具有访问键，设置<xref:System.Windows.Forms.Label.UseMnemonic%2A>属性设置为`true`并指示访问键与一个 & 号 (&) 和与符号以显示两个 & 号。  
  
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
- [如何：调整 Windows 窗体标签控件以适应其内容的大小](../../../../docs/framework/winforms/controls/how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Label 控件概述](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)
- [Label 控件](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
