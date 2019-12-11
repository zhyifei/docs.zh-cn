---
title: 如何：在混合应用程序中启用视觉样式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- visual styles [Windows Forms]
ms.assetid: 95de9b9c-d804-405c-b2d1-49a88c1e0fe1
ms.openlocfilehash: 251c53a8665d2eae7c3b5bb23b0a388009362dcc
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960112"
---
# <a name="how-to-enable-visual-styles-in-a-hybrid-application"></a>如何：在混合应用程序中启用视觉样式
本主题演示如何在基于 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]的应用程序中承载的 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件上启用视觉样式。  
  
 如果你的应用程序调用 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 方法，则大部分 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件将自动使用视觉样式。 有关详细信息，请参阅[使用视觉样式呈现控件](../../winforms/controls/rendering-controls-with-visual-styles.md)。  
  
 有关本主题中所述任务的完整代码列表，请参阅[在混合应用程序示例中启用视觉样式](https://go.microsoft.com/fwlink/?LinkID=159986)。  
  
## <a name="enabling-windows-forms-visual-styles"></a>启用 Windows 窗体视觉样式  
  
#### <a name="to-enable-windows-forms-visual-styles"></a>启用 Windows 窗体视觉样式  
  
1. 创建一个名为 `HostingWfWithVisualStyles`的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序项目。  
  
2. 在解决方案资源管理器中，添加对下列程序集的引用。  
  
    - WindowsFormsIntegration  
  
    - System.Windows.Forms  
  
3. 在 "工具箱" 中，双击 "<xref:System.Windows.Controls.Grid>" 图标以在设计图面上放置 <xref:System.Windows.Controls.Grid> 元素。  
  
4. 在属性窗口中，将 "<xref:System.Windows.FrameworkElement.Height%2A>" 和 "<xref:System.Windows.FrameworkElement.Width%2A>" 属性的值设置为 "**自动**"。  
  
5. 在设计视图或 XAML 视图中，选择 "<xref:System.Windows.Window>"。  
  
6. 在属性窗口中，单击 "**事件**" 选项卡。  
  
7. 双击 "<xref:System.Windows.FrameworkElement.Loaded>" 事件。
  
8. 在 Mainwindow.xaml 或 MainWindow.xaml.cs 中，插入以下代码以处理 <xref:System.Windows.FrameworkElement.Loaded> 事件。  
  
     [!code-csharp[HostingWfWithVisualStyles#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWfWithVisualStyles/CSharp/HostingWfWithVisualStyles/Window1.xaml.cs#11)]
     [!code-vb[HostingWfWithVisualStyles#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWfWithVisualStyles/VisualBasic/HostingWfWithVisualStyles/Window1.xaml.vb#11)]  
  
9. 按 F5 生成并运行该应用程序。  
  
     [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件用视觉样式绘制。  
  
## <a name="disabling-windows-forms-visual-styles"></a>禁用 Windows 窗体视觉样式  
 若要禁用视觉样式，只需删除对 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 方法的调用。  
  
#### <a name="to-disable-windows-forms-visual-styles"></a>禁用 Windows 窗体视觉样式  
  
1. 在代码编辑器中打开 MainWindow.xaml.vb 或 MainWindow.xaml.cs。  
  
2. 注释掉对 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> 方法的调用。  
  
3. 按 F5 生成并运行该应用程序。  
  
     [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 控件将用默认系统样式进行绘制。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>
- <xref:System.Windows.Forms.VisualStyles>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [使用视觉样式呈现控件](../../winforms/controls/rendering-controls-with-visual-styles.md)
- [演练：在 WPF 中承载 Windows 窗体控件](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
