---
title: Windows Communication Foundation 中的传输
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 6bb8e8b90c26533661684bd403b9ec439f1bb37e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498119"
---
# <a name="transports-in-windows-communication-foundation"></a>Windows Communication Foundation 中的传输
传输层是通道堆栈的最低层。 使用 Windows Communication Foundation (WCF) 中的主要传输是 HTTP、 HTTPS、 TCP 和命名的管道。 本节中的主题讨论如何选择传输、配置传输和设置优化属性。  
  
 WCF 包括其他传输协议。 有关消息队列 (也称为 MSMQ) 传输的信息，请参阅[队列和可靠会话](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)。 有关对等传输的信息，请参阅[对等网络](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)。  
  
## <a name="in-this-section"></a>本节内容  
 [选择传输](../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 说明三种主要传输和选择其中一种传输时的注意事项。  
  
 [选择消息编码器](../../../../docs/framework/wcf/feature-details/choosing-a-message-encoder.md)  
 说明选择消息编码绑定元素时要考虑的因素。  
  
 [流消息传输](../../../../docs/framework/wcf/feature-details/streaming-message-transfer.md)  
 说明如何配置传输层进行流式处理。  
  
 [配置 HTTP 和 HTTPS](../../../../docs/framework/wcf/feature-details/configuring-http-and-https.md)  
 说明如何配置 HTTP 和 HTTPS 传输绑定元素。  
  
 [如何：用受限保留项替换 WCF URL 保留项](../../../../docs/framework/wcf/feature-details/how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 介绍如何使用 WCFURL 受限保留项。  
  
 [传输配额](../../../../docs/framework/wcf/feature-details/transport-quotas.md)  
 说明设置传输层中可用配额时的注意事项。  
  
 [使用 NAT 和防火墙](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)  
 说明在防火墙后发送或接收消息时或存在网络地址转换 (NAT) 时如何配置传输层。  
  
 [Net.TCP 端口共享](../../../../docs/framework/wcf/feature-details/net-tcp-port-sharing.md)  
 介绍如何使用 WCF 的 Net.TCP 端口共享组件。  
  
## <a name="reference"></a>参考  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a>相关章节  
 [绑定](../../../../docs/framework/wcf/feature-details/bindings.md)  
  
 [扩展绑定](../../../../docs/framework/wcf/extending/extending-bindings.md)
