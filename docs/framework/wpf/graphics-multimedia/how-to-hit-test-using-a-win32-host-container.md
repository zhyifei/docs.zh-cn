---
title: "如何：使用 Win32 宿主容器执行命中测试"
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
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9a5cb77a53cbb106593b70d618bab67ef816e901
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a><span data-ttu-id="39c99-102">如何：使用 Win32 宿主容器执行命中测试</span><span class="sxs-lookup"><span data-stu-id="39c99-102">How to: Hit Test Using a Win32 Host Container</span></span>
<span data-ttu-id="39c99-103">你可以创建视觉对象中的[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]窗口是通过为可视对象提供宿主窗口容器。</span><span class="sxs-lookup"><span data-stu-id="39c99-103">You can create visual objects within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window by providing a host window container for the visual objects.</span></span> <span data-ttu-id="39c99-104">若要为包含的视觉对象提供事件处理，需要处理传递到宿主窗口容器的消息筛选器循环的消息。</span><span class="sxs-lookup"><span data-stu-id="39c99-104">To provide event handling for the contained visual objects you process the messages passed to the host window container’s message filter loop.</span></span> <span data-ttu-id="39c99-105">请参阅[教程： 在 Win32 应用程序中承载视觉对象](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)有关如何托管中的可视化对象的详细信息[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口。</span><span class="sxs-lookup"><span data-stu-id="39c99-105">Refer to [Tutorial: Hosting Visual Objects in a Win32 Application](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md) for more information on how to host visual objects in a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39c99-106">示例</span><span class="sxs-lookup"><span data-stu-id="39c99-106">Example</span></span>  
 <span data-ttu-id="39c99-107">下面的代码演示如何设置鼠标事件处理程序[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]用作视觉对象的宿主容器的窗口。</span><span class="sxs-lookup"><span data-stu-id="39c99-107">The following code shows how to set up mouse event handlers for a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] window that is used as a host container for visual objects.</span></span>  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 <span data-ttu-id="39c99-108">下面的示例演示如何设置以捕获特定的鼠标事件的响应的命中测试。</span><span class="sxs-lookup"><span data-stu-id="39c99-108">The following example shows how to set up a hit test in response to trapping specific mouse events.</span></span>  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <span data-ttu-id="39c99-109"><xref:System.Windows.Interop.HwndSource>对象代表[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]中的内容[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]窗口。</span><span class="sxs-lookup"><span data-stu-id="39c99-109">The <xref:System.Windows.Interop.HwndSource> object presents [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content within a [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] window.</span></span> <span data-ttu-id="39c99-110">值<xref:System.Windows.Interop.HwndSource.RootVisual%2A>属性<xref:System.Windows.Interop.HwndSource>对象表示可视化树层次结构中的最顶层节点。</span><span class="sxs-lookup"><span data-stu-id="39c99-110">The value of the <xref:System.Windows.Interop.HwndSource.RootVisual%2A> property of the <xref:System.Windows.Interop.HwndSource> object represents the top-most node in the visual tree hierarchy.</span></span>  
  
 <span data-ttu-id="39c99-111">上的命中测试的完整示例对象使用 Win32 宿主容器，请参阅[命中测试的 Win32 间的互操作示例](http://go.microsoft.com/fwlink/?LinkID=159995)。</span><span class="sxs-lookup"><span data-stu-id="39c99-111">For the complete sample on hit testing objects using a Win32 host container, see [Hit Test with Win32 Interoperation Sample](http://go.microsoft.com/fwlink/?LinkID=159995).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c99-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39c99-112">See Also</span></span>  
 <xref:System.Windows.Interop.HwndSource>  
 [<span data-ttu-id="39c99-113">可视化层中的命中测试</span><span class="sxs-lookup"><span data-stu-id="39c99-113">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [<span data-ttu-id="39c99-114">教程：在 Win32 应用程序中承载视觉对象</span><span class="sxs-lookup"><span data-stu-id="39c99-114">Tutorial: Hosting Visual Objects in a Win32 Application</span></span>](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)
