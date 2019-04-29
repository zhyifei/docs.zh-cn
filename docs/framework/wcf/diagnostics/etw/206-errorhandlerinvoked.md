---
title: 206 - ErrorHandlerInvoked
ms.date: 03/30/2017
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
ms.openlocfilehash: 40a92d77c57728249569a854eab8767ff371bca2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781922"
---
# <a name="206---errorhandlerinvoked"></a>206 - ErrorHandlerInvoked
## <a name="properties"></a>属性  
  
|||  
|-|-|  
|Id|206|  
|关键字|疑难解答，ServiceModel|  
|级别|信息|  
|通道|Microsoft-Windows-应用程序服务器-应用程序/分析|  
  
## <a name="description"></a>描述  
 当 `ErrorHandler` 有机会处理在服务操作中发生的异常后，将发出此事件。  
  
## <a name="message"></a>消息  
 调度程序调用的 errorhandler 来处理类型"%1"类型"%3"的异常。 ErrorHandled 为“%2”。  
  
## <a name="details"></a>详细信息  
  
|数据项名称|数据项类型|描述|  
|--------------------|--------------------|-----------------|  
|TypeName|`xs:string`|所调用 `ErrorHandler` 的类型的 CLR FullName。|  
|Handled|`xs:unsignedByte`|如果错误处理程序已处理错误，则为 `true`；否则为 `false`。|  
|ExceptionTypeName|`xs:string`|待处理异常的 CLR FullName。|  
|HostReference|`xs:string`|对于 Web 承载的服务，此字段唯一标识 Web 层次结构中的服务。 其格式定义为网站名称应用程序虚拟路径&#124;服务虚拟路径&#124;ServiceName。 示例:默认网站/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService。|  
|应用程序域|`xs:string`|由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。|
