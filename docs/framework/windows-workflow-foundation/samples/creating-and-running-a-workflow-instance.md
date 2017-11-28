---
title: "创建和运行工作流实例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d53becfc126f1acee4759ddff956b4435c9aa769
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="creating-and-running-a-workflow-instance"></a><span data-ttu-id="17ff6-102">创建和运行工作流实例</span><span class="sxs-lookup"><span data-stu-id="17ff6-102">Creating and Running a Workflow Instance</span></span>
<span data-ttu-id="17ff6-103">此示例演示如何运行工作流实例。</span><span class="sxs-lookup"><span data-stu-id="17ff6-103">This sample shows how to run a workflow instance.</span></span> <span data-ttu-id="17ff6-104">它演示如何以同步方式和异步方式执行这一操作。</span><span class="sxs-lookup"><span data-stu-id="17ff6-104">It shows how to execute it synchronously and asynchronously.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="17ff6-105">演示</span><span class="sxs-lookup"><span data-stu-id="17ff6-105">Demonstrates</span></span>  
 <span data-ttu-id="17ff6-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="17ff6-106"><xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="17ff6-107">讨论</span><span class="sxs-lookup"><span data-stu-id="17ff6-107">Discussion</span></span>  
 <span data-ttu-id="17ff6-108">此示例的第一部分使用 <xref:System.Activities.WorkflowInvoker.Invoke%2A>。</span><span class="sxs-lookup"><span data-stu-id="17ff6-108">The first part of the sample uses <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span> <span data-ttu-id="17ff6-109">这是执行工作流的最基本方法。</span><span class="sxs-lookup"><span data-stu-id="17ff6-109">This is the most basic way to execute a workflow.</span></span> <span data-ttu-id="17ff6-110">使用 <xref:System.Activities.WorkflowInvoker.Invoke%2A> 执行的工作流以同步方式执行。</span><span class="sxs-lookup"><span data-stu-id="17ff6-110">Workflows executed with <xref:System.Activities.WorkflowInvoker.Invoke%2A> are executed synchronously.</span></span>  
  
 <span data-ttu-id="17ff6-111">该示例的第二部分使用 <xref:System.Activities.WorkflowApplication> 类。</span><span class="sxs-lookup"><span data-stu-id="17ff6-111">The second part of the sample uses the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="17ff6-112">利用 <xref:System.Activities.WorkflowApplication>，您可以对每个实例进行更多控制，包括与正在运行的工作流进行交互的能力和异步运行工作流的能力。</span><span class="sxs-lookup"><span data-stu-id="17ff6-112"><xref:System.Activities.WorkflowApplication> enables you to have more control over each instance, including the ability to interact with the running workflow and to run the workflow asynchronously.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="17ff6-113">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="17ff6-113">The samples may already be installed on your machine.</span></span> <span data-ttu-id="17ff6-114">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="17ff6-114">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="17ff6-115">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="17ff6-115">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="17ff6-116">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="17ff6-116">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a><span data-ttu-id="17ff6-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="17ff6-117">See Also</span></span>  
 [<span data-ttu-id="17ff6-118">使用 WorkflowInvoker 和 WorkflowApplication</span><span class="sxs-lookup"><span data-stu-id="17ff6-118">Using WorkflowInvoker and WorkflowApplication</span></span>](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
