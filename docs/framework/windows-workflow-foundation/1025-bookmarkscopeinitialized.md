---
title: 1025 - BookmarkScopeInitialized
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63584434-e709-471d-9e96-97d3d99e70d6
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cc59e0f2a8d91924ca973d04829e29813d3cc3a2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1025---bookmarkscopeinitialized"></a>1025 - BookmarkScopeInitialized
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|1025|  
|关键字|WFRuntime|  
|级别|详细|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示已初始化 BookmarkScope。  
  
## <a name="message"></a>消息  
 TemporaryId 为“%1”的 BookmarkScope 已初始化，ID 为:“%2”。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|TemporaryId|xs:string|书签的临时 ID。|  
|InitializedId|xs:string|书签的初始化的 ID。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
