---
title: PeerTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 40bf6be2-8087-4cb3-a66c-408d53eb9269
ms.openlocfilehash: 68e6a25e4e3f47c556363e2fd5aa8d3bb9946449
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
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
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
