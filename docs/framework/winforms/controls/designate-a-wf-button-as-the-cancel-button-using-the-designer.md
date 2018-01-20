---
title: "如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- buttons [Windows Forms], cancel buttons
- Button control [Windows Forms], designating as cancel button
ms.assetid: 30e77d9c-d565-4ab5-a84a-62c043af8822
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0772fd01c2431df3b3aea034616913bd44dc0f05
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-designate-a-windows-forms-button-as-the-cancel-button-using-the-designer"></a>如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮
在任何 Windows 窗体中，你可以指定<xref:System.Windows.Forms.Button>控件取消按钮。 每当用户按 ESC 键时，无论哪个窗体上的其他控件具有焦点，则单击取消按钮。 通常，这样的按钮进行编程，使用户能够快速退出操作，而无须执行任何操作。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-designate-the-cancel-button"></a>若要指定取消按钮  
  
1.  选择按钮所驻留的表单。  
  
2.  在**属性**窗口中，设置窗体的<xref:System.Windows.Forms.Form.CancelButton%2A>属性<xref:System.Windows.Forms.Button>控件的名称。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Form.CancelButton%2A>  
 [Button 控件概述](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [如何选择 Windows 窗体 Button 控件](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [如何：响应 Windows 窗体 Button 控件单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [如何：使用设计器将 Windows 窗体按钮指定为“接受”按钮](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [Button 控件](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
