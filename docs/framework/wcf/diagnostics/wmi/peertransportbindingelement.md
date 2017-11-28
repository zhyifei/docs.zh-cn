---
title: PeerTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 48364c2bcfa50476ac5f9f00f87c17f97dc14017
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="peertransportbindingelement"></a>PeerTransportBindingElement
PeerTransportBindingElement  
  
## <a name="syntax"></a>语法  
  
```  
class PeerTransportBindingElement : TransportBindingElement  
{  
  string ListenIPAddress;  
  sint32 Port;  
  PeerSecuritySettings Security;  
};  
```  
  
## <a name="methods"></a>方法  
 PeerTransportBindingElement 类未定义任何方法。  
  
## <a name="properties"></a>属性  
 PeerTransportBindingElement 类具有以下属性：  
  
### <a name="listenipaddress"></a>ListenIPAddress  
 数据类型：String  
  
 访问类型：只读  
  
 对等节点在其上侦听消息的 IP 地址。  
  
### <a name="port"></a>端口  
 数据类型：sint32  
  
 访问类型：只读  
  
 网络接口端口，此绑定在该端口上处理对等通道消息。  
  
### <a name="security"></a>安全性  
 数据类型：PeerSecuritySettings  
  
 访问类型：只读  
  
 对等传输安全设置。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
