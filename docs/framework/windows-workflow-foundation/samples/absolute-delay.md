---
title: "绝对延迟"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b483139a-39bb-4560-8003-8969a8fc2cd1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6974c7bb281aa6685725b65edd06bb40a907559
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="absolute-delay"></a><span data-ttu-id="24e77-102">绝对延迟</span><span class="sxs-lookup"><span data-stu-id="24e77-102">Absolute Delay</span></span>
<span data-ttu-id="24e77-103">此示例的主要方案是，通过在工作流应用程序中使用持久性计时器延迟到指定的 <xref:System.DateTime>。</span><span class="sxs-lookup"><span data-stu-id="24e77-103">The main scenario for this sample is to delay until a specified <xref:System.DateTime> using durable timers in a workflow application.</span></span> <span data-ttu-id="24e77-104">这不同于使用内置 <xref:System.Activities.Statements.Delay> 活动，因为后者只允许延迟一段给定的 <xref:System.TimeSpan>（或分钟数/秒数）。</span><span class="sxs-lookup"><span data-stu-id="24e77-104">This is different from using the built-in <xref:System.Activities.Statements.Delay> activity as this will only allow you to delay for a given <xref:System.TimeSpan> (or number of minutes/seconds).</span></span>  
  
 <span data-ttu-id="24e77-105">您可能希望在某些实际方案中进行此区分，这些方案包括：</span><span class="sxs-lookup"><span data-stu-id="24e77-105">Some real-life scenarios in which you may want to make this distinction include the following:</span></span>  
  
1.  <span data-ttu-id="24e77-106">您希望将邮件发送时间延迟 30 秒以确保您未犯任何错误。</span><span class="sxs-lookup"><span data-stu-id="24e77-106">You want to delay sending a mail for 30 seconds to make sure you didn’t make any errors.</span></span>  
  
2.  <span data-ttu-id="24e77-107">您正在加班，并希望所有邮件延迟到正常工作时间（如上午 8 点）。</span><span class="sxs-lookup"><span data-stu-id="24e77-107">You are working overtime and want to delay all of your mails until normal business hours (such as 8 am).</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="24e77-108">演示</span><span class="sxs-lookup"><span data-stu-id="24e77-108">Demonstrates</span></span>  
  
1.  <span data-ttu-id="24e77-109">用于实现绝对延迟的 <xref:System.Activities.Statements.DurableTimerExtension></span><span class="sxs-lookup"><span data-stu-id="24e77-109"><xref:System.Activities.Statements.DurableTimerExtension> for implementing Absolute Delay</span></span>  
  
2.  <span data-ttu-id="24e77-110">将 <xref:System.Activities.WorkflowApplication> 用于持久性计时器来设置持久性</span><span class="sxs-lookup"><span data-stu-id="24e77-110">Setting up persistence using <xref:System.Activities.WorkflowApplication> for Durable Timers</span></span>  
  
3.  <span data-ttu-id="24e77-111">在使用扩展点时使用 <xref:System.Activities.NativeActivity%601></span><span class="sxs-lookup"><span data-stu-id="24e77-111">Use of <xref:System.Activities.NativeActivity%601> for using Extensibility points</span></span>  
  
4.  <span data-ttu-id="24e77-112">在 SendEmail 活动中使用 <xref:System.Activities.CodeActivity%601></span><span class="sxs-lookup"><span data-stu-id="24e77-112">Use of <xref:System.Activities.CodeActivity%601> in the SendEmail activity</span></span>  
  
5.  <xref:System.Activities.Statements.Delay>  
  
6.  <span data-ttu-id="24e77-113">仅 XAML 工作流</span><span class="sxs-lookup"><span data-stu-id="24e77-113">XAML-only workflow</span></span>  
  
 <span data-ttu-id="24e77-114">此示例演示如何创建一个自定义活动，该活动接受 <xref:System.DateTime> 并使用持久性计时器来注册延迟持续时间。</span><span class="sxs-lookup"><span data-stu-id="24e77-114">This sample demonstrates how to create a custom activity which takes in a <xref:System.DateTime> and uses durable timers to register the delay duration.</span></span> <span data-ttu-id="24e77-115">在使用持久性计时器时，您必须使用 <xref:System.Activities.NativeActivity> 创建书签，因为您需要将此书签注册到计时器扩展。</span><span class="sxs-lookup"><span data-stu-id="24e77-115">When using durable timers, you must use a <xref:System.Activities.NativeActivity> to create a bookmark, as you will need to register this bookmark with the timer extension.</span></span> <span data-ttu-id="24e77-116">在此示例中，当持久性计时器过期时，将调用 `OnTimerExpired` 方法。</span><span class="sxs-lookup"><span data-stu-id="24e77-116">In this sample, when the durable timer expires, the `OnTimerExpired` method will be called.</span></span> <span data-ttu-id="24e77-117">请务必在 <xref:System.Activities.NativeActivity%601.CacheMetadata%2A> 事件中添加计时器扩展，以确保为运行时提供此信息。</span><span class="sxs-lookup"><span data-stu-id="24e77-117">Make sure that you are adding the timer extension in the <xref:System.Activities.NativeActivity%601.CacheMetadata%2A> event to ensure you are providing the runtime with this information.</span></span> <span data-ttu-id="24e77-118">另一个实现细节是，您需要实现逻辑以将 <xref:System.DateTime> 转换为 <xref:System.TimeSpan>，因为持久性计时器只接受 <xref:System.DateTime></span><span class="sxs-lookup"><span data-stu-id="24e77-118">The only other implementation detail is that you will need to implement logic to convert from <xref:System.DateTime> to <xref:System.TimeSpan>, as durable timers only take in a <xref:System.DateTime>.</span></span> <span data-ttu-id="24e77-119">。</span><span class="sxs-lookup"><span data-stu-id="24e77-119">Do note that there is a small lapse in accuracy by doing</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24e77-120">将 <xref:System.DateTime> 转换为 <xref:System.TimeSpan> 会损失少量精度。</span><span class="sxs-lookup"><span data-stu-id="24e77-120">There is a small loss of accuracy by converting from <xref:System.DateTime> to <xref:System.TimeSpan>.</span></span>  
  
 <span data-ttu-id="24e77-121">此示例还演示如何为 <xref:System.Activities.WorkflowApplication> 启用持久性。</span><span class="sxs-lookup"><span data-stu-id="24e77-121">This sample also demonstrates how to turn on persistence for a <xref:System.Activities.WorkflowApplication>.</span></span> <span data-ttu-id="24e77-122">在此特定示例中，我们将使用持久性计时器，在该计时器中，工作流数据将在等待计时器过期的空闲时间内卸载到持久性数据库中。</span><span class="sxs-lookup"><span data-stu-id="24e77-122">For this particular sample, we will be using durable timers in which the workflow data will be unloaded into the persistence database during the idle time while waiting for timer to expire.</span></span> <span data-ttu-id="24e77-123">此实现还可用于其他持久性操作。</span><span class="sxs-lookup"><span data-stu-id="24e77-123">This implementation can also be used for other persistence actions.</span></span> <span data-ttu-id="24e77-124">此示例演示如何使用 SQL Server 设置持久性连接字符串以及如何创建实例存储以便为工作流实例保留数据。</span><span class="sxs-lookup"><span data-stu-id="24e77-124">This sample shows how to set up the persistence connection string with SQL Server, and how to create the instance store in order to persist the data for workflow instances.</span></span> <span data-ttu-id="24e77-125">提供了有关如何在引发使工作流实例可运行的事件后恢复工作流的逻辑。</span><span class="sxs-lookup"><span data-stu-id="24e77-125">Logic is provided on how to resume the workflow once an event is raised which makes the workflow instance runnable.</span></span>  
  
 <span data-ttu-id="24e77-126">在执行此示例时，您将看到内置延迟开始和完成的时间，而后者会导致发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="24e77-126">As you step through this sample, you will see the time in which the built-in delay begins and completes, which in turn will cause an e-mail message to be sent.</span></span> <span data-ttu-id="24e77-127">从这里开始，AbsoluteDelay 活动将暂停直到指定的 <xref:System.DateTime>（如果 <xref:System.DateTime> 已过期，则为 0 秒），而后者会在过期后发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="24e77-127">From there, the AbsoluteDelay activity will halt until a specified <xref:System.DateTime> (or 0 seconds if the <xref:System.DateTime> has expired) which in turn will send out an email upon expiration.</span></span> <span data-ttu-id="24e77-128">这将显示内置 <xref:System.Activities.Statements.Delay> 功能与使用 AbsoluteDelay 活动的两种不同用例。</span><span class="sxs-lookup"><span data-stu-id="24e77-128">This will show the two different use cases of the built-in <xref:System.Activities.Statements.Delay> functionality versus using an AbsoluteDelay activity.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="24e77-129">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="24e77-129">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="24e77-130">请确保在您的计算机上已经安装了 SQL Server Express（或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="24e77-130">Ensure you have SQL Server Express (or higher) installed on your machine</span></span>  
  
2.  <span data-ttu-id="24e77-131">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 命令提示符处运行 setup.cmd（位于 WF/Basic/Services/AbsoluteDelay/CS 中）以创建 AbsoluteDelaySampleDB 数据库、持久性架构和持久性逻辑。</span><span class="sxs-lookup"><span data-stu-id="24e77-131">Run setup.cmd (from WF/Basic/Services/AbsoluteDelay/CS) in a [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] command prompt to create the AbsoluteDelaySampleDB database, create the persistence schema and create the persistence logic.</span></span>  
  
3.  <span data-ttu-id="24e77-132">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开解决方案。</span><span class="sxs-lookup"><span data-stu-id="24e77-132">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
4.  <span data-ttu-id="24e77-133">在 Delay 活动中指定持续时间。</span><span class="sxs-lookup"><span data-stu-id="24e77-133">Specify the Duration in the Delay activity.</span></span>  
  
5.  <span data-ttu-id="24e77-134">在 AbsoluteDelay 活动中指定 ExpirationTime。</span><span class="sxs-lookup"><span data-stu-id="24e77-134">Specify the ExpirationTime in the AbsoluteDelay activity.</span></span>  
  
6.  <span data-ttu-id="24e77-135">更新 SendMail 活动中的 SendMailTo、SendMailFrom、SendMailSubject、SendMailBody 和 SmtpHost 字段。</span><span class="sxs-lookup"><span data-stu-id="24e77-135">Update the SendMailTo, SendMailFrom, SendMailSubject, SendMailBody, and SmtpHost fields in the SendMail activity.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="24e77-136">如果未输入有效 SMTP 主机，则应用程序将引发 SMTP 异常。</span><span class="sxs-lookup"><span data-stu-id="24e77-136">If you do not enter a valid SMTP host, the application will throw a SMTP exception.</span></span>  
  
7.  <span data-ttu-id="24e77-137">生成解决方案，通过选择**生成**，**生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="24e77-137">Build the solution by selecting **Build**, **Build Solution**.</span></span>  
  
8.  <span data-ttu-id="24e77-138">运行解决方案，按**F5**。</span><span class="sxs-lookup"><span data-stu-id="24e77-138">Run the solution by pressing **F5**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="24e77-139">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="24e77-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="24e77-140">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="24e77-140">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="24e77-141">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="24e77-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="24e77-142">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="24e77-142">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\AbsoluteDelay`
