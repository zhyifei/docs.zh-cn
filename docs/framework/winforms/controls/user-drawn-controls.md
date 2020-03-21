---
title: 用户描述的控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
ms.openlocfilehash: c68c8c88376cfe7295962264c466030115f2f3db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182009"
---
# <a name="user-drawn-controls"></a>用户描述的控件
.NET 框架使您能够轻松开发自己的控件。 您可以创建用户控件，这是一组由代码绑定在一起的标准控件，也可以从零开始设计自己的控件。 您甚至可以使用继承创建从现有控件继承的控件，并添加到其固有功能。 无论您使用何种方法，.NET Framework 都提供了为创建的任何控件绘制自定义图形界面的功能。  
  
 控件的绘制是通过在控件方法中执行代码来完成的<xref:System.Windows.Forms.Control.OnPaint%2A>。 <xref:System.Windows.Forms.Control.OnPaint%2A>方法的单个参数是一个<xref:System.Windows.Forms.PaintEventArgs>对象，该对象提供呈现控件所需的所有信息和功能。 提供<xref:System.Windows.Forms.PaintEventArgs>将在呈现控件时使用的两个主体对象作为属性：  
  
- <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>对象 - 表示将绘制的控件部分的矩形。 这可以是整个控件，也可以是控件的一部分，具体取决于控件的绘制方式。  
  
- <xref:System.Drawing.Graphics>对象 - 封装多个面向图形的对象和方法，这些对象和方法提供了绘制控件所需的功能。  
  
 有关<xref:System.Drawing.Graphics>对象以及如何使用它的详细信息，请参阅[如何：为绘图创建图形对象](../advanced/how-to-create-graphics-objects-for-drawing.md)。  
  
 每当<xref:System.Windows.Forms.Control.OnPaint%2A>在屏幕上绘制或刷新控件时，都会触发该事件，并且<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>对象表示将在其中进行绘制的矩形。 如果需要刷新整个控件，将<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>表示整个控件的大小。 但是，如果只需要刷新控件的一部分，则<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>对象将仅表示需要重绘的区域。 这种情况的一个示例是，当控件被用户界面中的另一个控件或窗体部分遮盖时。  
  
 从<xref:System.Windows.Forms.Control>类继承时，必须重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法并在 其中提供图形呈现代码。 如果要向用户控件或继承的控件提供自定义图形界面，还可以重写<xref:System.Windows.Forms.Control.OnPaint%2A>该方法。 下面显示了一个示例：  
  
```vb  
Protected Overrides Sub OnPaint(ByVal e As PaintEventArgs)  
   ' Call the OnPaint method of the base class.  
   MyBase.OnPaint(e)  
  
   ' Declare and instantiate a drawing pen.  
   Using myPen As System.Drawing.Pen = New System.Drawing.Pen(Color.Aqua)  
      ' Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, New Rectangle(Me.Location, Me.Size))  
   End Using
End Sub  
```  
  
```csharp  
protected override void OnPaint(PaintEventArgs e)  
{  
   // Call the OnPaint method of the base class.  
   base.OnPaint(e);  
  
   // Declare and instantiate a new pen.  
   using (System.Drawing.Pen myPen = new System.Drawing.Pen(Color.Aqua))  
   {
      // Draw an aqua rectangle in the rectangle represented by the control.  
      e.Graphics.DrawRectangle(myPen, new Rectangle(this.Location,
         this.Size));  
   }
}  
```  
  
 前面的示例演示如何使用非常简单的图形表示形式呈现控件。 它调用基<xref:System.Windows.Forms.Control.OnPaint%2A>类的方法，它创建一个<xref:System.Drawing.Pen>要用来绘制的对象，最后在由 和<xref:System.Windows.Forms.Control.Location%2A><xref:System.Windows.Forms.Control.Size%2A>的 控件确定的矩形中绘制椭圆。 尽管大多数呈现代码将明显比这更复杂，但此示例演示了<xref:System.Drawing.Graphics><xref:System.Windows.Forms.PaintEventArgs>对象中包含的对象的使用。 请注意，如果要从已具有图形表示形式（如<xref:System.Windows.Forms.UserControl>或<xref:System.Windows.Forms.Button>）的类继承，并且不希望将该表示形式合并到渲染中，则不应调用基类<xref:System.Windows.Forms.Control.OnPaint%2A>的方法。  
  
 控件方法中<xref:System.Windows.Forms.Control.OnPaint%2A>的代码将在首次绘制控件时以及刷新控件时执行。 为确保每次调整控件大小时重新绘制控件，请向控件的构造函数添加以下行：  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> 使用<xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType>属性实现非矩形控件。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [如何：创建用于绘制的 Graphics 对象](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [构成控件](constituent-controls.md)
- [各种自定义控件](varieties-of-custom-controls.md)
