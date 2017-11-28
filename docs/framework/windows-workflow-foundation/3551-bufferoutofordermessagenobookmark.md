---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9a380def22c270a3fafe118a426609a93862c447
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="3551---bufferoutofordermessagenobookmark"></a>3551 - BufferOutOfOrderMessageNoBookmark
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|3551|  
|关键字|WFServices|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 指示书签恢复已失败。 服务实例准备好处理此特定操作时，将再次尝试该缓冲的接收操作。  
  
## <a name="message"></a>消息  
 此时不能执行服务实例“%1”上的操作“%2”。 服务实例准备好处理此特定操作时，将进行另一个尝试。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|操作的名称。|  
|ServiceInstanceId|xs:string|服务实例的 ID。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
