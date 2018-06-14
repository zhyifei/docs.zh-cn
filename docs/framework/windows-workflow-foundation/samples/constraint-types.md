---
title: 约束类型
ms.date: 03/30/2017
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
ms.openlocfilehash: 53e5975017c3a27ede8ad07cd93f78f71df2d3e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517503"
---
# <a name="constraint-types"></a>约束类型
本实例演示将约束应用于工作流的两种不同方法：一种方法是从活动内部应用（生成），另一种方法是从活动外部应用（策略）。 在此方案中，某个活动作者（来自于第三方软件公司）想要验证两个参数之间的关系。 在此例中，成本应小于或等于价格。 这是一个常规的验证生成约束。  
  
 然后，一个店主想要为此常规活动中添加一些验证。 对于他而言，他想要让大多数产品的价格为 9.99 美元或者更少。 因此，他在 `CreateProduct` 活动之上使用一个策略约束。  
  
 在此示例中：  
  
 活动作者（生成）必须：  
  
-   创建一个约束 (`PriceGreaterThanCost`)。 这是存放全部验证逻辑的位置。  
  
-   重写 `System.Activities.CodeActivity.OnGetConstraints()` 并将约束 (`PriceGreaterThanCost`) 添加到约束集 <xref:System.Collections.IList> 中。  
  
 工作流作者（策略）必须：  
  
-   使用要验证的活动实例来创建一个工作流 (`CreateProduct`)。  
  
-   创建一个约束 (`MaxPrice`)。  
  
-   创建一个 <xref:System.Activities.Validation.ValidationSettings> 实例 (`validationSettings`)，并将约束 (`MaxPrice`) 添加到集合 `AdditionalConstraints` 中。 在此处，工作流作者可以将策略约束添加到任何活动，例如一个序列或并行活动。  
  
-   调用 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>，它将返回 <xref:System.Activities.Validation.ValidationResults> 对象的 <xref:System.Activities.Validation.ValidationError> 的集合。  
  
-   （可选）输出 <xref:System.Activities.Validation.ValidationError> 对象。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 ConstraintTypes.sln 示例解决方案。  
  
2.  生成和运行解决方案。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`