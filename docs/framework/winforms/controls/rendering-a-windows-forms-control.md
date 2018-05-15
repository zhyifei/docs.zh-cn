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
ms.openlocfilehash: a2d7a02e725e3f8065b80a6b30ea21158be43ea8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="rendering-a-windows-forms-control"></a><span data-ttu-id="e12e8-102">呈现 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="e12e8-102">Rendering a Windows Forms Control</span></span>
<span data-ttu-id="e12e8-103">呈现是指创建在用户的屏幕上的可视表示形式的过程。</span><span class="sxs-lookup"><span data-stu-id="e12e8-103">Rendering refers to the process of creating a visual representation on a user's screen.</span></span> <span data-ttu-id="e12e8-104">Windows 窗体使用[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]（的新 Windows 图形库） 呈现。</span><span class="sxs-lookup"><span data-stu-id="e12e8-104">Windows Forms uses [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] (the new Windows graphics library) for rendering.</span></span> <span data-ttu-id="e12e8-105">提供对访问托管的类[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]中<xref:System.Drawing?displayProperty=nameWithType>命名空间及其子命名空间。</span><span class="sxs-lookup"><span data-stu-id="e12e8-105">The managed classes that provide access to [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] are in the <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces.</span></span>  
  
 <span data-ttu-id="e12e8-106">控件呈现中包括以下元素：</span><span class="sxs-lookup"><span data-stu-id="e12e8-106">The following elements are involved in control rendering:</span></span>  
  
-   <span data-ttu-id="e12e8-107">提供的基类的绘制功能<xref:System.Windows.Forms.Control?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e12e8-107">The drawing functionality provided by the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="e12e8-108">重要元素[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]图形库。</span><span class="sxs-lookup"><span data-stu-id="e12e8-108">The essential elements of the [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] graphics library.</span></span>  
  
-   <span data-ttu-id="e12e8-109">该几何图形的绘图区域。</span><span class="sxs-lookup"><span data-stu-id="e12e8-109">The geometry of the drawing region.</span></span>  
  
-   <span data-ttu-id="e12e8-110">用于释放图形资源的过程。</span><span class="sxs-lookup"><span data-stu-id="e12e8-110">The procedure for freeing graphics resources.</span></span>  
  
## <a name="drawing-functionality-provided-by-control"></a><span data-ttu-id="e12e8-111">绘制控件提供功能</span><span class="sxs-lookup"><span data-stu-id="e12e8-111">Drawing Functionality Provided by Control</span></span>  
 <span data-ttu-id="e12e8-112">基类<xref:System.Windows.Forms.Control>绘制可通过提供功能其<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="e12e8-112">The base class <xref:System.Windows.Forms.Control> provides drawing functionality through its <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="e12e8-113">中的控件引发<xref:System.Windows.Forms.Control.Paint>只要它需要更新显示的事件。</span><span class="sxs-lookup"><span data-stu-id="e12e8-113">A control raises the <xref:System.Windows.Forms.Control.Paint> event whenever it needs to update its display.</span></span> <span data-ttu-id="e12e8-114">有关.NET Framework 中的事件的详细信息，请参阅[处理和引发事件](../../../../docs/standard/events/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e12e8-114">For more information about events in the .NET Framework, see [Handling and Raising Events](../../../../docs/standard/events/index.md).</span></span>  
  
 <span data-ttu-id="e12e8-115">事件数据类<xref:System.Windows.Forms.Control.Paint>事件， <xref:System.Windows.Forms.PaintEventArgs>，包含所需的绘制控件的数据-图形对象以及表示要在中绘制的区域的矩形对象的句柄。</span><span class="sxs-lookup"><span data-stu-id="e12e8-115">The event data class for the <xref:System.Windows.Forms.Control.Paint> event, <xref:System.Windows.Forms.PaintEventArgs>, holds the data needed for drawing a control — a handle to a graphics object and a rectangle object that represents the region to draw in.</span></span> <span data-ttu-id="e12e8-116">中显示这些对象在下面的代码段中加粗。</span><span class="sxs-lookup"><span data-stu-id="e12e8-116">These objects are shown in bold in the following code fragment.</span></span>  
  
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
  
 <span data-ttu-id="e12e8-117"><xref:System.Drawing.Graphics> 是封装绘制功能的托管的类的讨论中所述[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]本主题中更高版本。</span><span class="sxs-lookup"><span data-stu-id="e12e8-117"><xref:System.Drawing.Graphics> is a managed class that encapsulates drawing functionality, as described in the discussion of [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] later in this topic.</span></span> <span data-ttu-id="e12e8-118"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>是的一个实例<xref:System.Drawing.Rectangle>结构和定义可以在其中绘制控件的可用区域。</span><span class="sxs-lookup"><span data-stu-id="e12e8-118">The <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is an instance of the <xref:System.Drawing.Rectangle> structure and defines the available area in which a control can draw.</span></span> <span data-ttu-id="e12e8-119">控件开发人员可以计算<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>使用<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>控件，如本主题中后面的几何图形的讨论中所述的属性。</span><span class="sxs-lookup"><span data-stu-id="e12e8-119">A control developer can compute the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> using the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of a control, as described in the discussion of geometry later in this topic.</span></span>  
  
 <span data-ttu-id="e12e8-120">控件必须通过重写提供呈现逻辑<xref:System.Windows.Forms.Control.OnPaint%2A>方法，它继承自<xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="e12e8-120">A control must provide rendering logic by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="e12e8-121"><xref:System.Windows.Forms.Control.OnPaint%2A> 获取访问权限的图形对象和要通过在绘制的矩形<xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A>和<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>属性<xref:System.Windows.Forms.PaintEventArgs>实例传递给它。</span><span class="sxs-lookup"><span data-stu-id="e12e8-121"><xref:System.Windows.Forms.Control.OnPaint%2A> gets access to a graphics object and a rectangle to draw in through the <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> properties of the <xref:System.Windows.Forms.PaintEventArgs> instance passed to it.</span></span>  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <span data-ttu-id="e12e8-122"><xref:System.Windows.Forms.Control.OnPaint%2A>基方法<xref:System.Windows.Forms.Control>类不实现任何绘制的功能，但仅仅是调用与注册的事件委托<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="e12e8-122">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base <xref:System.Windows.Forms.Control> class does not implement any drawing functionality but merely invokes the event delegates that are registered with the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="e12e8-123">当你重写<xref:System.Windows.Forms.Control.OnPaint%2A>，通常应调用<xref:System.Windows.Forms.Control.OnPaint%2A>方法的基类，以便已注册的委托能够接收<xref:System.Windows.Forms.Control.Paint>事件。</span><span class="sxs-lookup"><span data-stu-id="e12e8-123">When you override <xref:System.Windows.Forms.Control.OnPaint%2A>, you should typically invoke the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class so that registered delegates receive the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="e12e8-124">但是，绘制其整个图面的控件不应调用基类的<xref:System.Windows.Forms.Control.OnPaint%2A>，因为这将带来闪烁。</span><span class="sxs-lookup"><span data-stu-id="e12e8-124">However, controls that paint their entire surface should not invoke the base class's <xref:System.Windows.Forms.Control.OnPaint%2A>, as this introduces flicker.</span></span> <span data-ttu-id="e12e8-125">有关的重写示例<xref:System.Windows.Forms.Control.OnPaint%2A>事件，请参阅[如何： 创建 Windows 窗体控件，显示进度](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="e12e8-125">For an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> event, see the [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e12e8-126">不会调用<xref:System.Windows.Forms.Control.OnPaint%2A>直接从控件; 相反，调用<xref:System.Windows.Forms.Control.Invalidate%2A>方法 (继承自<xref:System.Windows.Forms.Control>) 或通过某些其他方法调用<xref:System.Windows.Forms.Control.Invalidate%2A>。</span><span class="sxs-lookup"><span data-stu-id="e12e8-126">Do not invoke <xref:System.Windows.Forms.Control.OnPaint%2A> directly from your control; instead, invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method (inherited from <xref:System.Windows.Forms.Control>) or some other method that invokes <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="e12e8-127"><xref:System.Windows.Forms.Control.Invalidate%2A>方法反过来调用<xref:System.Windows.Forms.Control.OnPaint%2A>。</span><span class="sxs-lookup"><span data-stu-id="e12e8-127">The <xref:System.Windows.Forms.Control.Invalidate%2A> method in turn invokes <xref:System.Windows.Forms.Control.OnPaint%2A>.</span></span> <span data-ttu-id="e12e8-128"><xref:System.Windows.Forms.Control.Invalidate%2A>方法重载，并根据自变量提供给<xref:System.Windows.Forms.Control.Invalidate%2A> `e`，控件重绘其部分或全部其屏幕区域。</span><span class="sxs-lookup"><span data-stu-id="e12e8-128">The <xref:System.Windows.Forms.Control.Invalidate%2A> method is overloaded, and, depending on the arguments supplied to <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, a control redraws either some or all of its screen area.</span></span>  
  
 <span data-ttu-id="e12e8-129">基<xref:System.Windows.Forms.Control>类定义用于绘制的另一种方法-<xref:System.Windows.Forms.Control.OnPaintBackground%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e12e8-129">The base <xref:System.Windows.Forms.Control> class defines another method that is useful for drawing — the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method.</span></span>  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <span data-ttu-id="e12e8-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> 绘制背景 (，从而形状) 的窗口，并保证要快速完成，而<xref:System.Windows.Forms.Control.OnPaint%2A>绘制详细信息，并且可能会降低，因为各个绘制请求合并成一个<xref:System.Windows.Forms.Control.Paint>涵盖所有方面必须具备的事件在重绘。</span><span class="sxs-lookup"><span data-stu-id="e12e8-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> paints the background (and thereby the shape) of the window and is guaranteed to be fast, while <xref:System.Windows.Forms.Control.OnPaint%2A> paints the details and might be slower because individual paint requests are combined into one <xref:System.Windows.Forms.Control.Paint> event that covers all areas that have to be redrawn.</span></span> <span data-ttu-id="e12e8-131">你可能想要调用<xref:System.Windows.Forms.Control.OnPaintBackground%2A>如果，例如，你想要绘制控件的颜色渐变背景。</span><span class="sxs-lookup"><span data-stu-id="e12e8-131">You might want to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> if, for instance, you want to draw a gradient-colored background for your control.</span></span>  
  
 <span data-ttu-id="e12e8-132">虽然<xref:System.Windows.Forms.Control.OnPaintBackground%2A>具有类似于事件的术语和采用相同的自变量作为`OnPaint`方法，<xref:System.Windows.Forms.Control.OnPaintBackground%2A>不是真正的事件方法。</span><span class="sxs-lookup"><span data-stu-id="e12e8-132">While <xref:System.Windows.Forms.Control.OnPaintBackground%2A> has an event-like nomenclature and takes the same argument as the `OnPaint` method, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> is not a true event method.</span></span> <span data-ttu-id="e12e8-133">没有任何`PaintBackground`事件和<xref:System.Windows.Forms.Control.OnPaintBackground%2A>不会调用事件委托。</span><span class="sxs-lookup"><span data-stu-id="e12e8-133">There is no `PaintBackground` event and <xref:System.Windows.Forms.Control.OnPaintBackground%2A> does not invoke event delegates.</span></span> <span data-ttu-id="e12e8-134">在重写<xref:System.Windows.Forms.Control.OnPaintBackground%2A>方法，派生的类不需要调用<xref:System.Windows.Forms.Control.OnPaintBackground%2A>其基本类的方法。</span><span class="sxs-lookup"><span data-stu-id="e12e8-134">When overriding the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method, a derived class is not required to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method of its base class.</span></span>  
  
## <a name="gdi-basics"></a><span data-ttu-id="e12e8-135">GDI + 基础知识</span><span class="sxs-lookup"><span data-stu-id="e12e8-135">GDI+ Basics</span></span>  
 <span data-ttu-id="e12e8-136"><xref:System.Drawing.Graphics>类提供绘制圆形、 三角形、 弧线和省略号，如各种形状的方法，以及用于显示文本的方法。</span><span class="sxs-lookup"><span data-stu-id="e12e8-136">The <xref:System.Drawing.Graphics> class provides methods for drawing various shapes such as circles, triangles, arcs, and ellipses, as well as methods for displaying text.</span></span> <span data-ttu-id="e12e8-137"><xref:System.Drawing?displayProperty=nameWithType>命名空间和及其子命名空间包含类，用于封装各种图形元素，如形状 （圆形、 矩形、 弧线和其他）、 颜色、 字体、 画笔和等等。</span><span class="sxs-lookup"><span data-stu-id="e12e8-137">The <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces contain classes that encapsulate graphics elements such as shapes (circles, rectangles, arcs, and others), colors, fonts, brushes, and so on.</span></span> <span data-ttu-id="e12e8-138">有关详细信息[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]，请参阅[使用托管图形类](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)。</span><span class="sxs-lookup"><span data-stu-id="e12e8-138">For more information about [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], see [Using Managed Graphics Classes](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md).</span></span> <span data-ttu-id="e12e8-139">Essentials[!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]中也介绍了[如何： 创建 Windows 窗体控件，显示进度](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="e12e8-139">The essentials of [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] are also described in the [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="geometry-of-the-drawing-region"></a><span data-ttu-id="e12e8-140">绘图区域的几何图形</span><span class="sxs-lookup"><span data-stu-id="e12e8-140">Geometry of the Drawing Region</span></span>  
 <span data-ttu-id="e12e8-141"><xref:System.Windows.Forms.Control.ClientRectangle%2A>控件的属性指定可供用户的屏幕上的控件的矩形区域而<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>属性<xref:System.Windows.Forms.PaintEventArgs>指定实际绘制的区域。</span><span class="sxs-lookup"><span data-stu-id="e12e8-141">The <xref:System.Windows.Forms.Control.ClientRectangle%2A> property of a control specifies the rectangular region available to the control on the user's screen, while the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs> specifies the area that is actually painted.</span></span> <span data-ttu-id="e12e8-142">(请记住，完成绘制<xref:System.Windows.Forms.Control.Paint>事件方法采用<xref:System.Windows.Forms.PaintEventArgs>作为其自变量的实例)。</span><span class="sxs-lookup"><span data-stu-id="e12e8-142">(Remember that painting is done in the <xref:System.Windows.Forms.Control.Paint> event method that takes a <xref:System.Windows.Forms.PaintEventArgs> instance as its argument).</span></span> <span data-ttu-id="e12e8-143">控件可能需要绘制仅为一部分其可用的区域，如是控件的显示更改这种情况时一小部分。</span><span class="sxs-lookup"><span data-stu-id="e12e8-143">A control might need to paint only a portion of its available area, as is the case when a small section of the control's display changes.</span></span> <span data-ttu-id="e12e8-144">在这些情况下，控件开发人员必须计算实际的矩形绘制，并将传递给<xref:System.Windows.Forms.Control.Invalidate%2A>。</span><span class="sxs-lookup"><span data-stu-id="e12e8-144">In those situations, a control developer must compute the actual rectangle to draw in and pass that to <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="e12e8-145">重载的版本<xref:System.Windows.Forms.Control.Invalidate%2A>采用<xref:System.Drawing.Rectangle>或<xref:System.Drawing.Region>作为自变量使用该自变量生成<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>属性<xref:System.Windows.Forms.PaintEventArgs>。</span><span class="sxs-lookup"><span data-stu-id="e12e8-145">The overloaded versions of <xref:System.Windows.Forms.Control.Invalidate%2A> that take a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.Region> as an argument use that argument to generate the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
 <span data-ttu-id="e12e8-146">以下代码段显示了`FlashTrackBar`自定义控件计算以进行绘制的矩形区域。</span><span class="sxs-lookup"><span data-stu-id="e12e8-146">The following code fragment shows how the `FlashTrackBar` custom control computes the rectangular area to draw in.</span></span> <span data-ttu-id="e12e8-147">`client`变量表示<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e12e8-147">The `client` variable denotes the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property.</span></span> <span data-ttu-id="e12e8-148">有关完整示例，请参阅[如何： 创建 Windows 窗体控件，显示进度](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="e12e8-148">For a complete sample, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a><span data-ttu-id="e12e8-149">释放图形资源</span><span class="sxs-lookup"><span data-stu-id="e12e8-149">Freeing Graphics Resources</span></span>  
 <span data-ttu-id="e12e8-150">图形对象非常昂贵，因为它们使用系统资源。</span><span class="sxs-lookup"><span data-stu-id="e12e8-150">Graphics objects are expensive because they use system resources.</span></span> <span data-ttu-id="e12e8-151">此类对象包含的实例<xref:System.Drawing.Graphics?displayProperty=nameWithType>类的实例以及<xref:System.Drawing.Brush?displayProperty=nameWithType>， <xref:System.Drawing.Pen?displayProperty=nameWithType>，和其他图形类。</span><span class="sxs-lookup"><span data-stu-id="e12e8-151">Such objects include instances of the <xref:System.Drawing.Graphics?displayProperty=nameWithType> class as well as instances of <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, and other graphics classes.</span></span> <span data-ttu-id="e12e8-152">务必创建图形资源，仅当你需要它并将其释放时立即在完成使用它。</span><span class="sxs-lookup"><span data-stu-id="e12e8-152">It is important that you create a graphics resource only when you need it and release it soon as you are finished using it.</span></span> <span data-ttu-id="e12e8-153">如果你创建的类型的实现<xref:System.IDisposable>界面，请调用其<xref:System.IDisposable.Dispose%2A>方法完成后使用它以释放资源。</span><span class="sxs-lookup"><span data-stu-id="e12e8-153">If you create a type that implements the <xref:System.IDisposable> interface, call its <xref:System.IDisposable.Dispose%2A> method when you are finished with it in order to free resources.</span></span>  
  
 <span data-ttu-id="e12e8-154">以下代码段显示了`FlashTrackBar`自定义控件需要创建和发布<xref:System.Drawing.Brush>资源。</span><span class="sxs-lookup"><span data-stu-id="e12e8-154">The following code fragment shows how the `FlashTrackBar` custom control creates and releases a <xref:System.Drawing.Brush> resource.</span></span> <span data-ttu-id="e12e8-155">有关完整的源代码，请参阅[如何： 创建 Windows 窗体控件，显示进度](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)。</span><span class="sxs-lookup"><span data-stu-id="e12e8-155">For the complete source code, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="e12e8-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="e12e8-156">See Also</span></span>  
 [<span data-ttu-id="e12e8-157">如何：创建显示进度的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="e12e8-157">How to: Create a Windows Forms Control That Shows Progress</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md)
