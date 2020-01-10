---
title: 如何：使用 Win32 宿主容器执行命中测试
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: b71783f2d061c9139de4449d8e0106eb00345894
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740175"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>如何：使用 Win32 宿主容器执行命中测试
可以通过为视觉对象提供主机窗口容器，在 Win32 窗口中创建视觉对象。 若要为包含的视觉对象提供事件处理，需要处理传递到宿主窗口容器的消息筛选器循环的消息。 有关如何在 Win32 窗口中承载视觉对象的详细信息，请参阅[教程：在 Win32 应用程序中承载视觉对象](tutorial-hosting-visual-objects-in-a-win32-application.md)。  
  
## <a name="example"></a>示例  
 下面的代码演示如何为 Win32 窗口设置鼠标事件处理程序，该窗口用作视觉对象的宿主容器。  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 下面的示例演示如何设置用于响应捕获特定鼠标事件的命中测试。  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <xref:System.Windows.Interop.HwndSource> 对象在 Win32 窗口中提供 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 内容。 <xref:System.Windows.Interop.HwndSource> 对象的 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 属性的值表示可视化树层次结构中最顶层的节点。  
  
 有关使用 Win32 主机容器命中测试对象的完整示例，请参阅[使用 Win32 互操作进行命中测试示例](https://go.microsoft.com/fwlink/?LinkID=159995)。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Interop.HwndSource>
- [可视化层中的命中测试](hit-testing-in-the-visual-layer.md)
- [教程：在 Win32 应用程序中承载视觉对象](tutorial-hosting-visual-objects-in-a-win32-application.md)
