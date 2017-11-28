---
title: 1140 - FlowchartStart
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aa2c71e-a4ab-4aed-b76d-4795e8493b70
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cc73721480452bd913561284a3f2ff82c3c6d8f8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1140---flowchartstart"></a>1140 - FlowchartStart
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|1140|  
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
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
