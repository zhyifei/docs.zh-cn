---
title: 如何：使用设计器为 Windows 窗体控件创建访问键
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], access keys
- Button control [Windows Forms], access keys
- dialog box controls [Windows Forms], mnemonics
- access keys [Windows Forms], creating for controls
- mnemonics [Windows Forms], adding to dialog box controls
- ampersand character in shortcut key
- Windows Forms controls, access keys
- examples [Windows Forms], controls
- Text property [Windows Forms], specifying access keys for controls
- keyboard shortcuts [Windows Forms], creating for controls
- access keys [Windows Forms], Windows Forms
- ALT key
ms.assetid: 4c374c4c-4ca9-4a68-ac96-9dc3ab0f518a
ms.openlocfilehash: 023973e7fa4ab1e8b802d8c7cd8abef8201ed720
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532546"
---
# <a name="how-to-create-access-keys-for-windows-forms-controls-using-the-designer"></a>如何：使用设计器为 Windows 窗体控件创建访问键
*访问密钥*菜单、 菜单项或如按钮控件的标签的文本中带下划线的字符。 它使用户能够通过同时按下 ALT 键和预定义的访问键"单击"按钮。 例如，如果某个按钮可运行一个过程来打印窗体，因此其`Text`"P"使得字母"P"以显示为带有下划线的按钮文本中在运行时的字母前到"打印，"添加一个与号 (&) 设置属性。 用户可以运行该命令通过按 ALT + P 与按钮相关联。 不能具有不能接收焦点的控件的访问密钥。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-create-an-access-key-for-a-control"></a>若要创建的控件的访问密钥  
  
1.  在**属性**窗口中，设置`Text`属性将成为访问键的字母前为一个字符串，包含一个 & 号 (&)。 例如，若要设置为访问键的字母"P"，键入**和打印**到网格。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Button>  
 [如何：响应 Windows 窗体 Button 控件单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [如何：设置 Windows 窗体控件显示的文本](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [标记各个 Windows 窗体控件并创建它们的快捷键](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
