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
ms.openlocfilehash: 2ced508eb83e2955fdcd1ad87fb6415e2052446f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206039"
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="df9b2-102">如何：调用打印对话框</span><span class="sxs-lookup"><span data-stu-id="df9b2-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="df9b2-103">若要提供从你应用程序打印的功能，可以只需创建和打开<xref:System.Windows.Controls.PrintDialog>对象。</span><span class="sxs-lookup"><span data-stu-id="df9b2-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df9b2-104">示例</span><span class="sxs-lookup"><span data-stu-id="df9b2-104">Example</span></span>  
 <span data-ttu-id="df9b2-105"><xref:System.Windows.Controls.PrintDialog> 控件为 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]、配置和 [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] 作业提交提供单一入口点。</span><span class="sxs-lookup"><span data-stu-id="df9b2-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] job submission.</span></span> <span data-ttu-id="df9b2-106">该控件是易于使用，可以通过使用实例化[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]标记或代码。</span><span class="sxs-lookup"><span data-stu-id="df9b2-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="df9b2-107">下面的示例演示如何实例化并在 code 中打开该控件以及如何从其打印。</span><span class="sxs-lookup"><span data-stu-id="df9b2-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="df9b2-108">它还演示如何以确保设置特定范围的页面的选项的对话框会给用户。</span><span class="sxs-lookup"><span data-stu-id="df9b2-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="df9b2-109">此代码示例假定 c： 驱动器的根目录中的文件 FixedDocumentSequence.xps。</span><span class="sxs-lookup"><span data-stu-id="df9b2-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="df9b2-110">打开对话框后，用户将能够从他们的计算机上安装的打印机中选择。</span><span class="sxs-lookup"><span data-stu-id="df9b2-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="df9b2-111">此外将选择的选项[Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319)若要创建[!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]文件而不是打印。</span><span class="sxs-lookup"><span data-stu-id="df9b2-111">They will also have the option of selecting the [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319) to create an [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file instead of printing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df9b2-112"><xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>控制[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]，本主题中对其进行讨论不应混淆与<xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType>Windows 窗体的组件。</span><span class="sxs-lookup"><span data-stu-id="df9b2-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of Windows Forms.</span></span>  
  
 <span data-ttu-id="df9b2-113">严格地说，您可以使用<xref:System.Windows.Controls.PrintDialog.PrintDocument%2A>甚至不用打开对话框的方法。</span><span class="sxs-lookup"><span data-stu-id="df9b2-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="df9b2-114">在此意义上，控件可用作不可见的打印组件。</span><span class="sxs-lookup"><span data-stu-id="df9b2-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="df9b2-115">但出于性能原因，它会更好的做法可以使用两种<xref:System.Printing.PrintQueue.AddJob%2A>方法或多个<xref:System.Windows.Xps.XpsDocumentWriter.Write%2A>并<xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>方法的<xref:System.Windows.Xps.XpsDocumentWriter>。</span><span class="sxs-lookup"><span data-stu-id="df9b2-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="df9b2-116">有关详细信息，请参阅[以编程方式打印 XPS 文件](how-to-programmatically-print-xps-files.md)和。</span><span class="sxs-lookup"><span data-stu-id="df9b2-116">For more about this, see [Programmatically Print XPS Files](how-to-programmatically-print-xps-files.md) and .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df9b2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="df9b2-117">See also</span></span>

- <xref:System.Windows.Controls.PrintDialog>
- [<span data-ttu-id="df9b2-118">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="df9b2-118">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="df9b2-119">打印概述</span><span class="sxs-lookup"><span data-stu-id="df9b2-119">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="df9b2-120">Microsoft XPS 文档编写器</span><span class="sxs-lookup"><span data-stu-id="df9b2-120">Microsoft XPS Document Writer</span></span>](https://go.microsoft.com/fwlink/?LinkId=147319)
