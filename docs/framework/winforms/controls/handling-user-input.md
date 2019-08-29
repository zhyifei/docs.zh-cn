---
title: 处理用户输入
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: f92b742c3f6feec72e5b3150204d7d984636281d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934093"
---
# <a name="handling-user-input"></a>处理用户输入
本主题介绍提供<xref:System.Windows.Forms.Control?displayProperty=nameWithType>的主键盘和鼠标事件。 处理事件时，控件作者应重写受保护的 `On`*EventName* 方法，而不是向事件附加委托。 若要查看事件，请参阅[从组件引发事件](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120))。  
  
> [!NOTE]
> 如果没有与某个事件相关联的数据, 则<xref:System.EventArgs>会将基类的一个实例作为参数传递`On`到*事件名称*方法。  
  
## <a name="keyboard-events"></a>键盘事件  
 控件可以处理的常见键盘事件为<xref:System.Windows.Forms.Control.KeyDown>、 <xref:System.Windows.Forms.Control.KeyPress>和<xref:System.Windows.Forms.Control.KeyUp>。  
  
|事件名称|要重写的方法|事件说明|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|仅在最初按下键时引发。|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|每次按键时引发。 如果某个键处于关闭状态, <xref:System.Windows.Forms.Control.KeyPress>则按操作系统定义的重复速率引发事件。|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|在松开某个键时引发。|  
  
> [!NOTE]
> 处理键盘输入比重写上表中的事件要复杂得多，这超出了本主题的讨论范围。 有关详细信息，请参阅 [Windows 窗体中的用户输入](../user-input-in-windows-forms.md)。  
  
## <a name="mouse-events"></a>鼠标事件  
 控件可以处理的鼠标事件包括<xref:System.Windows.Forms.Control.MouseDown> <xref:System.Windows.Forms.Control.MouseHover>、 <xref:System.Windows.Forms.Control.MouseEnter> <xref:System.Windows.Forms.Control.MouseLeave> <xref:System.Windows.Forms.Control.MouseMove>、、、和<xref:System.Windows.Forms.Control.MouseUp>。  
  
|事件名称|要重写的方法|事件说明|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|指针位于控件上时，按下鼠标按钮会引发该事件。|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|指针首次进入控件区域时引发。|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|指针悬停在控件上时引发。|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|指针离开控件区域时引发。|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|指针在控件区域中移动时引发。|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|指针位于控件上或指针离开控件区域时，松开鼠标按钮会引发该事件。|  
  
 下面的代码片段演示了一个重写<xref:System.Windows.Forms.Control.MouseDown>事件的示例。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 下面的代码片段演示了一个重写<xref:System.Windows.Forms.Control.MouseMove>事件的示例。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 下面的代码片段演示了一个重写<xref:System.Windows.Forms.Control.MouseUp>事件的示例。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 有关该`FlashTrackBar`示例的完整源代码, 请参阅[如何:创建显示进度](how-to-create-a-windows-forms-control-that-shows-progress.md)的 Windows 窗体控件。  
  
## <a name="see-also"></a>请参阅

- [Windows 窗体控件中的事件](events-in-windows-forms-controls.md)
- [定义事件](defining-an-event-in-windows-forms-controls.md)
- [事件](../../../standard/events/index.md)
- [Windows 窗体中的用户输入](../user-input-in-windows-forms.md)
