---
title: "WSTrustChannelFactory 和 WSTrustChannel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 96cec467-e963-4132-b18b-7d0b3a2e979f
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# WSTrustChannelFactory 和 WSTrustChannel
如果您已经熟悉 Windows Communication Foundation \(WCF\)，则可以断定 WCF 客户已识别的联合。  通过配置具有 <xref:System.ServiceModel.WSFederationHttpBinding> 或类似的自定义绑定的一个 WCF 客户端上，可以启用的联合为身份验证服务。  
  
 WCF 获取由安全令牌服务 \(STS\) 在幕后发出的标记并使用此标记验证到服务。  对此方法的主要限制不可见性与客户端的服务器通信。  WCF 自动生成请求安全令牌 \(RST\) 为基于发出的标记 STS 参数的绑定。  这意味着客户不能更改 RST 参数随请求，检查请求安全令牌响应 \(RSTR\) 获取信息如显示声明或缓存标记后使用。  
  
 目前，WCF 客户适合基关联的方案。  但是，Windows 标识基础 \(WIF\) 支持的一个主要方案需要对 RST 的控制在 WCF 轻松不允许的级别。  WIF 因此，将使您能够更多控制与通信的 STS 的功能。  
  
 WIF 联合支持以下方案：  
  
-   使用无身份验证的任何 WIF 依赖，将一个 WCF 客户为联合的服务  
  
-   使 WCF 客户端的 ActAs WIF 插入或 OnBehalfOf 元素到 RST 到 STS  
  
-   使用单独的 STS WIF 然后使从获取的标记 WCF 客户端验证使用该标记。  有关更多信息，请参见 [ClaimsAwareWebService](http://go.microsoft.com/fwlink/?LinkID=248406) 中的示例。  
  
 第一种是截然不同的：现有 WCF 客户端继续与 WIF 关系方和 STSs 一起使用。  本主题讨论的其余两种情况。  
  
## 引发一 ActAs\/OnBehalfOf 的现有 WCF 客户  
 在典型的方案中，客户端服务标识委托调用中间层，然后调用一后端服务。  中间层服务充当或操作，代表客户。  
  
> [!TIP]
>  ActAs 和 OnBehalfOf 具有的差异？  
>   
>  从 procotol WS\-Trust 位置：  
>   
>  1.  ActAs 元素指示 RST 请求者让包含有关声明两个不同的实体的标记：请求者以及在 ActAs 元素的标记表示实体的外部。  
> 2.  OnBehalfOf 元素指示 RST 请求者希望只有包含元素声明为实体的标记：在 OnBehalfOf 元素的标记表示实体的外部。  
>   
>  ActAs 功能通常用在需要委托，发出最终标记复合的接收者可以检查整个链委托以及查看不仅客户，但所有中间的方案。  这让其执行基于整个标识将字符串和其他相关活动的访问控制和审核。  ActAs 功能通常在多层的系统验证和传递有关的标识信息。层之间，而无需将此信息在应用程序或业务逻辑层。  
>   
>  OnBehalfOf 功能最初仅在客户标识重要并有效与标识模拟功能可用窗口中的方案。  当使用时 OnBehalfOf，发出的是最终只能看到有关原始客户端声明，并且，中间不保留有关的信息。  OnBehalfOf 功能使用的常见模式是客户端无法访问 STS 直接，而的代理模式通过代理网关进行通信。  代理网关验证调用方并使调用方有关的信息放入然后路由到处理的实际 STS RST 信息的 OnBehalfOf 元素。  得到的标记包含只有声明与的客户代理，使代理能够完全透明的颁发的接收器。WIF 请注意不支持 \<wsse:SecurityTokenReference\> 或 \<wsa:EndpointReferences\> 作为 \<wst:OnBehalfOf\> 的子。  WS\-Trust 规范中是允许三种方式标识原始请求 \(代表用户代理操作\)。  这些是：  
>   
>  -   安全标记引用。  对标记的引用，在消息或能检索到带的外部\)。  
> -   终结点引用。  用于键，搜索数据，再从带区外部。  
> -   安全标记。  直接以标识初始请求。  
>   
>  WIF 只支持安全令牌，加密或未加密，以 wst 一个 \<wst:OnBehalfOf\> 直接子元素。  
  
 使用在 RST，的 ActAs 和 OnBehalfOf 标记元素中传达此信息。WS\-Trust 发出者。  
  
 WCF 公开允许任意 XML 元素添加到 RST 绑定的一个扩展性点。  但是，因为扩展点附加到绑定，需要的情况 RST 内容每调用更改必须再次创建每次调用的客户，会降低性能。  WIF 使用 `ChannelFactory` 类的扩展方法允许开发人员获取从附加 RST 的条带外部的任何标记。  下面的代码示例演示如何将表示客户的 X.509 \(如标记、用户名或安全断言 Markup Language \(SAML\) \-标记\) 并将其附加到 RST 的发出者发送到。  
  
```  
IHelloService serviceChannel = channelFactory.CreateChannelActingAs<IHelloService>( clientSamlToken );  
serviceChannel.Hello(“Hi!”);  
```  
  
 WIF 提供以下优点：  
  
-   RST 可以每个通道修改；中间层服务，因此无需重新创建各个客户端上的通道工厂，从而提高性能。  
  
-   这样做与现有 WCF 客户，使一种的升级路径就可以为现有中间层若要启用 WCF 服务标识委托语义。  
  
 但是，仍没有可见性。STS 客户的通信。  我们将查看这一点。第三个方案。  
  
## 通信直接与发出者和使用发出的标记验证  
 对于一些高级方案，引发 WCF 客户不足够。  通常使用 WCF 消息仅使用在\/消息协定并手动处理客户端发出者分析响应的开发人员。  
  
 WIF 介绍 <xref:System.ServiceModel.Security.WSTrustChannelFactory> 和 <xref:System.ServiceModel.Security.WSTrustChannel> 类使客户直接与 WS\-Trust 发出者进行通信。  <xref:System.ServiceModel.Security.WSTrustChannelFactory> 和 <xref:System.ServiceModel.Security.WSTrustChannel> 类支持到流的强类型的 RST 和对象 RSTR 在客户端发出者和之间，如下面的代码示例所示。  
  
```  
WSTrustChannelFactory trustChannelFactory = new WSTrustChannelFactory( stsBinding, stsAddress );  
WSTrustChannel channel = (WSTrustChannel) trustChannelFactory.CreateChannel();  
RequestSecurityToken rst = new RequestSecurityToken(RequestTypes.Issue);  
rst.AppliesTo = new EndpointAddress(serviceAddress);  
RequestSecurityTokenResponse rstr = null;  
SecurityToken token = channel.Issue(rst, out rstr);  
```  
  
 请注意 <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> 方法的 `out` 参数可为 RSTR 的访问客户端检查的。  
  
 到目前为止，我们仅看到了获取标记。  从返回 <xref:System.ServiceModel.Security.WSTrustChannel> 对象的标记。包含任何信息用于进行身份验证是必需的。关系方的 `GenericXmlSecurityToken`。  下面的代码示例演示如何使用此标记。  
  
```  
IHelloService serviceChannel = channelFactory.CreateChannelWithIssuedToken<IHelloService>( token ); serviceChannel.Hello(“Hi!”);  
```  
  
 在 `ChannelFactory` 对象上调用 <xref:System.ServiceModel.ChannelFactory%601.CreateChannelWithIssuedToken%2A> 扩展方法向指示 WIF 您获得一标记从带外部，因此，有时应停止常规调用 WCF 的颁发者和使用验证关系方获取到的标记。  这具有以下优点：  
  
-   为您对标记发布过程的完全控制。  
  
-   它通过直接设置在发出的 RST 的属性支持 ActAs\/OnBehalfOf 方案。  
  
-   其启用动态客户端计算机的信任决定使基于 RSTR 的内容。  
  
-   它允许您缓存和重用从 <xref:System.ServiceModel.Security.WSTrustChannel.Issue%2A> 方法返回的标记。  
  
-   <xref:System.ServiceModel.Security.WSTrustChannelFactory> 和 <xref:System.ServiceModel.Security.WSTrustChannel> 都允许通道缓存、错误和语义恢复控件根据 WCF 最佳做法。  
  
## 请参阅  
 [WIF 功能](../../../docs/framework/security/wif-features.md)