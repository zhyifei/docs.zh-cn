---
title: 自定义呈现墨迹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom-rendering ink
- ink [WPF], custom-rendering
- classes [WPF], InkCanvas
ms.assetid: 65c978a7-0ee0-454f-ac7f-b1bd2efecac5
ms.openlocfilehash: 0ceb831057a9a92aa7319d2004f04d7cf5ac820e
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111824"
---
# <a name="custom-rendering-ink"></a>自定义呈现墨迹
描<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>边的属性允许您指定描边的外观，例如其大小、颜色和形状，但有时可能需要自定义超出<xref:System.Windows.Ink.Stroke.DrawingAttributes%2A>允许的外观。 建议通过使用喷笔、油画和多种其他效果呈现外观，从而自定义墨迹的外观。 Windows 演示文稿基础 （WPF） 允许您通过实现自定义<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>和<xref:System.Windows.Ink.Stroke>对象来自定义渲染墨迹。  
  
 本主题包含以下小节：  
  
- [建筑](#Architecture)  
  
- [实现动态呈现器](#ImplementingADynamicRenderer)  
  
- [实现自定义笔划](#ImplementingCustomStrokes)  
  
- [实现自定义 InkCanvas](#ImplementingACustomInkCanvas)  
  
- [结论](#Conclusion)  
  
<a name="Architecture"></a>
## <a name="architecture"></a>体系结构  
 墨迹呈现会出现两次：用户将墨迹写入墨迹书写表面时，以及将笔划添加到启用了墨迹的表面之后。 当用户<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>在数字化器上移动 Tablet 笔时，渲<xref:System.Windows.Ink.Stroke>染墨迹，并在将 Tablet 笔添加到元素后渲染。  
  
 动态呈现墨迹时需要实现三个类。  
  
1. **动态呈现器**：实现派生自<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>的类。 此类是专门<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>化的，用于在绘制描边时呈现笔画。 在<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>单独的线程上执行渲染，因此，即使应用程序用户界面 （UI） 线程被阻止，墨迹表面也会显示收集墨迹。 有关线程模型的详细信息，请参阅[墨迹线程模型](the-ink-threading-model.md)。 要自定义动态渲染描边，请重写<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A>方法。  
  
2. **描边**：实现派生自<xref:System.Windows.Ink.Stroke>的类。 此类负责<xref:System.Windows.Input.StylusPoint>将数据转换为<xref:System.Windows.Ink.Stroke>对象后静态呈现数据。 重写<xref:System.Windows.Ink.Stroke.DrawCore%2A>方法以确保描边的静态呈现与动态渲染一致。  
  
3. **墨水画布：** 实现派生自<xref:System.Windows.Controls.InkCanvas>的类。 将自定义<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>属性分配给<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>属性。 重写<xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A>方法并将自定义描边添加到<xref:System.Windows.Controls.InkCanvas.Strokes%2A>属性。 这样可以确保墨迹外观一致。  
  
<a name="ImplementingADynamicRenderer"></a>
## <a name="implementing-a-dynamic-renderer"></a>实现动态呈现器  
 尽管<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>类是 的标准部分[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，但要执行更专用的渲染，则必须创建从 派生<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>并重写<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.OnDraw%2A>方法的自定义动态渲染器。  
  
 下面的示例演示了使用线性<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>渐变画笔效果绘制墨迹的自定义。  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#1)]
[!code-vb[AdvancedInkTopicsSamples#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#1)]  
  
<a name="ImplementingCustomStrokes"></a>
## <a name="implementing-custom-strokes"></a>实现自定义笔划  
 实现从 <xref:System.Windows.Ink.Stroke> 派生的类。 此类负责将数据转换为<xref:System.Windows.Input.StylusPoint><xref:System.Windows.Ink.Stroke>对象后呈现数据。 重写类<xref:System.Windows.Ink.Stroke.DrawCore%2A>以执行实际绘图。  
  
 笔画类还可以使用 方法<xref:System.Windows.Ink.Stroke.AddPropertyData%2A>存储自定义数据。 此数据持续存在时会与笔划数据一起存储。  
  
 该<xref:System.Windows.Ink.Stroke>类还可以执行命中测试。 您还可以通过重写当前类中<xref:System.Windows.Ink.Stroke.HitTest%2A>的方法来实现您自己的命中测试算法。  
  
 以下 C# 代码演示了<xref:System.Windows.Ink.Stroke>将<xref:System.Windows.Input.StylusPoint>数据呈现为 3D 描边的自定义类。  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#2)]
[!code-vb[AdvancedInkTopicsSamples#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#2)]  
  
<a name="ImplementingACustomInkCanvas"></a>
## <a name="implementing-a-custom-inkcanvas"></a>实现自定义 InkCanvas  
 使用自定义<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>和描边的最简单方法是实现派生并<xref:System.Windows.Controls.InkCanvas>使用这些类的类。 具有<xref:System.Windows.Controls.InkCanvas>一个<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>属性，用于指定在用户绘制描边时如何呈现笔画。  
  
 要在 操作<xref:System.Windows.Controls.InkCanvas>上自定义渲染描边，可以执行以下操作：  
  
- 创建派生自 的<xref:System.Windows.Controls.InkCanvas>类。  
  
- 将自定义属性<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>分配给属性<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A?displayProperty=nameWithType>。  
  
- 重写 <xref:System.Windows.Controls.InkCanvas.OnStrokeCollected%2A> 方法。 使用此方法时，请删除之前添加到 InkCanvas 的原始笔划。 然后创建自定义描边，将其添加到属性，<xref:System.Windows.Controls.InkCanvas.Strokes%2A>然后用包含自定义描边的新项<xref:System.Windows.Controls.InkCanvasStrokeCollectedEventArgs>调用基类。  
  
 以下 C# 代码演示了<xref:System.Windows.Controls.InkCanvas>使用自定义<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>和收集自定义描边的自定义类。  
  
 [!code-csharp[AdvancedInkTopicsSamples#9](~/samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#9)]  
  
 可以<xref:System.Windows.Controls.InkCanvas>有多个<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>。 通过将多个对象添加到<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer><xref:System.Windows.UIElement.StylusPlugIns%2A>属性，<xref:System.Windows.Controls.InkCanvas>可以向 添加多个对象。  
  
<a name="Conclusion"></a>
## <a name="conclusion"></a>结束语  
 您可以通过派生自己的<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>和<xref:System.Windows.Ink.Stroke><xref:System.Windows.Controls.InkCanvas>类来自定义墨迹的外观。 将这些类结合使用可以确保用户绘制笔划时和笔划被收集后的笔划外观保持一致。  
  
## <a name="see-also"></a>另请参阅

- [高级墨迹处理](advanced-ink-handling.md)
