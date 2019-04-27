---
title: 1146 - FlowchartSwitchCase
ms.date: 03/30/2017
ms.assetid: 274e9209-1720-4512-a615-e742f00895f4
ms.openlocfilehash: 9f4e3af664ed30634e4b56f16cd6caf2366c3674
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923898"
---
# <a name="1146---flowchartswitchcase"></a>1146 - FlowchartSwitchCase
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|1146|  
|关键字|WFActivities|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示在 Flowchart 开关中已选择的大小写。  
  
## <a name="message"></a>消息  
 Flowchart“%1”/FlowSwitch - 选择了 Case“%2”。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|FlowChart|xs:string|FlowChart 的显示名称。|  
|Case|xs:string|所选的开关大小写。|  
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
