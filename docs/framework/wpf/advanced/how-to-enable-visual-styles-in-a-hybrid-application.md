---
title: "如何：在混合应用程序中启用视觉样式"
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
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e628835f0e5fb315f15b9e9946c48f7017092bae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a>如何：在混合应用程序中启用视觉样式
本主题演示如何启用[!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]视觉样式上[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件中托管[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-基于应用程序。  
  
 如果你的应用程序调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>方法，大部分你[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件自动将你的应用程序在运行时使用可视样式[!INCLUDE[TLA#tla_winxp](../../../../includes/tlasharptla-winxp-md.md)]。 有关详细信息，请参阅[以视觉样式呈现控件](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)。  
  
 本主题中所示的任务的完整代码清单，请参阅[启用混合应用程序示例中的视觉样式](http://go.microsoft.com/fwlink/?LinkID=159986)。  
  
## <a name="enabling-windows-forms-visual-styles"></a>启用 Windows 窗体视觉样式  
  
#### <a name="to-enable-windows-forms-visual-styles"></a>启用 Windows 窗体视觉样式  
  
1.  创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序项目中名为`HostingWfWithVisualStyles`。  
  
2.  在解决方案资源管理器中，添加对下列程序集的引用。  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  在工具箱中，双击<xref:System.Windows.Controls.Grid>图标将<xref:System.Windows.Controls.Grid>设计图面上的元素。  
  
4.  在属性窗口中，设置的值<xref:System.Windows.FrameworkElement.Height%2A>和<xref:System.Windows.FrameworkElement.Width%2A>属性设置为**自动**。  
  
5.  在设计视图或 XAML 视图中，选择<xref:System.Windows.Window>。  
  
6.  在属性窗口中，单击**事件**选项卡。  
  
7.  双击<xref:System.Windows.FrameworkElement.Loaded>事件。
  
8.  在 MainWindow.xaml.vb 或 MainWindow.xaml.cs 中，插入以下代码以处理<xref:System.Windows.FrameworkElement.Loaded>事件。  
  
     [!code-csharp[HostingWfWithVisualStyles#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. 按 F5 生成并运行该应用程序。  
  
     [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]使用视觉样式绘制控件。  
  
## <a name="disabling-windows-forms-visual-styles"></a>禁用 Windows 窗体视觉样式  
 若要禁用视觉样式，只需删除对的调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>方法。  
  
#### <a name="to-disable-windows-forms-visual-styles"></a>禁用 Windows 窗体视觉样式  
  
1.  在代码编辑器中打开 MainWindow.xaml.vb 或 MainWindow.xaml.cs。  
  
2.  注释掉对的调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A>方法。  
  
3.  按 F5 生成并运行该应用程序。  
  
     [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]使用默认系统样式绘制控件。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>  
 <xref:System.Windows.Forms.VisualStyles>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [使用视觉样式呈现控件](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 [演练：在 WPF 中承载 Windows 窗体控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
