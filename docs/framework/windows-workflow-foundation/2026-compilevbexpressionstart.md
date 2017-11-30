---
title: 2026 - CompileVbExpressionStart
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: daad57eb-8198-49b5-9920-aa0e7428ccf1
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 056771021035857e0100a581dcfce07aeca30b1f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="2026---compilevbexpressionstart"></a>2026 - CompileVbExpressionStart
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|2026|  
|关键字|WFRuntime|  
|级别|详细|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示 VB 表达式编译的开头。  
  
## <a name="message"></a>消息  
 正在编译 VB 表达式“%1”  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|Expression|xs:string|要编译的 VisualBasic 表达式。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
