---
title: "演练：使用 ElementHost 控件映射属性"
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
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 030183e77a141036416a3bcb8a4c4018df0a7e65
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a>演练：使用 ElementHost 控件映射属性
本演练演示如何使用<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>属性映射[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]到上一个承载的相应属性的属性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]元素。  
  
 本演练涉及以下任务：  
  
-   创建项目。  
  
-   定义新的属性映射。  
  
-   删除默认属性映射。  
  
-   扩展默认属性映射。  
  
 本演练的任务的完整代码清单，请参阅[映射属性使用 ElementHost 控件示例](http://go.microsoft.com/fwlink/?LinkID=160018)。  
  
 完成后，你将能够映射[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]到对应的属性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]上承载的元素的属性。  
  
## <a name="prerequisites"></a>系统必备  
 你需要以下组件来完成本演练：  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]。  
  
## <a name="creating-the-project"></a>创建项目  
  
#### <a name="to-create-the-project"></a>要创建项目  
  
1.  创建[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]应用程序项目中名为`PropertyMappingWithElementHost`。 有关详细信息，请参阅[如何：创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)。  
  
2.  在解决方案资源管理器中，添加对以下引用[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]程序集。  
  
    -   PresentationCore  
  
    -   PresentationFramework  
  
    -   WindowsBase  
  
    -   WindowsFormsIntegration  
  
3.  将以下代码复制到顶部`Form1`代码文件。  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  在 Windows 窗体设计器中打开 `Form1`。 双击要添加的事件处理程序的窗体<xref:System.Windows.Forms.Form.Load>事件。  
  
5.  返回到 Windows 窗体设计器并添加一个事件处理程序窗体的<xref:System.Windows.Forms.Control.Resize>事件。 有关详细信息，请参阅[如何： 使用设计器创建事件处理程序](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2)。  
  
6.  声明<xref:System.Windows.Forms.Integration.ElementHost>字段`Form1`类。  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## <a name="defining-new-property-mappings"></a>定义新的属性映射  
 <xref:System.Windows.Forms.Integration.ElementHost>控件提供了一些默认属性映射。 通过调用将添加新的属性映射<xref:System.Windows.Forms.Integration.PropertyMap.Add%2A>方法<xref:System.Windows.Forms.Integration.ElementHost>控件的<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>。  
  
#### <a name="to-define-new-property-mappings"></a>若要定义新的属性映射  
  
1.  将以下代码复制到的定义`Form1`类。  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     `AddMarginMapping`方法将添加的新映射<xref:System.Windows.Forms.Control.Margin%2A>属性。  
  
     `OnMarginChange`方法将转换<xref:System.Windows.Forms.Control.Margin%2A>属性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.FrameworkElement.Margin%2A>属性。  
  
2.  将以下代码复制到的定义`Form1`类。  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     `AddRegionMapping`方法将添加的新映射<xref:System.Windows.Forms.Control.Region%2A>属性。  
  
     `OnRegionChange`方法将转换<xref:System.Windows.Forms.Control.Region%2A>属性[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.UIElement.Clip%2A>属性。  
  
     `Form1_Resize`方法可处理窗体的<xref:System.Windows.Forms.Control.Resize>事件并调整其大小以适合托管的元素的剪辑区域。  
  
## <a name="removing-a-default-property-mapping"></a>删除默认属性映射  
 通过调用来移除默认属性映射<xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A>方法<xref:System.Windows.Forms.Integration.ElementHost>控件的<xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>。  
  
#### <a name="to-remove-a-default-property-mapping"></a>删除默认属性映射  
  
-   将以下代码复制到的定义`Form1`类。  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     `RemoveCursorMapping`方法删除默认映射<xref:System.Windows.Forms.Control.Cursor%2A>属性。  
  
## <a name="extending-a-default-property-mapping"></a>扩展默认属性映射  
 可以使用默认属性映射，并使用自己的映射对其进行扩展。  
  
#### <a name="to-extend-a-default-property-mapping"></a>扩展默认属性映射  
  
-   将以下代码复制到的定义`Form1`类。  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     `ExtendBackColorMapping`方法将自定义的属性转换器添加到现有<xref:System.Windows.Forms.Control.BackColor%2A>属性映射。  
  
     `OnBackColorChange`方法将托管控件的特定映像<xref:System.Windows.Controls.Control.Background%2A>属性。 `OnBackColorChange`应用的默认属性映射后调用方法。  
  
## <a name="initializing-your-property-mappings"></a>初始化属性映射  
  
#### <a name="to-initialize-your-property-mappings"></a>初始化属性映射  
  
1.  将以下代码复制到的定义`Form1`类。  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     `Form1_Load`方法将处理<xref:System.Windows.Forms.Form.Load>事件并执行以下初始化。  
  
    -   创建[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Button>元素。  
  
    -   调用先前在演练中定义的方法来设置属性映射。  
  
    -   将初始值分配给映射的属性。  
  
2.  按 F5 生成并运行该应用程序。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [Windows 窗体和 WPF 属性映射](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [WPF 设计器](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [演练：在 Windows 窗体中承载 WPF 复合控件](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
