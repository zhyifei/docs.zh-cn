---
title: 如何：枚举打印队列的子集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: bf45d6fb3fb161ca5171e94b9ab7af1e0e6f0c3d
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43786931"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="2d8e2-102">如何：枚举打印队列的子集</span><span class="sxs-lookup"><span data-stu-id="2d8e2-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="2d8e2-103">负责管理公司范围内的打印机的信息技术 (IT) 专业人员所面临的常见情况是生成具有某些特征的打印机的列表。</span><span class="sxs-lookup"><span data-stu-id="2d8e2-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="2d8e2-104">提供此功能<xref:System.Printing.PrintServer.GetPrintQueues%2A>方法<xref:System.Printing.PrintServer>对象和<xref:System.Printing.EnumeratedPrintQueueTypes>枚举。</span><span class="sxs-lookup"><span data-stu-id="2d8e2-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d8e2-105">示例</span><span class="sxs-lookup"><span data-stu-id="2d8e2-105">Example</span></span>  
 <span data-ttu-id="2d8e2-106">在下面的示例中，代码先创建标志，用于指定我们想要列出的打印队列的特性数组。</span><span class="sxs-lookup"><span data-stu-id="2d8e2-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="2d8e2-107">在此示例中，我们正在寻找打印队列打印服务器上本地安装并共享。</span><span class="sxs-lookup"><span data-stu-id="2d8e2-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="2d8e2-108"><xref:System.Printing.EnumeratedPrintQueueTypes>枚举提供了许多其他的值。</span><span class="sxs-lookup"><span data-stu-id="2d8e2-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="2d8e2-109">该代码随后创建<xref:System.Printing.LocalPrintServer>对象，一个类派生自<xref:System.Printing.PrintServer>。</span><span class="sxs-lookup"><span data-stu-id="2d8e2-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="2d8e2-110">本地打印服务器是在其运行应用程序的计算机。</span><span class="sxs-lookup"><span data-stu-id="2d8e2-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="2d8e2-111">最后一个重要步骤是将数组传递给<xref:System.Printing.PrintServer.GetPrintQueues%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="2d8e2-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="2d8e2-112">最后，会向用户显示结果。</span><span class="sxs-lookup"><span data-stu-id="2d8e2-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="2d8e2-113">您可以扩展此示例通过让`foreach`循环通过每个打印队列的步骤执行进一步筛选。</span><span class="sxs-lookup"><span data-stu-id="2d8e2-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="2d8e2-114">例如，您可以筛选掉不支持通过循环调用双面打印的打印机每个打印队列的<xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>方法和测试返回的值进行双面打印是否存在。</span><span class="sxs-lookup"><span data-stu-id="2d8e2-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d8e2-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d8e2-115">See Also</span></span>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [<span data-ttu-id="2d8e2-116">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="2d8e2-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="2d8e2-117">打印概述</span><span class="sxs-lookup"><span data-stu-id="2d8e2-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="2d8e2-118">Microsoft XPS 文档编写器</span><span class="sxs-lookup"><span data-stu-id="2d8e2-118">Microsoft XPS Document Writer</span></span>](https://go.microsoft.com/fwlink/?LinkId=147319)
