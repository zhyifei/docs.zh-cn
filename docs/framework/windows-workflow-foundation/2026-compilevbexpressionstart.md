---
title: 2026 - CompileVbExpressionStart
ms.date: 03/30/2017
ms.assetid: daad57eb-8198-49b5-9920-aa0e7428ccf1
ms.openlocfilehash: a80cc9c6c7768626d65c3a31570d5342a395edf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61755696"
---
# <a name="2026---compilevbexpressionstart"></a>2026 - CompileVbExpressionStart
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|2026|  
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
|表达式|xs:string|要编译的 VisualBasic 表达式。|  
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
