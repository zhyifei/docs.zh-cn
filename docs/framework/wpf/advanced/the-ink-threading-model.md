---
title: "墨迹线程处理模型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application user interface thread [WPF]
- stylus plug-in
- ink threading model [WPF]
- ink [WPF], rendering
- pen thread [WPF]
- threading model [WPF]
- rendering ink [WPF]
- dynamic rendering thread [WPF]
- ink collection plug-in
- plug-ins [WPF], for ink
ms.assetid: c85fcad1-cb50-4431-847c-ac4145a35c89
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: efbd05f88b962363e3b866fbf914f6d3a37823cc
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="the-ink-threading-model"></a>墨迹线程处理模型
墨迹在 Tablet PC 上的优势之一是，其外观很像编写使用普通的笔和纸。  若要实现此目的，触笔收集以高得多的速度比鼠标将墨迹呈现为用户写入的输入的数据。  应用程序的用户界面 (UI) 线程不收集钢笔数据和呈现墨迹满足需求，因为它可能被阻止。  为了解决此问题，问题[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序时用户会编写墨迹使用两个其他线程。  
  
 以下列表描述参与收集和呈现数字墨迹线程：  
  
-   笔线程-将触笔输入的线程。  （事实上，这是一个线程池，但本主题将其称为笔线程。）  
  
-   应用程序用户界面线程的控制应用程序的用户界面的线程。  
  
-   动态呈现线程-呈现时用户墨迹线程绘制笔画。 窗口 Presentation Foundation 中所述，动态呈现线程是不同于呈现应用程序的其他 UI 元素的线程[线程处理模型](../../../../docs/framework/wpf/advanced/threading-model.md)。  
  
 墨迹模型都是相同是否应用程序使用<xref:System.Windows.Controls.InkCanvas>或自定义控件类似于中的一个[创建墨迹输入控件](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)。  虽然本主题讨论方面的线程处理<xref:System.Windows.Controls.InkCanvas>，创建自定义控件时，将应用相同的概念。  
  
## <a name="threading-overview"></a>线程处理概述  
 下图阐释了线程处理模型，当用户绘制笔画时：  
  
 ![绘制笔画时的线程处理模型。] (../../../../docs/framework/wpf/advanced/media/inkthreading-drawingink.png "InkThreading_DrawingInk")  
  
1.  用户绘制笔画时发生的操作  
  
    1.  当用户绘制笔画时，触笔接触点参与笔线程。  触笔插件，包括<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>，接受笔线程上的触笔点并有机会修改在之前将其<xref:System.Windows.Controls.InkCanvas>接收它们。  
  
    2.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>呈现动态呈现线程上的触笔点。 在上一步在同一时间发生此异常。  
  
    3.  <xref:System.Windows.Controls.InkCanvas>接收 UI 线程上的触笔点。  
  
2.  用户结束笔画后发生的操作  
  
    1.  当用户完成绘制笔画，<xref:System.Windows.Controls.InkCanvas>创建<xref:System.Windows.Ink.Stroke>对象，并将其添加到<xref:System.Windows.Controls.InkPresenter>，这样可以静态呈现。  
  
    2.  UI 线程警报<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>静态呈现描边，因此<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>中移除的笔划的其可视表示形式。  
  
## <a name="ink-collection-and-stylus-plug-ins"></a>墨迹集合和触笔插件  
 每个<xref:System.Windows.UIElement>具有<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>。  <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>中的对象<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>接收并且可以修改笔线程上的触笔点。 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>对象接收根据它们在中顺序的触笔点<xref:System.Windows.Input.StylusPlugIns.StylusPlugInCollection>。  
  
 下图演示了一个假想的场景其中<xref:System.Windows.UIElement.StylusPlugIns%2A>集合<xref:System.Windows.UIElement>包含`stylusPlugin1`、 <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>，和`stylusPlugin2`按顺序。  
  
 ![顺序触笔插件影响输出。] (../../../../docs/framework/wpf/advanced/media/inkthreading-pluginorder.png "InkThreading_PluginOrder")  
  
 在上图中，以下行为将发生：  
  
1.  `StylusPlugin1`修改的 x 值和 y。  
  
2.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>接收的已修改的触笔点并将它们呈现在动态呈现线程。  
  
3.  `StylusPlugin2`接收的已修改的触笔点并进一步修改的 x 值和 y。  
  
4.  应用程序收集触笔接触点，以及当用户完成描边，静态呈现笔画。  
  
 假设`stylusPlugin1`将触笔接触点限制为矩形和`stylusPlugin2`将转换到右的触笔点。  在前面的方案中，<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>接收的受限制的触笔点，而非已翻译的触笔点。  当用户书写笔画时，描边呈现的矩形的边界内，但是不会对笔画用户提起笔之前要转换。  
  
### <a name="performing-operations-with-a-stylus-plug-in-on-the-ui-thread"></a>使用触笔插件在 UI 线程上执行操作  
 由于无法对笔线程执行准确的命中测试，某些元素偶尔可能会收到适用于其他元素的触笔输入。 如果你需要确保在执行操作之前已正确路由输入，订阅并执行中的操作<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusDownProcessed%2A>， <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusMoveProcessed%2A>，或<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn.OnStylusUpProcessed%2A>方法。 在执行准确的命中测试后，将通过应用程序线程中调用这些方法。 若要订阅对这些方法，调用<xref:System.Windows.Input.StylusPlugIns.RawStylusInput.NotifyWhenProcessed%2A>的方法中，在钢笔线程上发生的方法。  
  
 下图说明了笔线程和 UI 线程方面的触笔事件之间的关系<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>。  
  
 ![墨迹线程处理模型 &#40;UI 和 Pen &#41;] (../../../../docs/framework/wpf/advanced/media/inkthreading-plugincallbacks.png "InkThreading_PluginCallbacks")  
  
## <a name="rendering-ink"></a>呈现墨迹  
 用户绘制笔画，如<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>因此墨迹显示为"流"从笔即使 UI 线程忙碌呈现在单独线程上的墨迹。  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>动态呈现线程上生成可视化树，因为它收集触笔接触点。  当用户完成描边，<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>要求应用程序执行下一次呈现时收到通知。  应用程序完成下一步的呈现处理过程后,<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>清理其可视化树。  下图说明了此过程。  
  
 ![墨迹线程处理关系图](../../../../docs/framework/wpf/advanced/media/inkthreading-visualtree.png "InkThreading_VisualTree")  
  
1.  用户开始描边。  
  
    1.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>创建的可视化树。  
  
2.  用户绘制笔画。  
  
    1.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>生成的可视化树。  
  
3.  用户结束描边。  
  
    1.  <xref:System.Windows.Controls.InkPresenter>笔画添加到其可视化树。  
  
    2.  媒体集成层 (MIL) 静态呈现笔画。  
  
    3.  <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>清理视觉对象。
