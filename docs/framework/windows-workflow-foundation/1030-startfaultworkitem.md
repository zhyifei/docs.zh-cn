---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 3848d644e77041a62a52eb2eae5eeef286dfe334
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924314"
---
# <a name="1030---startfaultworkitem"></a>1030 - StartFaultWorkItem
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|1030|  
|关键字|WFRuntime|  
|级别|详细|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示 FaultWorkItem 正在开始执行。  
  
## <a name="message"></a>消息  
 开始为 Activity"%1"、 DisplayName FaultWorkItem 执行:"%2"、 InstanceId:"%3"。  异常是从 Activity“%4”、DisplayName“%5”、InstanceId“%6”传播的。  
  
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
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
