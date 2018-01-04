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
# <a name="how-to-discover-whether-a-print-job-can-be-printed-at-this-time-of-day"></a><span data-ttu-id="78a23-102">如何：确定此时是否可以打印一项打印作业</span><span class="sxs-lookup"><span data-stu-id="78a23-102">How to: Discover Whether a Print Job Can Be Printed At This Time of Day</span></span>
<span data-ttu-id="78a23-103">打印队列并不总是可用的一天 24 小时。</span><span class="sxs-lookup"><span data-stu-id="78a23-103">Print queues are not always available for 24 hours a day.</span></span> <span data-ttu-id="78a23-104">它们具有开始和结束时间属性，可设置为使它们在每天的某些时间不可用。</span><span class="sxs-lookup"><span data-stu-id="78a23-104">They have start and end time properties that can be set to make them unavailable at certain times of day.</span></span> <span data-ttu-id="78a23-105">例如，此功能可以用于保留以供在下午 5 点后的特定部门专用打印机。</span><span class="sxs-lookup"><span data-stu-id="78a23-105">This feature can be used, for example, to reserve a printer for the exclusive use of a certain department after 5 P.M..</span></span> <span data-ttu-id="78a23-106">该部门都使用不同队列维护比其他部门打印机。</span><span class="sxs-lookup"><span data-stu-id="78a23-106">That department would have a different queue servicing the printer than other departments use.</span></span> <span data-ttu-id="78a23-107">将设置为其他部门队列来下午 5 点以后将不可用，尽管可将队列的支持的部门设置为始终保持可用。</span><span class="sxs-lookup"><span data-stu-id="78a23-107">The queue for the other departments would be set to be unavailable after 5 P.M., while queue for the favored department could be set to be available at all times.</span></span>  
  
 <span data-ttu-id="78a23-108">此外，打印作业本身可以被设置为仅在指定的时间范围内可打印。</span><span class="sxs-lookup"><span data-stu-id="78a23-108">Moreover, print jobs themselves can be set to be printable only within a specified span of time.</span></span>  
  
 <span data-ttu-id="78a23-109"><xref:System.Printing.PrintQueue>和<xref:System.Printing.PrintSystemJobInfo>类中公开[!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)]的[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]提供一种远程检查是否给定的打印作业可以打印给定队列上的当前时间。</span><span class="sxs-lookup"><span data-stu-id="78a23-109">The <xref:System.Printing.PrintQueue> and <xref:System.Printing.PrintSystemJobInfo> classes exposed in the [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] of [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] provide a means for remotely checking whether a given print job can print on a given queue at the current time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="78a23-110">示例</span><span class="sxs-lookup"><span data-stu-id="78a23-110">Example</span></span>  
 <span data-ttu-id="78a23-111">下面的示例是一个示例，可以使用诊断问题的打印作业。</span><span class="sxs-lookup"><span data-stu-id="78a23-111">The example below is a sample that can diagnose problems with a print job.</span></span>  
  
 <span data-ttu-id="78a23-112">有两个主要步骤，此类型的函数，如下所示。</span><span class="sxs-lookup"><span data-stu-id="78a23-112">There are two major steps for this kind of function as follows.</span></span>  
  
1.  <span data-ttu-id="78a23-113">读取<xref:System.Printing.PrintQueue.StartTimeOfDay%2A>和<xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>属性<xref:System.Printing.PrintQueue>以确定它们之间是否为当前时间。</span><span class="sxs-lookup"><span data-stu-id="78a23-113">Read the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties of the <xref:System.Printing.PrintQueue> to determine whether the current time is between them.</span></span>  
  
2.  <span data-ttu-id="78a23-114">读取<xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A>和<xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A>属性<xref:System.Printing.PrintSystemJobInfo>以确定它们之间是否为当前时间。</span><span class="sxs-lookup"><span data-stu-id="78a23-114">Read the <xref:System.Printing.PrintSystemJobInfo.StartTimeOfDay%2A> and <xref:System.Printing.PrintSystemJobInfo.UntilTimeOfDay%2A> properties of the <xref:System.Printing.PrintSystemJobInfo> to determine whether the current time is between them.</span></span>  
  
 <span data-ttu-id="78a23-115">但是问题变复杂，原因在于这些属性不是<xref:System.DateTime>对象。</span><span class="sxs-lookup"><span data-stu-id="78a23-115">But complications arise from the fact that these properties are not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="78a23-116">相反，它们是<xref:System.Int32>express 作为午夜算起的分钟数的一天的时间的对象。</span><span class="sxs-lookup"><span data-stu-id="78a23-116">Instead they are <xref:System.Int32> objects that express the time of day as the number of minutes since midnight.</span></span> <span data-ttu-id="78a23-117">此外，这不是午夜当前所在的时区，但午夜 UTC （协调世界时）。</span><span class="sxs-lookup"><span data-stu-id="78a23-117">Moreover, this is not midnight in the current time zone, but midnight UTC (Coordinated Universal Time).</span></span>  
  
 <span data-ttu-id="78a23-118">第一个代码示例演示静态方法**ReportQueueAndJobAvailability**，后者传递<xref:System.Printing.PrintSystemJobInfo>，调用帮助器方法，以确定是否可以在当前时间打印作业，如果它不是，可以打印时。</span><span class="sxs-lookup"><span data-stu-id="78a23-118">The first code example presents the static method **ReportQueueAndJobAvailability**, which is passed a <xref:System.Printing.PrintSystemJobInfo> and calls helper methods to determine whether the job can print at the current time and, if not, when it can print.</span></span> <span data-ttu-id="78a23-119">请注意，<xref:System.Printing.PrintQueue>不传递给方法。</span><span class="sxs-lookup"><span data-stu-id="78a23-119">Notice that a <xref:System.Printing.PrintQueue> is not passed to the method.</span></span> <span data-ttu-id="78a23-120">这是因为<xref:System.Printing.PrintSystemJobInfo>包括对中的队列的引用其<xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="78a23-120">This is because the <xref:System.Printing.PrintSystemJobInfo> includes a reference to the queue in its <xref:System.Printing.PrintSystemJobInfo.HostingPrintQueue%2A> property.</span></span>  
  
 <span data-ttu-id="78a23-121">从属方法包括重载**ReportAvailabilityAtThisTime**方法可以采用该方法<xref:System.Printing.PrintQueue>或<xref:System.Printing.PrintSystemJobInfo>作为参数。</span><span class="sxs-lookup"><span data-stu-id="78a23-121">The subordinate methods include the overloaded **ReportAvailabilityAtThisTime** method which can take either a <xref:System.Printing.PrintQueue> or a <xref:System.Printing.PrintSystemJobInfo> as a parameter.</span></span> <span data-ttu-id="78a23-122">此外，还有**TimeConverter.ConvertToLocalHumanReadableTime**。</span><span class="sxs-lookup"><span data-stu-id="78a23-122">There is also a **TimeConverter.ConvertToLocalHumanReadableTime**.</span></span> <span data-ttu-id="78a23-123">下面讨论了所有这些方法。</span><span class="sxs-lookup"><span data-stu-id="78a23-123">All of these methods are discussed below.</span></span>  
  
 <span data-ttu-id="78a23-124">**ReportQueueAndJobAvailability**方法首先检查以查看该队列或打印作业是否不可用在此时间。</span><span class="sxs-lookup"><span data-stu-id="78a23-124">The **ReportQueueAndJobAvailability** method begins by checking to see if either the queue or the print job is unavailable at this time.</span></span> <span data-ttu-id="78a23-125">如果其中任一个不可用，它然后检查是否不可用的队列。</span><span class="sxs-lookup"><span data-stu-id="78a23-125">If either of them is unavailable, it then checks to see if the queue unavailable.</span></span> <span data-ttu-id="78a23-126">如果不可用，然后该方法将报告此事实数据表和当队列将再次变得可用的时间。</span><span class="sxs-lookup"><span data-stu-id="78a23-126">If it is not available, then the method reports this fact and the time when the queue will become available again.</span></span> <span data-ttu-id="78a23-127">它然后检查作业和如果它是不可用，它将报告下次跨越时它可以打印时。</span><span class="sxs-lookup"><span data-stu-id="78a23-127">It then checks the job and if it is unavailable, it reports the next time span when it when it can print.</span></span> <span data-ttu-id="78a23-128">最后，该方法将报告时可以打印作业的最早时间。</span><span class="sxs-lookup"><span data-stu-id="78a23-128">Finally, the method reports the earliest time when the job can print.</span></span> <span data-ttu-id="78a23-129">这是两次的更高版本。</span><span class="sxs-lookup"><span data-stu-id="78a23-129">This is the later of following two times.</span></span>  
  
-   <span data-ttu-id="78a23-130">打印队列下一步可用的时间。</span><span class="sxs-lookup"><span data-stu-id="78a23-130">The time when the print queue is next available.</span></span>  
  
-   <span data-ttu-id="78a23-131">打印作业下一步可用的时间。</span><span class="sxs-lookup"><span data-stu-id="78a23-131">The time when the print job is next available.</span></span>  
  
 <span data-ttu-id="78a23-132">报告每天的时间、 时<xref:System.DateTime.ToShortTimeString%2A>因为年、 月和天输出中的，取消显示此方法也会调用方法。</span><span class="sxs-lookup"><span data-stu-id="78a23-132">When reporting times of day, the <xref:System.DateTime.ToShortTimeString%2A> method is also called because this method suppresses the years, months, and days from the output.</span></span> <span data-ttu-id="78a23-133">你无法将打印队列或打印作业的可用性的限制到特定的年、 月或天。</span><span class="sxs-lookup"><span data-stu-id="78a23-133">You cannot restrict the availability of either a print queue or a print job to particular years, months, or days.</span></span>  
  
 [!code-cpp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#reportqueueandjobavailability)]
 [!code-csharp[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#reportqueueandjobavailability)]
 [!code-vb[DiagnoseProblematicPrintJob#ReportQueueAndJobAvailability](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#reportqueueandjobavailability)]  
  
 <span data-ttu-id="78a23-134">两个重载的**ReportAvailabilityAtThisTime**方法是相同类型传递到它们，因此仅除外<xref:System.Printing.PrintQueue>下面显示了版本。</span><span class="sxs-lookup"><span data-stu-id="78a23-134">The two overloads of the **ReportAvailabilityAtThisTime** method are identical except for the type passed to them, so only the <xref:System.Printing.PrintQueue> version is presented below.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78a23-135">方法都是相同类型除外事实引发这一问题，该示例不会创建泛型方法的原因**ReportAvailabilityAtThisTime\<T >**。</span><span class="sxs-lookup"><span data-stu-id="78a23-135">The fact that the methods are identical except for type raises the question of why the sample does not create a generic method **ReportAvailabilityAtThisTime\<T>**.</span></span> <span data-ttu-id="78a23-136">原因是此类方法将一定要限制为具有的类**StartTimeOfDay**和**UntilTimeOfDay**属性调用的方法，但泛型方法可能仅会局限于单个类和公用的唯一类<xref:System.Printing.PrintQueue>和<xref:System.Printing.PrintSystemJobInfo>在继承树是<xref:System.Printing.PrintSystemObject>具有任何此类属性。</span><span class="sxs-lookup"><span data-stu-id="78a23-136">The reason is that such a method would have to be restricted to a class that has the **StartTimeOfDay** and **UntilTimeOfDay** properties that the method calls, but a generic method can only be restricted to a single class and the only class common to both <xref:System.Printing.PrintQueue> and <xref:System.Printing.PrintSystemJobInfo> in the inheritance tree is <xref:System.Printing.PrintSystemObject> which has no such properties.</span></span>  
  
 <span data-ttu-id="78a23-137">**ReportAvailabilityAtThisTime**方法 （如下面的代码示例所示） 开始初始化<xref:System.Boolean>sentinel 变量`true`。</span><span class="sxs-lookup"><span data-stu-id="78a23-137">The **ReportAvailabilityAtThisTime** method (presented in the code example below) begins by initializing a <xref:System.Boolean> sentinel variable to `true`.</span></span> <span data-ttu-id="78a23-138">将重置为`false`，如果队列不可用。</span><span class="sxs-lookup"><span data-stu-id="78a23-138">It will be reset to `false`, if the queue is not available.</span></span>  
  
 <span data-ttu-id="78a23-139">接下来，该方法将检查以查看开始和"之前"时间是否相同。</span><span class="sxs-lookup"><span data-stu-id="78a23-139">Next, the method checks to see if the start and "until" times are identical.</span></span> <span data-ttu-id="78a23-140">如果它们是，队列将始终可用，因此此方法返回`true`。</span><span class="sxs-lookup"><span data-stu-id="78a23-140">If they are, the queue is always available, so the method returns `true`.</span></span>  
  
 <span data-ttu-id="78a23-141">如果队列不可用的时间，该方法使用静态<xref:System.DateTime.UtcNow%2A>属性来获取当前时间作为<xref:System.DateTime>对象。</span><span class="sxs-lookup"><span data-stu-id="78a23-141">If the queue is not available all the time, the method uses the static <xref:System.DateTime.UtcNow%2A> property to get the current time as a <xref:System.DateTime> object.</span></span> <span data-ttu-id="78a23-142">(我们不需要本地时间，因为<xref:System.Printing.PrintQueue.StartTimeOfDay%2A>和<xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>属性本身就是 UTC 时间。)</span><span class="sxs-lookup"><span data-stu-id="78a23-142">(We do not need local time because the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are themselves in UTC time.)</span></span>  
  
 <span data-ttu-id="78a23-143">但是，这两个属性不是<xref:System.DateTime>对象。</span><span class="sxs-lookup"><span data-stu-id="78a23-143">However, these two properties are not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="78a23-144">它们是<xref:System.Int32>将时间表示为分钟后 UTC 午夜数。</span><span class="sxs-lookup"><span data-stu-id="78a23-144">They are <xref:System.Int32>s expressing the time as the number of minutes-after-UTC-midnight.</span></span> <span data-ttu-id="78a23-145">因此我们需要将转换我们<xref:System.DateTime>分钟后午夜到的对象。</span><span class="sxs-lookup"><span data-stu-id="78a23-145">So we do have to convert our <xref:System.DateTime> object to minutes-after-midnight.</span></span> <span data-ttu-id="78a23-146">完成后，该方法将只需检查以查看是否"现在"是之间队列的开始和"截止时间，设置为 false，如果"现在"sentinel 不之间两次，并返回 sentinel。</span><span class="sxs-lookup"><span data-stu-id="78a23-146">When that is done, the method simply checks to see whether "now" is between the queue's start and "until" times, sets the sentinel to false if "now" is not between the two times, and returns the sentinel.</span></span>  
  
 [!code-cpp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#printqueuestartuntil)]
 [!code-csharp[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#printqueuestartuntil)]
 [!code-vb[DiagnoseProblematicPrintJob#PrintQueueStartUntil](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#printqueuestartuntil)]  
  
 <span data-ttu-id="78a23-147">**TimeConverter.ConvertToLocalHumanReadableTime** （如下面的代码示例所示） 的方法不使用任何方法引入了[!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]，因此是简要讨论。</span><span class="sxs-lookup"><span data-stu-id="78a23-147">The **TimeConverter.ConvertToLocalHumanReadableTime** method (presented in the code example below) does not use any methods introduced with [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)], so the discussion is brief.</span></span> <span data-ttu-id="78a23-148">此方法不具有双转换任务： 它必须采用一个整数，该整数表示午夜分钟后，并将其转换为用户可读的时间和它必须将其转换为本地时间。</span><span class="sxs-lookup"><span data-stu-id="78a23-148">The method has a double conversion task: it must take an integer expressing minutes-after-midnight and convert it to a human-readable time and it must convert this to the local time.</span></span> <span data-ttu-id="78a23-149">这是通过实现通过先创建<xref:System.DateTime>设置为午夜 UTC，然后它使用的对象<xref:System.DateTime.AddMinutes%2A>方法将添加的分钟数传递给方法。</span><span class="sxs-lookup"><span data-stu-id="78a23-149">It accomplishes this by first creating a <xref:System.DateTime> object that is set to midnight UTC and then it uses the <xref:System.DateTime.AddMinutes%2A> method to add the minutes that were passed to the method.</span></span> <span data-ttu-id="78a23-150">这将返回一个新<xref:System.DateTime>表示传递给方法的原始时间。</span><span class="sxs-lookup"><span data-stu-id="78a23-150">This returns a new <xref:System.DateTime> expressing the original time that was passed to the method.</span></span> <span data-ttu-id="78a23-151"><xref:System.DateTime.ToLocalTime%2A>方法然后将此转换为本地时间。</span><span class="sxs-lookup"><span data-stu-id="78a23-151">The <xref:System.DateTime.ToLocalTime%2A> method then converts this to local time.</span></span>  
  
 [!code-cpp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CPP/Program.cpp#timeconverter)]
 [!code-csharp[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/CSharp/Program.cs#timeconverter)]
 [!code-vb[DiagnoseProblematicPrintJob#TimeConverter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DiagnoseProblematicPrintJob/visualbasic/program.vb#timeconverter)]  
  
## <a name="see-also"></a><span data-ttu-id="78a23-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="78a23-152">See Also</span></span>  
 <xref:System.DateTime>  
 <xref:System.Printing.PrintSystemJobInfo>  
 <xref:System.Printing.PrintQueue>  
 [<span data-ttu-id="78a23-153">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="78a23-153">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="78a23-154">打印概述</span><span class="sxs-lookup"><span data-stu-id="78a23-154">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
