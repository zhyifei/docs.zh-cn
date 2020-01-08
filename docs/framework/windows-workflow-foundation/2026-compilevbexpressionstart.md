---
title: 2026 - CompileVbExpressionStart
ms.date: 03/30/2017
ms.assetid: daad57eb-8198-49b5-9920-aa0e7428ccf1
ms.openlocfilehash: 8f8fc79a6b56b85bb55569420ca7511fa7e41d7a
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344601"
---
# <a name="2026---compilevbexpressionstart"></a>2026 - CompileVbExpressionStart
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|ID|2026|  
|关键字|WFRuntime|  
|Level|详细|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/调试|  
  
## <a name="description"></a>描述  
 指示 Visual Basic 表达式编译的开头。  
  
## <a name="message"></a>Message  
 正在编译 Visual Basic 表达式 "%1"  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|表达式|xs:string|要编译的 VisualBasic 表达式。|  
|应用程序域|xs:string|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
