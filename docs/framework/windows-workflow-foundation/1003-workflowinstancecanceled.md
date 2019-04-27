---
title: 1003 - WorkflowInstanceCanceled
ms.date: 03/30/2017
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
ms.openlocfilehash: c76a2dab6a95bda7f3969af07f814aba30071c7f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008624"
---
# <a name="1003---workflowinstancecanceled"></a>1003 - WorkflowInstanceCanceled
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|1003|  
|关键字|WFRuntime|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示工作流实例在“已取消”状态下完成。  
  
## <a name="message"></a>消息  
 WorkflowInstance Id“%1”在“已取消”状态下完成。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|工作流的实例 ID|  
|应用程序域|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
