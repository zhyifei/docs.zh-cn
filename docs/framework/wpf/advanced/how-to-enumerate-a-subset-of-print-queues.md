---
title: "如何：枚举打印队列的子集"
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
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 397ec40e2d8a0694e208296593687e9268546fc7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>如何：枚举打印队列的子集
信息技术 (IT) 专业人员负责管理公司范围内打印机所面临的常见情况是生成具有特定特征的打印机的列表。 此功能由<xref:System.Printing.PrintServer.GetPrintQueues%2A>方法<xref:System.Printing.PrintServer>对象和<xref:System.Printing.EnumeratedPrintQueueTypes>枚举。  
  
## <a name="example"></a>示例  
 在下面的示例中，代码先创建标志，用于指定我们想要列出的打印队列的特征的数组。 在此示例中，我们正在寻找打印队列打印服务器上本地安装并共享。 <xref:System.Printing.EnumeratedPrintQueueTypes>枚举提供许多其他功能。  
  
 该代码随后创建<xref:System.Printing.LocalPrintServer>对象，派生自该类<xref:System.Printing.PrintServer>。 本地的打印服务器是在其运行应用程序的计算机。  
  
 最后一个重要步骤是将数组传递给<xref:System.Printing.PrintServer.GetPrintQueues%2A>方法。  
  
 最后，会向用户显示结果。  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 您可以通过无扩展此示例`foreach`循环通过每个打印队列的步骤执行进一步屏蔽。 例如，你无法筛选掉不通过让循环调用支持双面打印的打印机每个打印队列<xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>方法和测试的返回值的双工是否存在。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [打印概述](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)
