---
title: "用户描述的控件"
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
- custom controls [Windows Forms], user-drawn
- OnPaint method [Windows Forms]
- user-drawn controls [Windows Forms]
ms.assetid: 034af4b5-457f-4160-a937-22891817faa8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e9e486058850616c2304ce0032c35baa855fdf2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="user-drawn-controls"></a>用户描述的控件
.NET Framework 可为你提供的功能能够轻松地开发你自己的控件。 你可以创建一个用户控件，它是一组由代码绑定在一起的标准控件，或可以向上设计您自己的控件从零开始。 你甚至可以使用继承创建继承自现有控件的控件并将添加到其固有的功能。 无论你使用何种方法.NET Framework 提供了用于绘制自定义图形界面为你创建的任何控件的功能。  
  
 通过该控件的代码的执行实现控件的绘制<xref:System.Windows.Forms.Control.OnPaint%2A>方法。 单个参数<xref:System.Windows.Forms.Control.OnPaint%2A>方法是<xref:System.Windows.Forms.PaintEventArgs>对象，它提供的所有信息和呈现控件所需的功能。 <xref:System.Windows.Forms.PaintEventArgs>提供作为属性的两个将使用在你的控件呈现的主体对象：  
  
-   <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>对象的表示的部分将绘制的控件的矩形。 这可以是整个控件或根据如何绘制控件的控件的一部分。  
  
-   <xref:System.Drawing.Graphics>对象-封装几个面向图形的对象和提供必要的功能，绘制控件的方法。  
  
 有关详细信息<xref:System.Drawing.Graphics>对象以及如何使用它，请参阅[如何： 创建图形对象的绘图](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)。  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>绘制或在屏幕上，刷新控件时激发事件和<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>对象表示在其中绘制会发生的矩形。 如果整个控件需要刷新，<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>将表示整个控件的大小。 如果只有控件的一部分需要刷新，但是，<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>对象将表示仅需要重绘的区域。 这种情况的示例将时控件部分已由另一个控件或窗体中的用户界面遮盖。  
  
 从继承时<xref:System.Windows.Forms.Control>类，必须重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法并提供中的图形呈现代码。 如果你想要提供到用户控件或继承的控件的自定义图形界面，你可以也会这样通过重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。 一个示例所示：  
  
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
  
 前面的示例演示如何呈现具有非常简单的图形表示形式的控件。 它调用<xref:System.Windows.Forms.Control.OnPaint%2A>基本类的方法，它创建<xref:System.Drawing.Pen>其中进行绘制，对象，该矩形中的绘制一个椭圆由最后<xref:System.Windows.Forms.Control.Location%2A>和<xref:System.Windows.Forms.Control.Size%2A>的控件。 虽然大多数呈现代码显著比这更复杂，但此示例演示如何使用<xref:System.Drawing.Graphics>中包含对象<xref:System.Windows.Forms.PaintEventArgs>对象。 请注意，如果从已有的图形表示，例如一个类继承<xref:System.Windows.Forms.UserControl>或<xref:System.Windows.Forms.Button>，并且不希望将该表示形式合并到呈现，不应调用基类的<xref:System.Windows.Forms.Control.OnPaint%2A>方法。  
  
 中的代码<xref:System.Windows.Forms.Control.OnPaint%2A>的控件的方法将执行在首次绘制控件后，只要它刷新。 若要确保每次调整后，重绘控件，请向您的控件的构造函数添加以下行：  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  使用<xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType>属性来实现非矩形控件。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Control.Region%2A>  
 <xref:System.Windows.Forms.ControlStyles>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Windows.Forms.PaintEventArgs>  
 [如何：创建用于绘制的图形对象](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [构成控件](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 [各种自定义控件](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)
