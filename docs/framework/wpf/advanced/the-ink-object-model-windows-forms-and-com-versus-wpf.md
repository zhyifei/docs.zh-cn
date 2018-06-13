---
title: Ink 对象模型：Windows 窗体和 COM 与 WPF 之比较
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling ink [WPF]
- InkCanvas control [WPF]
- ink object model [WPF]
- tablet pen [WPF], events [WPF]
- ink [WPF], enabling
- events [WPF], tablet pen
ms.assetid: 577835be-b145-4226-8570-1d309e9b3901
ms.openlocfilehash: aead6d6bf3956c1b5af56d21fb7c15bd1b80bc0d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548924"
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>Ink 对象模型：Windows 窗体和 COM 与 WPF 之比较

有实质上是支持数字墨迹的三个平台： Tablet PC Windows 窗体平台、 平板电脑 COM 平台层和 Windows Presentation Foundation (WPF) 平台。  为模型类似的对象模型，但该对象的 Windows 窗体和 COM 平台共享[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]平台具有显著差异。  本主题讨论了在高级别的差异，以便使用了一个对象模型的开发人员可以更好地了解其他对象模型。  
  
## <a name="enabling-ink-in-an-application"></a>在应用程序中启用墨迹  
 所有三个平台都附带了对象和控件，使应用程序接收来自触笔的输入。  Windows 窗体和 COM 平台附带[Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx)， [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx)， [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx)和[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx)类。  [Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx)和[Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx)是控件，你可以添加到应用程序以收集墨迹。  [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx)和[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx)可以附加到现有的窗口墨迹启用 windows 和自定义控件。  
  
 WPF 平台包括<xref:System.Windows.Controls.InkCanvas>控件。  你可以添加<xref:System.Windows.Controls.InkCanvas>到你的应用程序并立即开始收集墨迹。 与<xref:System.Windows.Controls.InkCanvas>，用户可以复制、 选择和调整大小墨迹。  你可以添加到其他控件<xref:System.Windows.Controls.InkCanvas>，用户可以太手写通过这些控件。  你可以通过添加创建墨迹启用自定义控件<xref:System.Windows.Controls.InkPresenter>给它，以及收集其触笔接触点。  
  
 下表列出了在何处可以了解有关在应用程序中启用墨迹：  
  
|若要执行此操作...|在 WPF 平台上...|在 Windows 窗体/COM 平台上...|  
|-----------------|--------------------------|------------------------------------------|  
|墨迹启用控件添加到应用程序|请参阅[Getting Started with 墨迹](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md)。|请参阅[自动声明窗体示例](http://msdn.microsoft.com/bec4333a-62ca-4254-a39b-04bc2c556992)|  
|启用自定义控件上的墨迹|请参阅[创建墨迹输入控件](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)。|请参阅[墨迹剪贴板示例](http://msdn.microsoft.com/a0c42f1c-543d-44f8-83d9-fe810de410ff)。|  
  
## <a name="ink-data"></a>墨迹数据  
 Windows 窗体和 COM 平台上[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx)， [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx)， [Microsoft.Ink.InkEdit](https://msdn.microsoft.com/library/ms835842.aspx)，和[Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx)每个公开[Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType)对象。 [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx)对象包含的数据的一个或多[Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType)对象，并公开公共方法和属性以管理和操作这些笔画。  [Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx)对象管理包含; 描边的生存期[Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx)对象创建和删除它所拥有的笔画。  每个[Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx)具有在其父级中是唯一的标识符[Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx)对象。  
  
 在 WPF 平台上，<xref:System.Windows.Ink.Stroke?displayProperty=nameWithType>类拥有并管理自己的生存期。 一组<xref:System.Windows.Ink.Stroke>中可以一起收集的对象<xref:System.Windows.Ink.StrokeCollection>，提供方法常用墨迹数据管理操作如命中测试、 擦除、 转换和序列化墨迹。 A<xref:System.Windows.Ink.Stroke>可以属于零、 一个或多个<xref:System.Windows.Ink.StrokeCollection>对象在任何为提供的时间。  而不是让[Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType)对象，<xref:System.Windows.Controls.InkCanvas>和<xref:System.Windows.Controls.InkPresenter>包含<xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>。  
  
 以下两个图例比较墨迹数据对象模型。  Windows 窗体和 COM 平台上[Microsoft.Ink.Ink](https://msdn.microsoft.com/library/aa515768.aspx?displayProperty=nameWithType)对象约束的生存期[Microsoft.Ink.Stroke](https://msdn.microsoft.com/library/ms827842.aspx?displayProperty=nameWithType)对象以及属于单个描边的触笔数据包。  两个或多个笔画可以引用相同[Microsoft.Ink.DrawingAttributes](https://msdn.microsoft.com/library/ms837931.aspx?displayProperty=nameWithType)对象，如下面的插图中所示。  
  
 ![COM 的墨迹对象模型关系图&#47;Winforms。] (../../../../docs/framework/wpf/advanced/media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 上[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]，每个<xref:System.Windows.Ink.Stroke?displayProperty=nameWithType>是公共语言运行时对象存在，只要有对它的引用。  每个<xref:System.Windows.Ink.Stroke>引用<xref:System.Windows.Input.StylusPointCollection>和<xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType>对象，也是公共语言运行时对象。  
  
 ![WPF 墨迹对象模型示意图。] (../../../../docs/framework/wpf/advanced/media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 下表比较了如何完成一些常见的任务上[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]平台和 Windows 窗体和 COM 平台。  
  
|任务|Windows Presentation Foundation|Windows 窗体和 COM|  
|----------|-------------------------------------|---------------------------|  
|保存墨迹|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft.Ink.Ink.Save](https://technet.microsoft.com/library/security/microsoft.ink.ink.save(v=vs.90))|  
|加载墨迹|创建<xref:System.Windows.Ink.StrokeCollection>与<xref:System.Windows.Ink.StrokeCollection.%23ctor%2A>构造函数。|[Microsoft.Ink.Ink.Load](https://msdn.microsoft.com/library/microsoft.ink.ink.load(v=vs.90).aspx)|  
|命中的测试|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[Microsoft.Ink.Ink.HitTest](https://msdn.microsoft.com/library/aa515934.aspx)|  
|复制墨迹|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[Microsoft.Ink.Ink.ClipboardCopy](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardcopy(v=vs.100).aspx)|  
|粘贴墨迹|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[Microsoft.Ink.Ink.ClipboardPaste](https://msdn.microsoft.com/library/microsoft.ink.ink.clipboardpaste(v=vs.100).aspx)|  
|访问自定义属性的集合的描边|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> (的属性是内部存储，并且通过访问<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>， <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A>，和<xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>)|使用[Microsoft.Ink.Ink.ExtendedProperties](https://msdn.microsoft.com/library/microsoft.ink.ink.extendedproperties(v=vs.100).aspx)|  
  
### <a name="sharing-ink-between-platforms"></a>平台之间共享墨迹  
 尽管平台墨迹数据的不同的对象模型，但共享平台之间的数据，则非常简单。 下面的示例将墨迹保存从 Windows 窗体应用程序，并将墨迹加载到 Windows Presentation Foundation 应用程序。  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 下面的示例将墨迹保存从 Windows Presentation Foundation 应用程序，并将墨迹加载到 Windows 窗体应用程序。  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]
## <a name="events-from-the-tablet-pen"></a>触笔事件  
 [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx)， [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx)，和[Microsoft.Ink.InkPicture](https://msdn.microsoft.com/library/aa514604.aspx)平台上的 Windows 窗体和 COM 接收事件时用户输入笔数据。  [Microsoft.Ink.InkOverlay](https://msdn.microsoft.com/library/ms833057.aspx)或[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/ms836493.aspx)附加到任何窗口或控件，并可以由平板电脑输入数据引发的事件订阅。  这些事件发生时线程依赖于的事件是否与笔、 鼠标，将引发或以编程方式。  关于线程处理与这些事件之间的关系的详细信息，请参阅[一般线程处理注意事项](http://msdn.microsoft.com/cf35724f-5f80-4b3e-992a-a9d5ea99aae9)和[线程上激发事件可以](http://msdn.microsoft.com/d1a5ab9b-d474-4ed7-9aa8-b5bdb771934f)。  
  
 在 Windows Presentation Foundation 平台上，<xref:System.Windows.UIElement>类具有笔输入的事件。 这意味着每个控件都公开完整的触笔事件集。  触笔事件具有隧道/冒泡事件对，并始终在应用程序线程上发生。  有关详细信息，请参阅[路由事件概述](../../../../docs/framework/wpf/advanced/routed-events-overview.md)。  
  
 如下图所示将引发触笔事件的类的对象模型进行比较。 Windows Presentation Foundation 对象模型也仍旧显示仅将冒泡事件，不隧道事件对应项。  
  
 ![WPF 与 Winforms 中的触笔事件的图示。] (../../../../docs/framework/wpf/advanced/media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>钢笔数据  
 所有三个平台为你提供了截获和处理来自触笔的数据的方法。  在 Windows 窗体和 COM 平台上，这可通过创建[Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx)、 将窗口或控件附加到它，以及创建一个类以实现[Microsoft.StylusInput.IStylusSyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylussyncplugin(v=vs.100).aspx)或[Microsoft.StylusInput.IStylusAsyncPlugin](https://msdn.microsoft.com/library/microsoft.stylusinput.istylusasyncplugin(v=vs.100).aspx)接口。 自定义插件然后添加到的插件集合[Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx)。 有关此对象模型的详细信息，请参阅[StylusInput Api 的体系结构](http://msdn.microsoft.com/88bab0ab-df9f-4813-9a9f-9a137813f0b4)。  
  
 上[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]平台，<xref:System.Windows.UIElement>类公开的插件的在设计上与类似集合[Microsoft.StylusInput.RealTimeStylus](https://msdn.microsoft.com/library/microsoft.stylusinput.realtimestylus(v=vs.100).aspx)。  若要截获钢笔数据，创建继承自的类<xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>和向其中添加对象<xref:System.Windows.UIElement.StylusPlugIns%2A>集合<xref:System.Windows.UIElement>。 有关此交互的详细信息，请参阅[触笔截获输入](../../../../docs/framework/wpf/advanced/intercepting-input-from-the-stylus.md)。  
  
 在所有平台上，线程池接收通过触笔事件墨迹数据，并将其发送到应用程序线程。  关于线程处理 COM 和 Windows 平台上的详细信息，请参阅[线程处理注意事项 StylusInput Api](http://msdn.microsoft.com/5d98768a-c60b-4bb0-8640-9bf38254d41f)。  关于线程处理上 Windows 演示文稿软件的详细信息，请参阅[墨迹线程处理模型](../../../../docs/framework/wpf/advanced/the-ink-threading-model.md)。  
  
 下图将接收钢笔钢笔线程池上的数据的类的对象模型进行比较。  
  
 ![StylusPlugin 模型 WPF 与 Winforms 图示。] (../../../../docs/framework/wpf/advanced/media/ink-stylusplugins.png "Ink_StylusPlugins")
