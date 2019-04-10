---
title: 在自定义设计器中使用 ExpressionTextBox
ms.date: 03/30/2017
ms.assetid: f82e73e7-a256-4a4d-82b7-c0d62f4ab5e7
ms.openlocfilehash: 7c1ba262046a665b8d63157fe3cdb4b1a41c37bf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229376"
---
# <a name="using-the-expressiontextbox-in-a-custom-activity-designer"></a><span data-ttu-id="accc2-102">在自定义设计器中使用 ExpressionTextBox</span><span class="sxs-lookup"><span data-stu-id="accc2-102">Using the ExpressionTextBox in a Custom Activity Designer</span></span>
<span data-ttu-id="accc2-103">此示例演示如何在自定义活动设计器中使用 <xref:System.Activities.Presentation.View.ExpressionTextBox>。</span><span class="sxs-lookup"><span data-stu-id="accc2-103">This sample shows how to use the <xref:System.Activities.Presentation.View.ExpressionTextBox> in a custom activity designer.</span></span> <span data-ttu-id="accc2-104">自定义活动 `MultiAssign` 将两个字符串值分配给两个字符串变量。</span><span class="sxs-lookup"><span data-stu-id="accc2-104">The custom activity, `MultiAssign`, assigns two string values to two string variables.</span></span> <span data-ttu-id="accc2-105">某些 <xref:System.Activities.Presentation.View.ExpressionTextBox> 控件绑定到 <xref:System.Activities.InArgument>，而某些控件绑定到 <xref:System.Activities.OutArgument>。</span><span class="sxs-lookup"><span data-stu-id="accc2-105">Some <xref:System.Activities.Presentation.View.ExpressionTextBox> controls bind to <xref:System.Activities.InArgument>s and some bind to <xref:System.Activities.OutArgument>s.</span></span>

## <a name="sample-details"></a><span data-ttu-id="accc2-106">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="accc2-106">Sample details</span></span>
 <span data-ttu-id="accc2-107">`ArgumentToExpressionConverter` 是在将表达式绑定到参数时使用的类型转换器。</span><span class="sxs-lookup"><span data-stu-id="accc2-107">The `ArgumentToExpressionConverter` is the type converter used when binding expressions to arguments.</span></span> <span data-ttu-id="accc2-108">根据需要，必须将 `ConverterParameter` 设置为 `In` 或 `Out`。</span><span class="sxs-lookup"><span data-stu-id="accc2-108">The `ConverterParameter` must be set to `In` or `Out` as appropriate.</span></span> `InOut` <span data-ttu-id="accc2-109">不支持。</span><span class="sxs-lookup"><span data-stu-id="accc2-109">is not supported.</span></span>

 <span data-ttu-id="accc2-110">`UseLocationExpression`上使用特性`OutArgument`s，指定表达式应为左值 （"左侧的值"或"位置值"） 表达式。</span><span class="sxs-lookup"><span data-stu-id="accc2-110">The `UseLocationExpression` attribute is used on `OutArgument`s to specify that the expression should be an L-value ("left value" or "location value") expression.</span></span> <span data-ttu-id="accc2-111">在大多数情况下，左值表达式是有效的 Visual Basic 标识符，用于指示要返回的 `OutArgument` 是变量还是参数名称。</span><span class="sxs-lookup"><span data-stu-id="accc2-111">In most cases, an L-value expression is a valid Visual Basic identifier used to indicate that the `OutArgument` being returned is a variable or argument name.</span></span>

 <span data-ttu-id="accc2-112">在此示例中，将 `MaxLines` 特性设置为 1，未设置 `MinLines`。</span><span class="sxs-lookup"><span data-stu-id="accc2-112">The `MaxLines` attribute is set to one in this example and `MinLines` is not set.</span></span> <span data-ttu-id="accc2-113">这表示无论用户键入多少文本，<xref:System.Activities.Presentation.View.ExpressionTextBox> 都是大小固定的一行。</span><span class="sxs-lookup"><span data-stu-id="accc2-113">This indicates that the <xref:System.Activities.Presentation.View.ExpressionTextBox> is a fixed size of one line regardless of the amount of text typed by the user.</span></span> <span data-ttu-id="accc2-114">若要允许 <xref:System.Activities.Presentation.View.ExpressionTextBox> 增大以容纳用户输入，请将 `MaxLines` 设置为大于 `MinLines`。</span><span class="sxs-lookup"><span data-stu-id="accc2-114">To allow the <xref:System.Activities.Presentation.View.ExpressionTextBox> to grow to fit user input, set `MaxLines` greater than `MinLines`.</span></span>

 <span data-ttu-id="accc2-115">ExpressionTextBox 只能绑定到参数，不能绑定到 CLR 属性。</span><span class="sxs-lookup"><span data-stu-id="accc2-115">An ExpressionTextBox can only be bound to arguments, and cannot be bound to CLR properties.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="accc2-116">使用此示例</span><span class="sxs-lookup"><span data-stu-id="accc2-116">To use this sample</span></span>

1.  <span data-ttu-id="accc2-117">使用 Visual Studio 2010 打开 ExpressionTextBoxSample.sln 文件。</span><span class="sxs-lookup"><span data-stu-id="accc2-117">Using Visual Studio 2010, open the ExpressionTextBoxSample.sln file.</span></span>

2.  <span data-ttu-id="accc2-118">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="accc2-118">To build the solution, press CTRL+SHIFT+B.</span></span>

#### <a name="to-run-this-sample"></a><span data-ttu-id="accc2-119">运行此示例</span><span class="sxs-lookup"><span data-stu-id="accc2-119">To run this sample</span></span>

1.  <span data-ttu-id="accc2-120">向解决方案添加新工作流控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="accc2-120">Add a new Workflow Console Application to the solution.</span></span>

2.  <span data-ttu-id="accc2-121">添加对的引用**expressiontextboxsample**从新的工作流控制台应用程序项目的项目。</span><span class="sxs-lookup"><span data-stu-id="accc2-121">Add a reference to the **ExpressionTextBoxSample** project from the new Workflow Console Application project.</span></span>

3.  <span data-ttu-id="accc2-122">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="accc2-122">Build the solution.</span></span>

4.  <span data-ttu-id="accc2-123">拖动**MultiAssign**活动从工具箱拖放到工作流。</span><span class="sxs-lookup"><span data-stu-id="accc2-123">Drag the **MultiAssign** activity from the toolbox and drop it into the workflow.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="accc2-124">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="accc2-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="accc2-125">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="accc2-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="accc2-126">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="accc2-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="accc2-127">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="accc2-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\ExpressionTextBox`  
  
## <a name="see-also"></a><span data-ttu-id="accc2-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="accc2-128">See also</span></span>

- <xref:System.Activities.Presentation.View.ExpressionTextBox>
- [<span data-ttu-id="accc2-129">使用工作流设计器开发应用程序</span><span class="sxs-lookup"><span data-stu-id="accc2-129">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
