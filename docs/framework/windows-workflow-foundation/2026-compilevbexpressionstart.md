---
title: 2026 - CompileVbExpressionStart
ms.date: 03/30/2017
ms.assetid: daad57eb-8198-49b5-9920-aa0e7428ccf1
ms.openlocfilehash: a80cc9c6c7768626d65c3a31570d5342a395edf2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
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
