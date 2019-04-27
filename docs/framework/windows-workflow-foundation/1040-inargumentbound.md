---
title: 1040 - InArgumentBound
ms.date: 03/30/2017
ms.assetid: 7dfaad1b-36c0-4575-84c1-31d63b0eaf5d
ms.openlocfilehash: 984372c07ccfb11f2f05d5488fa5ffc95075db41
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009742"
---
# <a name="1040---inargumentbound"></a>1040 - InArgumentBound
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|1040|  
|关键字|WFActivities|  
|级别|详细|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示已绑定 In 自变量。  
  
## <a name="message"></a>消息  
 Activity“%2”、DisplayName“%3”、InstanceId“%4”中的 In 自变量“%1”已经与值 %5 绑定。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|InArgument|xs:string|InArgument 的名称。|  
|活动|xs:string|活动的类型名称。|  
|DisplayName|xs:string|活动的显示名称。|  
|InstanceId|xs:string|活动的实例 ID。|  
|“值”|xs:string|绑定到 InArgument 的值。|  
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
