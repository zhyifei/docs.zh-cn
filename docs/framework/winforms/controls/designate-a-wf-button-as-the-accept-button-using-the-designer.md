---
title: "如何：使用设计器将 Windows 窗体按钮指定为“接受”按钮"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: a1da0590-755f-49f2-aca7-609fac6351bf
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 044fa4ab2e9a37038e9db9a2784fad4190713806
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button-using-the-designer"></a>如何：使用设计器将 Windows 窗体按钮指定为“接受”按钮
在任何 Windows 窗体中，你可以指定<xref:System.Windows.Forms.Button>控件接受按钮，也称为默认按钮。 每当用户按 ENTER 键，无论哪个窗体上的其他控件具有焦点单击默认按钮。 为以下情形时具有焦点的控件是另一个按钮的异常-将在这种情况下，单击具有焦点的按钮-/ 多行文本框中，或自定义控件捕获 ENTER 键。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-designate-the-accept-button"></a>若要指定接受按钮  
  
1.  选择按钮所驻留的表单。  
  
2.  在**属性**窗口中，设置窗体的<xref:System.Windows.Forms.Form.AcceptButton%2A>属性<xref:System.Windows.Forms.Button>控件的名称。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.Form.AcceptButton%2A>  
 [Button 控件概述](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [如何选择 Windows 窗体 Button 控件](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [如何：响应 Windows 窗体 Button 控件单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [Button 控件](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
