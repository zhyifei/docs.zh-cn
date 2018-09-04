---
title: 基本验证
ms.date: 03/30/2017
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
ms.openlocfilehash: 74d99e2d426e9ea5701fad80418fdf019112cc9e
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43558435"
---
# <a name="basic-validation"></a>基本验证
此示例包含 `CreateProduct` 活动，该活动验证它的 `Cost` 参数是否小于或等于它的 `Price` 参数。  
  
## <a name="sample-details"></a>示例详细信息  
 有两个使用验证的作者：活动作者（创建活动的验证逻辑）和工作流作者（对特定工作流调用验证服务）。 在此方案中，活动作者想要强制其活动的每个实例的成本都必须小于或等于价格。  
  
 活动作者（活动内部）必须：  
  
-   创建一个约束 (`PriceGreaterThanCost`)。 这是存放全部验证逻辑的位置。  
  
-   重写 `System.Activities.CodeActivity.OnGetConstraints()` 并将约束 (`PriceGreaterThanCost`) 添加到约束集 <xref:System.Collections.IList> 中。  
  
 工作流作者（主程序）必须：  
  
-   使用要验证的活动实例来创建一个工作流 (`CreateProduct`)。  
  
-   调用 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>，它将返回<xref:System.Activities.Validation.ValidationResults> 的 <xref:System.Activities.Validation.ValidationError> 集合。  
  
-   （可选）输出 <xref:System.Activities.Validation.ValidationError> 对象。  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中打开 BasicValidation.sln 示例解决方案。  
  
2.  生成和运行解决方案。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`