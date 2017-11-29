---
title: "设计和实现服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: defining service contracts [WCF]
ms.assetid: 036fae20-7c55-4002-b71d-ac4466e167a3
caps.latest.revision: "37"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ee2564b59ba0c0377c93c22787974ac0a980e64b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="designing-and-implementing-services"></a>设计和实现服务
本部分演示如何定义和实现[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]协定。 服务协定指定终结点与外界通信的内容。 更具体地说，它是有关一组特定消息的声明，这些消息被组织成基本消息交换模式 (MEP)，如请求/答复、单向和双工。 如果说服务协定是一组在逻辑上相关的消息交换，那么服务操作就是单个消息交换。 例如，`Hello` 操作显然必须接受一条消息（以便调用方能够发出问候），并可能返回也可能不返回一条消息（具体取决于操作的礼节性）。  
  
 有关协定和其他核心更多信息[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]概念，请参阅[基本 Windows Communication Foundation 概念](../../../docs/framework/wcf/fundamental-concepts.md)。 本主题重点介绍对服务协定的理解。 有关如何构建使用服务协定使用连接到服务的客户端的详细信息，请参阅[WCF 客户端概述](../../../docs/framework/wcf/wcf-client-overview.md)。  
  
## <a name="overview"></a>概述  
 本主题为 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务的设计和实现提供高级概念性阐释。 子主题提供有关具体设计和实现内容的更为详细的信息。 在设计和实现 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 应用程序之前，建议您：  
  
-   了解什么是服务协定、服务协定的工作原理以及如何创建服务协定。  
  
-   了解运行时配置或宿主环境可能不支持的协定状态最低要求。  
  
## <a name="service-contracts"></a>服务协定  
 服务协定指定以下内容：  
  
-   协定公开的操作。  
  
-   针对交换的消息所进行的各种操作的签名。  
  
-   这些消息的数据类型。  
  
-   操作的位置。  
  
-   用于支持与服务成功通信的特定协议和序列化格式。  
  
 例如，采购订单协定可能具有一个 `CreateOrder` 操作，该操作接受订单信息类型输入并返回成功或失败信息，包括一个订单标识符。 它还可能具有一个 `GetOrderStatus` 操作，该操作接受一个订单标识符并返回订单状态信息。 此类服务协定需要指定：  
  
1.  采购订单协定由 `CreateOrder` 和 `GetOrderStatus` 操作组成。  
  
2.  这些操作指定了输入消息和输出消息。  
  
3.  这些消息可以携带的数据。  
  
4.  有关成功处理消息所必需的通信基础结构的分类声明。 例如，这些详细信息包括建立成功通信是否需要安全以及需要哪些形式的安全。  
  
 若要表达这种对其他应用程序在许多平台 （包括非 Microsoft 平台） 上的信息，XML 服务协定公开以表示标准 XML 格式，如[Web 服务描述语言](http://go.microsoft.com/fwlink/?LinkId=94952)(WSDL) 和[XML 架构](http://go.microsoft.com/fwlink/?LinkId=94953)(XSD) 等。 许多平台的开发人员都可以使用此公共协定信息创建可与该服务通信的应用程序，既因为开发人员理解规范的语言，又因为这些语言通过描述服务支持的公共形式、格式和协议，支持互操作。 详细了解如何[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]句柄这类的信息，请参阅[元数据](../../../docs/framework/wcf/feature-details/metadata.md)。  
  
 协定可以用多种方式进行表示，虽然 WSDL 和 XSD 语言非常适合以易于理解的方式描述服务，但这些语言很难直接使用，它们仅用于描述服务，而不能描述服务协定实现。 因此，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 应用程序使用托管属性、接口和类来定义服务的结构并实现服务。  
  
 得到的在托管类型中定义的协定可以是*导出*作为元数据 — WSDL 和 XSD-客户端或其他服务实施者需要时。 结果可以得到一个简单的编程模型，可以使用公共元数据向任何客户端应用程序描述该模型。 基础 SOAP 消息的详细信息、传输和安全相关信息等可以留给 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 进行处理，它可以在服务协定类型系统和 XML 类型系统之间自动执行必要的转换。  
  
 有关设计协定的详细信息，请参阅[设计服务协定](../../../docs/framework/wcf/designing-service-contracts.md)。 有关实现协定的详细信息，请参阅[实现服务协定](../../../docs/framework/wcf/implementing-service-contracts.md)。  
  
### <a name="messages-up-front-and-center"></a>面向消息  
 如果您习惯于远程过程调用 (RPC) 样式的方法签名（其请求功能的标准形式为向某一方法传递参数，然后从对象或其他类型的代码接收返回值），则使用托管接口、类和方法模拟服务操作简单而直观。 例如，使用托管语言（如 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 和 C++ COM）的程序员可以运用 RPC 样式方法（不管是使用对象还是接口）方面的知识来创建 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务协定，而不会遇到 RPC 样式分布式对象系统中固有的问题。 面向服务的优势是可以实现松耦合、面向消息的编程，同时保持轻松熟悉的 RPC 编程体验。  
  
 许多程序员感觉使用面向消息的应用程序编程接口更舒服，例如，像 Microsoft MSMQ 这样的消息队列、.NET Framework 中的 <xref:System.Messaging> 命名空间或在 HTTP 请求中发送非结构化 XML。 有关在消息级别进行编程的详细信息，请参阅[使用消息协定](../../../docs/framework/wcf/feature-details/using-message-contracts.md)，[服务通道级编程](../../../docs/framework/wcf/extending/service-channel-level-programming.md)，和[与 POX 应用程序互操作性](../../../docs/framework/wcf/feature-details/interoperability-with-pox-applications.md).  
  
### <a name="understanding-the-hierarchy-of-requirements"></a>了解需求的层次结构  
 服务协定对操作进行分组，指定消息交换模式、消息类型和消息携带的数据类型，并指示实现为了支持该协定而必须具有的运行时行为类别（例如，可能要求对消息进行加密和签名）。 服务协定本身并未明确指定如何满足这些要求，而只是指定这些要求必须得到满足。 加密类型或消息的签名方式取决于相容服务的实现和配置。  
  
 请注意协定为添加行为而对服务协定实现和运行时配置提出特定要求的方式。 为了公开某一服务以供使用而必须满足的这组要求建立于前一组要求之上。 如果协定对实现提出要求，那么实现可能会对配置和绑定提出更多的要求，以便使服务能够运行。 最后，主机应用程序还必须支持服务配置和绑定所添加的任何要求。  
  
 在设计、实现、配置和承载 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 服务应用程序时必须要记住这一添加要求的过程。 例如，协定可能会指定需要支持某一会话。 如果是这样，您必须配置绑定以支持该协定性要求，否则服务实现将无法正常工作。 或者，如果你的服务要求 Windows 集成身份验证并寄宿在 Internet 信息服务 (IIS) 中，则服务所在的 Web 应用程序必须打开 Windows 集成身份验证并关闭匿名支持。 有关功能和不同的服务主机应用程序类型的影响的详细信息，请参阅[托管服务](../../../docs/framework/wcf/hosting-services.md)。  
  
## <a name="see-also"></a>另请参阅  
 [设计服务协定](../../../docs/framework/wcf/designing-service-contracts.md)  
 [实现服务协定](../../../docs/framework/wcf/implementing-service-contracts.md)
