---
title: "如何：创建只读文本框（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 264ef1a7c1f121f889d57dcb0e36e216610418fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a>如何：创建只读文本框（Windows 窗体）
可以将可编辑的 Windows 窗体文本框转换为只读的控件。 例如，在文本框中可能会显示一个值，通常编辑，但可能不是由于应用程序的状态的当前。  
  
### <a name="to-create-a-read-only-text-box"></a>若要创建只读文本框  
  
1.  设置<xref:System.Windows.Forms.TextBox>控件的<xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>属性`true`。 属性设置为`true`，用户仍可以向下滚动并突出显示但不允许更改文本框中的文本。 A**复制**命令在文本框中，将能正常运行但**剪切**和**粘贴**命令不可。  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A>属性仅会影响在运行时的用户交互。 你仍可更改文本框内容以编程方式在运行时更改<xref:System.Windows.Forms.TextBox.Text%2A>的文本框中的属性。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.TextBox>  
 [TextBox 控件概述](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)  
 [如何：在 Windows 窗体 TextBox 控件中控制插入点](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 [如何：使用 Windows 窗体 TextBox 控件创建密码文本框](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 [如何：在字符串中添加引号](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 [如何：在 Windows 窗体 TextBox 控件中选择文本](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)  
 [如何：在 Windows 窗体 TextBox 控件中查看多个行](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 [TextBox 控件](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)
