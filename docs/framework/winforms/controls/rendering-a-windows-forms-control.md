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
ms.openlocfilehash: 8de87e17d1baedccfe18bfded3ccab7ab59f0a09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125679"
---
# <a name="rendering-a-windows-forms-control"></a><span data-ttu-id="42169-102">呈现 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="42169-102">Rendering a Windows Forms Control</span></span>
<span data-ttu-id="42169-103">呈现是指创建用户的屏幕上的可视表示形式的过程。</span><span class="sxs-lookup"><span data-stu-id="42169-103">Rendering refers to the process of creating a visual representation on a user's screen.</span></span> <span data-ttu-id="42169-104">Windows 窗体使用[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]（是的新 Windows 图形库） 以进行呈现。</span><span class="sxs-lookup"><span data-stu-id="42169-104">Windows Forms uses [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] (the new Windows graphics library) for rendering.</span></span> <span data-ttu-id="42169-105">提供访问权限的托管的类[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]位于<xref:System.Drawing?displayProperty=nameWithType>命名空间及其子命名空间。</span><span class="sxs-lookup"><span data-stu-id="42169-105">The managed classes that provide access to [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] are in the <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces.</span></span>  
  
 <span data-ttu-id="42169-106">控件呈现中包括以下元素：</span><span class="sxs-lookup"><span data-stu-id="42169-106">The following elements are involved in control rendering:</span></span>  
  
-   <span data-ttu-id="42169-107">提供由基类的绘图功能<xref:System.Windows.Forms.Control?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="42169-107">The drawing functionality provided by the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="42169-108">基本元素[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]图形库。</span><span class="sxs-lookup"><span data-stu-id="42169-108">The essential elements of the [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] graphics library.</span></span>  
  
-   <span data-ttu-id="42169-109">几何图形的绘图区域。</span><span class="sxs-lookup"><span data-stu-id="42169-109">The geometry of the drawing region.</span></span>  
  
-   <span data-ttu-id="42169-110">用于释放图形资源的过程。</span><span class="sxs-lookup"><span data-stu-id="42169-110">The procedure for freeing graphics resources.</span></span>  
  
## <a name="drawing-functionality-provided-by-control"></a><span data-ttu-id="42169-111">绘图控件提供的功能</span><span class="sxs-lookup"><span data-stu-id="42169-111">Drawing Functionality Provided by Control</span></span>  
 <span data-ttu-id="42169-112">类的基类<xref:System.Windows.Forms.Control>提供了绘图功能通过其<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="42169-112">The base class <xref:System.Windows.Forms.Control> provides drawing functionality through its <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="42169-113">中的控件引发<xref:System.Windows.Forms.Control.Paint>事件时需要更新其显示。</span><span class="sxs-lookup"><span data-stu-id="42169-113">A control raises the <xref:System.Windows.Forms.Control.Paint> event whenever it needs to update its display.</span></span> <span data-ttu-id="42169-114">有关.NET Framework 中的事件的详细信息，请参阅[处理和引发事件](../../../standard/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="42169-114">For more information about events in the .NET Framework, see [Handling and Raising Events](../../../standard/events/index.md).</span></span>  
  
 <span data-ttu-id="42169-115">事件数据类<xref:System.Windows.Forms.Control.Paint>事件， <xref:System.Windows.Forms.PaintEventArgs>，包含所需的绘制控件的数据-图形对象以及表示要在中绘制的区域的矩形对象的句柄。</span><span class="sxs-lookup"><span data-stu-id="42169-115">The event data class for the <xref:System.Windows.Forms.Control.Paint> event, <xref:System.Windows.Forms.PaintEventArgs>, holds the data needed for drawing a control — a handle to a graphics object and a rectangle object that represents the region to draw in.</span></span> <span data-ttu-id="42169-116">中显示这些对象中的以下代码片段以粗体显示。</span><span class="sxs-lookup"><span data-stu-id="42169-116">These objects are shown in bold in the following code fragment.</span></span>  
  
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
  
 <span data-ttu-id="42169-117"><xref:System.Drawing.Graphics> 为托管的类封装绘制功能的讨论中所述[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]本主题中更高版本。</span><span class="sxs-lookup"><span data-stu-id="42169-117"><xref:System.Drawing.Graphics> is a managed class that encapsulates drawing functionality, as described in the discussion of [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] later in this topic.</span></span> <span data-ttu-id="42169-118"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>的一个实例<xref:System.Drawing.Rectangle>结构，并定义可以在其中绘制控件的可用区域。</span><span class="sxs-lookup"><span data-stu-id="42169-118">The <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is an instance of the <xref:System.Drawing.Rectangle> structure and defines the available area in which a control can draw.</span></span> <span data-ttu-id="42169-119">控件开发人员可以计算<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>使用<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>控件，如本主题后面的几何图形的讨论中所述的属性。</span><span class="sxs-lookup"><span data-stu-id="42169-119">A control developer can compute the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> using the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of a control, as described in the discussion of geometry later in this topic.</span></span>  
  
 <span data-ttu-id="42169-120">控件必须提供呈现逻辑通过重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法，它继承自<xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="42169-120">A control must provide rendering logic by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="42169-121"><xref:System.Windows.Forms.Control.OnPaint%2A> 获取的访问权限的图形对象并通过在中绘制一个矩形<xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A>并<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>的属性<xref:System.Windows.Forms.PaintEventArgs>实例传递给它。</span><span class="sxs-lookup"><span data-stu-id="42169-121"><xref:System.Windows.Forms.Control.OnPaint%2A> gets access to a graphics object and a rectangle to draw in through the <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> properties of the <xref:System.Windows.Forms.PaintEventArgs> instance passed to it.</span></span>  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <span data-ttu-id="42169-122"><xref:System.Windows.Forms.Control.OnPaint%2A>方法的基<xref:System.Windows.Forms.Control>类不实现任何绘图功能，但只是调用已注册的事件委托<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="42169-122">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base <xref:System.Windows.Forms.Control> class does not implement any drawing functionality but merely invokes the event delegates that are registered with the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="42169-123">当您重写<xref:System.Windows.Forms.Control.OnPaint%2A>，通常应调用<xref:System.Windows.Forms.Control.OnPaint%2A>基类以便注册的委托的方法接收<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="42169-123">When you override <xref:System.Windows.Forms.Control.OnPaint%2A>, you should typically invoke the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class so that registered delegates receive the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="42169-124">但是，其整个图面绘制的控件不应调用基类的<xref:System.Windows.Forms.Control.OnPaint%2A>，因为这就引入了闪烁。</span><span class="sxs-lookup"><span data-stu-id="42169-124">However, controls that paint their entire surface should not invoke the base class's <xref:System.Windows.Forms.Control.OnPaint%2A>, as this introduces flicker.</span></span> <span data-ttu-id="42169-125">有关重写的示例<xref:System.Windows.Forms.Control.OnPaint%2A>事件，请参阅[如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="42169-125">For an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> event, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42169-126">不要调用<xref:System.Windows.Forms.Control.OnPaint%2A>直接从您的控件; 相反，调用<xref:System.Windows.Forms.Control.Invalidate%2A>方法 (继承自<xref:System.Windows.Forms.Control>) 或其他方法调用<xref:System.Windows.Forms.Control.Invalidate%2A>。</span><span class="sxs-lookup"><span data-stu-id="42169-126">Do not invoke <xref:System.Windows.Forms.Control.OnPaint%2A> directly from your control; instead, invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method (inherited from <xref:System.Windows.Forms.Control>) or some other method that invokes <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="42169-127"><xref:System.Windows.Forms.Control.Invalidate%2A>方法又调用<xref:System.Windows.Forms.Control.OnPaint%2A>。</span><span class="sxs-lookup"><span data-stu-id="42169-127">The <xref:System.Windows.Forms.Control.Invalidate%2A> method in turn invokes <xref:System.Windows.Forms.Control.OnPaint%2A>.</span></span> <span data-ttu-id="42169-128"><xref:System.Windows.Forms.Control.Invalidate%2A>方法重载，并根据自变量提供给<xref:System.Windows.Forms.Control.Invalidate%2A> `e`，控件将重绘其部分或全部其屏幕区域。</span><span class="sxs-lookup"><span data-stu-id="42169-128">The <xref:System.Windows.Forms.Control.Invalidate%2A> method is overloaded, and, depending on the arguments supplied to <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, a control redraws either some or all of its screen area.</span></span>  
  
 <span data-ttu-id="42169-129">基<xref:System.Windows.Forms.Control>类定义可用于绘图的另一种方法 —<xref:System.Windows.Forms.Control.OnPaintBackground%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="42169-129">The base <xref:System.Windows.Forms.Control> class defines another method that is useful for drawing — the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method.</span></span>  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <span data-ttu-id="42169-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> 绘制背景 (并因此形状) 的窗口和保证可快速完成，而<xref:System.Windows.Forms.Control.OnPaint%2A>绘制详细信息和可能是较慢，因为单个的绘制请求合并成一个<xref:System.Windows.Forms.Control.Paint>介绍了需要的所有区域的事件重绘。</span><span class="sxs-lookup"><span data-stu-id="42169-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> paints the background (and thereby the shape) of the window and is guaranteed to be fast, while <xref:System.Windows.Forms.Control.OnPaint%2A> paints the details and might be slower because individual paint requests are combined into one <xref:System.Windows.Forms.Control.Paint> event that covers all areas that have to be redrawn.</span></span> <span data-ttu-id="42169-131">你可能想要调用<xref:System.Windows.Forms.Control.OnPaintBackground%2A>如果，例如，想要绘制控件的颜色渐变背景。</span><span class="sxs-lookup"><span data-stu-id="42169-131">You might want to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> if, for instance, you want to draw a gradient-colored background for your control.</span></span>  
  
 <span data-ttu-id="42169-132">虽然<xref:System.Windows.Forms.Control.OnPaintBackground%2A>具有类似于事件的命名法并采用相同参数作为`OnPaint`方法，<xref:System.Windows.Forms.Control.OnPaintBackground%2A>并不是真正的事件方法。</span><span class="sxs-lookup"><span data-stu-id="42169-132">While <xref:System.Windows.Forms.Control.OnPaintBackground%2A> has an event-like nomenclature and takes the same argument as the `OnPaint` method, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> is not a true event method.</span></span> <span data-ttu-id="42169-133">没有任何`PaintBackground`事件和<xref:System.Windows.Forms.Control.OnPaintBackground%2A>不会调用事件委托。</span><span class="sxs-lookup"><span data-stu-id="42169-133">There is no `PaintBackground` event and <xref:System.Windows.Forms.Control.OnPaintBackground%2A> does not invoke event delegates.</span></span> <span data-ttu-id="42169-134">重写时<xref:System.Windows.Forms.Control.OnPaintBackground%2A>方法，派生的类不需要调用<xref:System.Windows.Forms.Control.OnPaintBackground%2A>其基类的方法。</span><span class="sxs-lookup"><span data-stu-id="42169-134">When overriding the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method, a derived class is not required to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method of its base class.</span></span>  
  
## <a name="gdi-basics"></a><span data-ttu-id="42169-135">GDI + 基础知识</span><span class="sxs-lookup"><span data-stu-id="42169-135">GDI+ Basics</span></span>  
 <span data-ttu-id="42169-136"><xref:System.Drawing.Graphics>类提供绘制各种形状，如圆圈、 三角形、 弧线和椭圆的方法，以及用于显示文本的方法。</span><span class="sxs-lookup"><span data-stu-id="42169-136">The <xref:System.Drawing.Graphics> class provides methods for drawing various shapes such as circles, triangles, arcs, and ellipses, as well as methods for displaying text.</span></span> <span data-ttu-id="42169-137"><xref:System.Drawing?displayProperty=nameWithType>命名空间和及其子命名空间包含类封装图形元素，如 （圆圈、 矩形、 弧线和其他人） 的形状、 颜色、 字体、 画笔和等等。</span><span class="sxs-lookup"><span data-stu-id="42169-137">The <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces contain classes that encapsulate graphics elements such as shapes (circles, rectangles, arcs, and others), colors, fonts, brushes, and so on.</span></span> <span data-ttu-id="42169-138">有关详细信息[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]，请参阅[使用托管图形类](../advanced/using-managed-graphics-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="42169-138">For more information about [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], see [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md).</span></span> <span data-ttu-id="42169-139">基础知识[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]中也描述了[如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="42169-139">The essentials of [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] are also described in the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="geometry-of-the-drawing-region"></a><span data-ttu-id="42169-140">几何图形的绘图区域</span><span class="sxs-lookup"><span data-stu-id="42169-140">Geometry of the Drawing Region</span></span>  
 <span data-ttu-id="42169-141"><xref:System.Windows.Forms.Control.ClientRectangle%2A>控件的属性指定可用于在用户的屏幕上，控件的矩形区域时<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>属性的<xref:System.Windows.Forms.PaintEventArgs>指定实际绘制的区域。</span><span class="sxs-lookup"><span data-stu-id="42169-141">The <xref:System.Windows.Forms.Control.ClientRectangle%2A> property of a control specifies the rectangular region available to the control on the user's screen, while the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs> specifies the area that is actually painted.</span></span> <span data-ttu-id="42169-142">(请记住，完成绘制<xref:System.Windows.Forms.Control.Paint>采用的事件方法<xref:System.Windows.Forms.PaintEventArgs>实例作为其参数)。</span><span class="sxs-lookup"><span data-stu-id="42169-142">(Remember that painting is done in the <xref:System.Windows.Forms.Control.Paint> event method that takes a <xref:System.Windows.Forms.PaintEventArgs> instance as its argument).</span></span> <span data-ttu-id="42169-143">控件可能需要绘制只有其可用区域中，部分因为是控件的显示更改这种情况时一小部分。</span><span class="sxs-lookup"><span data-stu-id="42169-143">A control might need to paint only a portion of its available area, as is the case when a small section of the control's display changes.</span></span> <span data-ttu-id="42169-144">在这些情况下，控件开发人员必须计算实际的矩形中绘制，并将其传递给<xref:System.Windows.Forms.Control.Invalidate%2A>。</span><span class="sxs-lookup"><span data-stu-id="42169-144">In those situations, a control developer must compute the actual rectangle to draw in and pass that to <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="42169-145">重载的版本<xref:System.Windows.Forms.Control.Invalidate%2A>采用<xref:System.Drawing.Rectangle>或<xref:System.Drawing.Region>作为参数使用该参数生成<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>属性<xref:System.Windows.Forms.PaintEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="42169-145">The overloaded versions of <xref:System.Windows.Forms.Control.Invalidate%2A> that take a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.Region> as an argument use that argument to generate the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
 <span data-ttu-id="42169-146">以下代码段显示了`FlashTrackBar`自定义控件计算绘制的矩形区域。</span><span class="sxs-lookup"><span data-stu-id="42169-146">The following code fragment shows how the `FlashTrackBar` custom control computes the rectangular area to draw in.</span></span> <span data-ttu-id="42169-147">`client`变量表示<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="42169-147">The `client` variable denotes the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property.</span></span> <span data-ttu-id="42169-148">有关完整示例，请参阅[如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="42169-148">For a complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a><span data-ttu-id="42169-149">释放图形资源</span><span class="sxs-lookup"><span data-stu-id="42169-149">Freeing Graphics Resources</span></span>  
 <span data-ttu-id="42169-150">图形对象非常昂贵，因为它们使用的系统资源。</span><span class="sxs-lookup"><span data-stu-id="42169-150">Graphics objects are expensive because they use system resources.</span></span> <span data-ttu-id="42169-151">此类对象包含的实例<xref:System.Drawing.Graphics?displayProperty=nameWithType>类的实例以及<xref:System.Drawing.Brush?displayProperty=nameWithType>， <xref:System.Drawing.Pen?displayProperty=nameWithType>，和其他图形类。</span><span class="sxs-lookup"><span data-stu-id="42169-151">Such objects include instances of the <xref:System.Drawing.Graphics?displayProperty=nameWithType> class as well as instances of <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, and other graphics classes.</span></span> <span data-ttu-id="42169-152">仅当需要它并将其释放时创建的图形资源很重要很快完成后使用它。</span><span class="sxs-lookup"><span data-stu-id="42169-152">It is important that you create a graphics resource only when you need it and release it soon as you are finished using it.</span></span> <span data-ttu-id="42169-153">如果您创建的类型实现<xref:System.IDisposable>接口中，调用其<xref:System.IDisposable.Dispose%2A>方法完成后使用它来释放资源。</span><span class="sxs-lookup"><span data-stu-id="42169-153">If you create a type that implements the <xref:System.IDisposable> interface, call its <xref:System.IDisposable.Dispose%2A> method when you are finished with it in order to free resources.</span></span>  
  
 <span data-ttu-id="42169-154">以下代码段显示如何`FlashTrackBar`自定义控件创建和释放<xref:System.Drawing.Brush>资源。</span><span class="sxs-lookup"><span data-stu-id="42169-154">The following code fragment shows how the `FlashTrackBar` custom control creates and releases a <xref:System.Drawing.Brush> resource.</span></span> <span data-ttu-id="42169-155">有关完整的源代码，请参阅[如何：创建显示进度的 Windows 窗体控件](how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="42169-155">For the complete source code, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="42169-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="42169-156">See also</span></span>

- [<span data-ttu-id="42169-157">如何：创建显示进度的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="42169-157">How to: Create a Windows Forms Control That Shows Progress</span></span>](how-to-create-a-windows-forms-control-that-shows-progress.md)
