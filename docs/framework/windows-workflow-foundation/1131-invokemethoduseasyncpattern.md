---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 150973935d12455aa671043a619fbd6fd7e77425
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009950"
---
# <a name="1131---invokemethoduseasyncpattern"></a>1131 - InvokeMethodUseAsyncPattern
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|1131|  
|关键字|WFRuntime|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 在 CacheMetadata 步骤中，InvokeMethod 活动指示它在调用方法时使用异步模式。  
  
## <a name="message"></a>消息  
 InvokeMethod“%1”- 方法使用“%2”和“%3”的异步模式。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|InvokeMethod 活动的显示名称。|  
|BeginMethod|xs:string|begin 方法的名称。|  
|EndMethod|xs:string|end 方法的名称。|  
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
