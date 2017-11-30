---
title: Expressions2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43a85905-77b5-4893-bb38-1cb9b293d69d
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 681b96d24288cc1a86c9c4525e31ed67f1a18331
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="expressions"></a><span data-ttu-id="39a66-102">表达式</span><span class="sxs-lookup"><span data-stu-id="39a66-102">Expressions</span></span>
<span data-ttu-id="39a66-103">此示例演示如何在工作流中使用基本表达式。</span><span class="sxs-lookup"><span data-stu-id="39a66-103">This sample demonstrates how to use basic expressions in a workflow.</span></span> <span data-ttu-id="39a66-104">它包含一个工作流，此工作流计算虚构的公司中两名员工的基本工资统计信息。</span><span class="sxs-lookup"><span data-stu-id="39a66-104">It consists of a workflow that calculates basic salary statistics for two employees of a fictitious company.</span></span> <span data-ttu-id="39a66-105">Employee.cs 和 SalaryStats.cs 中定义了两个类，即 `Employee` 和 `SalaryStats`。</span><span class="sxs-lookup"><span data-stu-id="39a66-105">Two classes, `Employee` and `SalaryStats`, are defined in Employee.cs and SalaryStats.cs.</span></span> <span data-ttu-id="39a66-106">演示如何对复杂类型的变量属性执行简单算术和字符串运算的工作流中使用了这两个类。</span><span class="sxs-lookup"><span data-stu-id="39a66-106">These classes are used in a workflow that shows how to perform simple arithmetic and string operations on properties of variables of complex types.</span></span>  
  
 <span data-ttu-id="39a66-107">XAML 和 C# 中都定义了工资计算工作流以演示两种创作样式。</span><span class="sxs-lookup"><span data-stu-id="39a66-107">The salary calculation workflow is defined both in XAML and in C# to demonstrate the two authoring styles.</span></span> <span data-ttu-id="39a66-108">XAML 版本包含在 SalaryCalculation.xaml 中，可以在工作流设计器中对其进行查看和编辑。</span><span class="sxs-lookup"><span data-stu-id="39a66-108">The XAML version is contained in SalaryCalculation.xaml and can be viewed and edited in the workflow designer.</span></span> <span data-ttu-id="39a66-109">C# 版本驻留在 Program.cs 中。</span><span class="sxs-lookup"><span data-stu-id="39a66-109">The C# version resides in Program.cs.</span></span> <span data-ttu-id="39a66-110">XAML 中使用的表达式符合 Visual Basic 语法，并使用要执行的 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> 和 <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> 表达式活动。</span><span class="sxs-lookup"><span data-stu-id="39a66-110">The expressions used in XAML conform to Visual Basic syntax, and use <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> and <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> expression activities to execute.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="39a66-111">请参阅 Visual Basic 表达式， [Visual Basic 表达式](http://go.microsoft.com/fwlink/?LinkId=165912)。</span><span class="sxs-lookup"><span data-stu-id="39a66-111"> Visual Basic expressions see, [Visual Basic Expressions](http://go.microsoft.com/fwlink/?LinkId=165912).</span></span> <span data-ttu-id="39a66-112">另一方面，C# 中的表达式作为 lambda 表达式写入，并使用 <xref:System.Activities.Expressions.LambdaValue%601> 和 <xref:System.Activities.Expressions.LambdaReference%601> 表达式活动。</span><span class="sxs-lookup"><span data-stu-id="39a66-112">On the other hand, expressions in C# are written as lambda expressions and use <xref:System.Activities.Expressions.LambdaValue%601> and <xref:System.Activities.Expressions.LambdaReference%601> expression activities.</span></span> <span data-ttu-id="39a66-113">将表达式作为 lambda 表达式写入可允许 C# 编译器提供语法突出显示和静态验证。</span><span class="sxs-lookup"><span data-stu-id="39a66-113">Writing expressions as lambda expressions allows the C# compiler to provide syntax highlighting and static verification.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="39a66-114">lambda 表达式在 C# 中，请参阅[Lambda 表达式 （C# 编程指南）](http://go.microsoft.com/fwlink/?LinkId=182082)。</span><span class="sxs-lookup"><span data-stu-id="39a66-114"> lambda expressions in C#, see [Lambda Expressions (C# Programming Guide)](http://go.microsoft.com/fwlink/?LinkId=182082).</span></span> <span data-ttu-id="39a66-115">如果使用 Visual Basic 在代码中编写工作流，则使用 Visual Basic lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="39a66-115">If a workflow is authored in code using Visual Basic, then Visual Basic lambda expressions are used.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="39a66-116">lambda 表达式在 Visual Basic 中，请参阅[Lambda 表达式 (Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=152437)。</span><span class="sxs-lookup"><span data-stu-id="39a66-116"> lambda expressions in Visual Basic, see [Lambda Expressions (Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=152437).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="39a66-117">有关创作工作流使用代码，请参阅[创作工作流、 活动和表达式使用命令性代码](../../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)。</span><span class="sxs-lookup"><span data-stu-id="39a66-117"> about authoring workflows using code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](../../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="39a66-118">运行示例</span><span class="sxs-lookup"><span data-stu-id="39a66-118">To run the sample</span></span>  
  
1.  <span data-ttu-id="39a66-119">在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 Expressions.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="39a66-119">Open the Expressions.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="39a66-120">按 CTRL + SHIFT + B 生成解决方案，或选择**生成解决方案**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="39a66-120">Press CTRL+SHIFT+B to build the solution or select **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="39a66-121">若要在 Visual Studio 设计器中打开 SalaryCalculation.xaml，您必须先编译项目以确保 `Employee` 和 `SalaryStats` 类对该设计器可用。</span><span class="sxs-lookup"><span data-stu-id="39a66-121">To open SalaryCalculation.xaml in the Visual Studio designer, you must first compile your project to ensure that `Employee` and `SalaryStats` classes are available to the designer.</span></span>  
  
3.  <span data-ttu-id="39a66-122">成功生成之后，按 F5，或选择**启动调试**从**调试**菜单。</span><span class="sxs-lookup"><span data-stu-id="39a66-122">Once the build has succeeded, press F5 or select **Start Debugging** from the **Debug** menu.</span></span> <span data-ttu-id="39a66-123">或者，你可以按 Ctrl + F5，或选择**启动但不调试**从**调试**菜单运行而不调试。</span><span class="sxs-lookup"><span data-stu-id="39a66-123">Alternatively you can press Ctrl+F5 or select **Start Without Debugging** from the **Debug** menu to run without debugging.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="39a66-124">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="39a66-124">The samples may already be installed on your computer.</span></span> <span data-ttu-id="39a66-125">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="39a66-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="39a66-126">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="39a66-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="39a66-127">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="39a66-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Expressions`