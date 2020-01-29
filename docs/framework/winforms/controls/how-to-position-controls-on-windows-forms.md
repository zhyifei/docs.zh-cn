---
title: 放置控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 144a0021c74f0fb5afec1d511315168fb28528e9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735911"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="f293c-102">如何：在 Windows 窗体上定位控件</span><span class="sxs-lookup"><span data-stu-id="f293c-102">How to: Position controls on Windows Forms</span></span>

<span data-ttu-id="f293c-103">若要定位控件，请使用 Visual Studio 中的 Windows 窗体设计器或指定 <xref:System.Windows.Forms.Control.Location%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="f293c-103">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="f293c-104">在 Windows 窗体设计器的设计图面上放置控件</span><span class="sxs-lookup"><span data-stu-id="f293c-104">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="f293c-105">在 Visual Studio 中，用鼠标将控件拖到适当的位置。</span><span class="sxs-lookup"><span data-stu-id="f293c-105">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="f293c-106">选择控件，并将其与箭头键一起移动，以便更精确地定位。</span><span class="sxs-lookup"><span data-stu-id="f293c-106">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="f293c-107">此外，*对齐线*还有助于在窗体上准确放置控件。</span><span class="sxs-lookup"><span data-stu-id="f293c-107">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="f293c-108">有关详细信息，请参阅[演练：使用对齐线排列 Windows 窗体上的控件](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)。</span><span class="sxs-lookup"><span data-stu-id="f293c-108">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="f293c-109">使用属性窗口定位控件</span><span class="sxs-lookup"><span data-stu-id="f293c-109">Position a control using the Properties window</span></span>

1. <span data-ttu-id="f293c-110">在 Visual Studio 中，选择要定位的控件。</span><span class="sxs-lookup"><span data-stu-id="f293c-110">In Visual Studio, select the control you want to position.</span></span>

2. <span data-ttu-id="f293c-111">在 "**属性**" 窗口中，输入 <xref:System.Windows.Forms.Control.Location%2A> 属性的值（用逗号分隔），以将该控件定位在其容器中。</span><span class="sxs-lookup"><span data-stu-id="f293c-111">In the **Properties** window, enter values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

   <span data-ttu-id="f293c-112">第一个数字（X）是距容器左边框的距离;第二个数字（Y）是与容器区域的上边框的距离（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="f293c-112">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f293c-113">您可以展开 <xref:System.Windows.Forms.Control.Location%2A> 属性，分别键入**X**和**Y**值。</span><span class="sxs-lookup"><span data-stu-id="f293c-113">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="f293c-114">以编程方式定位控件</span><span class="sxs-lookup"><span data-stu-id="f293c-114">Position a control programmatically</span></span>

1. <span data-ttu-id="f293c-115">将控件的 <xref:System.Windows.Forms.Control.Location%2A> 属性设置为 <xref:System.Drawing.Point>。</span><span class="sxs-lookup"><span data-stu-id="f293c-115">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="f293c-116">使用 <xref:System.Windows.Forms.Control.Left%2A> 子属性更改控件位置的 X 坐标。</span><span class="sxs-lookup"><span data-stu-id="f293c-116">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="f293c-117">以编程方式递增控件的位置</span><span class="sxs-lookup"><span data-stu-id="f293c-117">Increment a control's location programmatically</span></span>

<span data-ttu-id="f293c-118">设置 <xref:System.Windows.Forms.Control.Left%2A> 子属性以增加控件的 X 坐标。</span><span class="sxs-lookup"><span data-stu-id="f293c-118">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

```vb
Button1.Left += 200
```

```csharp
button1.Left += 200;
```

```cpp
button1->Left += 200;
```

> [!NOTE]
> <span data-ttu-id="f293c-119">使用 <xref:System.Windows.Forms.Control.Location%2A> 属性可以同时设置控件的 X 和 Y 位置。</span><span class="sxs-lookup"><span data-stu-id="f293c-119">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="f293c-120">若要单独设置位置，请使用控件的 <xref:System.Windows.Forms.Control.Left%2A> （**X**）或 <xref:System.Windows.Forms.Control.Top%2A> （**Y**）子属性。</span><span class="sxs-lookup"><span data-stu-id="f293c-120">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="f293c-121">不要尝试隐式设置表示按钮位置的 <xref:System.Drawing.Point> 结构的 X 和 Y 坐标，因为此结构包含按钮坐标的副本。</span><span class="sxs-lookup"><span data-stu-id="f293c-121">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="f293c-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f293c-122">See also</span></span>

- [<span data-ttu-id="f293c-123">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="f293c-123">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="f293c-124">演练：使用对齐线在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="f293c-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="f293c-125">演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="f293c-125">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="f293c-126">演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="f293c-126">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="f293c-127">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="f293c-127">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="f293c-128">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="f293c-128">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="f293c-129">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="f293c-129">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="f293c-130">[如何：设置的屏幕位置 Windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f293c-130">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>
