---
title: "如何：调用打印对话框"
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
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ba541b367e56a809fa444528dccd69860c4de46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="530da-102">如何：调用打印对话框</span><span class="sxs-lookup"><span data-stu-id="530da-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="530da-103">若要使你能够从你应用程序打印，可以只需创建并打开<xref:System.Windows.Controls.PrintDialog>对象。</span><span class="sxs-lookup"><span data-stu-id="530da-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="530da-104">示例</span><span class="sxs-lookup"><span data-stu-id="530da-104">Example</span></span>  
 <span data-ttu-id="530da-105"><xref:System.Windows.Controls.PrintDialog> 控件为 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]、配置和 [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] 作业提交提供单一入口点。</span><span class="sxs-lookup"><span data-stu-id="530da-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] job submission.</span></span> <span data-ttu-id="530da-106">控件是易于使用，可以通过实例化[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]标记或代码。</span><span class="sxs-lookup"><span data-stu-id="530da-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="530da-107">下面的示例演示如何实例化并打开在代码中的控件以及如何从其打印。</span><span class="sxs-lookup"><span data-stu-id="530da-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="530da-108">它还演示如何以确保设置特定范围的页的选项的对话框会给用户。</span><span class="sxs-lookup"><span data-stu-id="530da-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="530da-109">此代码示例假定是 c： 驱动器的根目录中的文件 FixedDocumentSequence.xps。</span><span class="sxs-lookup"><span data-stu-id="530da-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="530da-110">打开对话框后，用户将能够选择从其计算机上安装的打印机。</span><span class="sxs-lookup"><span data-stu-id="530da-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="530da-111">它们还将具有选择的选项[Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)创建[!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]文件而不是打印。</span><span class="sxs-lookup"><span data-stu-id="530da-111">They will also have the option of selecting the [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319) to create an [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file instead of printing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="530da-112"><xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>控制[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]，本主题中对其进行讨论不应混淆与<xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType>组件的[!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="530da-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)].</span></span>  
  
 <span data-ttu-id="530da-113">严格地说，你可以使用<xref:System.Windows.Controls.PrintDialog.PrintDocument%2A>方法，而不断打开此对话框。</span><span class="sxs-lookup"><span data-stu-id="530da-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="530da-114">在这种意义上，控件可以用作不可见的打印组件。</span><span class="sxs-lookup"><span data-stu-id="530da-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="530da-115">但出于性能原因，它会更好的做法可以使用两种<xref:System.Printing.PrintQueue.AddJob%2A>方法或一个多<xref:System.Windows.Xps.XpsDocumentWriter.Write%2A>和<xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>方法<xref:System.Windows.Xps.XpsDocumentWriter>。</span><span class="sxs-lookup"><span data-stu-id="530da-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="530da-116">有关详细信息，请参阅[以编程方式打印 XPS 文件](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md)和。</span><span class="sxs-lookup"><span data-stu-id="530da-116">For more about this, see [Programmatically Print XPS Files](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) and .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="530da-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="530da-117">See Also</span></span>  
 <xref:System.Windows.Controls.PrintDialog>  
 [<span data-ttu-id="530da-118">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="530da-118">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="530da-119">打印概述</span><span class="sxs-lookup"><span data-stu-id="530da-119">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="530da-120">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="530da-120">Microsoft XPS Document Writer</span></span>](http://go.microsoft.com/fwlink/?LinkId=147319)
