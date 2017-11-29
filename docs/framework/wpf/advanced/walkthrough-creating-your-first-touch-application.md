---
title: "演练：创建您的第一个触控应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ee85a5d8764fc27205cf09e1af43069b25096ef1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-your-first-touch-application"></a>演练：创建您的第一个触控应用程序
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]允许应用程序响应触摸屏。 例如，你可以通过使用一个与应用程序交互或多个手指触摸式设备，如本演练中创建的应用程序使用户能够移动，请触摸屏上调整大小，或通过使用触摸旋转单个对象。  
  
## <a name="prerequisites"></a>先决条件  
 你需要以下组件来完成本演练：  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)]。  
  
-   Windows 7。  
  
-   接受触摸屏输入，如触摸屏，能够支持 Windows 触摸屏的设备。  
  
 此外，应该基本了解如何创建中的应用程序的[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，尤其是如何订阅和处理事件。 有关详细信息，请参阅[演练： 我第一个 WPF 桌面应用程序](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)。  
  
## <a name="creating-the-application"></a>创建应用程序  
  
#### <a name="to-create-the-application"></a>创建应用程序  
  
1.  在 Visual Basic 或 Visual C# 中创建名为 `BasicManipulation` 的新 WPF 应用程序项目。 有关详细信息，请参阅[如何：创建新的 WPF 应用程序项目](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)。  
  
2.  MainWindow.xaml 的内容替换为以下 XAML。  
  
     此标记创建的简单应用程序包含一个红色<xref:System.Windows.Shapes.Rectangle>上<xref:System.Windows.Controls.Canvas>。 <xref:System.Windows.UIElement.IsManipulationEnabled%2A>属性<xref:System.Windows.Shapes.Rectangle>设置为 true，因此，它将收到操作事件。 应用程序订阅<xref:System.Windows.UIElement.ManipulationStarting>， <xref:System.Windows.UIElement.ManipulationDelta>，和<xref:System.Windows.UIElement.ManipulationInertiaStarting>事件。 这些事件包含要移动的逻辑<xref:System.Windows.Shapes.Rectangle>用户处理。  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  如果使用的 Visual Basic 中，在 MainWindow.xaml 的第一行中，将`x:Class="BasicManipulation.MainWindow"`与`x:Class="MainWindow"`。  
  
4.  在`MainWindow`类中，添加以下<xref:System.Windows.UIElement.ManipulationStarting>事件处理程序。  
  
     <xref:System.Windows.UIElement.ManipulationStarting>事件发生时[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]检测到触控输入开始的对象执行操作。 该代码指定操作的位置应为相对于<xref:System.Windows.Window>通过设置<xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>属性。  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  在`MainWindow`类中，添加以下<xref:System.Windows.Input.ManipulationDelta>事件处理程序。  
  
     <xref:System.Windows.Input.ManipulationDelta>触摸输入更改位置，并且可以在操作过程中发生多次时发生事件。 引发手指后，也可能发生此事件。 例如，如果用户在屏幕上拖动手指<xref:System.Windows.Input.ManipulationDelta>事件在手指移动时出现多次。 当用户悬停在屏幕中，为指<xref:System.Windows.Input.ManipulationDelta>事件会不断发生以模拟惯性。  
  
     该代码将应用<xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A>到<xref:System.Windows.UIElement.RenderTransform%2A>的<xref:System.Windows.Shapes.Rectangle>将其移动在用户移动触控输入。 它还检查是否<xref:System.Windows.Shapes.Rectangle>超出数组界限的<xref:System.Windows.Window>事件惯性过程中发生时。 如果是，应用程序调用<xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType>方法来结束操作。  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  在`MainWindow`类中，添加以下<xref:System.Windows.UIElement.ManipulationInertiaStarting>事件处理程序。  
  
     <xref:System.Windows.UIElement.ManipulationInertiaStarting>用户悬停在屏幕中的所有指时发生事件。 该代码设置的初始速度和减速移动、 扩展以及在该矩形的旋转。  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  生成并运行该项目。  
  
     你应看到在窗口中显示一个红色正方形。  
  
## <a name="testing-the-application"></a>测试应用程序  
 若要测试应用程序，请尝试执行下列操作。 请注意你可以执行多个以下项之一在同一时间进行操作。  
  
-   若要移动<xref:System.Windows.Shapes.Rectangle>，置于手指<xref:System.Windows.Shapes.Rectangle>和在屏幕上移动上方的手指。  
  
-   若要调整大小<xref:System.Windows.Shapes.Rectangle>，放入两根手指<xref:System.Windows.Shapes.Rectangle>并移动指，或将其彼此。  
  
-   要旋转<xref:System.Windows.Shapes.Rectangle>，放入两根手指<xref:System.Windows.Shapes.Rectangle>并旋转相互环绕指。  
  
 若要使惯性，快速执行上一操作时引发手指从屏幕。 <xref:System.Windows.Shapes.Rectangle>将继续移动、 调整大小，或旋转它停止前几秒钟。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>
