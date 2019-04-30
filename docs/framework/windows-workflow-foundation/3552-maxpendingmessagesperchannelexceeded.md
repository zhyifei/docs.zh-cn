---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.date: 03/30/2017
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
ms.openlocfilehash: a163ed216cbdfbf2b9d77d25979733d6bdb121d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945933"
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a>3552 - MaxPendingMessagesPerChannelExceeded
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|3552|  
|关键字|配额、WFServices|  
|级别|警告|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 指示达到了中止值“MaxPendingMessagesPerChannel”。  
  
## <a name="message"></a>消息  
 已命中的中止值 maxpendingmessagesperchannel 的"%1"。 若要增加此限制，请调整 BufferedReceiveServiceBehavior 中的 MaxPendingMessagesPerChannel 属性。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|限制值|xs:string|中止值 MaxPendingMessagesPerChannel。|  
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
