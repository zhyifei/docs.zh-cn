---
title: 1140 - FlowchartStart
ms.date: 03/30/2017
ms.assetid: 9aa2c71e-a4ab-4aed-b76d-4795e8493b70
ms.openlocfilehash: 556fd0421966083b29c925bf7555f9d8a2e7d7f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924509"
---
# <a name="1140---flowchartstart"></a>1140 - FlowchartStart
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|1140|  
|关键字|WFActivities|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示已安排流程图启动。  
  
## <a name="message"></a>消息  
 Flowchart“%1”- 已安排启动。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|FlowChart|xs:string|FlowChart 的显示名称。|  
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
