---
title: ActivityTransfer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c1caf0ae27efce858328e5db88434253be61d50
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="activitytransfer"></a>ActivityTransfer
活动传输事件  
  
## <a name="syntax"></a>语法  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a>方法  
 ActivityTransfer 类不定义任何方法。  
  
## <a name="properties"></a>属性  
 ActivityTransfer 类具有以下属性：  
  
### <a name="activityid"></a>ActivityID  
  
-   数据类型：object  
    访问类型：只读  
  
-   活动 ID  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
-   数据类型：object  
    访问类型：只读  
  
-   相关活动 ID  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义。|
