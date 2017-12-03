---
title: "WF 中的错误处理活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24b68bd3-cef5-4413-ab82-2e2625f209aa
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a8b7ed6837e9ee88e85324ed5d7a2b9ff3e419a9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="error-handling-activities-in-wf"></a>WF 中的错误处理活动
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]提供多个系统提供的活动，用于实现错误处理和恢复。 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][异常](../../../docs/framework/windows-workflow-foundation/exceptions.md)。  
  
## <a name="error-handling-activities"></a>错误处理活动  
  
|||  
|-|-|  
|<xref:System.Activities.Statements.Rethrow>|重新引发从 `TryCatch` 活动中引发的最后一个异常。|  
|<xref:System.Activities.Statements.Throw>|引发异常。|  
|<xref:System.Activities.Statements.TryCatch>|实现异常处理。|
