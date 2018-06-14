---
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 2a382a2f12f4800cd70286a553af253e2af64c9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510454"
---
# <a name="1020---createbookmark"></a>1020 - CreateBookmark
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|1020|  
|关键字|WFRuntime|  
|级别|详细|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示已为活动创建了书签。  
  
## <a name="message"></a>消息  
 已为 Activity"%1"、 DisplayName 创建书签:"%2"、 InstanceId:"%3"。  BookmarkName: %4、BookmarkScope: %5。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|Activity|xs:string|活动的类型名称。|  
|DisplayName|xs:string|活动的显示名称。|  
|InstanceId|xs:string|活动的实例 ID。|  
|BookmarkName|xs:string|书签的名称。|  
|BookmarkScope|xs:string|书签的范围。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
