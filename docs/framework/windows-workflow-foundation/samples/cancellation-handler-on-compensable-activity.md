---
title: 可补偿活动上的取消处理程序
ms.date: 03/30/2017
ms.assetid: afd98bee-eccf-47e9-99c9-27cea84ce5ce
ms.openlocfilehash: ce4d67b26a2b4c6a9b507715b48e75e328c5b100
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="cancellation-handler-on-compensable-activity"></a><span data-ttu-id="0b967-102">可补偿活动上的取消处理程序</span><span class="sxs-lookup"><span data-stu-id="0b967-102">Cancellation Handler on Compensable Activity</span></span>
<span data-ttu-id="0b967-103">此示例演示如何对 <xref:System.Activities.Statements.CompensableActivity> 使用取消处理程序。</span><span class="sxs-lookup"><span data-stu-id="0b967-103">This sample demonstrates the use of a cancellation handler on a <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 <span data-ttu-id="0b967-104">此示例包含两个演示如何使用 <xref:System.Activities.Statements.CompensableActivity> 取消的方案。第一个方案包含一个根可补偿活动，而根可补偿活动又包含三个子可补偿活动。</span><span class="sxs-lookup"><span data-stu-id="0b967-104">This sample contains two scenarios that demonstrate the use of <xref:System.Activities.Statements.CompensableActivity> cancellation.The first scenario contains a root compensable activity that contains three child compensable activities.</span></span> <span data-ttu-id="0b967-105">两个子活动成功地运行完它们的活动主体。</span><span class="sxs-lookup"><span data-stu-id="0b967-105">Two child activities finish running their activity bodies successfully.</span></span> <span data-ttu-id="0b967-106">当运行第三个子活动主体时，它会遇到一个异常，该异常可通过取消第三个活动进程来处理，此后，将会触发根活动的取消。</span><span class="sxs-lookup"><span data-stu-id="0b967-106">When the third child activity body runs, it encounters an exception that is handled by canceling the third activity processing, after which the cancellation of the root activity is triggered.</span></span> <span data-ttu-id="0b967-107">此示例中根活动的逻辑是补偿较早完成的另外两个子活动。</span><span class="sxs-lookup"><span data-stu-id="0b967-107">The logic in the root activity in this example is to compensate the other two child activities that completed earlier.</span></span>  
  
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
  
 <span data-ttu-id="0b967-108">第二个方案演示如何与 <xref:System.Activities.Statements.TryCatch> 一起并行执行 <xref:System.Activities.Statements.Delay>，此操作在 <xref:System.Activities.Statements.TryCatch> 分支之前完成。</span><span class="sxs-lookup"><span data-stu-id="0b967-108">The second scenario demonstrates executing a <xref:System.Activities.Statements.TryCatch> in parallel with a <xref:System.Activities.Statements.Delay>, which finishes before the <xref:System.Activities.Statements.TryCatch> branch.</span></span> <span data-ttu-id="0b967-109">在完成第一个分支之后，完成条件将设置为 `true`，从而导致取消另一个分支。</span><span class="sxs-lookup"><span data-stu-id="0b967-109">The completion condition is set to `true` once the first branch finishes, causing the other branch to be canceled.</span></span>  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0b967-110">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="0b967-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0b967-111">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 CompensationCancellation.sln。</span><span class="sxs-lookup"><span data-stu-id="0b967-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open CompensationCancellation.sln.</span></span>  
  
2.  <span data-ttu-id="0b967-112">请按 CTRL+SHIFT+B 或从“生成”菜单中选择“生成解决方案”来生成示例。</span><span class="sxs-lookup"><span data-stu-id="0b967-112">Build the sample by pressing CTRL+SHIFT+B or select "Build Solution" from the Build menu..</span></span>  
  
3.  <span data-ttu-id="0b967-113">按 F5 或从“调试”菜单中选择“开始调试”来运行示例。</span><span class="sxs-lookup"><span data-stu-id="0b967-113">Run the sample by pressing F5 or select "Start Debugging" from the Debug menu.</span></span> <span data-ttu-id="0b967-114">或者，可以按 Ctrl+F5 或从“调试”菜单中选择“开始执行(不调试)”。</span><span class="sxs-lookup"><span data-stu-id="0b967-114">Alternately you may press Ctrl+F5 or select "Start without Debugging" from the Debug menu.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0b967-115">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="0b967-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0b967-116">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="0b967-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0b967-117">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="0b967-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0b967-118">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="0b967-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CompensationCancellation`