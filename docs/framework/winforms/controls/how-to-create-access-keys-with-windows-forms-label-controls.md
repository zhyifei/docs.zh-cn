---
title: 使用标签控件创建访问键
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
ms.openlocfilehash: 800afc03e71435e2721456b93bb9704af01f714a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731046"
---
# <a name="how-to-create-access-keys-with-windows-forms-label-controls"></a>如何：使用 Windows 窗体 Label 控件创建访问键
Windows 窗体 <xref:System.Windows.Forms.Label> 控件可用于定义其他控件的访问键。 在标签控件中定义访问键时，用户可以同时按 ALT 键和指定的字符，以便将焦点移到 Tab 键顺序中排在其后面的控件。 由于标签不能接收焦点，因此焦点会自动移到 Tab 键顺序中的下一个控件。 使用此方法可将访问键分配给文本框、组合框、列表框和数据网格。  
  
### <a name="to-assign-an-access-key-to-a-control-with-a-label"></a>为具有标签的控件分配访问键  
  
1. 首先绘制标签，然后绘制另一个控件。  
  
     \- 或 -  
  
     按任意顺序绘制控件，并将标签的 <xref:System.Windows.Forms.Control.TabIndex%2A> 属性设置为小于另一个控件的一个。  
  
2. 将标签的 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 属性设置为 `true`。  
  
3. 使用标签的 <xref:System.Windows.Forms.Label.Text%2A> 属性中的 "与" 符号（&）可以为标签分配访问键。 有关详细信息，请参阅[创建 Windows 窗体控件的访问键](how-to-create-access-keys-for-windows-forms-controls.md)。  
  
    > [!NOTE]
    > 可能需要显示标签控件中的与号，而不使用它们来创建访问键。 如果将标签控件绑定到记录集中的一个字段，而该记录集中的数据包含与号，则可能会出现这种情况。 若要在 "标签" 控件中显示 "&"，请将 <xref:System.Windows.Forms.Label.UseMnemonic%2A> 属性设置为 `false`。 如果希望显示 "&" 和 "访问密钥"，请将 "<xref:System.Windows.Forms.Label.UseMnemonic%2A>" 属性设置为 "`true`"，并使用一个 "and" 符（&）和 "and" 符显示带有两个 "&" 符的访问密钥。  
  
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
  
## <a name="see-also"></a>另请参阅

- [如何：重设 Windows 窗体 Label 控件大小以适应其内容](how-to-size-a-windows-forms-label-control-to-fit-its-contents.md)
- [Label 控件概述](label-control-overview-windows-forms.md)
- [Label 控件](label-control-windows-forms.md)
