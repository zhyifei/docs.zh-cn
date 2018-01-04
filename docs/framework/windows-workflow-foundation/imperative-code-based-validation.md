---
title: "基于命令性代码的验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae12537c-455e-42b1-82f4-cea4c46c023e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 79e50c9cc756915ffc1a2f376d6b46469c85dbf5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imperative-code-based-validation"></a>基于命令性代码的验证
基于命令性代码的验证为活动提供用于自身验证的简单方法，并且该方法可用于从 <xref:System.Activities.CodeActivity>、<xref:System.Activities.AsyncCodeActivity> 和 <xref:System.Activities.NativeActivity> 派生的活动。 会向活动中添加确定所有验证错误或警告的验证代码。  
  
## <a name="using-code-based-validation"></a>使用基于代码的验证  
 从 <xref:System.Activities.CodeActivity>、<xref:System.Activities.AsyncCodeActivity> 和 <xref:System.Activities.NativeActivity> 派生的活动支持基于代码的验证。 可以将验证代码放置在 <xref:System.Activities.CodeActivity.CacheMetadata%2A> 重写中，并且可以将验证错误或警告添加到元数据参数中。 在下面的示例，摘自[基本验证](../../../docs/framework/windows-workflow-foundation/samples/basic-validation.md)示例，如果`Cost`大于`Price`，验证错误添加到元数据。  
  
> [!NOTE]
>  请注意，`Cost` 和 `Price` 不是针对活动的参数，而是在设计时设置的属性。 这就是为什么可以在 <xref:System.Activities.CodeActivity.CacheMetadata%2A> 重写中验证其值的原因。 流过某一参数的数据值不能在设计时验证，因为在运行时之前数据不流动，但可以对活动参数进行验证，以便确保通过使用 `RequiredArgument` 特性和重载组对它们进行限定。 此示例代码查看 `RequiredArgument` 参数的 `Description` 特性，如果未绑定，则会生成验证错误。   中介绍了所需的参数[所需的参数和重载组](../../../docs/framework/windows-workflow-foundation/required-arguments-and-overload-groups.md)。  
  
```csharp  
public sealed class CreateProduct : CodeActivity  
{  
    public double Price { get; set; }  
    public double Cost { get; set; }  
  
    // [RequiredArgument] attribute will generate a validation error   
    // if the Description argument is not set.  
    [RequiredArgument]  
    public InArgument<string> Description { get; set; }  
  
    protected override void CacheMetadata(CodeActivityMetadata metadata)  
    {  
        base.CacheMetadata(metadata);  
        // Determine when the activity has been configured in an invalid way.  
        if (this.Cost > this.Price)  
        {  
            // Add a validation error with a custom message.  
            metadata.AddValidationError("The Cost must be less than or equal to the Price.");  
        }  
    }  
  
    protected override void Execute(CodeActivityContext context)  
    {  
        // Not needed for the sample.  
    }  
}  
```  
  
 默认情况下，调用 <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> 时会向元数据中添加一个验证错误。 若要添加验证警告，请使用接受 <xref:System.Activities.CodeActivityMetadata.AddValidationError%2A> 的 <xref:System.Activities.Validation.ValidationError> 重载，并通过设置 <xref:System.Activities.Validation.ValidationError> 属性来指定 <xref:System.Activities.Validation.ValidationError.IsWarning%2A> 表示一个警告。  
  
 当在工作流设计器中修改工作流，并且工作流设计器中显示任何验证错误或警告时，将执行验证。 此外，当调用工作流时，如果发生任何验证错误，默认验证逻辑将引发 <xref:System.Activities.InvalidWorkflowException>，此时，也将在运行时执行验证。 [!INCLUDE[crabout](../../../includes/crabout-md.md)]调用验证和访问任何验证警告或错误，请参阅[调用活动验证](../../../docs/framework/windows-workflow-foundation/invoking-activity-validation.md)。  
  
 由 <xref:System.Activities.CodeActivity.CacheMetadata%2A> 引发的任何异常不会视为验证错误。 这些异常将从对 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> 的调用中转义，并且必须由调用方进行处理。  
  
 基于代码的验证对于验证包含代码的活动非常有用，但它看不到工作流中的其他活动。 声明性约束验证提供了验证活动和工作流中的其他活动之间的关系的功能中, 介绍了[声明性约束](../../../docs/framework/windows-workflow-foundation/declarative-constraints.md)主题。
