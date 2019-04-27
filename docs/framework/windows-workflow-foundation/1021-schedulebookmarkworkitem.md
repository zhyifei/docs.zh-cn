---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: abc026165568d05faef619da28c94f27f37eea27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924418"
---
# <a name="1021---schedulebookmarkworkitem"></a>1021 - ScheduleBookmarkWorkItem
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|1021|  
|关键字|WFRuntime|  
|级别|详细|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示已安排 BookmarkWorkItem。  
  
## <a name="message"></a>消息  
 已为 Activity"%1"、 DisplayName 安排了 BookmarkWorkItem:"%2"、 InstanceId:"%3"。  BookmarkName: %4、BookmarkScope: %5。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|活动|xs:string|活动的类型名称。|  
|DisplayName|xs:string|活动的显示名称。|  
|InstanceId|xs:string|活动的实例 ID。|  
|BookmarkName|xs:string|书签的名称。|  
|BookmarkScope|xs:string|书签的范围。|  
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
