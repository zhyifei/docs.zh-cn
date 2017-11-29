---
title: "截获触笔输入"
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
- 'architecture [WPF], '
- ', '
- ', '
- ', '
ms.assetid: 791bb2f0-4e5c-4569-ac3c-211996808d44
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 611a2d2de56025e2f1b5add6106294834586f9af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="intercepting-input-from-the-stylus"></a>截获触笔输入
<xref:System.Windows.Input.StylusPlugIns>体系结构提供了用于通过实现低级别的控制的机制<xref:System.Windows.Input.Stylus>输入和数字墨迹创建<xref:System.Windows.Ink.Stroke>对象。 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类提供机制来实现自定义行为，并将其应用到来自触笔设备以获得最佳性能的数据的流。  
  
 本主题包含以下小节：  
  
-   [体系结构](#Architecture)  
  
-   [实现触笔插件](#ImplementingStylusPlugins)  
  
-   [将插件添加到 InkCanvas](#AddingYourPluginToAnInkCanvas)  
  
-   [结束语](#Conclusion)  
  
<a name="Architecture"></a>   
## <a name="architecture"></a>体系结构  
 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>的演进[StylusInput](http://go.microsoft.com/fwlink/?LinkId=50753&clcid=0x409)中所述的 Api[访问和操作笔输入](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)中[Microsoft Windows XP Tablet PC Edition 软件开发工具包 1.7](http://go.microsoft.com/fwlink/?linkid=11782&clcid=0x409)。  
  
 每个<xref:System.Windows.UIElement>具有<xref:System.Windows.UIElement.StylusPlugIns%2A>属性都<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>。 你可以添加<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>到元素的<xref:System.Windows.UIElement.StylusPlugIns%2A>属性可操作<xref:System.Windows.Input.StylusPoint>生成作为它的数据。 <xref:System.Windows.Input.StylusPoint>数据包含系统数字化器，包括支持的所有属性<xref:System.Windows.Input.StylusPoint.X%2A>和<xref:System.Windows.Input.StylusPoint.Y%2A>点数据，以及<xref:System.Windows.Input.StylusPoint.PressureFactor%2A>数据。  
  
 你<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>对象直接插入的数据来自流<xref:System.Windows.Input.Stylus>设备时你将添加<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>到<xref:System.Windows.UIElement.StylusPlugIns%2A>属性。 插件添加至顺序<xref:System.Windows.UIElement.StylusPlugIns%2A>集合决定将接收的顺序<xref:System.Windows.Input.StylusPoint>数据。 例如，如果添加筛选器插件，用于限制到特定区域中，输入，然后添加一个插件，写入识别笔势，识别手势插件将接收筛选<xref:System.Windows.Input.StylusPoint>数据。  
  
<a name="ImplementingStylusPlugins"></a>   
## <a name="implementing-stylus-plug-ins"></a>实现触笔插件  
 若要实现的插件，从派生类<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>。 此类为应用的 o 数据的流，因为它是来自<xref:System.Windows.Input.Stylus>。 您可以在此类修改的值<xref:System.Windows.Input.StylusPoint>数据。  
  
> [!CAUTION]
>  如果<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>会引发或导致异常，该应用程序将关闭。 你应在使用的控件进行全面测试<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>并仅使用的控件，如果您确信<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>将不会引发异常。  
  
 下面的示例演示一个插件，来修改限制触笔输入<xref:System.Windows.Input.StylusPoint.X%2A>和<xref:System.Windows.Input.StylusPoint.Y%2A>中值<xref:System.Windows.Input.StylusPoint>作为它的数据来自<xref:System.Windows.Input.Stylus>设备。  
  
 [!code-csharp[AdvancedInkTopicsSamples#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#19)]
 [!code-vb[AdvancedInkTopicsSamples#19](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#19)]  
[!code-csharp[AdvancedInkTopicsSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/DynamicRenderer.cs#3)]
[!code-vb[AdvancedInkTopicsSamples#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdvancedInkTopicsSamples/VisualBasic/DynamicRenderer.vb#3)]  
  
<a name="AddingYourPluginToAnInkCanvas"></a>   
## <a name="adding-your-plug-in-to-an-inkcanvas"></a>将插件添加到 InkCanvas  
 使用你的自定义插件的最简单方法是实现从 InkCanvas 派生的类并将其添加到<xref:System.Windows.UIElement.StylusPlugIns%2A>属性。  
  
 下面的示例演示自定义<xref:System.Windows.Controls.InkCanvas>对墨迹进行筛选。  
  
 [!code-csharp[AdvancedInkTopicsSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#4)]  
  
 如果你添加`FilterInkCanvas`到你的应用程序并运行它，你将注意到墨迹不限于直到区域后用户完成笔画。 这是因为<xref:System.Windows.Controls.InkCanvas>具有<xref:System.Windows.Controls.InkCanvas.DynamicRenderer%2A>属性，它是<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>和已经是成员的<xref:System.Windows.UIElement.StylusPlugIns%2A>集合。 自定义<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>你添加到<xref:System.Windows.UIElement.StylusPlugIns%2A>集合接收<xref:System.Windows.Input.StylusPoint>之后，数据<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>接收数据。 因此，<xref:System.Windows.Input.StylusPoint>数据在用户抬起笔结束笔画后不会直到筛选。 若要为用户将其绘制筛选墨迹，必须将插入`FilterPlugin`之前<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>。  
  
 下面的 C# 代码演示自定义<xref:System.Windows.Controls.InkCanvas>，筛选墨迹进行绘制。  
  
 [!code-csharp[AdvancedInkTopicsSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdvancedInkTopicsSamples/CSharp/Window1.xaml.cs#5)]  
  
<a name="Conclusion"></a>   
## <a name="conclusion"></a>结束语  
 通过派生你自己<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>类并将它们到插入<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>集合，你可以极大地提高你数字墨迹的行为。 你有权<xref:System.Windows.Input.StylusPoint>作为它的数据生成，为你提供机会自定义<xref:System.Windows.Input.Stylus>输入。 由于这种低级别访问<xref:System.Windows.Input.StylusPoint>数据，你可以为你的应用程序实现墨迹收集和呈现以最佳性能。  
  
## <a name="see-also"></a>另请参阅  
 [高级墨迹处理](../../../../docs/framework/wpf/advanced/advanced-ink-handling.md)  
 [访问和操作笔输入](http://go.microsoft.com/fwlink/?LinkId=50752&clcid=0x409)
