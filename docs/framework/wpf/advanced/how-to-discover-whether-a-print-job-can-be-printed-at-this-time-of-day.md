---
title: "如何：确定此时是否可以打印一项打印作业"
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
- cpp
helpviewer_keywords:
- print queues [WPF], timing
- printers [WPF], availability
- print jobs [WPF], timing
ms.assetid: 7e9c8ec1-abf6-4b3d-b1c6-33b35d3c4063
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ef9da205792823b7069024c5e4a3e9ac80d60a24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a>如何：确定此时是否可以打印一项打印作业
打印队列并不总是可用的一天 24 小时。 它们具有开始和结束时间属性，可设置为使它们在每天的某些时间不可用。 例如，此功能可以用于保留以供在下午 5 点后的特定部门专用打印机。 该部门都使用不同队列维护比其他部门打印机。 将设置为其他部门队列来下午 5 点以后将不可用，尽管可将队列的支持的部门设置为始终保持可用。  
  
 此外，打印作业本身可以被设置为仅在指定的时间范围内可打印。  
  
 <xref:System.Printing.PrintQueue>和<xref:System.Printing.PrintSystemJobInfo>类中公开[!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)]的[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]提供一种远程检查是否给定的打印作业可以打印给定队列上的当前时间。  
  
## <a name="example"></a>示例  
 下面的示例是一个示例，可以使用诊断问题的打印作业。  
  
 有两个主要步骤，此类型的函数，如下所示。  
  
1.  读取<xref:System.Printing.PrintQueue.StartTimeOfDay%2A>和<xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>属性<xref:System.Printing.PrintQueue>以确定它们之间是否为当前时间。  
  
2.  读取<xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A>和<xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A>属性<xref:System.Printing.PrintSystemJobInfo>以确定它们之间是否为当前时间。  
  
 但是问题变复杂，原因在于这些属性不是<xref:System.DateTime>对象。 相反，它们是<xref:System.Int32>express 作为午夜算起的分钟数的一天的时间的对象。 此外，这不是午夜当前所在的时区，但午夜 UTC （协调世界时）。  
  
 第一个代码示例演示静态方法**ReportQueueAndJobAvailability**，后者传递<xref:System.Printing.PrintSystemJobInfo>，调用帮助器方法，以确定是否可以在当前时间打印作业，如果它不是，可以打印时。 请注意，<xref:System.Printing.PrintQueue>不传递给方法。 这是因为<xref:System.Printing.PrintSystemJobInfo>包括对中的队列的引用其<xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A>属性。  
  
 从属方法包括重载**ReportAvailabilityAtThisTime**方法可以采用该方法<xref:System.Printing.PrintQueue>或<xref:System.Printing.PrintSystemJobInfo>作为参数。 此外，还有**TimeConverter.ConvertToLocalHumanReadableTime**。 下面讨论了所有这些方法。  
  
 **ReportQueueAndJobAvailability**方法首先检查以查看该队列或打印作业是否不可用在此时间。 如果其中任一个不可用，它然后检查是否不可用的队列。 如果不可用，然后该方法将报告此事实数据表和当队列将再次变得可用的时间。 它然后检查作业和如果它是不可用，它将报告下次跨越时它可以打印时。 最后，该方法将报告时可以打印作业的最早时间。 这是两次的更高版本。  
  
-   打印队列下一步可用的时间。  
  
-   打印作业下一步可用的时间。  
  
 报告每天的时间、 时<xref:System.DateTime.ToShortTimeString%2A>因为年、 月和天输出中的，取消显示此方法也会调用方法。 你无法将打印队列或打印作业的可用性的限制到特定的年、 月或天。  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 两个重载的**ReportAvailabilityAtThisTime**方法是相同类型传递到它们，因此仅除外<xref:System.Printing.PrintQueue>下面显示了版本。  
  
> [!NOTE]
>  方法都是相同类型除外事实引发这一问题，该示例不会创建泛型方法的原因**ReportAvailabilityAtThisTime\<T >**。 原因是此类方法将一定要限制为具有的类**StartTimeOfDay**和**UntilTimeOfDay**属性调用的方法，但泛型方法可能仅会局限于单个类和公用的唯一类<xref:System.Printing.PrintQueue>和<xref:System.Printing.PrintSystemJobInfo>在继承树是<xref:System.Printing.PrintSystemObject>具有任何此类属性。  
  
 **ReportAvailabilityAtThisTime**方法 （如下面的代码示例所示） 开始初始化<xref:System.Boolean>sentinel 变量`true`。 将重置为`false`，如果队列不可用。  
  
 接下来，该方法将检查以查看开始和"之前"时间是否相同。 如果它们是，队列将始终可用，因此此方法返回`true`。  
  
 如果队列不可用的时间，该方法使用静态<xref:System.DateTime.UtcNow%2A>属性来获取当前时间作为<xref:System.DateTime>对象。 (我们不需要本地时间，因为<xref:System.Printing.PrintQueue.StartTimeOfDay%2A>和<xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>属性本身就是 UTC 时间。)  
  
 但是，这两个属性不是<xref:System.DateTime>对象。 它们是<xref:System.Int32>将时间表示为分钟后 UTC 午夜数。 因此我们需要将转换我们<xref:System.DateTime>分钟后午夜到的对象。 完成后，该方法将只需检查以查看是否"现在"是之间队列的开始和"截止时间，设置为 false，如果"现在"sentinel 不之间两次，并返回 sentinel。  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 **TimeConverter.ConvertToLocalHumanReadableTime** （如下面的代码示例所示） 的方法不使用任何方法引入了[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]，因此是简要讨论。 此方法不具有双转换任务： 它必须采用一个整数，该整数表示午夜分钟后，并将其转换为用户可读的时间和它必须将其转换为本地时间。 这是通过实现通过先创建<xref:System.DateTime>设置为午夜 UTC，然后它使用的对象<xref:System.DateTime.AddMinutes%2A>方法将添加的分钟数传递给方法。 这将返回一个新<xref:System.DateTime>表示传递给方法的原始时间。 <xref:System.DateTime.ToLocalTime%2A>方法然后将此转换为本地时间。  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.DateTime>  
 <xref:System.Printing.PrintSystemJobInfo>  
 <xref:System.Printing.PrintQueue>  
 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [打印概述](../../../../docs/framework/wpf/advanced/printing-overview.md)
