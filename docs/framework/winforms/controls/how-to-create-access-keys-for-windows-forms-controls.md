---
title: 如何：创建 Windows 窗体控件的访问键
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- mnemonics
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4faa0991-28ec-4eca-91db-51dc2cd6a7ac
ms.openlocfilehash: 53ffd3632ff3e1179a72f1e2bfe4ea366e28b0f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-access-keys-for-windows-forms-controls"></a>如何：创建 Windows 窗体控件的访问键
*访问密钥*菜单、 菜单项或如按钮控件的标签的文本中带下划线的字符。 具有访问密钥，用户可以"单击"按钮通过同时按下 ALT 键和预定义的访问键。 例如，如果某个按钮可运行一个过程来打印窗体，因此其`Text`属性设置为"打印"之前的字母"P"使得字母"P"以在运行时中会带有下划线的按钮文本中添加一个与号。 用户可以运行该命令通过按 ALT + P 与按钮相关联。 不能具有不能接收焦点的控件的访问密钥。  
  
### <a name="to-create-an-access-key-for-a-control"></a>若要创建的控件的访问密钥  
  
1.  设置`Text`属性将设成快捷键的字母前为一个字符串，包含一个 & 号 (&)。  
  
    ```vb  
    ' Set the letter "P" as an access key.  
    Button1.Text = "&Print"  
    ```  
  
    ```csharp  
    // Set the letter "P" as an access key.  
    button1.Text = "&Print";  
    ```  
  
    ```cpp  
    // Set the letter "P" as an access key.  
    button1->Text = "&Print";  
    ```  
  
    > [!NOTE]
    >  若要而无需创建访问键，在标题中包含 & 符，包括两个 & 号 (& &)。 一个与号显示的标题中，带下划线的任何字符。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Button>  
 [如何：响应 Windows 窗体 Button 控件单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [如何：设置 Windows 窗体控件显示的文本](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [标记各个 Windows 窗体控件并创建它们的快捷键](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
