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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2746171c08cb5094b4ad39e753a20c595d48514e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="expressions"></a>表达式
此示例演示如何在工作流中使用基本表达式。 它包含一个工作流，此工作流计算虚构的公司中两名员工的基本工资统计信息。 Employee.cs 和 SalaryStats.cs 中定义了两个类，即 `Employee` 和 `SalaryStats`。 演示如何对复杂类型的变量属性执行简单算术和字符串运算的工作流中使用了这两个类。  
  
 XAML 和 C# 中都定义了工资计算工作流以演示两种创作样式。 XAML 版本包含在 SalaryCalculation.xaml 中，可以在工作流设计器中对其进行查看和编辑。 C# 版本驻留在 Program.cs 中。 XAML 中使用的表达式符合 Visual Basic 语法，并使用要执行的 <xref:Microsoft.VisualBasic.Activities.VisualBasicValue%601> 和 <xref:Microsoft.VisualBasic.Activities.VisualBasicReference%601> 表达式活动。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]请参阅 Visual Basic 表达式， [Visual Basic 表达式](http://go.microsoft.com/fwlink/?LinkId=165912)。 另一方面，C# 中的表达式作为 lambda 表达式写入，并使用 <xref:System.Activities.Expressions.LambdaValue%601> 和 <xref:System.Activities.Expressions.LambdaReference%601> 表达式活动。 将表达式作为 lambda 表达式写入可允许 C# 编译器提供语法突出显示和静态验证。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]lambda 表达式在 C# 中，请参阅[Lambda 表达式 （C# 编程指南）](http://go.microsoft.com/fwlink/?LinkId=182082)。 如果使用 Visual Basic 在代码中编写工作流，则使用 Visual Basic lambda 表达式。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]lambda 表达式在 Visual Basic 中，请参阅[Lambda 表达式 (Visual Basic)](http://go.microsoft.com/fwlink/?LinkId=152437)。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]有关创作工作流使用代码，请参阅[创作工作流、 活动和表达式使用命令性代码](../../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)。  
  
#### <a name="to-run-the-sample"></a>运行示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 Expressions.sln 解决方案。  
  
2.  按 CTRL + SHIFT + B 生成解决方案，或选择**生成解决方案**从**生成**菜单。  
  
    > [!NOTE]
    >  若要在 Visual Studio 设计器中打开 SalaryCalculation.xaml，您必须先编译项目以确保 `Employee` 和 `SalaryStats` 类对该设计器可用。  
  
3.  成功生成之后，按 F5，或选择**启动调试**从**调试**菜单。 或者，你可以按 Ctrl + F5，或选择**启动但不调试**从**调试**菜单运行而不调试。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Expressions`