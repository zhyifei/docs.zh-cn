---
title: ConnectionOrientedTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1308313-f0e2-49e6-977d-6b4ce9ad35d1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c0d399eb859118dfe94eb9e0a421fa405ae0f414
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="connectionorientedtransportbindingelement"></a>ConnectionOrientedTransportBindingElement
ConnectionOrientedTransportBindingElement  
  
## <a name="syntax"></a>语法  
  
```  
class ConnectionOrientedTransportBindingElement : TransportBindingElement  
{  
  datetime ChannelInitializationTimeout;  
  sint32 ConnectionBufferSize;  
  string HostNameComparisonMode;  
  sint32 MaxBufferSize;  
  datetime MaxOutputDelay;  
  sint32 MaxPendingAccepts;  
  sint32 MaxPendingConnections;  
  string TransferMode;  
};  
```  
  
## <a name="methods"></a>方法  
 ConnectionOrientedTransportBindingElement 类不定义任何方法。  
  
## <a name="properties"></a>属性  
 ConnectionOrientedTransportBindingElement 类具有以下属性：  
  
### <a name="channelinitializationtimeout"></a>ChannelInitializationTimeout  
 数据类型：DateTime  
  
 访问类型：只读  
  
 指定在超时前可用于完成通道初始化的时间间隔。  
  
### <a name="connectionbuffersize"></a>ConnectionBufferSize  
 数据类型：sint32  
  
 访问类型：只读  
  
 用于从客户端或服务传输网络上的序列化消息块的缓冲区大小。  
  
### <a name="hostnamecomparisonmode"></a>HostNameComparisonMode  
 数据类型：String  
  
 访问类型：只读  
  
 一个值，指示在对 URI 进行匹配时，是否使用主机名来访问服务。  
  
### <a name="maxbuffersize"></a>MaxBufferSize  
 数据类型：sint32  
  
 访问类型：只读  
  
 要使用的缓冲区最大大小。  
  
### <a name="maxoutputdelay"></a>MaxOutputDelay  
 数据类型：DateTime  
  
 访问类型：只读  
  
 消息块或完整消息在发出之前可以在内存中保持缓冲的最大时间间隔。  
  
### <a name="maxpendingaccepts"></a>MaxPendingAccepts  
 数据类型：sint32  
  
 访问类型：只读  
  
 可用于处理服务上的传入连接的最大挂起异步接受线程数。  
  
### <a name="maxpendingconnections"></a>MaxPendingConnections  
 数据类型：sint32  
  
 访问类型：只读  
  
 最大挂起连接数。  
  
### <a name="transfermode"></a>TransferMode  
 数据类型：String  
  
 访问类型：只读  
  
 一个值，指定通过面向连接的传输对消息进行缓冲还是流处理。  
  
## <a name="requirements"></a>要求  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>
