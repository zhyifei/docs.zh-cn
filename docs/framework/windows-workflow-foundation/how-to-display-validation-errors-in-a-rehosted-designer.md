---
title: "如何：在重新承载的设计器中显示验证错误"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9f76f1ad5282ecf10a3ce58db0f6e1bd8df1b4d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a>如何：在重新承载的设计器中显示验证错误
本主题说明如何在重新承载的 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 中检索和发布验证错误。 这为我们提供了一个用于确认重新承载的设计器中的工作流是否有效的过程。  
  
 此任务包含两个部分。 第一部分提供一个实现 <xref:System.Activities.Presentation.Validation.IValidationErrorService>。  在此接口上要实现一个关键方法 <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A>，该方法将一个包含有关错误的信息的 <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> 对象的列表传递给调试日志。  实现此接口之后，可通过将该实现的实例发布到编辑上下文来检索错误信息。  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a>实现 IValidationErrorService 接口  
  
1.  下面是一个将验证错误写入调试日志的简单实现的代码示例。  
  
    ```  
    using System.Activities.Presentation.Validation;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Linq;  
  
    namespace VariableFinderShell  
    {  
        class DebugValidationErrorService : IValidationErrorService  
        {  
            public void ShowValidationErrors(IList<ValidationErrorInfo> errors)  
            {  
                errors.ToList().ForEach(vei => Debug.WriteLine(string.Format("Error: {0} ", vei.Message)));  
            }  
        }  
    }  
    ```  
  
### <a name="publishing-to-the-editing-context"></a>发布到编辑上下文  
  
1.  下面是将此内容发布到编辑上下文的代码。  
  
    ```  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
