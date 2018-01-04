---
title: "Button 控件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Button
helpviewer_keywords:
- Button control [Windows Forms], about Button control
- buttons [Windows Forms], about buttons
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e04b99c9d85ae92ad4d013abc01c5b16914fe1c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="button-control-overview-windows-forms"></a>Button 控件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.Button> 控件允许用户通过单击来执行某项操作。 单击该按钮时，看上去它像是被按下并释放。 无论何时用户单击按钮，<xref:System.Windows.Forms.Control.Click>调用事件处理程序。 你将代码放置在<xref:System.Windows.Forms.Control.Click>事件处理程序来执行你选择的任何操作。  
  
 按钮上显示的文本包含在<xref:System.Windows.Forms.Control.Text%2A>属性。 如果你的文本超过按钮的宽度，它将换行到下一行。 但是，它将剪切如果该控件所能容纳的窗体的整体高度。 有关详细信息，请参阅[如何： 设置 Windows 窗体控件显示的文本](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)。 <xref:System.Windows.Forms.Control.Text%2A>属性可以包含的访问密钥，这样用户就可以通过按 ALT 键和访问密钥"单击"的控件。 有关详细信息，请参阅[如何： 为 Windows 窗体控件创建访问键](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)。 由控制文本的外观<xref:System.Windows.Forms.Control.Font%2A>属性和<xref:System.Windows.Forms.ButtonBase.TextAlign%2A>属性。  
  
 <xref:System.Windows.Forms.Button>控件还可以显示使用的图像<xref:System.Windows.Forms.ButtonBase.Image%2A>和<xref:System.Windows.Forms.ButtonBase.ImageList%2A>属性。 有关详细信息，请参阅[如何： 设置 Windows 窗体控件显示的图像](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Button>  
 [如何：响应 Windows 窗体 Button 控件单击](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)  
 [如何选择 Windows 窗体 Button 控件](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [如何：使用设计器将 Windows 窗体按钮指定为“接受”按钮](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)  
 [如何：使用设计器将 Windows 窗体按钮指定为“取消”按钮](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)  
 [Button 控件](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
