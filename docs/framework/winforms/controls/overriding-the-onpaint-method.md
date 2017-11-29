---
title: "重写 OnPaint 方法"
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
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 41205f7f0ec21e27b97d0b12415fca89ae526552
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="overriding-the-onpaint-method"></a>重写 OnPaint 方法
重写中定义的任何事件的基本步骤[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]相同，并且以下列表中汇总。  
  
#### <a name="to-override-an-inherited-event"></a>若要重写继承的事件  
  
1.  重写受保护`On` *EventName*方法。  
  
2.  调用`On` *EventName*从重写基类方法的`On` *EventName*方法，以便已注册的委托对事件进行接收。  
  
 <xref:System.Windows.Forms.Control.Paint>此处详细地讨论事件，因为每个 Windows 窗体控件必须重写<xref:System.Windows.Forms.Control.Paint>从它继承的事件<xref:System.Windows.Forms.Control>。 基<xref:System.Windows.Forms.Control>类不知道如何派生的控件需要绘制，而不提供中的任何绘制逻辑<xref:System.Windows.Forms.Control.OnPaint%2A>方法。 <xref:System.Windows.Forms.Control.OnPaint%2A>方法<xref:System.Windows.Forms.Control>只需将调度<xref:System.Windows.Forms.Control.Paint>到已注册的事件接收器的事件。  
  
 如果你通过中的示例过[如何： 开发简单的 Windows 窗体控件](../../../../docs/framework/winforms/controls/how-to-develop-a-simple-windows-forms-control.md)，你已经看到举例说明重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。 下面的代码片段取自该示例。  
  
```vb  
Public Class FirstControl  
   Inherits Control  
  
   Public Sub New()  
   End Sub  
  
   Protected Overrides Sub OnPaint(e As PaintEventArgs)  
      ' Call the OnPaint method of the base class.  
      MyBase.OnPaint(e)  
      ' Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, New SolidBrush(ForeColor), RectangleF.op_Implicit(ClientRectangle))  
   End Sub  
End Class   
```  
  
```csharp  
public class FirstControl : Control{  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }   
}   
```  
  
 <xref:System.Windows.Forms.PaintEventArgs>类包含的数据的<xref:System.Windows.Forms.Control.Paint>事件。 它具有两个属性，如下面的代码中所示。  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   ...  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property   
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs {  
...  
    public System.Drawing.Rectangle ClipRectangle {}  
    public System.Drawing.Graphics Graphics {}  
...  
}  
```  
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>是要绘制的矩形和<xref:System.Windows.Forms.PaintEventArgs.Graphics%2A>属性是指<xref:System.Drawing.Graphics>对象。 中的类<xref:System.Drawing?displayProperty=nameWithType>管理命名空间提供功能的访问的类[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]，新的 Windows 图形库。 <xref:System.Drawing.Graphics>对象具有方法来绘制点、 字符串、 线条、 弧、 省略号，以及许多其他形状。  
  
 一个控件时，将调用其<xref:System.Windows.Forms.Control.OnPaint%2A>方法需要更改其可视显示时。 此方法将依次引发<xref:System.Windows.Forms.Control.Paint>事件。  
  
## <a name="see-also"></a>另请参阅  
 [事件](../../../../docs/standard/events/index.md)  
 [呈现 Windows 窗体控件](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 [定义事件](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)
