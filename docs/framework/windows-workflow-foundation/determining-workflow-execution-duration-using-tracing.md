---
title: 使用跟踪确定工作流执行持续时间
ms.date: 03/30/2017
ms.assetid: f04ad0fd-edc7-4cbc-8979-356f2a1131c4
ms.openlocfilehash: 9f9c65f2c873d54da443db14e7f5797ef1e14174
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515080"
---
# <a name="determining-workflow-execution-duration-using-tracing"></a><span data-ttu-id="3e9c8-102">使用跟踪确定工作流执行持续时间</span><span class="sxs-lookup"><span data-stu-id="3e9c8-102">Determining Workflow Execution Duration Using Tracing</span></span>
<span data-ttu-id="3e9c8-103">本主题演示如何使用工作流跟踪来确定执行成功完成的自承载工作流所需的时间。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-103">This topic demonstrates how to determine the time it takes for a successfully completed, self-hosted workflow to execute by using workflow tracing.</span></span>  
  
### <a name="to-determine-workflow-application-execution-duration-by-using-workflow-tracing"></a><span data-ttu-id="3e9c8-104">使用工作流跟踪来确定工作流应用程序执行的持续时间</span><span class="sxs-lookup"><span data-stu-id="3e9c8-104">To determine workflow application execution duration by using workflow tracing</span></span>  
  
1.  <span data-ttu-id="3e9c8-105">打开 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-105">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  <span data-ttu-id="3e9c8-106">选择**文件**，**新**，**项目**。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-106">Select **File**, **New**, **Project**.</span></span>  <span data-ttu-id="3e9c8-107">下**C#**，选择**工作流**节点。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-107">Under **C#**, select the **Workflow** node.</span></span>  <span data-ttu-id="3e9c8-108">选择**工作流控制台应用程序**从模板列表中。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-108">Select **Workflow Console Application** from the list of templates.</span></span>  <span data-ttu-id="3e9c8-109">将新项目`WorkflowDurationTracing`单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-109">Name the new project `WorkflowDurationTracing` and click **OK**.</span></span>  
  
2.  <span data-ttu-id="3e9c8-110">打开 Workflow1.xaml。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-110">Open Workflow1.xaml.</span></span>  <span data-ttu-id="3e9c8-111">将 <xref:System.Activities.Statements.Delay> 活动拖动到设计器图面上。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-111">Drag a <xref:System.Activities.Statements.Delay> activity onto the designer surface.</span></span> <span data-ttu-id="3e9c8-112">将值 00:00:10（10 秒）分配给活动的“持续时间”属性。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-112">Assign the value 00:00:10 (ten seconds) to the Duration property of the activity.</span></span>  
  
3.  <span data-ttu-id="3e9c8-113">通过单击打开事件查看器**启动**，**运行**，并输入`eventvwr.exe`。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-113">Open Event Viewer by clicking **Start**, **Run**, and entering `eventvwr.exe`.</span></span>  
  
4.  <span data-ttu-id="3e9c8-114">如果尚未启用工作流跟踪，则展开**Applications and Services Logs**， **Microsoft**， **Windows**，**应用程序服务器-应用程序**.</span><span class="sxs-lookup"><span data-stu-id="3e9c8-114">If you haven’t enabled workflow tracing, expand **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="3e9c8-115">选择**视图**，**显示分析和调试日志**。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-115">Select **View**, **Show Analytic and Debug Logs**.</span></span> <span data-ttu-id="3e9c8-116">右键单击**调试**和选择**启用日志**。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-116">Right-click **Debug** and select **Enable Log**.</span></span> <span data-ttu-id="3e9c8-117">使事件查看器保持打开状态，以便在工作流运行后可以查看跟踪。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-117">Leave Event Viewer open so that traces can be viewed after the workflow is run.</span></span>  
  
5.  <span data-ttu-id="3e9c8-118">按 Ctrl+Shift+B 执行工作流应用程序。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-118">Execute the workflow application by pressing CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="3e9c8-119">在事件查看器中，查找 ID 为 1009 的最新事件和类似于以下内容的消息。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-119">In Event Viewer, find a recent event with ID 1009 and a message similar to the following.</span></span> <span data-ttu-id="3e9c8-120">记下记录消息的时间。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-120">Make a note of the time that the message was logged.</span></span>  
  
 <span data-ttu-id="3e9c8-121">**父 Activity '，DisplayName: '，InstanceId: ' 安排了子 Activity WorkflowDurationTracking.Workflow1、 DisplayName: Workflow1、 InstanceId:"1"。**</span><span class="sxs-lookup"><span data-stu-id="3e9c8-121">**Parent Activity '', DisplayName: '', InstanceId: '' scheduled child Activity 'WorkflowDurationTracking.Workflow1', DisplayName: 'Workflow1', InstanceId: '1'.**</span></span>  
  
7.  <span data-ttu-id="3e9c8-122">查找另一个 ID 为 1001 的最新事件和类似于以下内容的消息。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-122">Find another recent event with ID 1001 and a message similar to the following.</span></span>  <span data-ttu-id="3e9c8-123">从此消息的记录值中减去以前的消息时间，以确定工作流执行的持续时间，应该大约为 10 秒钟。</span><span class="sxs-lookup"><span data-stu-id="3e9c8-123">Subtract the previous message time from this message’s Logged value to determine workflow execution duration, which should be around 10 seconds.</span></span>  
  
 <span data-ttu-id="3e9c8-124">**WorkflowInstance Id"1bbac57b-3322-498e-9e27-8833fda3a5bf"已完成处于关闭状态。**</span><span class="sxs-lookup"><span data-stu-id="3e9c8-124">**WorkflowInstance Id: '1bbac57b-3322-498e-9e27-8833fda3a5bf' has completed in the Closed state.**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e9c8-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e9c8-125">See Also</span></span>  
 [<span data-ttu-id="3e9c8-126">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="3e9c8-126">Workflow Tracing</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-tracing.md)  
 [<span data-ttu-id="3e9c8-127">Windows Server App Fabric 监视</span><span class="sxs-lookup"><span data-stu-id="3e9c8-127">Windows Server App Fabric Monitoring</span></span>](http://go.microsoft.com/fwlink/?LinkId=201273)  
 [<span data-ttu-id="3e9c8-128">使用 App Fabric 监视应用程序</span><span class="sxs-lookup"><span data-stu-id="3e9c8-128">Monitoring Applications with App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkId=201275)
