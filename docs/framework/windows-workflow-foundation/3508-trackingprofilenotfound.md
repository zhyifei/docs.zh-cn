---
title: 3508 - TrackingProfileNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fb5636057193fcfb59e5062f6f3833a62b4f3027
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="3508---trackingprofilenotfound"></a>3508 - TrackingProfileNotFound
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|3508|  
|关键字|WFServices|  
|级别|详细|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 指示在配置文件中找不到 TrackingProfile，或 ActivityDefinitionId 与配置文件不匹配。  
  
## <a name="message"></a>消息  
 未找到 ActivityDefinitionId“%2”的 TrackingProfile“%1”。 在配置文件中找不到 TrackingProfile，或 ActivityDefinitionId 不匹配。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|TrackingProfile|xs:string|跟踪配置文件的名称。|  
|ActivityDefinitionId|xs:string|活动定义 ID。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
