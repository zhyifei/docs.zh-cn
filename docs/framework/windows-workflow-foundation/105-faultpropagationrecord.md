---
title: 105 - FaultPropagationRecord
ms.date: 03/30/2017
ms.assetid: 168473b1-b1e5-4e9f-8a2a-35bbdb2ef531
ms.openlocfilehash: c48f42a91ad9a15b49aad8c1ab684f2348954174
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924197"
---
# <a name="105---faultpropagationrecord"></a>105 - FaultPropagationRecord
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|105|  
|关键字|EndToEndMonitoring、Troubleshooting、HealthMonitoring、WFTracking|  
|级别|警告|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 当工作流实例中的某个活动发出 FaultPropagationRecord 时，ETW 跟踪参与者将发出此事件。  
  
## <a name="message"></a>消息  
 TrackRecord = FaultPropagationRecord, InstanceID=%1, RecordNumber=%2, EventTime=%3, FaultSourceActivityName=%4, FaultSourceActivityId=%5, FaultSourceActivityInstanceId=%6, FaultSourceActivityTypeName=%7, FaultHandlerActivityName=%8, FaultHandlerActivityId = %9, FaultHandlerActivityInstanceId =%10, FaultHandlerActivityTypeName=%11, Fault=%12, IsFaultSource=%13, Annotations=%14, ProfileName = %15  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|工作流的实例 ID|  
|RecordNumber|xs:long|发出的记录的序列号|  
|EventTime|xs:dateTime|发出该事件时的 UTC 时间|  
|FaultSourceActivityName|xs:string|发出错误的活动的名称|  
|FaultSourceActivityId|xs:string|发出错误的活动的 ID|  
|FaultSourceActivityInstanceId|xs:string|发出错误的活动的实例 ID|  
|FaultSourceActivityTypeName|xs:string|发出错误的活动的类型|  
|FaultHandlerActivityName|xs:string|错误处理程序活动的显示名称|  
|FaultHandlerActivityId|xs:string|错误处理程序活动的 ID|  
|FaultHandlerActivityInstanceId|xs:string|错误处理程序活动的实例 ID|  
|FaultHandlerActivityTypeName|xs:string|错误处理程序活动的类型|  
|Fault|xs:string|错误详细信息|  
|IsFaultSource|xs:unsignedByte|指示事件是否从出错源发出|  
|批注|xs:string|已添加到此事件中的批注。  值存储在一个 xml 元素中的格式\<项 >\<项名称 ="annotationName"type="System.String"> annotationValue\</i > \< /i t e >。  如果不指定任何批注，则该字符串包含\<项 / >。 ETW 事件大小受到 ETW 缓冲区大小或 ETW 事件最大负载的限制。 如果事件大小超出 ETW 限制，则通过丢弃批注并将替换为批注值来截断事件\<项 >... \< /i t e >。|  
|ProfileName|xs:string|导致发出此事件的跟踪配置文件的名称|  
|HostReference|xs:string|对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。  其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName 示例：'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'|  
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
