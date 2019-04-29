---
title: 客户端体系结构
ms.date: 03/30/2017
ms.assetid: 02624403-0d77-41cb-9a86-ab55e98c7966
ms.openlocfilehash: 4ced24f370e2ab54528c6adb2b3617d3d849e745
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781519"
---
# <a name="client-architecture"></a>客户端体系结构
应用程序使用 Windows Communication Foundation (WCF) 客户端对象调用服务操作。 本主题讨论 WCF 客户端对象、 WCF 客户端通道和基础通道体系结构及其关系。 WCF 客户端对象的基本概述，请参阅[WCF 客户端概述](../../../../docs/framework/wcf/wcf-client-overview.md)。 有关通道层的详细信息，请参阅[扩展通道层](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)。  
  
## <a name="overview"></a>概述  
 服务模型运行时创建 WCF 客户端，将以下内容组成：  
  
- 自动生成的服务协定客户端实现，该实现可以将应用程序代码中的调用转换为传出消息，将响应消息转换为输出参数并返回应用程序可以检索的值。  
  
- 控制接口 (<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>) 的实现，它可将各个接口组合在一起，并提供对控制功能（特别是用于关闭客户端会话和释放通道的能力）的访问。  
  
- 基于由使用的绑定指定的配置设置而生成的客户端通道。  
  
 应用程序可以按需，通过创建此类客户端<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>或通过创建的实例<xref:System.ServiceModel.ClientBase%601>派生类，它是由生成[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。 这些预先生成的客户端类可以封装并委托给由 <xref:System.ServiceModel.ChannelFactory> 动态构造的客户端通道实现。 因此，客户端通道和生成这些客户端通道的客户端工厂是此处讨论的焦点。  
  
## <a name="client-objects-and-client-channels"></a>客户端对象和客户端通道  
 WCF 客户端的基接口是<xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>接口公开核心客户端功能以及的基本通信对象功能<xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>的上下文功能<xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>，以及可扩展的行为<xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>.  
  
 但 <xref:System.ServiceModel.IClientChannel> 接口并不定义服务协定本身。 这些协定通过服务协定接口进行声明 (通常从服务元数据之类的工具生成[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md))。 WCF 客户端类型同时扩展<xref:System.ServiceModel.IClientChannel>和目标服务协定接口，以使应用程序能够直接调用操作，还可以访问客户端的运行时功能。 创建 WCF 客户端提供了 WCF<xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>可以连接和配置的服务终结点与之交互的对象创建运行的时所需的信息。  
  
 前面曾提到，然后才能使用它们，必须配置两种 WCF 客户端类型。 最简单的 WCF 客户端类型是派生的对象<xref:System.ServiceModel.ClientBase%601>(或<xref:System.ServiceModel.DuplexClientBase%601>如果服务协定是双工协定)。 通过使用以编程方式进行配置的构造函数，或者通过使用配置文件，然后直接调用该配置文件以调用服务操作，可以创建这些类型。 有关的基本概述<xref:System.ServiceModel.ClientBase%601>对象，请参阅[WCF 客户端概述](../../../../docs/framework/wcf/wcf-client-overview.md)。  
  
 第二个类型是在运行时从对 <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> 方法的调用中生成的。 通常涉及严格控制通信详细信息的应用程序使用此客户端类型，称为*客户端通道对象*，因为它可让更直接交互比基础的客户端运行时和通道系统。  
  
## <a name="channel-factories"></a>通道工厂  
 负责创建可支持客户端调用的基础运行时的类为 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> 类。 WCF 客户端对象和 WCF 客户端通道对象使用<xref:System.ServiceModel.ChannelFactory%601>对象来创建实例;<xref:System.ServiceModel.ClientBase%601>派生的客户端对象封装通道工厂的处理，但对于许多方案，它是非常合理直接通道工厂。 对此，常见的情况是从现有工厂重复创建新的客户端通道。 如果使用客户端对象，则可以通过调用，从 WCF 客户端对象获取基础通道工厂<xref:System.ServiceModel.ClientBase%601.ChannelFactory%2A?displayProperty=nameWithType>属性。  
  
 应该记住的是，在调用 <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> 之前，通道工厂会为所提供的配置创建客户端通道的新实例。 一旦您调用<xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A>(或<xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>， <xref:System.ServiceModel.ClientBase%601.CreateChannel%2A?displayProperty=nameWithType>，或在 WCF 客户端对象上的执行任何操作)，不能修改通道工厂和期待获取到不同的服务实例的通道即使只更改目标终结点地址。 如果您想用不同配置创建客户端对象或客户端通道，则必须首先创建新的通道工厂。  
  
 有关使用 WCF 客户端对象和 WCF 客户端通道的各种问题的详细信息，请参阅[使用 WCF 客户端访问服务](../../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)。  
  
 以下两个部分介绍创建和使用的 WCF 客户端通道对象。  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>创建新的 WCF 客户端通道对象  
 为了说明客户端通道的用法，假设已生成以下服务协定。  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 若要连接到 `ISampleService` 服务，请直接与通道工厂 (<xref:System.ServiceModel.ChannelFactory%601>) 一起使用生成的协定接口。 一旦为特定协定创建并配置通道工厂后，即可以调用 <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A> 方法以返回可用于与 `ISampleService` 服务通信的客户端通道对象。  
  
 当 <xref:System.ServiceModel.ChannelFactory%601> 类与服务协定接口一起使用时，您必须强制转换到 <xref:System.ServiceModel.IClientChannel> 接口以显式打开、关闭或中止通道。 为便于操作，Svcutil.exe 工具还生成一个帮助器接口，该接口可同时实现服务协定接口和 <xref:System.ServiceModel.IClientChannel> ，以使您无需进行强制转换就能够与客户端通道基础结构进行交互。 下面的代码演示实现上述服务协定的帮助器客户端通道的定义。  
  
 [!code-csharp[C_GeneratedCodeFiles#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#13)]  
  
#### <a name="creating-a-new-wcf-client-channel-object"></a>创建新的 WCF 客户端通道对象  
 若要使用客户端通道连接到 `ISampleService` 服务，请直接与通道工厂一起使用生成的协定接口（或帮助器版本），将协定接口的类型作为类型参数进行传递。 一旦为特定协定创建并配置通道工厂后，即可以调用 <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> 方法以返回可用于与 `ISampleService` 服务通信的客户端通道对象。  
  
 客户端通道对象在创建后可实现 <xref:System.ServiceModel.IClientChannel> 和协定接口。 因此，可以直接使用这些对象来调用操作，与支持该协定的服务进行交互。  
  
 使用客户端对象和客户端通道对象之间的区别仅仅在于其易于使用性和开发人员的喜好。 许多开发人员习惯于使用类和对象会更喜欢使用 WCF 客户端对象而不是 WCF 客户端通道。  
  
 有关示例，请参见 [如何：考虑使用 ChannelFactory](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)。
