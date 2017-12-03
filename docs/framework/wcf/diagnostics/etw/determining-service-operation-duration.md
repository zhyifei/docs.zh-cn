---
title: "确定服务操作持续时间"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 24f1bc22e088c0198ec8a8f8183611d2b43941b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="determining-service-operation-duration"></a><span data-ttu-id="84f30-102">确定服务操作持续时间</span><span class="sxs-lookup"><span data-stu-id="84f30-102">Determining service operation duration</span></span>
<span data-ttu-id="84f30-103">如果在 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 应用程序中启用了分析跟踪，则通过检查事件日志可方便地确定服务操作的执行持续时间。</span><span class="sxs-lookup"><span data-stu-id="84f30-103">If analytic tracing is enabled in a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] application, the duration of execution for a service operation can easily be determined by examining the event log.</span></span>  <span data-ttu-id="84f30-104">本主题演示如何确定完成服务操作所需的时间量。</span><span class="sxs-lookup"><span data-stu-id="84f30-104">This topic demonstrates how to determine the amount of time a service operation takes to complete.</span></span>  
  
### <a name="determining-service-operation-execution-duration"></a><span data-ttu-id="84f30-105">确定服务操作执行持续时间</span><span class="sxs-lookup"><span data-stu-id="84f30-105">Determining service operation execution duration</span></span>  
  
1.  <span data-ttu-id="84f30-106">通过单击打开事件查看器**启动**，**运行**，并输入`eventvwr.exe`。</span><span class="sxs-lookup"><span data-stu-id="84f30-106">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2.  <span data-ttu-id="84f30-107">如果尚未启用分析跟踪，则展开**Applications and Services Logs**， **Microsoft**， **Windows**，**应用程序服务器-应用程序**.</span><span class="sxs-lookup"><span data-stu-id="84f30-107">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="84f30-108">选择**视图**，**显示分析和调试日志**。</span><span class="sxs-lookup"><span data-stu-id="84f30-108">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="84f30-109">右键单击**分析**和选择**启用日志**。</span><span class="sxs-lookup"><span data-stu-id="84f30-109">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="84f30-110">保持事件查看器打开，以便在服务操作运行后可以查看跟踪。</span><span class="sxs-lookup"><span data-stu-id="84f30-110">Leave Event Viewer open so that traces can be viewed after the service operation is run.</span></span>  
  
3.  <span data-ttu-id="84f30-111">接下来，打开 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 应用程序，其中包含一个服务项目以及一个与该服务交互的客户端项目。</span><span class="sxs-lookup"><span data-stu-id="84f30-111">Next, open a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] application that includes a service project and a client project that interacts with that service.</span></span>  <span data-ttu-id="84f30-112">你可以创建这样的应用程序按照[入门教程](../../../../../docs/framework/wcf/getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="84f30-112">You can create such an application by following the [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  <span data-ttu-id="84f30-113">如果你有[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]安装的示例，你可以打开[入门](../../../../../docs/framework/wcf/samples/getting-started-sample.md)，其中包含已完成本教程中创建的项目。</span><span class="sxs-lookup"><span data-stu-id="84f30-113">If you have the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] samples installed, you can open the [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4.  <span data-ttu-id="84f30-114">通过按执行服务器应用程序**F5**。</span><span class="sxs-lookup"><span data-stu-id="84f30-114">Execute the server application by pressing **F5**.</span></span> <span data-ttu-id="84f30-115">通过右键单击执行客户端应用程序**客户端**项目并选择**调试**，**启动新实例**。</span><span class="sxs-lookup"><span data-stu-id="84f30-115">Execute the client application by right-clicking on the **Client** project and selecting **Debug**, **Start New Instance**.</span></span>  
  
5.  <span data-ttu-id="84f30-116">在事件查看器中，刷新分析日志，然后按事件 ID 对事件排序。</span><span class="sxs-lookup"><span data-stu-id="84f30-116">In Event Viewer, refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="84f30-117">查找事件 id [214-OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md)。</span><span class="sxs-lookup"><span data-stu-id="84f30-117">Look for events with Event ID [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).</span></span>  <span data-ttu-id="84f30-118">这些事件将显示已完成的操作以及操作的持续时间。</span><span class="sxs-lookup"><span data-stu-id="84f30-118">These events will show which operations have completed, and what the duration of the operation was.</span></span>  <span data-ttu-id="84f30-119">下面的事件显示 Add 操作的持续时间。</span><span class="sxs-lookup"><span data-stu-id="84f30-119">The following event shows the duration of an Add operation.</span></span>  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
