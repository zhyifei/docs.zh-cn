---
title: 1001 - WorkflowApplicationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a62a8448319e7b07a3ea302f00f2fa269bf654ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1001---workflowapplicationcompleted"></a>1001 - WorkflowApplicationCompleted
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|1001|  
|关键字|WFRuntime|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示工作流应用程序在“已关闭”状态下完成。  
  
## <a name="message"></a>消息  
 WorkflowInstance Id“%1”在“已关闭”状态下完成。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|工作流的实例 ID|  
|AppDomain|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
