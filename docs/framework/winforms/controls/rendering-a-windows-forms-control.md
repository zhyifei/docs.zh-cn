---
title: 呈现 Windows 窗体控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
ms.openlocfilehash: b24fbefac0dcfb666e25ad1d1726ef2cf8a5d84e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968277"
---
# <a name="rendering-a-windows-forms-control"></a>呈现 Windows 窗体控件
呈现是指在用户屏幕上创建视觉对象表示形式的过程。 Windows 窗体使用 GDI (新的 Windows 图形库) 来呈现。 提供对 GDI 的访问的托管类位于<xref:System.Drawing?displayProperty=nameWithType>命名空间及其子命名空间中。  
  
 控件呈现涉及以下元素:  
  
- 基类提供的绘制功能<xref:System.Windows.Forms.Control?displayProperty=nameWithType>。  
  
- GDI 图形库的重要元素。  
  
- 绘图区域的几何。  
  
- 用于释放图形资源的过程。  
  
## <a name="drawing-functionality-provided-by-control"></a>控件提供的绘制功能  
 基类<xref:System.Windows.Forms.Control>通过其<xref:System.Windows.Forms.Control.Paint>事件提供绘制功能。 每当控件需要更新<xref:System.Windows.Forms.Control.Paint>其显示时, 都会引发事件。 有关 .NET Framework 中事件的详细信息, 请参阅[处理和引发事件](../../../standard/events/index.md)。  
  
 <xref:System.Windows.Forms.Control.Paint>事件的事件数据类包含绘制控件所需的数据-图形对象的句柄和表示要在其中绘制的区域的矩形对象。 <xref:System.Windows.Forms.PaintEventArgs> 这些对象在以下代码片段中显示为粗体。  
  
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
  
 <xref:System.Drawing.Graphics>是一个封装了绘制功能的托管类, 如本主题后面的 GDI 讨论中所述。 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>是<xref:System.Drawing.Rectangle>结构的实例, 用于定义可在其中绘制控件的可用区域。 控件开发人员可以<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>使用控件的<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>属性计算, 如本主题后面的几何讨论中所述。  
  
 控件必须通过重写<xref:System.Windows.Forms.Control.OnPaint%2A>继承自<xref:System.Windows.Forms.Control>的方法来提供呈现逻辑。 <xref:System.Windows.Forms.Control.OnPaint%2A>获取对图形对象的访问, 以及通过<xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>传递给它的<xref:System.Windows.Forms.PaintEventArgs>实例的属性在中绘制的矩形。  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 基类<xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control.Paint>的方法不会实现任何绘制功能, 而只会调用向事件注册的事件委托。 <xref:System.Windows.Forms.Control> 重写<xref:System.Windows.Forms.Control.OnPaint%2A>时, 通常应<xref:System.Windows.Forms.Control.OnPaint%2A>调用基类的方法, 以便注册<xref:System.Windows.Forms.Control.Paint>的委托接收事件。 但是, 绘制整个图面的控件不应调用基类的<xref:System.Windows.Forms.Control.OnPaint%2A>, 因为这会引入闪烁。 有关替代<xref:System.Windows.Forms.Control.OnPaint%2A>事件的示例, [请参阅如何:创建显示进度](how-to-create-a-windows-forms-control-that-shows-progress.md)的 Windows 窗体控件。  
  
> [!NOTE]
> 不要直接从<xref:System.Windows.Forms.Control.OnPaint%2A>控件调用, 而应<xref:System.Windows.Forms.Control.Invalidate%2A>调用方法 (继承自<xref:System.Windows.Forms.Control>) 或调用的其他方法<xref:System.Windows.Forms.Control.Invalidate%2A>。 方法又会调用<xref:System.Windows.Forms.Control.OnPaint%2A>。 <xref:System.Windows.Forms.Control.Invalidate%2A> 重载方法时, 控件会重绘其部分或全部屏幕<xref:System.Windows.Forms.Control.Invalidate%2A>区域, 具体取决于提供给`e`的参数。 <xref:System.Windows.Forms.Control.Invalidate%2A>  
  
 基类<xref:System.Windows.Forms.Control>定义可用于绘制的<xref:System.Windows.Forms.Control.OnPaintBackground%2A>另一种方法, 即方法。  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>绘制窗口的背景 (进而使其成为一种形状), 并保证其速度非常快<xref:System.Windows.Forms.Control.OnPaint%2A> , 同时绘制详细信息并可能比较慢, 因为单个绘制请求合并<xref:System.Windows.Forms.Control.Paint>为一个事件, 该事件涵盖了需要重绘. 例如, <xref:System.Windows.Forms.Control.OnPaintBackground%2A>如果想要绘制控件的渐变颜色背景, 则可能需要调用。  
  
 虽然<xref:System.Windows.Forms.Control.OnPaintBackground%2A>具有类似事件的命名法并采用与`OnPaint`方法相同的参数, <xref:System.Windows.Forms.Control.OnPaintBackground%2A>但并不是真正的事件方法。 没有事件, 并且<xref:System.Windows.Forms.Control.OnPaintBackground%2A>不调用事件委托。 `PaintBackground` 重写<xref:System.Windows.Forms.Control.OnPaintBackground%2A>方法时, 派生类不需要调用其基类的<xref:System.Windows.Forms.Control.OnPaintBackground%2A>方法。  
  
## <a name="gdi-basics"></a>GDI + 基础知识  
 <xref:System.Drawing.Graphics>类提供用于绘制各种形状 (如圆、三角形、弧形和椭圆) 的方法, 以及用于显示文本的方法。 <xref:System.Drawing?displayProperty=nameWithType>命名空间及其子命名空间包含的类可封装图形元素 (如圆形、矩形、弧形等)、颜色、字体、画笔等。 有关 GDI 的详细信息, 请参阅[使用托管图形类](../advanced/using-managed-graphics-classes.md)。 还介绍[了 GDI 的基本原理。创建显示进度](how-to-create-a-windows-forms-control-that-shows-progress.md)的 Windows 窗体控件。  
  
## <a name="geometry-of-the-drawing-region"></a>绘图区域的几何图形  
 控件<xref:System.Windows.Forms.Control.ClientRectangle%2A>的属性指定可用于用户屏幕上的控件的矩形区域, <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>而的属性<xref:System.Windows.Forms.PaintEventArgs>指定实际绘制的区域。 (请记住, 在将<xref:System.Windows.Forms.Control.Paint> <xref:System.Windows.Forms.PaintEventArgs>实例作为其参数的事件方法中完成绘制)。 控件可能只需要绘制部分可用区域, 这种情况下, 当控件的小部分显示更改时。 在这些情况下, 控件开发人员必须计算要在其中<xref:System.Windows.Forms.Control.Invalidate%2A>进行绘制的实际矩形, 并将其传递给。 <xref:System.Windows.Forms.Control.Invalidate%2A> <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>采用或作为参数<xref:System.Windows.Forms.PaintEventArgs>的的重载版本使用该参数来生成的属性。 <xref:System.Drawing.Region> <xref:System.Drawing.Rectangle>  
  
 下面的代码段演示`FlashTrackBar`自定义控件如何计算要在中绘制的矩形区域。 `client` 变量<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>表示属性。 有关完整示例, 请参阅[如何:创建显示进度](how-to-create-a-windows-forms-control-that-shows-progress.md)的 Windows 窗体控件。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a>释放图形资源  
 图形对象开销高昂, 因为它们使用系统资源。 此<xref:System.Drawing.Graphics?displayProperty=nameWithType>类对象包括类的实例<xref:System.Drawing.Brush?displayProperty=nameWithType>, 以及、 <xref:System.Drawing.Pen?displayProperty=nameWithType>和其他图形类的实例。 只有在需要图形资源并在使用完毕后立即将其释放, 这一点非常重要。 如果创建实现<xref:System.IDisposable>接口的类型, 请在完成该操作<xref:System.IDisposable.Dispose%2A>后调用其方法, 以便释放资源。  
  
 下面的代码段演示`FlashTrackBar`自定义控件如何创建和<xref:System.Drawing.Brush>释放资源。 有关完整的源代码, 请参阅[如何:创建显示进度](how-to-create-a-windows-forms-control-that-shows-progress.md)的 Windows 窗体控件。  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a>请参阅

- [如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)
