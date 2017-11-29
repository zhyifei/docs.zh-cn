---
title: "如何：从自定义控件选择墨迹"
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
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd9693209cc35ecd3c0473133b7c21639a239ff5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-select-ink-from-a-custom-control"></a>如何：从自定义控件选择墨迹
通过添加<xref:System.Windows.Ink.IncrementalLassoHitTester>到自定义控件，您可以使控件，以便用户可以选择使用套索工具，方式类似于墨迹<xref:System.Windows.Controls.InkCanvas>选择使用套索墨迹。  
  
 此示例假定你熟悉创建墨迹启用自定义控件。  若要创建接受墨迹输入的自定义控件，请参阅[创建墨迹输入控件](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)。  
  
## <a name="example"></a>示例  
 当用户绘制套索，<xref:System.Windows.Ink.IncrementalLassoHitTester>预测用户完成套索后，哪些笔画将套索路径的边界内。  确定要套索路径的边界内的描边可以看作的选择。  所选的笔画也可能会变为未选定。  例如，如果用户反转方向时绘制套索，<xref:System.Windows.Ink.IncrementalLassoHitTester>可能会取消选择某些描边。  
  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>引发<xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged>事件，它使自定义控件，以响应用户在绘制套索时。  例如，你可以更改的描边的外观，当用户选择和会取消选择它们。  
  
## <a name="managing-the-ink-mode"></a>管理墨迹模式  
 如果套索显示方式与对控件墨迹不同，它是对用户有用。 若要完成此操作，自定义控件必须跟踪的用户是编写还是选择墨迹。 若要执行此操作的最简单方法是声明一个包含两个值的枚举： 一个用于指示用户正在编写墨迹，另一个用于指示用户正在选择墨迹。  
  
 [!code-csharp[HowToSelectInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 接下来，添加两个<xref:System.Windows.Ink.DrawingAttributes>到类： 一个用于用户会编写墨迹，一个用于当用户选择墨迹。  在构造函数中，初始化<xref:System.Windows.Ink.DrawingAttributes>和附加同时<xref:System.Windows.Ink.DrawingAttributes.AttributeChanged>到相同的事件处理程序的事件。 然后设置<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A>属性<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>到墨迹<xref:System.Windows.Ink.DrawingAttributes>。  
  
 [!code-csharp[HowToSelectInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 添加一个属性，公开选择模式。 当用户更改选择模式时，设置<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A>属性<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer>到相应<xref:System.Windows.Ink.DrawingAttributes>对象，然后重新安装<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>属性<xref:System.Windows.Controls.InkPresenter>。  
  
 [!code-csharp[HowToSelectInk#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 公开<xref:System.Windows.Ink.DrawingAttributes>作为属性，以便应用程序可以确定墨迹笔画和选择笔画的外观。  
  
 [!code-csharp[HowToSelectInk#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 属性时<xref:System.Windows.Ink.DrawingAttributes>对象更改，<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>必须重新附加到<xref:System.Windows.Controls.InkPresenter>。  事件处理程序中<xref:System.Windows.Ink.DrawingAttributes.AttributeChanged>事件，重新附加<xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A>到<xref:System.Windows.Controls.InkPresenter>。  
  
 [!code-csharp[HowToSelectInk#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a>使用 IncrementalLassoHitTester  
 创建和初始化<xref:System.Windows.Ink.StrokeCollection>包含所选的笔画。  
  
 [!code-csharp[HowToSelectInk#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 当用户开始绘制笔画时，墨迹或套索，请取消选择所有所选的描边。 然后，如果用户要绘制套索，创建<xref:System.Windows.Ink.IncrementalLassoHitTester>通过调用<xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A>，订阅<xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged>事件，并调用<xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A>。 此代码可以是单独的方法，并从调用<xref:System.Windows.UIElement.OnStylusDown%2A>和<xref:System.Windows.UIElement.OnMouseDown%2A>方法。  
  
 [!code-csharp[HowToSelectInk#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 添加到触笔接触点<xref:System.Windows.Ink.IncrementalLassoHitTester>时用户绘制套索。  调用以下方法从<xref:System.Windows.UIElement.OnStylusMove%2A>， <xref:System.Windows.UIElement.OnStylusUp%2A>， <xref:System.Windows.UIElement.OnMouseMove%2A>，和<xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A>方法。  
  
 [!code-csharp[HowToSelectInk#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 处理<xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType>事件，当用户选择，并取消选择笔画时进行响应。  <xref:System.Windows.Ink.LassoSelectionChangedEventArgs>类具有<xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A>和<xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A>获取描边的属性已选中和取消选中，分别。  
  
 [!code-csharp[HowToSelectInk#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 当用户完成绘制套索时，取消订阅<xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged>事件并调用<xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A>。  
  
 [!code-csharp[HowToSelectInk#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a>将所有集中到一起。  
 下面的示例是一个自定义控件，使用户能够选择使用套索墨迹。  
  
 [!code-csharp[HowToSelectInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>  
 <xref:System.Windows.Ink.StrokeCollection>  
 <xref:System.Windows.Input.StylusPointCollection>  
 [创建墨迹输入控件](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md)
