---
title: 39457 - TrackingRecordRaised
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a2731d1-c731-4b79-bb69-016cb69ef481
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 73bfd304794e096d076ab6bbff4a87bcd8de849a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="39457---trackingrecordraised"></a>39457 - TrackingRecordRaised
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|39457|  
|关键字|WFRuntime|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示 TrackingRecord 已提升为 TrackingParticipant。  
  
## <a name="message"></a>消息  
 跟踪记录 %1 提升为 %2。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|RecordNumber|xs:string|跟踪记录编号。|  
|ParticipantId|xs:string|跟踪参与者。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
