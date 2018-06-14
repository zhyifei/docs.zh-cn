---
title: 如何：调用打印对话框
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: f94a965f724e85fb63ed9c98ebddba40938eb9b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545553"
---
# <a name="how-to-invoke-a-print-dialog"></a>如何：调用打印对话框
若要使你能够从你应用程序打印，可以只需创建并打开<xref:System.Windows.Controls.PrintDialog>对象。  
  
## <a name="example"></a>示例  
 <xref:System.Windows.Controls.PrintDialog> 控件为 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]、配置和 [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] 作业提交提供单一入口点。 控件是易于使用，可以通过实例化[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]标记或代码。 下面的示例演示如何实例化并打开在代码中的控件以及如何从其打印。 它还演示如何以确保设置特定范围的页的选项的对话框会给用户。 此代码示例假定是 c： 驱动器的根目录中的文件 FixedDocumentSequence.xps。  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 打开对话框后，用户将能够选择从其计算机上安装的打印机。 它们还将具有选择的选项[Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)创建[!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]文件而不是打印。  
  
> [!NOTE]
>  <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>控制[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]，本主题中对其进行讨论不应混淆与<xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType>组件的 Windows 窗体。  
  
 严格地说，你可以使用<xref:System.Windows.Controls.PrintDialog.PrintDocument%2A>方法，而不断打开此对话框。 在这种意义上，控件可以用作不可见的打印组件。 但出于性能原因，它会更好的做法可以使用两种<xref:System.Printing.PrintQueue.AddJob%2A>方法或一个多<xref:System.Windows.Xps.XpsDocumentWriter.Write%2A>和<xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>方法<xref:System.Windows.Xps.XpsDocumentWriter>。 有关详细信息，请参阅[以编程方式打印 XPS 文件](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md)和。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Controls.PrintDialog>  
 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [打印概述](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)
