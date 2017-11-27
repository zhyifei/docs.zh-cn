---
title: "如何：在 Windows 窗体上定位控件"
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ff1096e6397f4422e0fbf6400a87041cfac6470
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-position-controls-on-windows-forms"></a><span data-ttu-id="92117-102">如何：在 Windows 窗体上定位控件</span><span class="sxs-lookup"><span data-stu-id="92117-102">How to: Position Controls on Windows Forms</span></span>
<span data-ttu-id="92117-103">若要放置控件，请使用 Windows 窗体设计器中，或指定<xref:System.Windows.Forms.Control.Location%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="92117-103">To position controls, use the Windows Forms Designer, or specify the <xref:System.Windows.Forms.Control.Location%2A> property.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92117-104">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="92117-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="92117-105">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="92117-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="92117-106">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="92117-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a><span data-ttu-id="92117-107">若要在 Windows 窗体设计器的设计图面上将控件放</span><span class="sxs-lookup"><span data-stu-id="92117-107">To position a control on the design surface of the Windows Forms Designer</span></span>  
  
-   <span data-ttu-id="92117-108">将控件拖到使用鼠标的适当位置。</span><span class="sxs-lookup"><span data-stu-id="92117-108">Drag the control to the appropriate location with the mouse.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92117-109">选择控件，并移动它带有箭头键以更精确地放置。</span><span class="sxs-lookup"><span data-stu-id="92117-109">Select the control and move it with the ARROW keys to position it more precisely.</span></span> <span data-ttu-id="92117-110">此外，*对齐线*有助于在你的窗体上精确地放置控件。</span><span class="sxs-lookup"><span data-stu-id="92117-110">Also, *snaplines* assist you in placing controls precisely on your form.</span></span> <span data-ttu-id="92117-111">有关详细信息，请参阅[演练： 在 Windows 窗体使用对齐线上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)。</span><span class="sxs-lookup"><span data-stu-id="92117-111">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
### <a name="to-position-a-control-using-the-properties-window"></a><span data-ttu-id="92117-112">若要使用属性窗口将控件放</span><span class="sxs-lookup"><span data-stu-id="92117-112">To position a control using the Properties window</span></span>  
  
1.  <span data-ttu-id="92117-113">单击你想要定位的控件。</span><span class="sxs-lookup"><span data-stu-id="92117-113">Click the control you want to position.</span></span>  
  
2.  <span data-ttu-id="92117-114">在**属性**窗口中，类型值<xref:System.Windows.Forms.Control.Location%2A>属性，使用逗号分隔，以定位该控件在其容器内的。</span><span class="sxs-lookup"><span data-stu-id="92117-114">In the **Properties** window, type values for the <xref:System.Windows.Forms.Control.Location%2A> property, separated by a comma, to position the control within its container.</span></span>  
  
     <span data-ttu-id="92117-115">第一个数字 (X) 是从容器; 的左边框的距离第二个数字 (Y) 是从上边界的容器区域中，以像素为单位的距离。</span><span class="sxs-lookup"><span data-stu-id="92117-115">The first number (X) is the distance from the left border of the container; the second number (Y) is the distance from the upper border of the container area, measured in pixels.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92117-116">你可以展开<xref:System.Windows.Forms.Control.Location%2A>属性键入**X**和**Y**单独值。</span><span class="sxs-lookup"><span data-stu-id="92117-116">You can expand the <xref:System.Windows.Forms.Control.Location%2A> property to type the **X** and **Y** values individually.</span></span>  
  
### <a name="to-position-a-control-programmatically"></a><span data-ttu-id="92117-117">以编程方式定位控件</span><span class="sxs-lookup"><span data-stu-id="92117-117">To position a control programmatically</span></span>  
  
1.  <span data-ttu-id="92117-118">设置<xref:System.Windows.Forms.Control.Location%2A>该控件的属性<xref:System.Drawing.Point>。</span><span class="sxs-lookup"><span data-stu-id="92117-118">Set the <xref:System.Windows.Forms.Control.Location%2A> property of the control to a <xref:System.Drawing.Point>.</span></span>  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  <span data-ttu-id="92117-119">更改控件的位置的 X 坐标使用<xref:System.Windows.Forms.Control.Left%2A>子属性。</span><span class="sxs-lookup"><span data-stu-id="92117-119">Change the X coordinate of the control's location using the <xref:System.Windows.Forms.Control.Left%2A> subproperty.</span></span>  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a><span data-ttu-id="92117-120">若要以编程方式递增控件的位置</span><span class="sxs-lookup"><span data-stu-id="92117-120">To increment a control's location programmatically</span></span>  
  
1.  <span data-ttu-id="92117-121">设置<xref:System.Windows.Forms.Control.Left%2A>子属性可增加该控件的 X 坐标。</span><span class="sxs-lookup"><span data-stu-id="92117-121">Set the <xref:System.Windows.Forms.Control.Left%2A> subproperty to increment the X coordinate of the control.</span></span>  
  
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
    >  <span data-ttu-id="92117-122">使用<xref:System.Windows.Forms.Control.Location%2A>属性来设置控件的 X 和 Y 将同时定位。</span><span class="sxs-lookup"><span data-stu-id="92117-122">Use the <xref:System.Windows.Forms.Control.Location%2A> property to set a control's X and Y positions simultaneously.</span></span> <span data-ttu-id="92117-123">若要单独设置位置，请使用控件的<xref:System.Windows.Forms.Control.Left%2A>(**X**) 或<xref:System.Windows.Forms.Control.Top%2A>(**Y**) 子属性。</span><span class="sxs-lookup"><span data-stu-id="92117-123">To set a position individually, use the control's <xref:System.Windows.Forms.Control.Left%2A> (**X**) or <xref:System.Windows.Forms.Control.Top%2A> (**Y**) subproperty.</span></span> <span data-ttu-id="92117-124">不要尝试隐式设置的 X 和 Y 坐标<xref:System.Drawing.Point>结构，它表示该按钮的位置，因为此结构包含按钮的坐标的副本。</span><span class="sxs-lookup"><span data-stu-id="92117-124">Do not try to implicitly set the X and Y coordinates of the <xref:System.Drawing.Point> structure that represents the button's location, because this structure contains a copy of the button's coordinates.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92117-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92117-125">See Also</span></span>  
 [<span data-ttu-id="92117-126">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="92117-126">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="92117-127">演练：使用对齐线在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="92117-127">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="92117-128">演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="92117-128">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [<span data-ttu-id="92117-129">演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="92117-129">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [<span data-ttu-id="92117-130">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="92117-130">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="92117-131">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="92117-131">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="92117-132">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="92117-132">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="92117-133">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="92117-133">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [<span data-ttu-id="92117-134">如何： 设置 Windows 窗体的屏幕位置</span><span class="sxs-lookup"><span data-stu-id="92117-134">How to: Set the Screen Location of Windows Forms</span></span>](http://msdn.microsoft.com/en-us/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)
