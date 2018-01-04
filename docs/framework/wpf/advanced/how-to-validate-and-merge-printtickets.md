---
title: "如何：验证和合并 PrintTicket"
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
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5cf2091d50433bb936b3d4976d1c3eabea73edc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-validate-and-merge-printtickets"></a>如何：验证和合并 PrintTicket
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [打印架构](http://go.microsoft.com/fwlink/?LinkId=186397)包括灵活且可扩展<xref:System.Printing.PrintCapabilities>和<xref:System.Printing.PrintTicket>元素。 前者可以详细列举的打印设备的功能，后者用于指定设备应如何使用这些功能来处理的文档、 单个文档或单个页面按特定顺序。  
  
 典型的支持打印的应用程序的任务序列将如下所示。  
  
1.  确定打印机的功能。  
  
2.  配置<xref:System.Printing.PrintTicket>以使用这些功能。  
  
3.  验证<xref:System.Printing.PrintTicket>。  
  
 这篇文章演示如何执行此操作。  
  
## <a name="example"></a>示例  
 在下面的简单示例中，我们是只关注打印机是否可以支持双工-双面打印。 主要步骤如下所示。  
  
1.  获取<xref:System.Printing.PrintCapabilities>对象<xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>方法。  
  
2.  测试存在所需的功能。 在下面的示例中，我们测试<xref:System.Printing.PrintCapabilities.DuplexingCapability%2A>属性<xref:System.Printing.PrintCapabilities>沿长边表的对象的两端张纸"翻页"上的打印功能是否存在。 由于<xref:System.Printing.PrintCapabilities.DuplexingCapability%2A>是一个集合，我们使用`Contains`方法<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>。  
  
    > [!NOTE]
    >  此步骤不是绝对必需的。 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A>使用下面的方法将检查每个请求<xref:System.Printing.PrintTicket>对打印机的功能。 如果打印机不支持请求的功能，打印机驱动程序将替换中的另一个请求<xref:System.Printing.PrintTicket>由方法返回。  
  
3.  如果打印机支持双工，该示例代码创建<xref:System.Printing.PrintTicket>，要求提供双工。 应用程序并不指定每个可能的打印机设置中可用，但<xref:System.Printing.PrintTicket>元素。 这将浪费的程序员和程序时间。 相反，代码设置的双工请求，然后合并这<xref:System.Printing.PrintTicket>与一个现有，完全配置且经过验证， <xref:System.Printing.PrintTicket>，在这种情况下，用户的默认<xref:System.Printing.PrintTicket>。  
  
4.  示例会调用相应地，<xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A>方法合并将新的、 最小，<xref:System.Printing.PrintTicket>使用用户的默认<xref:System.Printing.PrintTicket>。 这将返回<xref:System.Printing.ValidationResult>，包括新<xref:System.Printing.PrintTicket>作为其属性之一。  
  
5.  示例然后测试新<xref:System.Printing.PrintTicket>请求双工。 如果已存在，则代码会将其用户的新的默认打印票证。 如果没有执行上述步骤 2 和打印机不支持双工沿长边，则测试将会造成`false`。 （请参阅上面的说明。）  
  
6.  最后一个重要步骤是提交更改为<xref:System.Printing.PrintQueue.UserPrintTicket%2A>属性<xref:System.Printing.PrintQueue>与<xref:System.Printing.PrintQueue.Commit%2A>方法。  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 以便你可以快速测试此示例中，下面显示了代码的剩余部分。 创建项目和命名空间，然后将这篇文章中的代码段粘贴到命名空间块。  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Printing.PrintCapabilities>  
 <xref:System.Printing.PrintTicket>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [打印概述](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [打印架构](http://go.microsoft.com/fwlink/?LinkId=186397)
