---
title: WSAT_TraceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d24f74d4086a5499d3bfd4ef6183d377528acc21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="wsattracerecord"></a>WSAT_TraceRecord
WSAT_TraceRecord  
  
## <a name="syntax"></a>语法  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a>方法  
 WSAT_TraceRecord 类未定义任何方法。  
  
## <a name="properties"></a>属性  
 WSAT_TraceRecord 类具有以下属性：  
  
### <a name="activityid"></a>ActivityID  
 数据类型：object  
访问类型：只读  
  
 跟踪记录的活动 ID。  
  
### <a name="eventid"></a>事件 ID  
 数据类型：sint32  
访问类型：只读  
  
 跟踪记录的事件 ID。  
  
### <a name="tracerecord"></a>TraceRecord  
 数据类型：String  
访问类型：只读  
  
 跟踪记录  
  
## <a name="requirements"></a>惠?  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|
