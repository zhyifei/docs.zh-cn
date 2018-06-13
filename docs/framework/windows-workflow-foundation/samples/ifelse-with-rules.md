---
title: 带规则的 IfElse
ms.date: 03/30/2017
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
ms.openlocfilehash: 179ec29f957894433fb527a14048460f5ff6ee5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515116"
---
# <a name="ifelse-with-rules"></a><span data-ttu-id="c36e5-102">带规则的 IfElse</span><span class="sxs-lookup"><span data-stu-id="c36e5-102">IfElse With Rules</span></span>
<span data-ttu-id="c36e5-103">此示例演示如何将规则条件用于 <xref:System.Workflow.Activities.IfElseActivity> 活动。</span><span class="sxs-lookup"><span data-stu-id="c36e5-103">This sample shows the use of a rule condition with an <xref:System.Workflow.Activities.IfElseActivity> activity.</span></span>  
  
 <span data-ttu-id="c36e5-104">示例从宿主中传入一个 `OrderValue` 参数。</span><span class="sxs-lookup"><span data-stu-id="c36e5-104">The sample passes in an `OrderValue` parameter from the host.</span></span> <span data-ttu-id="c36e5-105">该参数的值用在 <xref:System.Workflow.Activities.IfElseActivity> 活动第一个分支上的规则条件中。</span><span class="sxs-lookup"><span data-stu-id="c36e5-105">The value of the parameter is used in a rule condition on the first branch of the <xref:System.Workflow.Activities.IfElseActivity> activity.</span></span> <span data-ttu-id="c36e5-106">如果值小于 10000，执行第一个分支，和<xref:System.Workflow.Activities.CodeActivity>中第一个分支的活动将打印**获取管理程序批准**到控制台。</span><span class="sxs-lookup"><span data-stu-id="c36e5-106">If the value is less than 10,000, the first branch executes, and the <xref:System.Workflow.Activities.CodeActivity> activity in the first branch prints **Get Manager Approval** to the console.</span></span> <span data-ttu-id="c36e5-107">如果值大于 10000，<xref:System.Workflow.Activities.CodeActivity>第二个分支中的活动执行，并输出**获取 VP 批准**。</span><span class="sxs-lookup"><span data-stu-id="c36e5-107">If the value is greater than 10,000, the <xref:System.Workflow.Activities.CodeActivity> activity in the second branch executes and prints **Get VP Approval**.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="c36e5-108">生成示例</span><span class="sxs-lookup"><span data-stu-id="c36e5-108">To build the sample</span></span>  
  
1.  <span data-ttu-id="c36e5-109">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开解决方案。</span><span class="sxs-lookup"><span data-stu-id="c36e5-109">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="c36e5-110">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="c36e5-110">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="c36e5-111">按 Ctrl+F5 运行解决方案而不进行调试。</span><span class="sxs-lookup"><span data-stu-id="c36e5-111">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="c36e5-112">运行示例</span><span class="sxs-lookup"><span data-stu-id="c36e5-112">To run the sample</span></span>  
  
-   <span data-ttu-id="c36e5-113">在 SDK 命令提示窗口中，运行 IfElseWithRules\bin\debug 文件夹（对于该示例的 Visual Basic 版本为 IfElseWithRules\bin 文件夹）中的 .exe 文件，该文件夹位于该示例的主文件夹下。</span><span class="sxs-lookup"><span data-stu-id="c36e5-113">In the SDK Command Prompt window, run the .exe file in the IfElseWithRules\bin\debug folder (or the IfElseWithRules\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c36e5-114">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="c36e5-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c36e5-115">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="c36e5-115">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c36e5-116">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="c36e5-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c36e5-117">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="c36e5-117">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## <a name="see-also"></a><span data-ttu-id="c36e5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c36e5-118">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules>  
 <xref:System.Workflow.Activities.IfElseActivity>  
 <xref:System.Workflow.Activities.CodeActivity>  
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>
