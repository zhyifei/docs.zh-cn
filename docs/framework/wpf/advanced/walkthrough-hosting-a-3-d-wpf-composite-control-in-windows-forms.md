---
title: "演练：在 Windows 窗体中承载 3-D WPF 复合控件"
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
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c5af705509d30f7dfd50ade0c07aca242deff4dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a>演练：在 Windows 窗体中承载 3-D WPF 复合控件
本演练演示如何创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]复合控件并将其在托管[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]控件和窗体使用<xref:System.Windows.Forms.Integration.ElementHost>控件。  
  
 在本演练中，你将实施[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> ，其中包含两个子控件。 <xref:System.Windows.Controls.UserControl>显示三维 (3-D) 圆锥。 呈现三维对象就可以很容易与[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]比使用[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。 因此，对主机的意义上[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl>类，以创建中的 3d 图形[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]。  
  
 本演练涉及以下任务：  
  
-   创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>。  
  
-   创建 Windows 窗体主机项目。  
  
-   承载[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>。  
  
 本演练的任务的完整代码清单，请参阅[承载 Windows 窗体示例中的三维 WPF 复合控件](http://go.microsoft.com/fwlink/?LinkID=160001)。  
  
## <a name="prerequisites"></a>先决条件  
 你需要以下组件来完成本演练：  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]。  
  
<a name="To_Create_the_UserControl"></a>   
## <a name="creating-the-usercontrol"></a>创建用户控件  
  
#### <a name="to-create-the-usercontrol"></a>若要创建用户控件  
  
1.  创建一个名为的 WPF 用户控件库项目`HostingWpfUserControlInWf`。  
  
2.  打开 UserControl1.xaml 在[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。  
  
3.  生成的代码替换为以下代码。  
  
     此代码定义<xref:System.Windows.Controls.UserControl?displayProperty=nameWithType>，其中包含两个子控件。 第一个子控件是<xref:System.Windows.Controls.Label?displayProperty=nameWithType>控件; 第二个是<xref:System.Windows.Controls.Viewport3D>显示三维锥体的控件。  
  
     [!code-xaml[HostingWpfUserControlInWf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]  
  
<a name="To_Create_the_Windows_Forms_Host_Project"></a>   
## <a name="creating-the-windows-forms-host-project"></a>创建 Windows 窗体宿主项目  
  
#### <a name="to-create-the-host-project"></a>创建宿主项目  
  
1.  添加一个名为的 Windows 应用程序项目`WpfUserControlHost`到解决方案。 有关详细信息，请参阅[如何：创建新的 WPF 应用程序项目](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)。  
  
2.  在解决方案资源管理器，将添加到名为 WindowsFormsIntegration.dll 的 WindowsFormsIntegration 程序集的引用。  
  
3.  将引用添加到以下[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]程序集：  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
4.  添加对的引用`HostingWpfUserControlInWf`项目。  
  
5.  在解决方案资源管理器，设置`WpfUserControlHost`项目为启动项目。  
  
<a name="To_Host_the_Windows_Presentation_Foundation"></a>   
## <a name="hosting-the-windows-presentation-foundation-usercontrol"></a>承载 Windows Presentation Foundation UserControl  
  
#### <a name="to-host-the-usercontrol"></a>若要托管的 UserControl  
  
1.  在 Windows 窗体设计器中，打开 form1。  
  
2.  在属性窗口中，单击**事件**，然后双击<xref:System.Windows.Forms.Form.Load>事件创建事件处理程序。  
  
     代码编辑器随即打开到新生成`Form1_Load`事件处理程序。  
  
3.  Form1.cs 中的代码替换为以下代码。  
  
     `Form1_Load`事件处理程序创建的实例`UserControl1`，并将它添加<xref:System.Windows.Forms.Integration.ElementHost>的子控件的控件的集合。 <xref:System.Windows.Forms.Integration.ElementHost>控件添加到的子控件的窗体的集合。  
  
     [!code-csharp[HostingWpfUserControlInWf#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]  
  
4.  按 F5 生成并运行该应用程序。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [WPF 设计器](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [演练：在 Windows 窗体中承载 WPF 复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [演练：在 WPF 中托管 Windows 窗体复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [承载 Windows 窗体示例中的 WPF 复合控件](http://go.microsoft.com/fwlink/?LinkID=160001)
