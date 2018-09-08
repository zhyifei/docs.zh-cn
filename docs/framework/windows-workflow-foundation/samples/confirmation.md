---
title: 确认
ms.date: 03/30/2017
ms.assetid: 8637aeaf-ac9e-49b8-93f4-da15dee45277
ms.openlocfilehash: caa712aa52da01ce44335a361fd6c9f5215316bf
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44132050"
---
# <a name="confirmation"></a>确认
此示例演示针对 <xref:System.Activities.Statements.CompensableActivity> 的使用和确认的四种常见方案。 此示例运行四个工作流以显示确认。 此示例具有声明性版本和命令性版本。  
  
## <a name="confirm-a-compensable-activity"></a>确认可补偿的活动  
 第一个工作流演示如何确认可补偿的活动，它由一个包含两个 <xref:System.Activities.Statements.CompensableActivity> 实例的序列组成。 完成第二个 <xref:System.Activities.Statements.CompensableActivity> 之后，确认活动将确认第一个活动。 成功完成该工作流后，将按照默认顺序自动确认所有尚未确认和补偿的 <xref:System.Activities.Statements.CompensableActivity> 实例。 若不进行确认，则会首先确认第二个 <xref:System.Activities.Statements.CompensableActivity>。  
  
## <a name="explicit-compensation"></a>显式补偿  
 第二种方案演示显示补偿 <xref:System.Activities.Statements.CompensableActivity> 对默认确认的影响。 此工作流由一个包含两个 <xref:System.Activities.Statements.CompensableActivity> 活动的序列组成，在第二个活动完成后，将显式补偿第一个活动。 因此，在完成该工作流时，仅确认第二个 <xref:System.Activities.Statements.CompensableActivity>。  
  
## <a name="controlling-the-order-of-confirmation-for-nested-compensableactivity-activities"></a>控制嵌套的 CompensableActivity 活动的确认顺序  
 第三种方案演示如何控制嵌套的 <xref:System.Activities.Statements.CompensableActivity> 的确认顺序。 此方案包含一个作为工作流的根的 <xref:System.Activities.Statements.CompensableActivity>。 根 <xref:System.Activities.Statements.CompensableActivity> 的主体是一个包含三个 <xref:System.Activities.Statements.CompensableActivity> 的序列。 根 <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> 的 <xref:System.Activities.Statements.CompensableActivity> 是一个序列，此序列指定先确认第一个活动，然后再确认第二个嵌套的 <xref:System.Activities.Statements.CompensableActivity>。 该工作流在完成时确认根 <xref:System.Activities.Statements.CompensableActivity>，然后依次确认第一个、第二个和第三个嵌套的 <xref:System.Activities.Statements.CompensableActivity>。 因此，默认的确认顺序实际上是相反的。 由于 <xref:System.Activities.Statements.CompensableActivity> 未将第三个 <xref:System.Activities.Statements.CompensableActivity> 显式确认为根 <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> 的一部分，因此将按照默认顺序对其进行确认。 但由于它是唯一未确认的 <xref:System.Activities.Statements.CompensableActivity>，这表示将对其进行确认。  
  
## <a name="scoping-of-variables"></a>变量的范围  
 第四种方案演示如何在执行 <xref:System.Activities.Statements.CompensableActivity>、 <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A> 或 <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> 处理程序时使为 <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> 或其某个父级定义的变量生存期仍处于范围内，即使活动已完成或工作流已完成。 此工作流由一个包含两个 <xref:System.Activities.Statements.CompensableActivity> 的序列组成。 在第一个活动的正文中，将变量 `mySum` 设置为 5 与 10 以及输出结果的和值。 在第二个 <xref:System.Activities.Statements.CompensableActivity> 的正文中，将和值设置为现有和值与 7 以及输出结果的和值。 为第一个 <xref:System.Activities.Statements.CompensableActivity> 定义一个自定义确认处理程序，此处理程序将输出和值、减去 7，然后重新输出和值。 通过检查输出的和值，可以很清楚地知道，该变量不仅位于两个 <xref:System.Activities.Statements.CompensableActivity> 的正文范围内，而且还位于 <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> 的正文范围内。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中加载解决方案。  
  
2.  运行 ConfirmationSample.exe 应用程序。  
  
3.  观察以下输出：  
  
 **显式确认： Start workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1： 确认 HandlerEnd 的 workflowCompensableActivity2： 确认 HandlerExplicit 补偿： StartworkflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: workflowCompensableActivity2 的补偿 HandlerEnd： 确认 HandlerCustom 确认处理程序： Start workflowCompensableActivity1 的：BodyCompensableActivity2: BodyCompensableActivity3: BodyEnd workflowCompensableActivity1： 确认 HandlerCompensableActivity2： 确认 HandlerCompensableActivity3： 确认 HandlerVariable 中确认处理程序的访问权限：开始 workflowCompensableActivity1: BodyCompensableActivity1： 之和： 15CompensableActivity2: BodyCompensableActivity2： 到 sumCompensableActivity2 添加 7： 现在之和： 22End workflowCompensableActivity2： 确认HandlerCompensableActivity1： 确认 HandlerCompensableActivity2： 之和： 22CompensableActivity2： 减去 12 后之现在： 10Press ENTER 退出。**  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\Confirmation`