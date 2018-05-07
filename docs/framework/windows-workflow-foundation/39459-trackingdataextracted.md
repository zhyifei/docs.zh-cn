---
title: 39459 - TrackingDataExtracted
ms.date: 03/30/2017
ms.assetid: fcf7be96-8a7b-4ae1-bf38-b77ea9ebfb6b
ms.openlocfilehash: 04fefaa987e311b4a0bf7fdf6ada6100f1685b3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="39459---trackingdataextracted"></a>39459 - TrackingDataExtracted
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|39459|  
|关键字|WFRuntime|  
|级别|详细|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示已在活动中提取跟踪数据。  
  
## <a name="message"></a>消息  
 正在跟踪在活动 %2 中提取的数据 %1。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|数据|xs:string|提取的数据的名称。|  
|Activity|xs:string|活动的名称。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
