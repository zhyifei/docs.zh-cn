---
title: 如何：以编程方式打印 XPS 文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing XPS files programmatically [WPF]
- XPS files [WPF], printing programmatically
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
ms.openlocfilehash: 6642fad7d20e60a8b92e5860b763511f4fc0be72
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "70169170"
---
# <a name="how-to-programmatically-print-xps-files"></a>如何：以编程方式打印 XPS 文件
您可以使用<xref:System.Printing.PrintQueue.AddJob%2A>方法的一个重载来打印[!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]文件, 而无需<xref:System.Windows.Controls.PrintDialog>打开或 (原则[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]上)。  
  
 你还可以使用[!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]的多个<xref:System.Windows.Xps.XpsDocumentWriter.Write%2A>和<xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>方法<xref:System.Windows.Xps.XpsDocumentWriter>打印文件。 有关此操作的详细信息，请参阅[打印 XPS 文档](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90))。  
  
 打印[!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]的另一种方法是使用<xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> <xref:System.Windows.Controls.PrintDialog>控件<xref:System.Windows.Controls.PrintDialog.PrintVisual%2A>的或方法。 请参阅[调用打印对话框](how-to-invoke-a-print-dialog.md)。  
  
## <a name="example"></a>示例  
 使用三参数<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>方法的主要步骤如下所示。 以下示例提供了详细信息。  
  
1. 确定打印机是否是 XPSDrv 打印机。 （有关 XPSDrv 的详细信息，请参阅[打印概述](printing-overview.md)。）  
  
2. 如果打印机不是 XPSDrv 打印机，将线程的单元设置为单线程。  
  
3. 实例化打印服务器并打印队列对象。  
  
4. 调用方法, 指定作业名称、要打印的文件, 以及<xref:System.Boolean>指示打印机是否为 XPSDrv 打印机的标志。  
  
 以下示例演示如何以批处理方式打印目录中的所有 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 文件。 尽管应用程序提示用户指定目录, 但是这三个参数<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>方法不[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]需要。 它可用于具有 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 文件名的任何代码路径和可以传递到该方法的路径。  
  
 当<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> <xref:System.Boolean>参数<xref:System.Printing.PrintQueue.AddJob%2A> 为`false`时, 必须在单线程单元中运行的三个参数重载, 在使用非 XPSDrv 打印机时, 该参数必须是。 但是, .NET 的默认单元状态为多线程。 由于本示例假定使用非 XPSDrv 打印机，因此此默认值必须为相反值。  
  
 有两种可用于更改此默认值的方法。 一种方法是<xref:System.STAThreadAttribute>直接在应用程序的`Main`方法 (通常`[System.STAThreadAttribute()]`为 "`static void Main(string[] args)`") 的第一行上方添加 (即 "")。 但是, 许多应用程序都要求`Main`方法具有多线程单元状态, 因此有另一种方法: 将<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>中的调用放在一个单独的线程中, 该线程的单元<xref:System.Threading.ApartmentState.STA>状态<xref:System.Threading.Thread.SetApartmentState%2A>设置为 with。 以下示例使用第二种方法。  
  
 因此, 该示例首先实例化<xref:System.Threading.Thread>对象并将**PrintXPS**方法作为<xref:System.Threading.ThreadStart>参数进行传递。 （该示例的后面部分定义了 **PrintXPS** 方法。）接下来，将线程设置为单线程单元。 `Main` 方法的唯一剩余代码会启动新线程。  
  
 该示例的内容主要关于 `static`**BatchXPSPrinter.PrintXPS** 方法。 创建打印服务器和队列后，该方法会提示用户提供包含 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 文件的目录。 验证目录是否存在以及其中是否存在\*.xps 文件后, 该方法会将每个此类文件添加到打印队列中。 该示例假设打印机不是 XPSDrv, 因此我们要传递`false`给<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>方法的最后一个参数。 出于此原因，该方法先验证文件中的 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 标记，然后再尝试将其转换为打印机的页面描述语言。 如果验证失败，会引发异常。 该示例代码将捕获该异常，并通知用户相关信息，然后继续处理下一 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 文件。  
  
 [!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
 [!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]  
  
 如果使用 XPSDrv 打印机，则可将最后一个参数设置为 `true`。 在这种情况下，由于 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 是打印机的页面描述语言，该方法会将文件发送到打印机，而不会对其进行验证或将其转换为另一种页面描述语言。 如果在设计时不确定应用程序是否将使用 XPSDrv 打印机, 则可以修改应用程序, 使其根据所找到的<xref:System.Printing.PrintQueue.IsXpsDevice%2A>内容来读取属性和分支。  
  
 由于在发布[!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]和 Microsoft .NET Framework 后, 最初会有很少的 xpsdrv 打印机可用, 因此可能需要将非 xpsdrv 打印机伪装为 XPSDrv 打印机。 为此，请将 Pipelineconfig.xml 添加到运行应用程序的计算机的注册表项中的以下文件列表：  
  
 HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Environments\Windows NT x86\Drivers\Version-3\\ *\<PseudoXPSPrinter>* \DependentFiles  
  
 其中 *\<PseudoXPSPrinter>* 是任一打印队列。 然后必须重新启动计算机。  
  
 此伪装允许您传递`true`的最后一个参数作为<xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>而不会导致异常，但由于 *\<出现>* 并不是真正的 XPSDrv 打印机，仅会打印垃圾。  
  
 **注意**为简单起见, 以上示例使用\*.xps 扩展名作为其测试[!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]文件。 但是，[!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 文件不需要具有此扩展名。 [isXPS.exe（isXPS 合规性工具）](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100))是一种测试文件是否具有 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 有效性的方法。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.AddJob%2A>
- <xref:System.Threading.ApartmentState>
- <xref:System.STAThreadAttribute>
- [XPS 文档](/windows/desktop/printdocs/documents)
- [打印 XPS 文档](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90))
- [托管和非托管线程处理](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [isXPS.exe（isXPS 合规性工具）](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100))
- [WPF 中的文档](documents-in-wpf.md)
- [打印概述](printing-overview.md)
