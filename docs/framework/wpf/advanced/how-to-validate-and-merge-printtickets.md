---
title: 如何：验证和合并 PrintTicket
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: bd7f399555b343a52ec6f36aa3b8c706747d8b06
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094522"
---
# <a name="how-to-validate-and-merge-printtickets"></a>如何：验证和合并 PrintTicket
Microsoft Windows[打印架构](/windows/win32/printdocs/printschema)包括灵活且可扩展的 <xref:System.Printing.PrintCapabilities> 和 <xref:System.Printing.PrintTicket> 元素。 前者列举打印设备的功能，后者指定设备应该如何根据特定的文档序列、单个文档或单个页面使用这些功能。  
  
 支持打印的应用程序的典型任务序列如下所示。  
  
1. 确定打印机的功能。  
  
2. 配置 <xref:System.Printing.PrintTicket> 以使用这些功能。  
  
3. 验证 <xref:System.Printing.PrintTicket>。  
  
 本文说明如何执行此操作。  
  
## <a name="example"></a>示例  
 在下面的简单示例中，仅对打印机是否可以支持双面打印感兴趣。 主要步骤如下所示。  
  
1. 获取具有 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 方法的 <xref:System.Printing.PrintCapabilities> 对象。  
  
2. 测试所需功能是否存在。 在下面的示例中，我们将测试 <xref:System.Printing.PrintCapabilities> 对象的 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 属性，以使在纸张的两面上都有打印功能，同时页面的长边。 由于 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 是集合，因此我们使用 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>的 `Contains` 方法。  
  
    > [!NOTE]
    > 此步骤并不是必需的。 下面使用的 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 方法将根据打印机的功能检查 <xref:System.Printing.PrintTicket> 中的每个请求。 如果打印机不支持所请求的功能，则打印机驱动程序将替换方法返回的 <xref:System.Printing.PrintTicket> 中的替代请求。  
  
3. 如果打印机支持双工，示例代码会创建一个请求双面打印的 <xref:System.Printing.PrintTicket>。 但应用程序不会指定 <xref:System.Printing.PrintTicket> 元素中提供的每个可能的打印机设置。 这会浪费程序员和计划时间。 相反，代码仅设置双工请求，然后将此 <xref:System.Printing.PrintTicket> 与现有的、完全配置和验证的 <xref:System.Printing.PrintTicket>（在本例中为用户的默认 <xref:System.Printing.PrintTicket>。  
  
4. 相应地，该示例调用 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 方法，以将新的、最小的 <xref:System.Printing.PrintTicket> 与用户的默认 <xref:System.Printing.PrintTicket>合并。 这会返回 <xref:System.Printing.ValidationResult>，其中包含新的 <xref:System.Printing.PrintTicket> 作为其属性之一。  
  
5. 然后，该示例测试新 <xref:System.Printing.PrintTicket> 是否请求双工。 如果是这样，则示例将使其成为用户的新默认打印票证。 如果上面的步骤2已省略，并且打印机不支持沿长边进行双面打印，则测试将导致 `false`。 （请参阅上面的说明。）  
  
6. 最后一个重要步骤是通过 <xref:System.Printing.PrintQueue.Commit%2A> 方法提交对 <xref:System.Printing.PrintQueue> 的 <xref:System.Printing.PrintQueue.UserPrintTicket%2A> 属性的更改。  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 因此，你可以快速测试此示例，下面提供了它的其余部分。 创建项目和命名空间，然后将本文中的代码片段粘贴到命名空间块。  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [WPF 中的文档](documents-in-wpf.md)
- [打印概述](printing-overview.md)
- [打印架构](/windows/win32/printdocs/printschema)
