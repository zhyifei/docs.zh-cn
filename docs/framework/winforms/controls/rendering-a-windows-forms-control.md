---
title: "呈现 Windows 窗体控件"
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
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 07e75bd44ab960744224c2d2d2cf2e53c42860fa
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="rendering-a-windows-forms-control"></a>呈现 Windows 窗体控件
呈现是指创建在用户的屏幕上的可视表示形式的过程。 Windows 窗体使用[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]（的新 Windows 图形库） 呈现。 提供对访问托管的类[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]中<xref:System.Drawing?displayProperty=nameWithType>命名空间及其子命名空间。  
  
 控件呈现中包括以下元素：  
  
-   提供的基类的绘制功能<xref:System.Windows.Forms.Control?displayProperty=nameWithType>。  
  
-   重要元素[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]图形库。  
  
-   该几何图形的绘图区域。  
  
-   用于释放图形资源的过程。  
  
## <a name="drawing-functionality-provided-by-control"></a>绘制控件提供功能  
 基类<xref:System.Windows.Forms.Control>绘制可通过提供功能其<xref:System.Windows.Forms.Control.Paint>事件。 中的控件引发<xref:System.Windows.Forms.Control.Paint>只要它需要更新显示的事件。 有关.NET Framework 中的事件的详细信息，请参阅[处理和引发事件](../../../../docs/standard/events/index.md)。  
  
 事件数据类<xref:System.Windows.Forms.Control.Paint>事件， <xref:System.Windows.Forms.PaintEventArgs>，包含所需的绘制控件的数据-图形对象以及表示要在中绘制的区域的矩形对象的句柄。 中显示这些对象在下面的代码段中加粗。  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   Implements IDisposable  
  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property  
   ' Other properties and methods.  
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs, IDisposable {  
public System.Drawing.Rectangle ClipRectangle {get;}  
public System.Drawing.Graphics Graphics {get;}  
// Other properties and methods.  
...  
}  
```  
  
 <xref:System.Drawing.Graphics>是封装绘制功能的托管的类的讨论中所述[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]本主题中更高版本。 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>是的一个实例<xref:System.Drawing.Rectangle>结构和定义可以在其中绘制控件的可用区域。 控件开发人员可以计算<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>使用<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>控件，如本主题中后面的几何图形的讨论中所述的属性。  
  
 控件必须通过重写提供呈现逻辑<xref:System.Windows.Forms.Control.OnPaint%2A>方法，它继承自<xref:System.Windows.Forms.Control>。 <xref:System.Windows.Forms.Control.OnPaint%2A>获取访问权限的图形对象和要通过在绘制的矩形<xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A>和<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>属性<xref:System.Windows.Forms.PaintEventArgs>实例传递给它。  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>基方法<xref:System.Windows.Forms.Control>类不实现任何绘制的功能，但仅仅是调用与注册的事件委托<xref:System.Windows.Forms.Control.Paint>事件。 当你重写<xref:System.Windows.Forms.Control.OnPaint%2A>，通常应调用<xref:System.Windows.Forms.Control.OnPaint%2A>方法的基类，以便已注册的委托能够接收<xref:System.Windows.Forms.Control.Paint>事件。 但是，绘制其整个图面的控件不应调用基类的<xref:System.Windows.Forms.Control.OnPaint%2A>，因为这将带来闪烁。 有关的重写示例<xref:System.Windows.Forms.Control.OnPaint%2A>事件，请参阅[如何： 创建 Windows 窗体控件，显示进度](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)。  
  
> [!NOTE]
>  不会调用<xref:System.Windows.Forms.Control.OnPaint%2A>直接从控件; 相反，调用<xref:System.Windows.Forms.Control.Invalidate%2A>方法 (继承自<xref:System.Windows.Forms.Control>) 或通过某些其他方法调用<xref:System.Windows.Forms.Control.Invalidate%2A>。 <xref:System.Windows.Forms.Control.Invalidate%2A>方法反过来调用<xref:System.Windows.Forms.Control.OnPaint%2A>。 <xref:System.Windows.Forms.Control.Invalidate%2A>方法重载，并根据自变量提供给<xref:System.Windows.Forms.Control.Invalidate%2A> `e`，控件重绘其部分或全部其屏幕区域。  
  
 基<xref:System.Windows.Forms.Control>类定义用于绘制的另一种方法-<xref:System.Windows.Forms.Control.OnPaintBackground%2A>方法。  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>绘制背景 (，从而形状) 的窗口，并保证要快速完成，而<xref:System.Windows.Forms.Control.OnPaint%2A>绘制详细信息，并且可能会降低，因为各个绘制请求合并成一个<xref:System.Windows.Forms.Control.Paint>涵盖所有方面必须具备的事件在重绘。 你可能想要调用<xref:System.Windows.Forms.Control.OnPaintBackground%2A>如果，例如，你想要绘制控件的颜色渐变背景。  
  
 虽然<xref:System.Windows.Forms.Control.OnPaintBackground%2A>具有类似于事件的术语和采用相同的自变量作为`OnPaint`方法，<xref:System.Windows.Forms.Control.OnPaintBackground%2A>不是真正的事件方法。 没有任何`PaintBackground`事件和<xref:System.Windows.Forms.Control.OnPaintBackground%2A>不会调用事件委托。 在重写<xref:System.Windows.Forms.Control.OnPaintBackground%2A>方法，派生的类不需要调用<xref:System.Windows.Forms.Control.OnPaintBackground%2A>其基本类的方法。  
  
## <a name="gdi-basics"></a>GDI + 基础知识  
 <xref:System.Drawing.Graphics>类提供绘制圆形、 三角形、 弧线和省略号，如各种形状的方法，以及用于显示文本的方法。 <xref:System.Drawing?displayProperty=nameWithType>命名空间和及其子命名空间包含类，用于封装各种图形元素，如形状 （圆形、 矩形、 弧线和其他）、 颜色、 字体、 画笔和等等。 有关详细信息[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]，请参阅[使用托管图形类](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)。 Essentials[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]中也介绍了[如何： 创建 Windows 窗体控件，显示进度](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)。  
  
## <a name="geometry-of-the-drawing-region"></a>绘图区域的几何图形  
 <xref:System.Windows.Forms.Control.ClientRectangle%2A>控件的属性指定可供用户的屏幕上的控件的矩形区域而<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>属性<xref:System.Windows.Forms.PaintEventArgs>指定实际绘制的区域。 (请记住，完成绘制<xref:System.Windows.Forms.Control.Paint>事件方法采用<xref:System.Windows.Forms.PaintEventArgs>作为其自变量的实例)。 控件可能需要绘制仅为一部分其可用的区域，如是控件的显示更改这种情况时一小部分。 在这些情况下，控件开发人员必须计算实际的矩形绘制，并将传递给<xref:System.Windows.Forms.Control.Invalidate%2A>。 重载的版本<xref:System.Windows.Forms.Control.Invalidate%2A>采用<xref:System.Drawing.Rectangle>或<xref:System.Drawing.Region>作为自变量使用该自变量生成<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>属性<xref:System.Windows.Forms.PaintEventArgs>。  
  
 以下代码段显示了`FlashTrackBar`自定义控件计算以进行绘制的矩形区域。 `client`变量表示<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>属性。 有关完整示例，请参阅[如何： 创建 Windows 窗体控件，显示进度](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>释放图形资源  
 图形对象非常昂贵，因为它们使用系统资源。 此类对象包含的实例<xref:System.Drawing.Graphics?displayProperty=nameWithType>类的实例以及<xref:System.Drawing.Brush?displayProperty=nameWithType>， <xref:System.Drawing.Pen?displayProperty=nameWithType>，和其他图形类。 务必创建图形资源，仅当你需要它并将其释放时立即在完成使用它。 如果你创建的类型的实现<xref:System.IDisposable>界面，请调用其<xref:System.IDisposable.Dispose%2A>方法完成后使用它以释放资源。  
  
 以下代码段显示了`FlashTrackBar`自定义控件需要创建和发布<xref:System.Drawing.Brush>资源。 有关完整的源代码，请参阅[如何： 创建 Windows 窗体控件，显示进度](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>另请参阅  
 [如何：创建显示进度的 Windows 窗体控件](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)
