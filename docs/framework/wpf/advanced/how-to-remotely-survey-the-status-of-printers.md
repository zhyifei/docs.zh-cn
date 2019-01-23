---
title: 如何：远程调查打印机的状态
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- surveying printer status remotely [WPF]
- printer status [WPF], surveying remotely
- remotely surveying printer status [WPF]
- status [WPF], printers [WPF], surveying remotely
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
ms.openlocfilehash: 330edd1119824d82558cf76d32d0d6641d26c80d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588362"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a><span data-ttu-id="df216-102">如何：远程调查打印机的状态</span><span class="sxs-lookup"><span data-stu-id="df216-102">How to: Remotely Survey the Status of Printers</span></span>
<span data-ttu-id="df216-103">在大中型公司，在任何给定时间里，都可能发生由于卡纸、纸张用完或某些其他有问题而导致多台打印机无法工作的情况。</span><span class="sxs-lookup"><span data-stu-id="df216-103">At any given time at medium and large companies there may be multiple printers that are not working due to a paper jam or being out of paper or some other problematic situation.</span></span> <span data-ttu-id="df216-104">打印机属性中公开的丰富[!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)]的 Microsoft.NET Framework 提供了一种方法用于执行快速调查打印机状态。</span><span class="sxs-lookup"><span data-stu-id="df216-104">The rich set of printer properties exposed in the [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] of Microsoft .NET Framework provide a means for performing a rapid survey of the states of printers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df216-105">示例</span><span class="sxs-lookup"><span data-stu-id="df216-105">Example</span></span>  
 <span data-ttu-id="df216-106">以下是创建此类实用程序的主要步骤。</span><span class="sxs-lookup"><span data-stu-id="df216-106">The major steps for creating this kind of utility are as follows.</span></span>  
  
1.  <span data-ttu-id="df216-107">获取所有打印服务器的列表。</span><span class="sxs-lookup"><span data-stu-id="df216-107">Obtain a list of all print servers.</span></span>  
  
2.  <span data-ttu-id="df216-108">循环访问服务器以查询其打印队列。</span><span class="sxs-lookup"><span data-stu-id="df216-108">Loop through the servers to query their print queues.</span></span>  
  
3.  <span data-ttu-id="df216-109">在每一轮服务器循环访问过程中，循环访问所有服务器的队列并读取每个属性，这些属性可能指示队列当前不在工作。</span><span class="sxs-lookup"><span data-stu-id="df216-109">Within each pass of the server loop, loop through all the server's queues and read each property that might indicate that the queue is not currently working.</span></span>  
  
 <span data-ttu-id="df216-110">以下代码是一系列代码段。</span><span class="sxs-lookup"><span data-stu-id="df216-110">The code below is a series of snippets.</span></span> <span data-ttu-id="df216-111">为简单起见，本示例假定存在通过 CRLF 分隔的打印服务器列表。</span><span class="sxs-lookup"><span data-stu-id="df216-111">For simplicity, this example assumes that there is a CRLF-delimited list of print servers.</span></span> <span data-ttu-id="df216-112">在变量`fileOfPrintServers`是<xref:System.IO.StreamReader>此文件的对象。</span><span class="sxs-lookup"><span data-stu-id="df216-112">The variable `fileOfPrintServers` is a <xref:System.IO.StreamReader> object for this file.</span></span> <span data-ttu-id="df216-113">由于每个服务器名称是在其对应行，任何调用的<xref:System.IO.StreamReader.ReadLine%2A>获取下一步的服务器的名称，并将移动<xref:System.IO.StreamReader>的光标移到下一行的开头。</span><span class="sxs-lookup"><span data-stu-id="df216-113">Since each server name is on its own line, any call of <xref:System.IO.StreamReader.ReadLine%2A> gets the name of the next server and moves the <xref:System.IO.StreamReader>'s cursor to the beginning of the next line.</span></span>  
  
 <span data-ttu-id="df216-114">在外部循环中，该代码会创建<xref:System.Printing.PrintServer>对象的最新的打印服务器，并指定要对服务器具有管理权限的应用程序。</span><span class="sxs-lookup"><span data-stu-id="df216-114">Within the outer loop, the code creates a <xref:System.Printing.PrintServer> object for the latest print server and specifies that the application is to have administrative rights to the server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df216-115">如果有多个服务器，则可以提高性能，通过使用<xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29>仅初始化都需要具备的属性的构造函数。</span><span class="sxs-lookup"><span data-stu-id="df216-115">If there are a lot of servers, you can improve performance by using the <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructors that only initialize the properties you are going to need.</span></span>  
  
 <span data-ttu-id="df216-116">该示例然后使用<xref:System.Printing.PrintServer.GetPrintQueues%2A>若要创建的所有服务器的集合的排队，并开始循环访问它们。</span><span class="sxs-lookup"><span data-stu-id="df216-116">The example then uses <xref:System.Printing.PrintServer.GetPrintQueues%2A> to create a collection of all of the server's queues and begins to loop through them.</span></span> <span data-ttu-id="df216-117">此内部循环包含一个分支结构，该结构对应于检查打印机状态的两种方法：</span><span class="sxs-lookup"><span data-stu-id="df216-117">This inner loop contains a branching structure corresponding to the two ways of checking a printer's status:</span></span>  
  
-   <span data-ttu-id="df216-118">可以读取的标志<xref:System.Printing.PrintQueue.QueueStatus%2A>属性的类型即<xref:System.Printing.PrintQueueStatus>。</span><span class="sxs-lookup"><span data-stu-id="df216-118">You can read the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property which is of type <xref:System.Printing.PrintQueueStatus>.</span></span>  
  
-   <span data-ttu-id="df216-119">你可以读取每个相关属性，如<xref:System.Printing.PrintQueue.IsOutOfPaper%2A>，和<xref:System.Printing.PrintQueue.IsPaperJammed%2A>。</span><span class="sxs-lookup"><span data-stu-id="df216-119">You can read each relevant property such as <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, and <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span></span>  
  
 <span data-ttu-id="df216-120">此示例演示这两种方法，因此该用户之前进行提示要使用的方法并回复"y"，如果他或她想要使用的标志<xref:System.Printing.PrintQueue.QueueStatus%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="df216-120">This example demonstrates both methods, so the user was previously prompted as to which method to use and responded with "y" if he or she wanted to use the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property.</span></span> <span data-ttu-id="df216-121">请参阅以下有关这两种方法的详细信息。</span><span class="sxs-lookup"><span data-stu-id="df216-121">See below for the details of the two methods.</span></span>  
  
 <span data-ttu-id="df216-122">最后，会向用户显示结果。</span><span class="sxs-lookup"><span data-stu-id="df216-122">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <span data-ttu-id="df216-123">若要使用的标志检查打印机状态<xref:System.Printing.PrintQueue.QueueStatus%2A>属性，检查每个相关标志以查看它是否设置。</span><span class="sxs-lookup"><span data-stu-id="df216-123">To check printer status using the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property, you check each relevant flag to see if it is set.</span></span> <span data-ttu-id="df216-124">检查是否在一组位标志中设置了一个位的标准方法是执行一个逻辑 AND 运算，其中将该组标志作为一个操作数，将标志本身作为另一操作数。</span><span class="sxs-lookup"><span data-stu-id="df216-124">The standard way to see if one bit is set in a set of bit flags is to perform a logical AND operation with the set of flags as one operand and the flag itself as the other.</span></span> <span data-ttu-id="df216-125">由于该标志本身仅设置一个位，因此逻辑 AND 的结果至多为设置了该相同位。</span><span class="sxs-lookup"><span data-stu-id="df216-125">Since the flag itself has only one bit set, the result of the logical AND is that, at most, that same bit is set.</span></span> <span data-ttu-id="df216-126">若要查明事实是否如此，只需将逻辑 AND 的结果与标志本身进行比较。</span><span class="sxs-lookup"><span data-stu-id="df216-126">To find out whether it is or not, just compare the result of the logical AND with the flag itself.</span></span> <span data-ttu-id="df216-127">有关详细信息，请参阅<xref:System.Printing.PrintQueueStatus>，则[& 运算符 (C#引用)](~/docs/csharp/language-reference/operators/and-operator.md)，并<xref:System.FlagsAttribute>。</span><span class="sxs-lookup"><span data-stu-id="df216-127">For more information, see <xref:System.Printing.PrintQueueStatus>, the [& Operator (C# Reference)](~/docs/csharp/language-reference/operators/and-operator.md), and <xref:System.FlagsAttribute>.</span></span>  
  
 <span data-ttu-id="df216-128">对于已设置了其位的各个特性，代码会将一条通知添加到将向用户显示的最终报告中。</span><span class="sxs-lookup"><span data-stu-id="df216-128">For each attribute whose bit is set, the code adds a notice to the final report that will be presented to the user.</span></span> <span data-ttu-id="df216-129">（下面会讨论代码结束时调用的 **ReportAvailabilityAtThisTime** 方法。）</span><span class="sxs-lookup"><span data-stu-id="df216-129">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 <span data-ttu-id="df216-130">若要使用各个属性检查打印机状态，只需读取各个属性，并将注释添加到最终报告，如果属性为 `true`，将向用户显示最终报告。</span><span class="sxs-lookup"><span data-stu-id="df216-130">To check printer status using each property, you simply read each property and add a note to the final report that will be presented to the user if the property is `true`.</span></span> <span data-ttu-id="df216-131">（下面会讨论代码结束时调用的 **ReportAvailabilityAtThisTime** 方法。）</span><span class="sxs-lookup"><span data-stu-id="df216-131">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 <span data-ttu-id="df216-132">创建了 **ReportAvailabilityAtThisTime** 方法，以应对需要确定队列在一天的当前时间是否可用的情况。</span><span class="sxs-lookup"><span data-stu-id="df216-132">The **ReportAvailabilityAtThisTime** method was created in case you need to determine if the queue is available at the current time of day.</span></span>  
  
 <span data-ttu-id="df216-133">该方法将不执行任何操作如果<xref:System.Printing.PrintQueue.StartTimeOfDay%2A>和<xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>属性相等，则因为在这种情况下打印机不可在任何时候。</span><span class="sxs-lookup"><span data-stu-id="df216-133">The method will do nothing if the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are equal; because in that case the printer is available at all times.</span></span> <span data-ttu-id="df216-134">如果它们不同，该方法将获取当前时间，它将拥有要转换为午夜过后的总分钟数，因为<xref:System.Printing.PrintQueue.StartTimeOfDay%2A>并<xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>属性是<xref:System.Int32>不表示分钟后午夜<xref:System.DateTime>对象。</span><span class="sxs-lookup"><span data-stu-id="df216-134">If they are different, the method gets the current time which then has to be converted into total minutes past midnight because the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are <xref:System.Int32>s representing minutes-after-midnight, not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="df216-135">最后，该方法会检查当前时间是否介于开始时间和“截至”时间之间。</span><span class="sxs-lookup"><span data-stu-id="df216-135">Finally, the method checks to see if the current time is between the start and "until" times.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a><span data-ttu-id="df216-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="df216-136">See also</span></span>
- <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>
- <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>
- <xref:System.DateTime>
- <xref:System.Printing.PrintQueueStatus>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- [<span data-ttu-id="df216-137">& 运算符 (C#引用)</span><span class="sxs-lookup"><span data-stu-id="df216-137">& Operator (C# Reference)</span></span>](~/docs/csharp/language-reference/operators/and-operator.md)
- [<span data-ttu-id="df216-138">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="df216-138">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
- [<span data-ttu-id="df216-139">打印概述</span><span class="sxs-lookup"><span data-stu-id="df216-139">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
