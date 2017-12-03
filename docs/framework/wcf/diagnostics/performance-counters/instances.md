---
title: "实例数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c8cf3460-0ca1-4411-8262-e9ecaf7f0a31
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 87423c3de551cb9fbf8c5a7756e2f0f999129a3b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="instances"></a>实例数
计数器名称：Instances（实例数）。  
  
## <a name="description"></a>描述  
 服务当前包含的实例上下文的数量。  
  
 在大部分时间里，实例上下文的数量都等于实例数。 但是，下列方案例外。  
  
-   服务方法显式调用 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> 方法。  
  
-   一个 <xref:System.ServiceModel.ReleaseInstanceMode> 被应用于一个 <xref:System.ServiceModel.OperationBehaviorAttribute> 实例。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
