---
title: "可补偿活动上的取消处理程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afd98bee-eccf-47e9-99c9-27cea84ce5ce
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f0f8e05d9a43b02412e7445480f7204fd2e7e13
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cancellation-handler-on-compensable-activity"></a><span data-ttu-id="811dc-102">可补偿活动上的取消处理程序</span><span class="sxs-lookup"><span data-stu-id="811dc-102">Cancellation Handler on Compensable Activity</span></span>
<span data-ttu-id="811dc-103">此示例演示如何对 <xref:System.Activities.Statements.CompensableActivity> 使用取消处理程序。</span><span class="sxs-lookup"><span data-stu-id="811dc-103">This sample demonstrates the use of a cancellation handler on a <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 <span data-ttu-id="811dc-104">此示例包含两个演示如何使用 <xref:System.Activities.Statements.CompensableActivity> 取消的方案。第一个方案包含一个根可补偿活动，而根可补偿活动又包含三个子可补偿活动。</span><span class="sxs-lookup"><span data-stu-id="811dc-104">This sample contains two scenarios that demonstrate the use of <xref:System.Activities.Statements.CompensableActivity> cancellation.The first scenario contains a root compensable activity that contains three child compensable activities.</span></span> <span data-ttu-id="811dc-105">两个子活动成功地运行完它们的活动主体。</span><span class="sxs-lookup"><span data-stu-id="811dc-105">Two child activities finish running their activity bodies successfully.</span></span> <span data-ttu-id="811dc-106">当运行第三个子活动主体时，它会遇到一个异常，该异常可通过取消第三个活动进程来处理，此后，将会触发根活动的取消。</span><span class="sxs-lookup"><span data-stu-id="811dc-106">When the third child activity body runs, it encounters an exception that is handled by canceling the third activity processing, after which the cancellation of the root activity is triggered.</span></span> <span data-ttu-id="811dc-107">此示例中根活动的逻辑是补偿较早完成的另外两个子活动。</span><span class="sxs-lookup"><span data-stu-id="811dc-107">The logic in the root activity in this example is to compensate the other two child activities that completed earlier.</span></span>  
  
```  
Try  
{  
    CA   
    {  
        CA1   
        {  
        }  
        CA2  
        {  
        }  
        CA3  
        {  
            //Exception here  
            // Then this will get cancelled  
        }  
  
       // Cancellation for the root activity automatically gets called, which, in turn, adds some logic to revert what was done (Or can decide to actually confirm CA1 & CA2 if the user so desires).  
    }  
}  
Catches {  
// Can do more stuff...  
}  
```  
  
 <span data-ttu-id="811dc-108">第二个方案演示如何与 <xref:System.Activities.Statements.TryCatch> 一起并行执行 <xref:System.Activities.Statements.Delay>，此操作在 <xref:System.Activities.Statements.TryCatch> 分支之前完成。</span><span class="sxs-lookup"><span data-stu-id="811dc-108">The second scenario demonstrates executing a <xref:System.Activities.Statements.TryCatch> in parallel with a <xref:System.Activities.Statements.Delay>, which finishes before the <xref:System.Activities.Statements.TryCatch> branch.</span></span> <span data-ttu-id="811dc-109">在完成第一个分支之后，完成条件将设置为 `true`，从而导致取消另一个分支。</span><span class="sxs-lookup"><span data-stu-id="811dc-109">The completion condition is set to `true` once the first branch finishes, causing the other branch to be canceled.</span></span>  
  
```  
Parallel   
{  
    Branch1   
    {  
        // Small Delay that times out (timeout1) before branch2.  
    }  
    Branch2   
    {  
        CA   
        {  
            CA1   
            {  
            }  
            CA2   
            {  
            }  
            CA3   
            {  
            }  
            If (timeout1)    
            {  
                call Cancel CA  
            }  
        }  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="811dc-110">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="811dc-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="811dc-111">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 CompensationCancellation.sln。</span><span class="sxs-lookup"><span data-stu-id="811dc-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open CompensationCancellation.sln.</span></span>  
  
2.  <span data-ttu-id="811dc-112">请按 CTRL+SHIFT+B 或从“生成”菜单中选择“生成解决方案”来生成示例。</span><span class="sxs-lookup"><span data-stu-id="811dc-112">Build the sample by pressing CTRL+SHIFT+B or select "Build Solution" from the Build menu..</span></span>  
  
3.  <span data-ttu-id="811dc-113">按 F5 或从“调试”菜单中选择“开始调试”来运行示例。</span><span class="sxs-lookup"><span data-stu-id="811dc-113">Run the sample by pressing F5 or select "Start Debugging" from the Debug menu.</span></span> <span data-ttu-id="811dc-114">或者，可以按 Ctrl+F5 或从“调试”菜单中选择“开始执行(不调试)”。</span><span class="sxs-lookup"><span data-stu-id="811dc-114">Alternately you may press Ctrl+F5 or select "Start without Debugging" from the Debug menu.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="811dc-115">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="811dc-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="811dc-116">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="811dc-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="811dc-117">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="811dc-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="811dc-118">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="811dc-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CompensationCancellation`