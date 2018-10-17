---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: edc154fcce0058455f1376a2a45807c92f7f2457
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49373686"
---
# <a name="servicethrottlingbehavior"></a>ServiceThrottlingBehavior
ServiceThrottlingBehavior  
  
## <a name="syntax"></a>语法  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a>方法  
 ServiceThrottlingBehavior 类未定义任何方法。  
  
## <a name="properties"></a>属性  
 ServiceThrottlingBehavior 类有以下属性：  
  
### <a name="maxconcurrentcalls"></a>MaxConcurrentCalls  
 数据类型：sint32  
  
 访问类型：只读  
  
 ServiceHost 中所有调度程序对象正在积极处理的消息的最大数量。  
  
### <a name="maxconcurrentinstances"></a>MaxConcurrentInstances  
 数据类型：sint32  
  
 访问类型：只读  
  
 一次可执行的服务对象的最大数量。  
  
### <a name="maxconcurrentsessions"></a>MaxConcurrentSessions  
 数据类型：sint32  
  
 访问类型：只读  
  
 主机一次可接受的最大会话数。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
