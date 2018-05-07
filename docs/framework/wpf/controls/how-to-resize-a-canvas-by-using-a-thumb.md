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
ms.openlocfilehash: c3e7176b0578c8fdc5f4331ad8f3b464f3a88b51
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>如何：使用 Thumb 调整画布的大小
此示例演示如何使用<xref:System.Windows.Controls.Primitives.Thumb>控件调整大小<xref:System.Windows.Controls.Canvas>控件。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.Primitives.Thumb>控件提供可用来移动或调整控件大小通过监视的拖动功能<xref:System.Windows.Controls.Primitives.Thumb.DragStarted>，<xref:System.Windows.Controls.Primitives.Thumb.DragDelta>和<xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>的事件<xref:System.Windows.Controls.Primitives.Thumb>。  
  
 用户开始拖动操作通过鼠标指针暂停在时按鼠标左键<xref:System.Windows.Controls.Primitives.Thumb>控件。 只要保持按下鼠标左键，将继续拖动操作。 在拖动操作过程中<xref:System.Windows.Controls.Primitives.Thumb.DragDelta>可以出现多次。 每次它出现时，<xref:System.Windows.Controls.Primitives.DragDeltaEventArgs>类提供对应于鼠标位置的变化的位置中的更改。 当用户释放鼠标左键时，完成拖动操作。 在拖动操作仅提供新坐标;它不会自动重新<xref:System.Windows.Controls.Primitives.Thumb>。  
  
 下面的示例演示<xref:System.Windows.Controls.Primitives.Thumb>即控制的子元素<xref:System.Windows.Controls.Canvas>控件。 事件处理程序其<xref:System.Windows.Controls.Primitives.Thumb.DragDelta>事件提供逻辑来移动<xref:System.Windows.Controls.Primitives.Thumb>并调整其大小<xref:System.Windows.Controls.Canvas>。 事件处理程序<xref:System.Windows.Controls.Primitives.Thumb.DragStarted>和<xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>事件更改的颜色<xref:System.Windows.Controls.Primitives.Thumb>拖动操作过程。 下面的示例定义<xref:System.Windows.Controls.Primitives.Thumb>。  
  
 [!code-xaml[Thumb#thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 下面的示例演示<xref:System.Windows.Controls.Primitives.Thumb.DragDelta>移动的事件处理程序<xref:System.Windows.Controls.Primitives.Thumb>并调整其大小<xref:System.Windows.Controls.Canvas>鼠标移动到的响应中。  
  
 [!code-csharp[Thumb#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 下面的示例演示<xref:System.Windows.Controls.Primitives.Thumb.DragStarted>事件处理程序。  
  
 [!code-csharp[Thumb#DragStartedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 下面的示例演示<xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>事件处理程序。  
  
 [!code-csharp[Thumb#DragCompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 有关完整的示例，请参阅[Thumb 拖功能示例](http://go.microsoft.com/fwlink/?LinkID=160042)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.Primitives.Thumb>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
