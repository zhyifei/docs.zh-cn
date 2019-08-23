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
ms.openlocfilehash: 50036f5bef323368b4970a080ca7a70cf94252d6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966490"
---
# <a name="user-drawn-controls"></a><span data-ttu-id="a4411-102">用户描述的控件</span><span class="sxs-lookup"><span data-stu-id="a4411-102">User-Drawn Controls</span></span>
<span data-ttu-id="a4411-103">.NET Framework 使你能够轻松地开发自己的控件。</span><span class="sxs-lookup"><span data-stu-id="a4411-103">The .NET Framework provides you with the ability to easily develop your own controls.</span></span> <span data-ttu-id="a4411-104">您可以创建一个用户控件, 该控件是通过代码绑定在一起的一组标准控件, 或者您可以从头开始设计自己的控件。</span><span class="sxs-lookup"><span data-stu-id="a4411-104">You can create a user control, which is a set of standard controls bound together by code, or you can design your own control from the ground up.</span></span> <span data-ttu-id="a4411-105">甚至可以使用继承来创建一个从现有控件继承的控件并将其添加到其固有的功能中。</span><span class="sxs-lookup"><span data-stu-id="a4411-105">You can even use inheritance to create a control that inherits from an existing control and add to its inherent functionality.</span></span> <span data-ttu-id="a4411-106">无论使用哪种方法, .NET Framework 都提供了为您创建的任何控件绘制自定义图形界面的功能。</span><span class="sxs-lookup"><span data-stu-id="a4411-106">Whatever approach you use, the .NET Framework provides the functionality to draw a custom graphical interface for any control you create.</span></span>  
  
 <span data-ttu-id="a4411-107">控件的绘制通过执行控件的<xref:System.Windows.Forms.Control.OnPaint%2A>方法中的代码来实现。</span><span class="sxs-lookup"><span data-stu-id="a4411-107">Painting of a control is accomplished by the execution of code in the control's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="a4411-108"><xref:System.Windows.Forms.Control.OnPaint%2A>方法的单个参数是一个<xref:System.Windows.Forms.PaintEventArgs>对象, 该对象提供了呈现控件所需的所有信息和功能。</span><span class="sxs-lookup"><span data-stu-id="a4411-108">The single argument of the <xref:System.Windows.Forms.Control.OnPaint%2A> method is a <xref:System.Windows.Forms.PaintEventArgs> object that provides all of the information and functionality required to render your control.</span></span> <span data-ttu-id="a4411-109"><xref:System.Windows.Forms.PaintEventArgs>提供了两个将用于呈现控件的主体对象:</span><span class="sxs-lookup"><span data-stu-id="a4411-109">The <xref:System.Windows.Forms.PaintEventArgs> provides as properties two principal objects that will be used in the rendering of your control:</span></span>  
  
- <span data-ttu-id="a4411-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>object-表示要绘制的控件部分的矩形。</span><span class="sxs-lookup"><span data-stu-id="a4411-110"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object - the rectangle that represents the part of the control that will be drawn.</span></span> <span data-ttu-id="a4411-111">这可以是整个控件或控件的一部分, 具体取决于控件的绘制方式。</span><span class="sxs-lookup"><span data-stu-id="a4411-111">This can be the entire control, or part of the control depending on how the control is drawn.</span></span>  
  
- <span data-ttu-id="a4411-112"><xref:System.Drawing.Graphics>对象-封装一些面向图形的对象和方法, 这些对象和方法提供绘制控件所必需的功能。</span><span class="sxs-lookup"><span data-stu-id="a4411-112"><xref:System.Drawing.Graphics> object - encapsulates several graphics-oriented objects and methods that provide the functionality necessary to draw your control.</span></span>  
  
 <span data-ttu-id="a4411-113">有关<xref:System.Drawing.Graphics>对象及其使用方法的详细信息, 请参阅[如何:为绘图](../advanced/how-to-create-graphics-objects-for-drawing.md)创建图形对象。</span><span class="sxs-lookup"><span data-stu-id="a4411-113">For more information on the <xref:System.Drawing.Graphics> object and how to use it, see [How to: Create Graphics Objects for Drawing](../advanced/how-to-create-graphics-objects-for-drawing.md).</span></span>  
  
 <span data-ttu-id="a4411-114">每当在屏幕上绘制或刷新控件时都会触发<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 事件,而对象表示在其中进行绘制的矩形。<xref:System.Windows.Forms.Control.OnPaint%2A></span><span class="sxs-lookup"><span data-stu-id="a4411-114">The <xref:System.Windows.Forms.Control.OnPaint%2A> event is fired whenever the control is drawn or refreshed on the screen, and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object represents the rectangle in which painting will take place.</span></span> <span data-ttu-id="a4411-115">如果需要刷新整个控件, <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>将表示整个控件的大小。</span><span class="sxs-lookup"><span data-stu-id="a4411-115">If the entire control needs to be refreshed, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> will represent the size of the entire control.</span></span> <span data-ttu-id="a4411-116">但是, 如果只需要刷新部分控件, 则<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>对象只表示需要重新绘制的区域。</span><span class="sxs-lookup"><span data-stu-id="a4411-116">If only part of the control needs to be refreshed, however, the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> object will represent only the region that needs to be redrawn.</span></span> <span data-ttu-id="a4411-117">此类情况的一个示例就是在用户界面中, 控件被另一个控件或窗体部分遮盖。</span><span class="sxs-lookup"><span data-stu-id="a4411-117">An example of such a case would be when a control was partially obscured by another control or form in the user interface.</span></span>  
  
 <span data-ttu-id="a4411-118">从<xref:System.Windows.Forms.Control>类继承时, 必须<xref:System.Windows.Forms.Control.OnPaint%2A>重写方法, 并在内提供图形呈现代码。</span><span class="sxs-lookup"><span data-stu-id="a4411-118">When inheriting from the <xref:System.Windows.Forms.Control> class, you must override the <xref:System.Windows.Forms.Control.OnPaint%2A> method and provide graphics-rendering code within.</span></span> <span data-ttu-id="a4411-119">如果要为用户控件或继承的控件提供自定义图形界面, 还可以通过重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a4411-119">If you want to provide a custom graphical interface to a user control or an inherited control, you can also do so by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span> <span data-ttu-id="a4411-120">下面显示了一个示例:</span><span class="sxs-lookup"><span data-stu-id="a4411-120">An example is shown below:</span></span>  
  
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
  
 <span data-ttu-id="a4411-121">前面的示例演示如何使用非常简单的图形表示形式呈现控件。</span><span class="sxs-lookup"><span data-stu-id="a4411-121">The preceding example demonstrates how to render a control with a very simple graphical representation.</span></span> <span data-ttu-id="a4411-122">它调用基类<xref:System.Windows.Forms.Control.OnPaint%2A>的方法, 并<xref:System.Drawing.Pen>创建用于绘制的对象, 最后在由<xref:System.Windows.Forms.Control.Location%2A>控件的和<xref:System.Windows.Forms.Control.Size%2A>确定的矩形中绘制一个椭圆。</span><span class="sxs-lookup"><span data-stu-id="a4411-122">It calls the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class, it creates a <xref:System.Drawing.Pen> object with which to draw, and finally draws an ellipse in the rectangle determined by the <xref:System.Windows.Forms.Control.Location%2A> and <xref:System.Windows.Forms.Control.Size%2A> of the control.</span></span> <span data-ttu-id="a4411-123">尽管大多数呈现代码的复杂程度要大得多, 但本示例演示了<xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs>对象中包含的对象的用法。</span><span class="sxs-lookup"><span data-stu-id="a4411-123">Although most rendering code will be significantly more complicated than this, this example demonstrates the use of the <xref:System.Drawing.Graphics> object contained within the <xref:System.Windows.Forms.PaintEventArgs> object.</span></span> <span data-ttu-id="a4411-124">请注意, 如果从已具有图形表示形式的类 (如<xref:System.Windows.Forms.UserControl>或<xref:System.Windows.Forms.Button>) 继承, 并且不希望将该表示形式合并到您的呈现中, 则不应调用基类的<xref:System.Windows.Forms.Control.OnPaint%2A>付款方式.</span><span class="sxs-lookup"><span data-stu-id="a4411-124">Note that if you are inheriting from a class that already has a graphical representation, such as <xref:System.Windows.Forms.UserControl> or <xref:System.Windows.Forms.Button>, and you do not wish to incorporate that representation into your rendering, you should not call your base class's <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
 <span data-ttu-id="a4411-125">控件的<xref:System.Windows.Forms.Control.OnPaint%2A>方法中的代码将在第一次绘制控件时和每次刷新时执行。</span><span class="sxs-lookup"><span data-stu-id="a4411-125">The code in the <xref:System.Windows.Forms.Control.OnPaint%2A> method of your control will execute when the control is first drawn, and whenever it is refreshed.</span></span> <span data-ttu-id="a4411-126">若要确保每次调整控件大小时都重新绘制控件, 请将以下行添加到控件的构造函数中:</span><span class="sxs-lookup"><span data-stu-id="a4411-126">To ensure that your control is redrawn every time it is resized, add the following line to the constructor of your control:</span></span>  
  
```vb  
SetStyle(ControlStyles.ResizeRedraw, True)  
```  
  
```csharp  
SetStyle(ControlStyles.ResizeRedraw, true);  
```  
  
> [!NOTE]
> <span data-ttu-id="a4411-127"><xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType>使用属性实现非矩形控件。</span><span class="sxs-lookup"><span data-stu-id="a4411-127">Use the <xref:System.Windows.Forms.Control.Region%2A?displayProperty=nameWithType> property to implement a non-rectangular control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4411-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4411-128">See also</span></span>

- <xref:System.Windows.Forms.Control.Region%2A>
- <xref:System.Windows.Forms.ControlStyles>
- <xref:System.Drawing.Graphics>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- <xref:System.Windows.Forms.PaintEventArgs>
- [<span data-ttu-id="a4411-129">如何：为绘图创建图形对象</span><span class="sxs-lookup"><span data-stu-id="a4411-129">How to: Create Graphics Objects for Drawing</span></span>](../advanced/how-to-create-graphics-objects-for-drawing.md)
- [<span data-ttu-id="a4411-130">构成控件</span><span class="sxs-lookup"><span data-stu-id="a4411-130">Constituent Controls</span></span>](constituent-controls.md)
- [<span data-ttu-id="a4411-131">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="a4411-131">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
