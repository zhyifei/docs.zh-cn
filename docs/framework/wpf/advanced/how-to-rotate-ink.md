---
title: 如何：旋转墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], rotating
- rotating ink [WPF]
ms.assetid: fac36cc9-dd01-41ca-9bde-9d33e3790bbe
ms.openlocfilehash: 51b06ec98b916a9f2f90a84b42007ef4c596ac60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545472"
---
# <a name="how-to-rotate-ink"></a><span data-ttu-id="d1123-102">如何：旋转墨迹</span><span class="sxs-lookup"><span data-stu-id="d1123-102">How to: Rotate Ink</span></span>
## <a name="example"></a><span data-ttu-id="d1123-103">示例</span><span class="sxs-lookup"><span data-stu-id="d1123-103">Example</span></span>  
 <span data-ttu-id="d1123-104">下面的示例将复制从墨迹<xref:System.Windows.Controls.InkCanvas>到<xref:System.Windows.Controls.Canvas>包含<xref:System.Windows.Controls.InkPresenter>。</span><span class="sxs-lookup"><span data-stu-id="d1123-104">The following example copies the ink from an <xref:System.Windows.Controls.InkCanvas> to a <xref:System.Windows.Controls.Canvas> that contains an <xref:System.Windows.Controls.InkPresenter>.</span></span>  <span data-ttu-id="d1123-105">当应用程序复制墨迹时，它还会将墨迹顺时针旋转 90 度。</span><span class="sxs-lookup"><span data-stu-id="d1123-105">When the application copies the ink, it also rotates the ink 90 degrees clockwise.</span></span>  
  
 [!code-xaml[HowToRotateInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[HowToRotateInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="d1123-106">示例</span><span class="sxs-lookup"><span data-stu-id="d1123-106">Example</span></span>  
 <span data-ttu-id="d1123-107">下面的示例是一个自定义<xref:System.Windows.Documents.Adorner>上旋转描边<xref:System.Windows.Controls.InkPresenter>。</span><span class="sxs-lookup"><span data-stu-id="d1123-107">The following example is a custom <xref:System.Windows.Documents.Adorner> that rotates the strokes on an <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-csharp[AdornerForStrokes#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/RotatingAdornerForStrokes.cs#1)]
 [!code-vb[AdornerForStrokes#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/RotatingAdornerForStrokes.vb#1)]  
  
 <span data-ttu-id="d1123-108">下面的示例是[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]定义文件<xref:System.Windows.Controls.InkPresenter>墨迹并用其填充它。</span><span class="sxs-lookup"><span data-stu-id="d1123-108">The following example is a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file that defines an <xref:System.Windows.Controls.InkPresenter> and populates it with ink.</span></span> <span data-ttu-id="d1123-109">`Window_Loaded`事件处理程序会添加到自定义的装饰器<xref:System.Windows.Controls.InkPresenter>。</span><span class="sxs-lookup"><span data-stu-id="d1123-109">The `Window_Loaded` event handler adds the custom adorner to the <xref:System.Windows.Controls.InkPresenter>.</span></span>  
  
 [!code-xaml[AdornerForStrokes#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[AdornerForStrokes#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml.cs#3)]
 [!code-vb[AdornerForStrokes#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/Window1.xaml.vb#3)]
