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
ms.openlocfilehash: bd7ce150e4dc0ecfe53f92ec8b557459f1e14e3a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651568"
---
# <a name="user-drawn-controls"></a><span data-ttu-id="e15f3-102">用户描述的控件</span><span class="sxs-lookup"><span data-stu-id="e15f3-102">User-Drawn Controls</span></span>
<span data-ttu-id="e15f3-103">.NET Framework 为您提供了轻松开发自己的控件的功能。</span><span class="sxs-lookup"><span data-stu-id="e15f3-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="e15f3-104">可以创建一个用户控件，这是一组标准控件绑定到一起的代码，或您可以设计自己的控件的基础知识，设置。</span><span class="sxs-lookup"><span data-stu-id="e15f3-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="e15f3-105">甚至可以使用继承创建继承自现有控件的控件并将添加到其固有的功能。</span><span class="sxs-lookup"><span data-stu-id="e15f3-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="e15f3-106">无论何种方法使用，.NET Framework 提供了用于绘制用于您创建的任何控件的自定义图形界面的功能。</span><span class="sxs-lookup"><span data-stu-id="e15f3-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="e15f3-107">控件的绘制通过在控件的代码执行来实现<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e15f3-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="e15f3-108">单个参数的<xref:System.Windows.Forms.Control.OnPaint%2A>方法是<xref:System.Windows.Forms.PaintEventArgs>对象，它提供的所有信息和呈现控件所需的功能。</span><span class="sxs-lookup"><span data-stu-id="e15f3-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="e15f3-109"><xref:System.Windows.Forms.PaintEventArgs>作为属性提供了将控件的呈现中使用的两个主要对象：</span><span class="sxs-lookup"><span data-stu-id="e15f3-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
- <span data-ttu-id="e15f3-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 对象的矩形，表示要绘制的控件的一部分。</span><span class="sxs-lookup"><span data-stu-id="e15f3-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="e15f3-111">这可以是整个控件或具体取决于如何绘制控件的控件的一部分。</span><span class="sxs-lookup"><span data-stu-id="e15f3-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
- <span data-ttu-id="e15f3-112"><xref:System.Drawing.Graphics> 对象-封装一些面向图形的对象和提供必要的功能，绘制控件的方法。</span><span class="sxs-lookup"><span data-stu-id="e15f3-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="e15f3-113">有关详细信息<xref:System.Drawing.Graphics>对象以及如何使用它，请参阅[如何：创建用于绘制图形对象](../advanced/how-to-create-graphics-objects-for-drawing.md)。</span><span class="sxs-lookup"><span data-stu-id="e15f3-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="e15f3-114"><xref:System.Windows.Forms.Control.OnPaint%2A>每当绘制或在屏幕上，刷新控件触发事件和<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>对象表示在其中绘制会发生的矩形。</span><span class="sxs-lookup"><span data-stu-id="e15f3-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="e15f3-115">如果整个控件需要刷新，<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>将表示整个控件的大小。</span><span class="sxs-lookup"><span data-stu-id="e15f3-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="e15f3-116">如果只有一部分的控件需要刷新，但是，<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>对象将表示仅在需要重绘的区域。</span><span class="sxs-lookup"><span data-stu-id="e15f3-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="e15f3-117">这种情况的示例将在另一个控件或窗体用户界面中的部分已遮住控件时。</span><span class="sxs-lookup"><span data-stu-id="e15f3-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="e15f3-118">从继承时<xref:System.Windows.Forms.Control>类，必须重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法并提供图形呈现代码中的。</span><span class="sxs-lookup"><span data-stu-id="e15f3-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="e15f3-119">如果你想要提供到用户控件或继承的控件的自定义图形界面，您可以也会这样通过重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e15f3-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="e15f3-120">示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="e15f3-120">An example is shown below:</span></span>  
  
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
  
 <span data-ttu-id="e15f3-121">前面的示例演示如何呈现控件的非常简单的图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="e15f3-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="e15f3-122">它将调用<xref:System.Windows.Forms.Control.OnPaint%2A>基类的方法，它创建<xref:System.Drawing.Pen>对象用来绘制，并绘制一个椭圆的矩形中由最后<xref:System.Windows.Forms.Control.Location%2A>和<xref:System.Windows.Forms.Control.Size%2A>的控件。</span><span class="sxs-lookup"><span data-stu-id="e15f3-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="e15f3-123">尽管大多数呈现代码都要比这更复杂，但此示例演示如何使用<xref:System.Drawing.Graphics>中包含对象<xref:System.Windows.Forms.PaintEventArgs>对象。</span><span class="sxs-lookup"><span data-stu-id="e15f3-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="e15f3-124">请注意，如果从已有的图形表示形式，例如一个类继承<xref:System.Windows.Forms.UserControl>或<xref:System.Windows.Forms.Button>，并不希望将该表示形式合并到您呈现，不应调用基类的<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e15f3-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="e15f3-125">中的代码<xref:System.Windows.Forms.Control.OnPaint%2A>控件的方法将执行迁移时首次绘制控件，或每当刷新。</span><span class="sxs-lookup"><span data-stu-id="e15f3-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="e15f3-126">若要确保每次调整大小，重绘控件，请将下行添加到您的控件的构造函数：</span><span class="sxs-lookup"><span data-stu-id="e15f3-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
>  <span data-ttu-id="e15f3-127">使用<xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType>属性用于实现非矩形控件。</span><span class="sxs-lookup"><span data-stu-id="e15f3-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e15f3-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="e15f3-128">See also</span></span>

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [<span data-ttu-id="e15f3-129">如何：创建用于绘制图形对象</span><span class="sxs-lookup"><span data-stu-id="e15f3-129">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="e15f3-130">构成控件</span><span class="sxs-lookup"><span data-stu-id="e15f3-130">Constituent Controls</span></span>](constituent-controls.md)
- [<span data-ttu-id="e15f3-131">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="e15f3-131">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
