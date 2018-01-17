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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e2d5d8963389cebd6dbff06fdf58693dbc6cbf9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
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
