---
title: OverloadGroups
ms.date: 03/30/2017
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
ms.openlocfilehash: 0773e76d36b25ad5485cc8912c7012815412de9f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514131"
---
# <a name="overloadgroups"></a>OverloadGroups
此示例包含 `CreateLocation` 活动，它具有两个有趣的特征：  
  
1.  它具有一些必需的参数和一些可选的参数。  
  
2.  它允许用户选择提供两个不同参数集中的一个。  
  
 使用以下两项功能可以实现上述行为：  
  
-   `[isRequired]` 验证是否已为某个特定活动的属性赋值，如果没有，则它将引发异常。  
  
-   `[OverloadGroup]` 汇集了一组参数，以便活动用户可在两个参数集中选择使用哪一个。 用户不能使用同一实例中不同重载组中的参数。  
  
 在设置不同的工作流之后，调用 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>，它将返回<xref:System.Activities.Validation.ValidationResults> 的 <xref:System.Activities.Validation.Constraint> 集合。 将 <xref:System.Activities.Validation.Constraint> 对象输出到控制台。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  打开**OverloadGroups.sln**示例解决方案中的[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。  
  
2.  生成和运行解决方案。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
