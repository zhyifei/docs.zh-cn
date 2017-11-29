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
ms.openlocfilehash: 393d1692526551b1eb9aa16f48d3c78c3cd6692f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="650e9-102">如何：枚举打印队列的子集</span><span class="sxs-lookup"><span data-stu-id="650e9-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="650e9-103">信息技术 (IT) 专业人员负责管理公司范围内打印机所面临的常见情况是生成具有特定特征的打印机的列表。</span><span class="sxs-lookup"><span data-stu-id="650e9-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="650e9-104">此功能由<xref:System.Printing.PrintServer.GetPrintQueues%2A>方法<xref:System.Printing.PrintServer>对象和<xref:System.Printing.EnumeratedPrintQueueTypes>枚举。</span><span class="sxs-lookup"><span data-stu-id="650e9-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="650e9-105">示例</span><span class="sxs-lookup"><span data-stu-id="650e9-105">Example</span></span>  
 <span data-ttu-id="650e9-106">在下面的示例中，代码先创建标志，用于指定我们想要列出的打印队列的特征的数组。</span><span class="sxs-lookup"><span data-stu-id="650e9-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="650e9-107">在此示例中，我们正在寻找打印队列打印服务器上本地安装并共享。</span><span class="sxs-lookup"><span data-stu-id="650e9-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="650e9-108"><xref:System.Printing.EnumeratedPrintQueueTypes>枚举提供许多其他功能。</span><span class="sxs-lookup"><span data-stu-id="650e9-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="650e9-109">该代码随后创建<xref:System.Printing.LocalPrintServer>对象，派生自该类<xref:System.Printing.PrintServer>。</span><span class="sxs-lookup"><span data-stu-id="650e9-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="650e9-110">本地的打印服务器是在其运行应用程序的计算机。</span><span class="sxs-lookup"><span data-stu-id="650e9-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="650e9-111">最后一个重要步骤是将数组传递给<xref:System.Printing.PrintServer.GetPrintQueues%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="650e9-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="650e9-112">最后，会向用户显示结果。</span><span class="sxs-lookup"><span data-stu-id="650e9-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="650e9-113">您可以通过无扩展此示例`foreach`循环通过每个打印队列的步骤执行进一步屏蔽。</span><span class="sxs-lookup"><span data-stu-id="650e9-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="650e9-114">例如，你无法筛选掉不通过让循环调用支持双面打印的打印机每个打印队列<xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>方法和测试的返回值的双工是否存在。</span><span class="sxs-lookup"><span data-stu-id="650e9-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="650e9-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="650e9-115">See Also</span></span>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [<span data-ttu-id="650e9-116">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="650e9-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="650e9-117">打印概述</span><span class="sxs-lookup"><span data-stu-id="650e9-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="650e9-118">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="650e9-118">Microsoft XPS Document Writer</span></span>](http://go.microsoft.com/fwlink/?LinkId=147319)
