---
title: 外部活动验证
ms.date: 03/30/2017
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
ms.openlocfilehash: 4805bec3deed0779b02687b11dd487e673802925
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43527802"
---
# <a name="external-activity-validation"></a><span data-ttu-id="ecf5e-102">外部活动验证</span><span class="sxs-lookup"><span data-stu-id="ecf5e-102">External Activity Validation</span></span>
<span data-ttu-id="ecf5e-103">此示例演示如何向不是由您创作的内置活动添加验证逻辑。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-103">This sample shows how to add validation logic to a built-in activity that you are not the author of.</span></span> <span data-ttu-id="ecf5e-104">验证逻辑包括强制工作流中存在的所有 <xref:System.Activities.Statements.If> 活动已设置其 <xref:System.Activities.Statements.If.Then%2A> 属性或其 <xref:System.Activities.Statements.If.Else%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-104">The validation logic consists of enforcing that all <xref:System.Activities.Statements.If> activities present in the workflow either have their <xref:System.Activities.Statements.If.Then%2A> property set or their <xref:System.Activities.Statements.If.Else%2A> property set.</span></span> <span data-ttu-id="ecf5e-105">此外，验证逻辑还包括检查工作流中存在的所有 <xref:System.Activities.Statements.Pick> 活动是否具有多个分支，如果不具有多个分支，则会生成一个警告。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-105">Also, the validation logic includes checking that all <xref:System.Activities.Statements.Pick> activities present in the workflow have more than one branch, and if that is not the case, a warning is generated.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="ecf5e-106">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="ecf5e-106">Sample details</span></span>  
 <span data-ttu-id="ecf5e-107">此示例使用要验证的每个活动（即 <xref:System.Activities.Statements.If> 活动和 <xref:System.Activities.Statements.Pick> 活动）的实例创建工作流。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-107">This sample creates a workflow with an instance of each activity to validate: the <xref:System.Activities.Statements.If> activity and the <xref:System.Activities.Statements.Pick> activity.</span></span> <span data-ttu-id="ecf5e-108">为每个验证行为创建一个 <xref:System.Activities.Validation.Constraint>。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-108">A <xref:System.Activities.Validation.Constraint> is created for each validation behavior.</span></span> <span data-ttu-id="ecf5e-109">此示例中创建的约束为 `ConstraintError_IfShouldHaveThenOrElse` 和 `ConstraintWarning_PickHasOneBranch`。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-109">The constraints created in this sample are `ConstraintError_IfShouldHaveThenOrElse` and `ConstraintWarning_PickHasOneBranch`.</span></span> <span data-ttu-id="ecf5e-110">紧接着，将这些约束添加到 `AdditionalConstraints` 实例的 <xref:System.Activities.Validation.ValidationSettings> 集合中。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-110">Next, these constraints are added to the `AdditionalConstraints` collection of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="ecf5e-111">最后，调用 `static` 的 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A><xref:System.Activities.Validation.ActivityValidationServices> 方法以验证工作流中的活动并将验证结果输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-111">Finally, the `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> method of <xref:System.Activities.Validation.ActivityValidationServices> is called to validate the activities in the workflow and the validation results are printed out to the console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecf5e-112">可以向任何活动添加策略约束。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-112">You can add policy constraints to any activity.</span></span> <span data-ttu-id="ecf5e-113">例如，可以向 <xref:System.Activities.Statements.Sequence> 或 <xref:System.Activities.Statements.Parallel> 活动添加策略约束。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-113">For example, you can add a policy constraint to a <xref:System.Activities.Statements.Sequence> or <xref:System.Activities.Statements.Parallel> activity.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ecf5e-114">使用此示例</span><span class="sxs-lookup"><span data-stu-id="ecf5e-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="ecf5e-115">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 ExternalActivityValidation.sln 文件。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ExternalActivityValidation.sln file.</span></span>  
  
2.  <span data-ttu-id="ecf5e-116">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ecf5e-117">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-117">To run the solution, press Ctrl+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ecf5e-118">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ecf5e-119">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="ecf5e-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ecf5e-120">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="ecf5e-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ecf5e-121">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="ecf5e-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`