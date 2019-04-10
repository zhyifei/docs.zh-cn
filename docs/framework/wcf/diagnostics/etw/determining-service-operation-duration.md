---
title: 确定服务操作持续时间
ms.date: 03/30/2017
ms.assetid: e8a93a2c-2c20-48b3-8986-57e90e9aa908
ms.openlocfilehash: fd7dec5784f50a0613b574822a31202a859b34c6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59299028"
---
# <a name="determining-service-operation-duration"></a><span data-ttu-id="71011-102">确定服务操作持续时间</span><span class="sxs-lookup"><span data-stu-id="71011-102">Determining service operation duration</span></span>
<span data-ttu-id="71011-103">如果 Windows Communication Foundation (WCF) 应用程序中启用了分析跟踪，则可轻松地通过检查事件日志确定服务操作的执行持续时间。</span><span class="sxs-lookup"><span data-stu-id="71011-103">If analytic tracing is enabled in a Windows Communication Foundation (WCF) application, the duration of execution for a service operation can easily be determined by examining the event log.</span></span>  <span data-ttu-id="71011-104">本主题演示如何确定完成服务操作所需的时间量。</span><span class="sxs-lookup"><span data-stu-id="71011-104">This topic demonstrates how to determine the amount of time a service operation takes to complete.</span></span>  
  
### <a name="determining-service-operation-execution-duration"></a><span data-ttu-id="71011-105">确定服务操作执行持续时间</span><span class="sxs-lookup"><span data-stu-id="71011-105">Determining service operation execution duration</span></span>  
  
1. <span data-ttu-id="71011-106">通过单击打开事件查看器**启动**，**运行**，并输入`eventvwr.exe`。</span><span class="sxs-lookup"><span data-stu-id="71011-106">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
2. <span data-ttu-id="71011-107">如果尚未启用分析跟踪，展开**应用程序和服务日志**， **Microsoft**， **Windows**，**应用程序服务器-应用程序**.</span><span class="sxs-lookup"><span data-stu-id="71011-107">If you haven’t enabled analytic tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="71011-108">选择**视图**，**显示分析和调试日志**。</span><span class="sxs-lookup"><span data-stu-id="71011-108">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="71011-109">右键单击**Analytic** ，然后选择**启用日志**。</span><span class="sxs-lookup"><span data-stu-id="71011-109">Right-click **Analytic** and select **Enable Log**.</span></span> <span data-ttu-id="71011-110">保持事件查看器打开，以便在服务操作运行后可以查看跟踪。</span><span class="sxs-lookup"><span data-stu-id="71011-110">Leave Event Viewer open so that traces can be viewed after the service operation is run.</span></span>  
  
3. <span data-ttu-id="71011-111">接下来，打开包含一个服务项目以及与该服务交互的客户端项目的 WCF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="71011-111">Next, open a WCF application that includes a service project and a client project that interacts with that service.</span></span>  <span data-ttu-id="71011-112">可以通过创建此类应用程序[入门教程](../../../../../docs/framework/wcf/getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="71011-112">You can create such an application by following the [Getting Started Tutorial](../../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  <span data-ttu-id="71011-113">如果您有安装 WCF 示例，可以打开[Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md)，其中包含本教程中创建的已完成的项目。</span><span class="sxs-lookup"><span data-stu-id="71011-113">If you have the WCF samples installed, you can open the [Getting Started](../../../../../docs/framework/wcf/samples/getting-started-sample.md), which contains the completed project created in the tutorial.</span></span>  
  
4. <span data-ttu-id="71011-114">按执行服务器应用程序**F5**。</span><span class="sxs-lookup"><span data-stu-id="71011-114">Execute the server application by pressing **F5**.</span></span> <span data-ttu-id="71011-115">通过右键单击执行客户端应用程序**客户端**项目并选择**调试**，**启动新实例**。</span><span class="sxs-lookup"><span data-stu-id="71011-115">Execute the client application by right-clicking on the **Client** project and selecting **Debug**, **Start New Instance**.</span></span>  
  
5. <span data-ttu-id="71011-116">在事件查看器中，刷新分析日志，然后按事件 ID 对事件排序。</span><span class="sxs-lookup"><span data-stu-id="71011-116">In Event Viewer, refresh the Analytic log and sort the events by Event ID.</span></span>  <span data-ttu-id="71011-117">查找事件 ID 的事件[214-OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md)。</span><span class="sxs-lookup"><span data-stu-id="71011-117">Look for events with Event ID [214 - OperationCompleted](../../../../../docs/framework/wcf/diagnostics/etw/214-operationcompleted.md).</span></span>  <span data-ttu-id="71011-118">这些事件将显示已完成的操作以及操作的持续时间。</span><span class="sxs-lookup"><span data-stu-id="71011-118">These events will show which operations have completed, and what the duration of the operation was.</span></span>  <span data-ttu-id="71011-119">下面的事件显示 Add 操作的持续时间。</span><span class="sxs-lookup"><span data-stu-id="71011-119">The following event shows the duration of an Add operation.</span></span>  
  
    ```Output  
    An OperationInvoker completed the call to the 'Add' method.  The method call duration was '3' ms.  
    ```
