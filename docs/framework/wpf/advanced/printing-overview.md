---
title: 打印概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print path [WPF], XPS
- printers [WPF], XPSDrv-based
- printing [WPF]
- PrintQueue class PrintServer class [WPF]
- XML Paper Specification (XPS) file format
- XPS (XML Paper Specification) file format
- XPSDrv-based printers
- GDI print path [WPF]
ms.assetid: 0de8ac41-9aa6-413d-a121-7aa6f41539b1
ms.openlocfilehash: 902d51341850b5245b9fa6410b1954b2ab373bbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187200"
---
# <a name="printing-overview"></a>打印概述
使用 Microsoft .NET 框架，使用 Windows 演示基础 （WPF） 的应用程序开发人员具有一套丰富的新打印和打印系统管理 API。 使用 Windows Vista，这些打印系统增强功能中的一些也可用于创建 Windows 窗体应用程序的开发人员和使用非托管代码的开发人员。 此新功能的核心是新的 XML 纸张规范 （XPS） 文件格式和 XPS 打印路径。  
  
 本主题包含以下各节。  
  
<a name="introduction_to_XPS"></a>
## <a name="about-xps"></a>关于 XPS  
 XPS 是一种电子文档格式、假脱机文件格式和页面描述语言。 它是一种开放文档格式，使用 XML、开放打包约定 （OPC） 和其他行业标准来创建跨平台文档。 XPS 简化了数字文档的创建、共享、打印、查看和存档过程。 有关 XPS 的其他信息，请参阅[XPS 文档](/windows/desktop/printdocs/documents)。  
  
 使用 WPF 打印基于 XPS 的内容的几种技术在[编程打印 XPS 文件中](how-to-programmatically-print-xps-files.md)进行了演示。 在查看本主题中的内容时，参考这些示例会很有帮助。 （非托管代码开发人员应查看[MXDC_ESCAPE函数](/windows/desktop/printdocs/mxdc-escape)的文档。 Windows 窗体开发人员必须在不支持完整<xref:System.Drawing.Printing>XPS 打印路径但支持混合 GDI 到 XPS 打印路径的命名空间中使用 API。 请参阅下面的**打印路径体系结构**。）  
  
<a name="XPS_print_path_intro"></a>
## <a name="xps-print-path"></a>XPS 打印路径  
 XML 纸张规范 （XPS） 打印路径是一项新 Windows 功能，可重新定义在 Windows 应用程序中处理打印的方式。 因为 XPS 可以替换文档演示语言（如 RTF）、打印后台打印器格式（如 WMF）和页面描述语言（如 PCL 或后记）;新的打印路径在打印驱动程序或设备中维护从应用程序发布到最终处理的 XPS 格式。  
  
 XPS 打印路径基于 XPS 打印机驱动程序模型 （XPSDrv） 构建，它为开发人员提供了多种好处，例如"您所看到的就是您得到的"（WYSIWYG）打印、改进了颜色支持以及显著提高了打印性能。 （有关 XPSDrv 的更多信息，请参阅[Windows 驱动程序工具包文档](/windows-hardware/drivers/)。  
  
 XPS 文档的打印后台程序的操作与早期版本的 Windows 基本相同。 但是，除了现有的 GDI 打印路径之外，它还增强了 XPS 打印路径。 新的打印路径本机使用 XPS 假脱机文件。 虽然为早期版本的 Windows 编写的用户模式打印机驱动程序将继续工作，但 XPS 打印机驱动程序 （XPSDrv） 需要一个才能使用 XPS 打印路径。  
  
 XPS 打印路径的优势非常重要，包括：  
  
- 威西威格打印支持  
  
- 对高级颜色配置文件的本机支持（包括 32 位/通道 (bpc)、CMYK、已命名的颜色、n 墨迹）以及对透明和渐变的本机支持。  
  
- 提高了 .NET 框架和基于 Win32 的应用程序的打印性能。  
  
- 行业标准 XPS 格式。  
  
 对于基本打印方案，提供简单直观的 API，并带有一个入口点，用于用户界面、配置和作业提交。 对于高级方案，为 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 自定义（或根本没有 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]）、同步或异步打印以及批量打印功能添加了附加支持。 这两个选项在完全或部分信任模式下都提供打印支持。  
  
 XPS 的设计考虑到了可扩展性。 通过使用可扩展性框架，可以模块化地将特性和功能添加到 XPS 中。 扩展性功能包括：  
  
- 打印架构。 公共架构将定期进行更新，并可以实现设备功能的迅速扩展。 （请参阅下面的 **PrintTicket 和 PrintCapabilities**。）  
  
- 可扩展筛选器管道。 XPS 打印机驱动程序 （XPSDrv） 过滤管道旨在支持直接和可扩展地打印 XPS 文档。 有关详细信息，请参阅 [XPSDrv 打印机驱动程序](/windows-hardware/drivers/print/xpsdrv-printer-drivers)。
  
### <a name="print-path-architecture"></a>打印路径体系结构  
 虽然 Win32 和 .NET 框架应用程序都支持 XPS，但 Win32 和 Windows 窗体应用程序使用 GDI 到 XPS 转换，以便为 XPS 打印机驱动程序 （XPSDrv） 创建 XPS 格式化的内容。 这些应用程序不需要使用 XPS 打印路径，并且可以继续使用基于增强的元文件 （EMF） 打印。 但是，大多数 XPS 功能和增强功能仅对面向 XPS 打印路径的应用程序可用。  
  
 为了启用 Win32 和 Windows 窗体应用程序使用基于 XPSDrv 的打印机，XPS 打印机驱动程序 （XPSDrv） 支持将 GDI 转换为 XPS 格式。 XPSDrv 型号还为 XPS 到 GDI 格式提供了转换器，以便 Win32 应用程序可以打印 XPS 文档。 对于 WPF 应用程序，只要写入操作的目标打印队列没有 XPSDrv<xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>驱动程序，XPS 格式转换为 GDI 格式由<xref:System.Windows.Xps.XpsDocumentWriter>类<xref:System.Windows.Xps.XpsDocumentWriter.Write%2A>和方法自动完成。 （Windows 窗体应用程序无法打印 XPS 文档。  
  
 下图描述了打印子系统，并定义了 Microsoft 提供的部分以及软件和硬件供应商定义的部分：  
  
 ![屏幕截图显示了 XPS 打印系统。](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>基本 XPS 打印  
 WPF 同时定义基本和高级 API。 对于不需要大量打印自定义或访问完整 XPS 功能集的应用程序，可提供基本打印支持。 基本打印支持通过一个打印对话框控件公开，该控件要求最低的配置，并采用熟悉的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]。 许多 XPS 功能都可用于使用此简化的打印模型。  
  
#### <a name="printdialog"></a>PrintDialog  
 该<xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType>控件为[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]、配置和 XPS 作业提交提供单个入口点。 若要了解如何实例化和使用该控件，请参阅[调用打印对话框](how-to-invoke-a-print-dialog.md)。  
  
### <a name="advanced-xps-printing"></a>高级 XPS 打印  
 要访问完整的 XPS 功能集，必须使用高级打印 API。 下面将更详细地介绍几个相关的 API。 有关 XPS 打印路径 API 的完整列表，请参阅<xref:System.Windows.Xps><xref:System.Printing>和 命名空间引用。  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket 和 PrintCapabilities  
 <xref:System.Printing.PrintTicket>和<xref:System.Printing.PrintCapabilities>类是高级 XPS 功能的基础。 这两种类型的对象都是面向打印的功能（如排序、双面打印、装订等）的 XML 格式结构。这些结构由打印架构定义。 <xref:System.Printing.PrintTicket> 指示打印机如何处理打印作业。 <xref:System.Printing.PrintCapabilities> 类定义打印机的各种功能。 通过查询打印机的功能，可以创建充分利用打印机的受支持功能的 <xref:System.Printing.PrintTicket>。 同样，可以避免不受支持的功能。  
  
 下面的示例演示如何使用代码查询打印机的 <xref:System.Printing.PrintCapabilities> 和创建 <xref:System.Printing.PrintTicket>。  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer 和 PrintQueue  
 <xref:System.Printing.PrintServer> 类表示一个网络打印服务器，而 <xref:System.Printing.PrintQueue> 类则表示一台打印机以及与其关联的输出作业队列。 总之，这些 API 允许对服务器的打印作业进行高级管理。 <xref:System.Printing.PrintServer> 或其派生类之一用于管理 <xref:System.Printing.PrintQueue>。 <xref:System.Printing.PrintQueue.AddJob%2A> 方法用于将新的打印作业插入队列。  
  
 下面的示例演示如何使用代码创建 <xref:System.Printing.LocalPrintServer> 和访问其默认的 <xref:System.Printing.PrintQueue>。  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 A<xref:System.Windows.Xps.XpsDocumentWriter>及其许多<xref:System.Windows.Xps.XpsDocumentWriter.Write%2A>和<xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A>方法用于将 XPS 文档写入 。 <xref:System.Printing.PrintQueue> 例如，<xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29>该方法用于输出 XPS 文档并<xref:System.Printing.PrintTicket>同步输出。 该方法<xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29>用于输出 XPS 文档并<xref:System.Printing.PrintTicket>异步输出。  
  
 下面的示例演示如何使用代码创建 <xref:System.Windows.Xps.XpsDocumentWriter>。  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 <xref:System.Printing.PrintQueue.AddJob%2A> 方法还提供打印方法。 请参阅[以编程方式打印 XPS 文件](how-to-programmatically-print-xps-files.md)。 以获取详细信息。  
  
<a name="GDI_Print_Path_intro"></a>
## <a name="gdi-print-path"></a>GDI 打印路径  
 虽然 WPF 应用程序本机支持 XPS 打印路径，但 Win32 和 Windows 窗体应用程序也可以利用某些 XPS 功能。 XPS 打印机驱动程序 （XPSDrv） 可将基于 GDI 的输出转换为 XPS 格式。 对于高级方案，支持使用[Microsoft XPS 文档转换器 （MXDC）](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)自定义内容转换。 同样，WPF 应用程序还可以通过调用<xref:System.Windows.Xps.XpsDocumentWriter.Write%2A><xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A><xref:System.Windows.Xps.XpsDocumentWriter>类的或方法之一并将非 XpsDrv 打印机指定为目标打印队列，输出到 GDI 打印路径。  

对于不需要 XPS 功能或支持的应用程序，当前 GDI 打印路径保持不变。  
  
- 有关 GDI 打印路径和各种 XPS 转换选项的其他参考资料，请参阅[Microsoft XPS 文档转换器 （MXDC）](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)和[XPSDrv 打印机驱动程序](/windows-hardware/drivers/print/xpsdrv-printer-drivers)。  
  
<a name="XPS_Driver_Model_intro"></a>
## <a name="xpsdrv-driver-model"></a>XPSDrv 驱动程序模型  
 在打印到启用 XPS 的打印机或驱动程序时，XPS 打印路径使用 XPS 作为本机打印假脱机格式，从而提高了后台程序的效率。 简化的后台打印过程消除了在文档后台化之前生成中间假脱机文件（如 EMF 数据文件）的需要。 通过更小的假脱机文件大小，XPS 打印路径可以减少网络流量并提高打印性能。  
  
 EMF 是一种封闭格式，表示应用程序输出为一系列对 GDI 的调用，用于呈现服务。 与 EMF 不同，XPS 假脱机格式表示实际文档，无需在输出到基于 XPS 的打印机驱动程序 （XPSDrv） 时需要进一步解释。 这些驱动程序可以用这种格式直接对数据进行操作。 此功能消除了使用 EMF 文件和基于 GDI 的打印驱动程序所需的数据和色彩空间转换。  
  
 与 EMF 等效项相比，当您使用针对 XPS 打印机驱动程序 （XPSDrv） 的 XPS 文档时，Spool 文件大小通常会减小;但是，也有例外：  
  
- 相当复杂、分为多层或者编写效率低下的向量图形可能比同一图形的位图图形更大。  
  
- 出于屏幕显示的目的，XPS 文件中嵌入了设备字体以及基于计算机的字体，而 GDI 打印后台文件未嵌入设备字体。 这两种字体都划分了子集（请参见下面的内容），而且打印机驱动程序可以在将文件传输给打印机之前删除这些设备字体。  
  
 可通过几种机制来减小后台打印文件的大小：  
  
- **字体子集划分**。 XPS 文件中仅存储实际文档中使用的字符。  
  
- **高级图形支持**。 对透明度和梯度基元的本机支持可避免 XPS 文档中内容的栅格化。  
  
- **公共资源的识别**。 将多次使用的资源（如表示公司徽标的图像）视为共享资源，并且只加载一次。  
  
- **ZIP 压缩**。 所有 XPS 文档都使用 ZIP 压缩。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Controls.PrintDialog>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.PrintQueue>
- [如何使用主题](printing-how-to-topics.md)
- [WPF 中的文档](documents-in-wpf.md)
- [XPS 文档](/windows/desktop/printdocs/documents)
- [文档序列化和存储](document-serialization-and-storage.md)
- [微软XPS文档转换器（MXDC）](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
