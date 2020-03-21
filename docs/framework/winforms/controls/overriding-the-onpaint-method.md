---
title: 重写 OnPaint 方法
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Paint event [Windows Forms], handling in Windows Forms custom control
- OnPaint method [Windows Forms], overriding in Windows Forms custom controls
ms.assetid: e9ca2723-0107-4540-bb21-4f5ffb4a9906
ms.openlocfilehash: 863726a6264f01de9f00296b4a64b9fd1bb96765
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182033"
---
# <a name="overriding-the-onpaint-method"></a>重写 OnPaint 方法
重写 .NET 框架中定义的任何事件的基本步骤相同，并汇总如下列表中。  
  
#### <a name="to-override-an-inherited-event"></a>重写继承的事件  
  
1. 重写受保护的`On`*事件名称*方法。  
  
2. `On`从重写`On`*的 EventName*方法调用基类的*EventName*方法，以便注册代理接收事件。  
  
 此处<xref:System.Windows.Forms.Control.Paint>将详细讨论该事件，因为每个 Windows 窗体控件都必须<xref:System.Windows.Forms.Control.Paint>覆盖从 继承的事件<xref:System.Windows.Forms.Control>。 基<xref:System.Windows.Forms.Control>类不知道如何绘制派生控件，也不在<xref:System.Windows.Forms.Control.OnPaint%2A>方法中提供任何绘制逻辑。 <xref:System.Windows.Forms.Control>简单地将<xref:System.Windows.Forms.Control.Paint>事件调度给已注册的事件接收器<xref:System.Windows.Forms.Control.OnPaint%2A>的方法。  
  
 如果您通过["如何：开发一个简单的 Windows 窗体控件"](how-to-develop-a-simple-windows-forms-control.md)中的示例，则您看到了重写<xref:System.Windows.Forms.Control.OnPaint%2A>该方法的示例。 以下代码片段取自该示例。  
  
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
public class FirstControl : Control {  
   public FirstControl() {}  
   protected override void OnPaint(PaintEventArgs e) {  
      // Call the OnPaint method of the base class.  
      base.OnPaint(e);  
      // Call methods of the System.Drawing.Graphics object.  
      e.Graphics.DrawString(Text, Font, new SolidBrush(ForeColor), ClientRectangle);  
   }
}
```  
  
 类<xref:System.Windows.Forms.PaintEventArgs>包含<xref:System.Windows.Forms.Control.Paint>事件的数据。 它有两个属性，如下代码所示。  
  
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
  
 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>是要绘制的矩形，<xref:System.Windows.Forms.PaintEventArgs.Graphics%2A>属性引用<xref:System.Drawing.Graphics>对象。 命名空间中的<xref:System.Drawing?displayProperty=nameWithType>类是托管类，提供对 GDI+ 功能（新的 Windows 图形库）的功能的访问。 该<xref:System.Drawing.Graphics>对象具有绘制点、字符串、线条、圆弧、椭圆和许多其他形状的方法。  
  
 控件每当需要更改其<xref:System.Windows.Forms.Control.OnPaint%2A>可视显示时调用其方法。 此方法反过来引发事件<xref:System.Windows.Forms.Control.Paint>。  
  
## <a name="see-also"></a>另请参阅

- [事件](../../../standard/events/index.md)
- [呈现 Windows 窗体控件](rendering-a-windows-forms-control.md)
- [定义事件](defining-an-event-in-windows-forms-controls.md)
