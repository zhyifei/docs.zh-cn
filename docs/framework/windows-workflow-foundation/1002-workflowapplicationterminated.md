---
title: 1002 - WorkflowApplicationTerminated
ms.date: 03/30/2017
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
ms.openlocfilehash: 01c9aba6e863e07a1a999a28fccefbab95a34d5b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008650"
---
# <a name="1002---workflowapplicationterminated"></a>1002 - WorkflowApplicationTerminated
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|1002|  
|关键字|WFRuntime|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示工作流应用程序因出现异常而在“出错”状态下终止。  
  
## <a name="message"></a>消息  
 WorkflowApplication Id“%1”已终止。 该应用程序因出现异常而在“出错”状态下完成。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|`xs:string`|工作流应用程序 ID|  
|例外|`xs:string`|异常的异常详细信息|  
|应用程序域|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
