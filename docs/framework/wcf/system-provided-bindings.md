---
title: "系统提供的绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bindings [WCF], system-provided
ms.assetid: 2c243746-45ce-4588-995e-c17126a579a6
caps.latest.revision: "60"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5f8df31e31c9617fe7bcd92789671d220382a82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="system-provided-bindings"></a>系统提供的绑定
绑定可指定在与终结点通话时所使用的通信机制，并指示如何连接到终结点。 绑定包含以下元素：  
  
-   协议堆栈确定用于发送到终结点的消息的安全性、可靠性和上下文流设置。  
  
-   传输确定将消息发送到终结点时使用的基础传输协议，例如 TCP 或 HTTP。  
  
-   编码确定用于发送到终结点的消息的网络编码，例如，文本/XML、二进制或消息传输优化机制 (MTOM)。  
  
 本主题介绍系统提供的所有 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 绑定。 如果这些都不符合应用程序的确切标准，则你可以创建自定义绑定。 [!INCLUDE[crabout](../../../includes/crabout-md.md)]创建自定义绑定，请参阅[自定义绑定](../../../docs/framework/wcf/extending/custom-bindings.md)。  
  
 通过支持 WS-Federation 协议的安全的、可互操作的绑定，联盟中的组织可以高效地对用户进行身份验证和授权。  
  
> [!IMPORTANT]
>  始终选择包括安全性的绑定。 默认情况下，除之外的所有绑定[ \<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)元素启用了安全性。 如果不选择安全绑定或禁用安全性，请务必以某种其他方式保护数据，如将其存储在受保护的数据中心中或隔离网络上。  
  
> [!IMPORTANT]
>  除非以某种其他方式保护数据，否则决不要将双工协定与不支持安全性或已禁用安全性的绑定一起使用。  
  
## <a name="system-provided-bindings"></a>系统提供的绑定  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 附带有以下绑定。  
  
|绑定|配置元素|描述|  
|-------------|---------------------------|-----------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|一个绑定，适用于与符合 WS-Basic Profile 的 Web 服务（例如基于 ASP.NET Web 服务 (ASMX) 的服务）进行的通信。 此绑定使用 HTTP 作为传输协议，并使用文本/XML 作为默认的消息编码。|  
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|一个安全且可互操作的绑定，适合于非双工服务约定。|  
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|一个安全且可互操作的绑定，适用于双工服务协定或通过 SOAP 媒介进行的通信。|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|一个支持 WS-Federation 协议的安全的、可互操作的绑定，使联盟中的组织可以高效地对用户进行身份验证和授权。|  
|<xref:System.ServiceModel.NetHttpBinding>|\<netHttpBinding >|为使用 HTTP 或 WebSocket 服务而设计且默认情况下使用二进制编码的绑定。|  
|<xref:System.ServiceModel.NetHttpsBinding>|\<netHttpsBinding >|为使用 HTTP 或 WebSocket 服务而设计且默认情况下使用二进制编码的安全绑定。|  
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|一个安全且经过优化的绑定，适用于 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 应用程序之间跨计算机的通信。|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<netNamedPipeBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)|一个安全、可靠且经过优化的绑定，适用于 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 应用程序之间计算机上的通信。|  
|<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|一个排队绑定，适用于 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 应用程序之间的跨计算机的通信。|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)|一个支持多计算机安全通信的绑定。|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding >](../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)|一个适合于 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 应用程序和现有消息队列应用程序之间的跨计算机通信的绑定。|  
|<xref:System.ServiceModel.BasicHttpContextBinding>|[\<basicHttpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpcontextbinding.md)|一个绑定，适用于与符合 WS-Basic Profile 且允许使用 HTTP Cookie 交换上下文的 Web 服务进行的通信。|  
|<xref:System.ServiceModel.NetTcpContextBinding>|[\<netTcpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/nettcpcontextbinding.md)|一个安全且经过优化的绑定，适用于允许使用 SOAP 标头交换上下文的 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 应用程序之间跨计算机的通信。|  
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|一个绑定，可用于为通过 HTTP 请求（而不是 SOAP 消息）公开的 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Web 服务配置终结点。|  
|<xref:System.ServiceModel.WSHttpContextBinding>|[\<wsHttpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpcontextbinding.md)|一种安全的和 |<xref:System.ServiceModel.UdpBinding>|\<但 udpBinding >|同时向大量客户端发送突然爆发出的简单消息时使用的绑定。|  
  
 下表显示系统提供的每个绑定的功能。 在表列中可找到绑定；在行中列出了功能，在第二个表中描述了这些功能。 下表提供所用绑定缩写的概要。 若要选择绑定，应确定哪列能满足所需的所有行中的功能。  
  
|绑定|互操作性|安全性（默认）|会话<br /><br /> (默认)|事务|双工|编码（默认）|流式处理<br /><br /> (默认)|  
|-------------|----------------------|--------------------------|-----------------------------|------------------|------------|--------------------------|-------------------------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1（基本配置文件 1.1）|（无）、传输、消息、混合|（无）|（无）|不可用|文本、(MTOM)|是<br /><br /> （缓冲式）|  
|<xref:System.ServiceModel.WSHttpBinding>|WS|传输、（消息）、混合|（无）、可靠会话、安全会话|（无）、是|不可用|（文本）、MTOM|否|  
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|（消息）、无|（可靠会话）、安全会话|（无）、是|是|（文本）、MTOM|否|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|（消息）、混合、无|（无）、可靠会话、安全会话|（无）、是|否|（文本）、MTOM|否|  
|<xref:System.ServiceModel.NetHttpBinding>|.NET|（无）、传输、消息、TransportWithMessageCredential、TransportCredentialOnly|请参见下面的注释|无|请参见下面的注释|（二进制）、文本、MTOM|是（缓冲式）|  
|<xref:System.ServiceModel.NetHttpsBinding>|.NET|（传输）、TransportWithMessageCredential|请参见下面的注释|无|请参见下面的注释|（二进制）、文本、MTOM|是（缓冲式）|  
|<xref:System.ServiceModel.NetTcpBinding>|.NET|（传输）、消息、无、混合|（传输）、可靠会话、安全会话|（无）、是|是|二进制|是<br /><br /> （缓冲式）|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|（传输）、无|无、（传输）|（无）、是|是|二进制|是<br /><br /> （缓冲式）|  
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|消息、（传输）、无|（无）、传输|无、（是）|否|二进制|否|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|对等|（传输）|（无）|（无）|是||否|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|MSMQ|（传输）|（无）|无、（是）|不可用|不可用|否|  
|<xref:System.ServiceModel.BasicHttpContextBinding>|Basic Profile 1.1（基本配置文件 1.1）|（无）、传输、消息、混合|（无）|（无）|不可用|文本、(MTOM)|是<br /><br /> （缓冲式）|  
|<xref:System.ServiceModel.NetTcpContextBinding>|.NET|（传输）、消息、无、混合|（传输）、可靠会话、安全会话|（无）、是|是|二进制|是<br /><br /> （缓冲式）|  
|<xref:System.ServiceModel.WSHttpContextBinding>|WS|传输、（消息）、混合|（无）、可靠会话、安全会话|（无）、是|不可用|文本、(MTOM)|否|  
|<xref:System.ServiceModel.UdpBinding>|.NET**注意：**互操作性可以通过实现此绑定实现的标准-UDP 上的 SOAP 规范。|（无）|（无）|（无）|不可用|（文本）|否|  
  
> [!IMPORTANT]
>  <xref:System.ServiceModel.NetHttpBinding> 是为使用 HTTP 或 WebSocket 服务设计的绑定，默认情况下使用二进制编码。 <xref:System.ServiceModel.NetHttpBinding> 将检测它是否与请求-答复协定或双工协定结合使用，并更改其行为以进行匹配 ― 它将针对请求-答复协定使用 HTTP，并针对双工协定使用 WebSocket。 可以使用重写此行为<!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A>-->`System.ServiceModel.NetHttpBinding.WebSocketTransportUsage`绑定设置： Allowed-这是默认值，行为方式如上面所述。NotAllowed-这阻止使用 Websocket。 尝试使用此设置使用双工协定将导致异常。这将强制必填字段-甚至对于请求-答复协定使用 Websocket。 NetHttpBinding HTTP 模式和 WebSocket 模式下支持可靠会话。 在 WebSocket 模式下，会话由传输来提供。  
  
 下表对上表列出的功能进行说明。  
  
|功能|描述|  
|-------------|-----------------|  
|互操作性类型|指定绑定用来确保互操作的协议或技术。|  
|安全性|指定如何保护通道：<br /><br /> -None: SOAP 消息不进行保护，客户端未经过身份验证。<br />-传输： 在传输层上满足安全要求。<br />-消息： 在消息层上满足安全要求。<br />混合： 声明包含在消息;完整性和保密性要求由传输层满足。|  
|会话|指定此绑定是否支持会话协定。|  
|事务|指定是否启用事务。|  
|双工|指定是否支持双工协定。 请注意，此功能要求支持绑定中的会话。|  
|编码|指定消息的网络格式。 允许的值包括：<br /><br /> 文本： 例如 utf-8。<br />-二进制<br />消息传输优化机制 (MTOM): 用于高效编码的 SOAP 信封的上下文中二进制 XML 元素的方法。|  
|流式处理|指定传入和传出消息是否支持流。 使用绑定上的 `TransferMode` 属性可设置值。 允许的值包括：<br /><br /> -   <xref:System.ServiceModel.TransferMode.Buffered>： 对请求和响应消息进行缓冲处理。<br />-   <xref:System.ServiceModel.TransferMode.Streamed>： 对请求和响应消息进行流式处理。<br />-   <xref:System.ServiceModel.TransferMode.StreamedRequest>： 请求消息进行流式处理，响应消息进行缓冲处理。<br />-   <xref:System.ServiceModel.TransferMode.StreamedResponse>： 请求消息进行缓冲处理，响应消息进行流式处理。|  
  
## <a name="see-also"></a>请参阅  
 [终结点创建概述](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [使用绑定配置服务和客户端](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [基本 WCF 编程](../../../docs/framework/wcf/basic-wcf-programming.md)
