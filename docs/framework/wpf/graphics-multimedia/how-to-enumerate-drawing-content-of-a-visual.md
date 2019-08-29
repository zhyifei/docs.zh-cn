---
title: 如何：枚举视觉对象的绘图内容
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 25aa0c3706005c1e16cedd7e06914db764545ebb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930074"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a>如何：枚举视觉对象的绘图内容
对象提供用于枚举的内容<xref:System.Windows.Media.Visual>的对象模型。 <xref:System.Windows.Media.Drawing>  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>方法来<xref:System.Windows.Media.DrawingGroup>检索的<xref:System.Windows.Media.Visual>值并对其进行枚举。  
  
> [!NOTE]
> 枚举视觉对象的内容时, 您是在检索<xref:System.Windows.Media.Drawing>对象, 而不是以矢量图形指令列表的形式呈现数据。 有关详细信息，请参阅 [WPF 图形呈现概述](wpf-graphics-rendering-overview.md)。  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.Drawing>
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.VisualTreeHelper>
- [Drawing 对象概述](drawing-objects-overview.md)
- [WPF 图形呈现概述](wpf-graphics-rendering-overview.md)
