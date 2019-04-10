---
title: 如何：使用 Thumb 重设画布大小
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resizing Canvas control [WPF]
- controls [WPF], Thumb
- controls [WPF], Canvas
- Thumb control [WPF]
- Canvas control [WPF]
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
ms.openlocfilehash: 14942157429b029147d47e2f88428c56e66523d1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146349"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="cf232-102">如何：使用 Thumb 重设画布大小</span><span class="sxs-lookup"><span data-stu-id="cf232-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="cf232-103">此示例演示如何使用<xref:System.Windows.Controls.Primitives.Thumb>控件来调整大小<xref:System.Windows.Controls.Canvas>控件。</span><span class="sxs-lookup"><span data-stu-id="cf232-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf232-104">示例</span><span class="sxs-lookup"><span data-stu-id="cf232-104">Example</span></span>  
 <span data-ttu-id="cf232-105"><xref:System.Windows.Controls.Primitives.Thumb>控件提供的拖放功能，可用于移动或调整控件大小通过监视<xref:System.Windows.Controls.Primitives.Thumb.DragStarted>，<xref:System.Windows.Controls.Primitives.Thumb.DragDelta>并<xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>的事件<xref:System.Windows.Controls.Primitives.Thumb>。</span><span class="sxs-lookup"><span data-stu-id="cf232-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="cf232-106">用户开始拖动操作通过鼠标指针暂停在时按鼠标左键<xref:System.Windows.Controls.Primitives.Thumb>控件。</span><span class="sxs-lookup"><span data-stu-id="cf232-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="cf232-107">只要保持按下鼠标左键，将继续拖动操作。</span><span class="sxs-lookup"><span data-stu-id="cf232-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="cf232-108">在拖动操作期间<xref:System.Windows.Controls.Primitives.Thumb.DragDelta>可以多次出现。</span><span class="sxs-lookup"><span data-stu-id="cf232-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="cf232-109">每次它出现时，<xref:System.Windows.Controls.Primitives.DragDeltaEventArgs>类提供的对应的鼠标位置更改的位置更改。</span><span class="sxs-lookup"><span data-stu-id="cf232-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="cf232-110">当用户释放鼠标左键时，已完成拖动操作。</span><span class="sxs-lookup"><span data-stu-id="cf232-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="cf232-111">拖动操作仅提供了新的坐标，;它不会自动重新<xref:System.Windows.Controls.Primitives.Thumb>。</span><span class="sxs-lookup"><span data-stu-id="cf232-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="cf232-112">下面的示例演示<xref:System.Windows.Controls.Primitives.Thumb>控件的子元素<xref:System.Windows.Controls.Canvas>控件。</span><span class="sxs-lookup"><span data-stu-id="cf232-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="cf232-113">事件处理程序及其<xref:System.Windows.Controls.Primitives.Thumb.DragDelta>事件提供逻辑来移动<xref:System.Windows.Controls.Primitives.Thumb>并调整其大小<xref:System.Windows.Controls.Canvas>。</span><span class="sxs-lookup"><span data-stu-id="cf232-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="cf232-114">事件处理程序<xref:System.Windows.Controls.Primitives.Thumb.DragStarted>并<xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>事件更改的颜色<xref:System.Windows.Controls.Primitives.Thumb>拖动操作过程。</span><span class="sxs-lookup"><span data-stu-id="cf232-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="cf232-115">下面的示例定义<xref:System.Windows.Controls.Primitives.Thumb>。</span><span class="sxs-lookup"><span data-stu-id="cf232-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="cf232-116">下面的示例演示<xref:System.Windows.Controls.Primitives.Thumb.DragDelta>事件处理程序移入<xref:System.Windows.Controls.Primitives.Thumb>并调整其大小<xref:System.Windows.Controls.Canvas>以响应鼠标移动。</span><span class="sxs-lookup"><span data-stu-id="cf232-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="cf232-117">下面的示例演示<xref:System.Windows.Controls.Primitives.Thumb.DragStarted>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cf232-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="cf232-118">下面的示例演示<xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cf232-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="cf232-119">有关完整示例，请参阅[Thumb 拖放功能示例](https://go.microsoft.com/fwlink/?LinkID=160042)。</span><span class="sxs-lookup"><span data-stu-id="cf232-119">For the complete sample, see [Thumb Drag Functionality Sample](https://go.microsoft.com/fwlink/?LinkID=160042).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf232-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf232-120">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
