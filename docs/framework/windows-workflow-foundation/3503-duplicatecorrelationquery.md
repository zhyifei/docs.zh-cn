---
title: 3503 - DuplicateCorrelationQuery
ms.date: 03/30/2017
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
ms.openlocfilehash: 37a689b30b0bcab9124472deb98627afbe30dfee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511395"
---
# <a name="3503---duplicatecorrelationquery"></a>3503 - DuplicateCorrelationQuery
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|3503|  
|关键字|WFServices|  
|级别|警告|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 指示找到了重复 CorrelationQuery。 计算相关性时将不使用重复查询。  
  
## <a name="message"></a>消息  
 找到了含有 Where='%1' 的重复 CorrelationQuery。 计算相关性时将不使用此重复查询。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|Where|xs:string|相关查询的 Where 部分。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
