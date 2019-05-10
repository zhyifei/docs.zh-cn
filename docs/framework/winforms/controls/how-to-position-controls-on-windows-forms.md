---
title: 如何：在 Windows 窗体上定位控件
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
ms.openlocfilehash: 241edbe60c327493c9123c6cf7bdc19b7ba2b724
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211655"
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="5db0f-102">如何：在 Windows 窗体上定位控件</span><span class="sxs-lookup"><span data-stu-id="5db0f-102">How to: Position Controls on Windows Forms</span></span>

<span data-ttu-id="5db0f-103">若要定位控件，在 Visual Studio 中使用 Windows 窗体设计器或指定<xref:System.Windows.Forms.Control.Location%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="5db0f-103">To position controls, use the Windows Forms Designer in Visual Studio or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>

## <a name="position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="5db0f-104">Windows 窗体设计器在设计图面上的将控件放</span><span class="sxs-lookup"><span data-stu-id="5db0f-104">Position a control on the design surface of the Windows Forms Designer</span></span>

<span data-ttu-id="5db0f-105">在 Visual Studio 中，将控件拖动到用鼠标的适当位置。</span><span class="sxs-lookup"><span data-stu-id="5db0f-105">In Visual Studio, drag the control to the appropriate location with the mouse.</span></span>

> [!NOTE]
> <span data-ttu-id="5db0f-106">选择控件并移动它带有箭头键以更精确地放置。</span><span class="sxs-lookup"><span data-stu-id="5db0f-106">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="5db0f-107">此外，*对齐线*帮助您在放置在窗体上精确的控制。</span><span class="sxs-lookup"><span data-stu-id="5db0f-107">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="5db0f-108">有关详细信息，请参见[演练：在 Windows 上排列控件窗体使用对齐线](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)。</span><span class="sxs-lookup"><span data-stu-id="5db0f-108">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>

## <a name="position-a-control-using-the-properties-window"></a><span data-ttu-id="5db0f-109">定位控件的使用属性窗口</span><span class="sxs-lookup"><span data-stu-id="5db0f-109">Position a control using the Properties window</span></span>

1. <span data-ttu-id="5db0f-110">在 Visual Studio 中，单击你想要定位的控件。</span><span class="sxs-lookup"><span data-stu-id="5db0f-110">In Visual Studio, click the control you want to position.</span></span>

2. <span data-ttu-id="5db0f-111">在中**属性**窗口中，类型值<xref:System.Windows.Forms.Control.Location%2A>属性，由逗号分隔，以放置在其容器内的控件。</span><span class="sxs-lookup"><span data-stu-id="5db0f-111">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>

     <span data-ttu-id="5db0f-112">第一个数字 (X) 是容器的从左边框; 的距离第二个数字 (Y) 是上边界的容器区域中，以像素为单位的距离。</span><span class="sxs-lookup"><span data-stu-id="5db0f-112">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5db0f-113">您可以展开<xref:System.Windows.Forms.Control.Location%2A>属性键入**X**并**Y**单独值。</span><span class="sxs-lookup"><span data-stu-id="5db0f-113">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>

## <a name="position-a-control-programmatically"></a><span data-ttu-id="5db0f-114">以编程方式定位控件</span><span class="sxs-lookup"><span data-stu-id="5db0f-114">Position a control programmatically</span></span>

1. <span data-ttu-id="5db0f-115">设置<xref:System.Windows.Forms.Control.Location%2A>到控件属性<xref:System.Drawing.Point>。</span><span class="sxs-lookup"><span data-stu-id="5db0f-115">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>

    ```vb
    Button1.Location = New Point(100, 100)
    ```

    ```csharp
    button1.Location = new Point(100, 100);
    ```

    ```cpp
    button1->Location = Point(100, 100);
    ```

2. <span data-ttu-id="5db0f-116">更改控件的位置的 X 坐标使用<xref:System.Windows.Forms.Control.Left%2A>子属性。</span><span class="sxs-lookup"><span data-stu-id="5db0f-116">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>

    ```vb
    Button1.Left = 300
    ```

    ```csharp
    button1.Left = 300;
    ```

    ```cpp
    button1->Left = 300;
    ```

## <a name="increment-a-controls-location-programmatically"></a><span data-ttu-id="5db0f-117">以编程方式递增控件的位置</span><span class="sxs-lookup"><span data-stu-id="5db0f-117">Increment a control's location programmatically</span></span>

<span data-ttu-id="5db0f-118">设置<xref:System.Windows.Forms.Control.Left%2A>子属性要递增的控件的 X 坐标。</span><span class="sxs-lookup"><span data-stu-id="5db0f-118">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>

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
> <span data-ttu-id="5db0f-119">使用<xref:System.Windows.Forms.Control.Location%2A>要设置控件的 X 和 Y 属性将同时定位。</span><span class="sxs-lookup"><span data-stu-id="5db0f-119">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="5db0f-120">若要单独设置位置，请使用控件的<xref:System.Windows.Forms.Control.Left%2A>(**X**) 或<xref:System.Windows.Forms.Control.Top%2A>(**Y**) 子属性。</span><span class="sxs-lookup"><span data-stu-id="5db0f-120">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="5db0f-121">不要尝试隐式设置的 X 和 Y 坐标<xref:System.Drawing.Point>结构，它表示该按钮的位置，因为此结构包含按钮的坐标的副本。</span><span class="sxs-lookup"><span data-stu-id="5db0f-121">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>

## <a name="see-also"></a><span data-ttu-id="5db0f-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="5db0f-122">See also</span></span>

- [<span data-ttu-id="5db0f-123">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="5db0f-123">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="5db0f-124">演练：使用对齐线的 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="5db0f-124">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [<span data-ttu-id="5db0f-125">演练：使用 TableLayoutPanel 的 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="5db0f-125">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [<span data-ttu-id="5db0f-126">演练：使用 FlowLayoutPanel 的 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="5db0f-126">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [<span data-ttu-id="5db0f-127">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="5db0f-127">Arranging Controls on Windows Forms</span></span>](arranging-controls-on-windows-forms.md)
- [<span data-ttu-id="5db0f-128">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="5db0f-128">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="5db0f-129">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="5db0f-129">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="5db0f-130">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="5db0f-130">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="5db0f-131">[如何：设置 Windows 窗体的屏幕位置](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5db0f-131">[How to: Set the Screen Location of Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))</span></span>
