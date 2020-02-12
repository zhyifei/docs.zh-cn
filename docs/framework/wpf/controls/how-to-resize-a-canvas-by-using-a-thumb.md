---
title: 如何：使用 Thumb 调整画布的大小
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
ms.openlocfilehash: 84f5ac2b53124b7f4d7c15741e94b40e7ee81526
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124294"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>如何：使用 Thumb 调整画布的大小
此示例演示如何使用 <xref:System.Windows.Controls.Primitives.Thumb> 控件调整 <xref:System.Windows.Controls.Canvas> 控件的大小。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.Primitives.Thumb> 控件提供的拖动功能可用于通过监视 <xref:System.Windows.Controls.Primitives.Thumb>的 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>、<xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 和 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 事件来移动控件或调整控件的大小。  
  
 当鼠标指针在 <xref:System.Windows.Controls.Primitives.Thumb> 控件上暂停时，用户通过按鼠标左键开始拖动操作。 只要鼠标左键处于按下状态，拖动操作便会继续。 在拖动操作过程中，<xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 可能发生多次。 每次发生时，<xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> 类都提供与鼠标位置变化相对应的位置的更改。 当用户释放鼠标左键时，拖动操作完成。 拖动操作仅提供新坐标;它不会自动重新定位 <xref:System.Windows.Controls.Primitives.Thumb>。  
  
 下面的示例演示一个 <xref:System.Windows.Controls.Primitives.Thumb> 控件，该控件是 <xref:System.Windows.Controls.Canvas> 控件的子元素。 其 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 事件的事件处理程序提供了用于移动 <xref:System.Windows.Controls.Primitives.Thumb> 和调整 <xref:System.Windows.Controls.Canvas>大小的逻辑。 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> 和 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 事件的事件处理程序在拖动操作过程中更改 <xref:System.Windows.Controls.Primitives.Thumb> 的颜色。 下面的示例定义 <xref:System.Windows.Controls.Primitives.Thumb>。  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 下面的示例演示了 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> 事件处理程序，该处理程序可移动 <xref:System.Windows.Controls.Primitives.Thumb>，并调整 <xref:System.Windows.Controls.Canvas> 大小以响应鼠标移动。  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 下面的示例演示 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> 事件处理程序。  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 下面的示例演示 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> 事件处理程序。  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 有关完整示例，请参阅[Thumb 拖动功能示例](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
