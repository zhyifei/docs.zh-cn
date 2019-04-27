---
title: 1124 - InvokeMethodIsStatic
ms.date: 03/30/2017
ms.assetid: b9643641-fb52-4fa8-b354-4dd6617d68f6
ms.openlocfilehash: 49a9dec73392681fd4150c611f78399a1e15dd48
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924054"
---
# <a name="1124---invokemethodisstatic"></a>1124 - InvokeMethodIsStatic
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|1124|  
|关键字|WFRuntime|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 在 CacheMetadata 步骤中，InvokeMethod 活动指示要调用的方法是静态的。  
  
## <a name="message"></a>消息  
 InvokeMethod“%1”- 方法为静态。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|InvokeMethod 活动的显示名称。|  
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
