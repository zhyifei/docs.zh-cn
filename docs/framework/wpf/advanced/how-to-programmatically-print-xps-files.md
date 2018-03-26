---
title: 如何：以编程方式打印 XPS 文件
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing XPS files programmatically [WPF]
- XPS files [WPF], printing programmatically
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b58e617fb04ecaba45ed655dc650459e89453dd
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2018
---
# <a name="how-to-programmatically-print-xps-files"></a>如何：以编程方式打印 XPS 文件
你可以使用的一个重载<xref:System.Printing.PrintQueue.AddJob%2A>方法打印[!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]文件而无需打开<xref:System.Windows.Controls.PrintDialog>或原则上，任何[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]根本。  
  
 你还可以打印[!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]文件使用多<xref:System.Windows.Xps.XpsDocumentWriter.Write%2A>和<xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>方法<xref:System.Windows.Xps.XpsDocumentWriter>。 有关此操作的详细信息，请参阅[打印 XPS 文档](http://msdn.microsoft.com/library/849555c8-0c4e-48c0-86bc-a5494c69b36c)。  
  
 另一种打印[!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]是使用<xref:System.Windows.Controls.PrintDialog.PrintDocument%2A>或<xref:System.Windows.Controls.PrintDialog.PrintVisual%2A>方法<xref:System.Windows.Controls.PrintDialog>控件。 请参阅[调用打印对话框](../../../../docs/framework/wpf/advanced/how-to-invoke-a-print-dialog.md)。  
  
## <a name="example"></a>示例  
 使用三个参数的主要步骤<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>方法如下所示。 以下示例提供了详细信息。  
  
1.  确定打印机是否是 XPSDrv 打印机。 （有关 XPSDrv 的详细信息，请参阅[打印概述](../../../../docs/framework/wpf/advanced/printing-overview.md)。）  
  
2.  如果打印机不是 XPSDrv 打印机，将线程的单元设置为单线程。  
  
3.  实例化打印服务器并打印队列对象。  
  
4.  调用方法，指定作业名称、 要打印的文件和一个<xref:System.Boolean>标志，该值指示是否在打印机防止。  
  
 以下示例演示如何以批处理方式打印目录中的所有 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 文件。 尽管该应用程序提示用户指定的目录，由三个参数<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>方法不需要[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。 它可用于具有 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 文件名的任何代码路径和可以传递到该方法的路径。  
  
 三个参数<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>重载<xref:System.Printing.PrintQueue.AddJob%2A>必须在单线程单元中运行时<xref:System.Boolean>参数是`false`，它必须是在使用非 XPSDrv 打印机时。 但是，[!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)] 的默认单元状态为多线程。 由于本示例假定使用非 XPSDrv 打印机，因此此默认值必须为相反值。  
  
 有两种可用于更改此默认值的方法。 一种方法是只需添加<xref:System.STAThreadAttribute>(即"`[System.STAThreadAttribute()]`") 正上方的应用程序的首行`Main`方法 (通常"`static void Main(string[] args)`")。 但是，许多应用程序要求`Main`方法具有多线程的单元状态，因此第二种方法： 将到调用放<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>其单元状态设置为一个单独的线程中<xref:System.Threading.ApartmentState.STA>与<xref:System.Threading.Thread.SetApartmentState%2A>。 以下示例使用第二种方法。  
  
 此示例相应地，方法是实例化从开始<xref:System.Threading.Thread>对象并将其传递**PrintXPS**方法作为<xref:System.Threading.ThreadStart>参数。 （该示例的后面部分定义了 **PrintXPS** 方法。）接下来，将线程设置为单线程单元。 `Main` 方法的唯一剩余代码会启动新线程。  
  
 该示例的内容主要关于 `static`**BatchXPSPrinter.PrintXPS** 方法。 创建打印服务器和队列后，该方法会提示用户提供包含 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 文件的目录。 在验证存在该目录且其中存在 *.xps 文件之后，该方法会将每个此类文件添加到打印队列。 该示例假定，打印机将是不是 XPSDrv，因此，我们传递`false`到的最后一个参数<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>方法。 出于此原因，该方法先验证文件中的 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 标记，然后再尝试将其转换为打印机的页面描述语言。 如果验证失败，会引发异常。 该示例代码将捕获该异常，并通知用户相关信息，然后继续处理下一 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 文件。  
  
 [!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
 [!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]  
  
 如果使用 XPSDrv 打印机，则可将最后一个参数设置为 `true`。 在这种情况下，由于 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 是打印机的页面描述语言，该方法会将文件发送到打印机，而不会对其进行验证或将其转换为另一种页面描述语言。 如果您不确定在设计时是否应用程序将使用为防止，则可以修改应用程序具有它读取<xref:System.Printing.PrintQueue.IsXpsDevice%2A>属性和根据它所找到的分支。  
  
 由于发布 [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] 和 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] 后，最初存在几个可立即使用的 XPSDrv 打印机，可能需要将非 XPSDrv 打印机伪装为 XPSDrv 打印机。 为此，请将 Pipelineconfig.xml 添加到运行应用程序的计算机的注册表项中的以下文件列表：  
  
 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Environments\Windows NT x86\Drivers\Version-3\\*\<PseudoXPSPrinter>*\DependentFiles  
  
 其中 *\<PseudoXPSPrinter>* 是任一打印队列。 然后必须重新启动计算机。  
  
 此是经过伪装将使你能够将传递`true`作为最后一个参数的<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>而不会导致异常，但由于*\<出现 >*实际上不防止仅仅是乱码将打印。  
  
 **请注意**为简单起见，以上示例通过测试是否存在 *.xps 扩展名来确定文件是否为 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]。 但是，[!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 文件不需要具有此扩展名。 [isXPS.exe（isXPS 合规性工具）](http://msdn.microsoft.com/library/bfbb433f-7ab6-417a-90f0-71443d76bcb3)是一种测试文件是否具有 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 有效性的方法。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.AddJob%2A>  
 <xref:System.Threading.ApartmentState>  
 <xref:System.STAThreadAttribute>  
 [XPS](http://www.microsoft.com/xps)  
 [打印 XPS 文档](http://msdn.microsoft.com/library/849555c8-0c4e-48c0-86bc-a5494c69b36c)  
 [托管和非托管线程处理](http://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5)  
 [isXPS.exe（isXPS 合规性工具）](http://msdn.microsoft.com/library/bfbb433f-7ab6-417a-90f0-71443d76bcb3)  
 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [打印概述](../../../../docs/framework/wpf/advanced/printing-overview.md)
