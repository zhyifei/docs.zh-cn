---
title: "处理用户输入"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c3da2c4661acdb358c38fb871de70fd470f7991
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="handling-user-input"></a>处理用户输入
本主题描述由提供的主要键盘和鼠标事件<xref:System.Windows.Forms.Control?displayProperty=nameWithType>。 处理事件时，控件作者应重写受保护的 `On`*EventName* 方法，而不是向事件附加委托。 若要查看事件，请参阅[从组件引发事件](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0)。  
  
> [!NOTE]
>  如果没有与某个事件，基本类的实例关联的数据<xref:System.EventArgs>作为的自变量传递`On` *EventName*方法。  
  
## <a name="keyboard-events"></a>键盘事件  
 你的控件可以处理的常见键盘事件是<xref:System.Windows.Forms.Control.KeyDown>， <xref:System.Windows.Forms.Control.KeyPress>，和<xref:System.Windows.Forms.Control.KeyUp>。  
  
|事件名称|要重写的方法|事件说明|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|仅在最初按下键时引发。|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|每次按键时引发。 如果按住某个键，<xref:System.Windows.Forms.Control.KeyPress>由操作系统定义的重复速率引发事件。|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|在松开某个键时引发。|  
  
> [!NOTE]
>  处理键盘输入比重写上表中的事件要复杂得多，这超出了本主题的讨论范围。 有关详细信息，请参阅 [Windows 窗体中的用户输入](../../../../docs/framework/winforms/user-input-in-windows-forms.md)。  
  
## <a name="mouse-events"></a>鼠标事件  
 你的控件可以处理的鼠标事件<xref:System.Windows.Forms.Control.MouseDown>， <xref:System.Windows.Forms.Control.MouseEnter>， <xref:System.Windows.Forms.Control.MouseHover>， <xref:System.Windows.Forms.Control.MouseLeave>， <xref:System.Windows.Forms.Control.MouseMove>，和<xref:System.Windows.Forms.Control.MouseUp>。  
  
|事件名称|要重写的方法|事件说明|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|指针位于控件上时，按下鼠标按钮会引发该事件。|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|指针首次进入控件区域时引发。|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|指针悬停在控件上时引发。|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|指针离开控件区域时引发。|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|指针在控件区域中移动时引发。|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|指针位于控件上或指针离开控件区域时，松开鼠标按钮会引发该事件。|  
  
 下面的代码段显示了的重写示例<xref:System.Windows.Forms.Control.MouseDown>事件。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 下面的代码段显示了的重写示例<xref:System.Windows.Forms.Control.MouseMove>事件。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 下面的代码段显示了的重写示例<xref:System.Windows.Forms.Control.MouseUp>事件。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 有关 `FlashTrackBar` 示例的完整源代码，请参阅[如何：创建显示进度的 Windows 窗体控件](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)。  
  
## <a name="see-also"></a>另请参阅  
 [Windows 窗体控件中的事件](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [定义事件](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [事件](../../../../docs/standard/events/index.md)  
 [Windows 窗体中的用户输入](../../../../docs/framework/winforms/user-input-in-windows-forms.md)
