---
title: 1031 - CompleteFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a87ecb0a50437d83dd3c80d213553c8ac2143968
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="1031---completefaultworkitem"></a>1031 - CompleteFaultWorkItem
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|1031|  
|关键字|WFRuntime|  
|级别|详细|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示 FaultWorkItem 已完成。  
  
## <a name="message"></a>消息  
 Activity“%1”、DisplayName“%2”、InstanceId“%3”的 FaultWorkItem 已经完成。 异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|FaultActivity|xs:string|错误活动的类型名称。|  
|FaultActivityDisplayName|xs:string|错误活动的显示名称。|  
|FaultActivityInstanceId|xs:string|错误活动的实例 ID。|  
|ExceptionActivity|xs:string|引发了异常的活动的类型名称。|  
|ExceptionActivityDisplayName|xs:string|引发了异常的活动的显示名称。|  
|ExceptionActivityInstanceId|xs:string|引发了异常的活动的实例 ID。|  
|例外|xs:string|异常的异常详细信息|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
