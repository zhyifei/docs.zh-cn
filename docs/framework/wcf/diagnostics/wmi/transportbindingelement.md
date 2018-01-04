---
title: TransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 062b45eb5d627903142ca1a5fd4db6df0855384b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="transportbindingelement"></a>TransportBindingElement
TransportBindingElement  
  
## <a name="syntax"></a>语法  
  
```  
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a>方法  
 TransportBindingElement 类未定义任何方法。  
  
## <a name="properties"></a>属性  
 TransportBindingElement 类具有以下属性：  
  
### <a name="manualaddressing"></a>ManualAddressing  
 数据类型：Boolean  
  
 访问类型：只读  
  
 一个布尔值，该值指定用户是否要控制消息寻址。  
  
### <a name="maxbufferpoolsize"></a>MaxBufferPoolSize  
 数据类型：sint64  
  
 访问类型：只读  
  
 绑定的最大缓冲池大小。  
  
### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize  
 数据类型：sint64  
  
 访问类型：只读  
  
 此绑定所处理的消息的最大大小。  
  
### <a name="scheme"></a>方案  
 数据类型：String  
  
 访问类型：只读  
  
 传输的 URI 方案。  
  
## <a name="requirements"></a>惠?  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
