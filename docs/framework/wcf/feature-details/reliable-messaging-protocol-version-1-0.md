---
title: 可靠消息传送协议版本 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: f45a0d5e50e9ab8a07a203d2c40ad36ef298a40d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497047"
---
# <a name="reliable-messaging-protocol-version-10"></a>可靠消息传送协议版本 1.0
本主题介绍 Windows Communication Foundation (WCF) 的实现详细信息，用于 Ws-reliable Messaging 2005 年 2 月 （版本 1.0） 协议需要使用 HTTP 传输进行互操作。 WCF 遵循 Ws-reliable Messaging 规范的约束和本主题中所述的说明。 请注意，WS-ReliableMessaging 版本 1.0 协议是从 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 开始实现的。  
  
 Ws-reliable Messaging 2005 年 2 月在通过的 WCF 中实现协议<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>。  
  
 为方便起见，本主题使用以下角色：  
  
-   发起方：启动 WS-Reliable Message 序列创建的客户端  
  
-   响应方：接收发起方的请求的服务  
  
 本文档使用下表中的前缀和命名空间。  
  
|前缀|命名空间|  
|------------|---------------|  
|wsrm|http://schemas.xmlsoap.org/ws/2005/02/rm|  
|netrm|http://schemas.microsoft.com/ws/2006/05/rm|  
|秒|http://www.w3.org/2003/05/soap-envelope|  
|wsa|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|wsse|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
  
## <a name="messaging"></a>消息  
  
### <a name="sequence-establishment-messages"></a>序列建立消息  
 WCF 实现`CreateSequence`和`CreateSequenceResponse`消息以建立可靠的消息序列。 适用以下约束：  
  
-   B1101: WCF 发起程序不会生成可选的 Expires 元素中`CreateSequence`消息或在情况下时`CreateSequence`消息包含`Offer`元素、 可选`Expires`中的元素`Offer`元素。  
  
-   B1102： 当访问`CreateSequence`消息时，WCF`Responder`发送和接收同时`Expires`如果它们存在，但不使用其值的元素。  
  
 WS-Reliable Messaging 引入了 `Offer` 机制来建立两个形成会话的反向相关的序列。  
  
-   R1103：如果 `CreateSequence` 包含一个 `Offer` 元素，则可靠消息响应方要么必须接受序列并使用包含形成两个相关反向序列的 `CreateSequenceResponse` 元素的 `wsrm:Accept` 进行响应，要么必须拒绝 `CreateSequence` 请求。  
  
-   R1104：在反向序列上流动的 `SequenceAcknowledgement` 和应用程序消息必须发送到 `ReplyTo` 的 `CreateSequence` 终结点引用。  
  
-   R1105：`AcksTo` 中的 `ReplyTo` 和 `CreateSequence` 终结点引用必须具有与八进制识别匹配的地址值。  
  
     WCF 响应方验证的 URI 部分`AcksTo`和`ReplyTo`创建序列之前 Epr 是否相同。  
  
-   R1106：`AcksTo` 中的 `ReplyTo` 和 `CreateSequence` 终结点引用应具有相同的引用参数集。  
  
     WCF 不强制但假定的该 [引用参数]`AcksTo`和`ReplyTo`上`CreateSequence`是相同的使用 [reference parameters] 从`ReplyTo`用于确认和相反序列消息的终结点引用。  
  
-   R1107：在使用 `Offer` 机制建立两个反向序列时，在反向序列上流动的 `SequenceAcknowledgement` 和应用程序消息必须发送到 `ReplyTo` 的 `CreateSequence` 终结点引用。  
  
-   R1108：使用 Offer 机制建立两个反向序列时，`[address]` 的 `wsrm:AcksTo` 元素的 `wsrm:Accept` 终结点引用子元素的 `CreateSequenceResponse` 属性必须与 `CreateSequence` 的识别字节的目标 URI 相匹配。  
  
-   R1109：在使用 `Offer` 机制建立两个反向序列时，发起方发送的消息和响应方的消息确认必须发送到同一个终结点引用。  
  
     WCF 使用 Ws-reliable Messaging 的发起方和响应方之间建立可靠会话。 WCF 的 Ws-reliable Messaging 实现提供可靠会话单向、 请求-答复和完全双工消息传递模式。 Ws-reliable Messaging`Offer`上的机制`CreateSequence` / `CreateSequenceResponse`使您可以建立两个相关的相反序列，并提供适合于所有消息终结点的会话协议。 WCF 提供了安全保证，包括会话完整性的端到端保护会话，因为它是可行以确保旨在到相同方的消息到达同一目标的。 这也允许在应用程序消息上捎带序列确认消息。 因此，约束 R1104、 R1105 和 R1108 适用于 WCF。  
  
 `CreateSequence` 消息的一个示例。  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action s:mustUnderstand="1">  
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequence  
    </a:Action>  
    <a:ReplyTo>  
      <a:Address>          
         http://Business456.com/clientA        
      </a:Address>  
    </a:ReplyTo>  
    <a:MessageID>  
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
    </a:MessageID>  
    <a:To s:mustUnderstand="1">  
      http://Business456.com/clientA  
    </a:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequence>  
      <wsrm:AcksTo>  
       <wsa:Address>  
         http://Business456.com/clientA  
       </wsa:Address>  
     </wsrm:AcksTo>  
     <wsrm:Offer>  
      <wsrm:Identifier>  
        urn:uuid:0afb8d36-bf26-4776-b8cf-8c91fddb5496  
      </wsrm:Identifier>  
     </wsrm:Offer>  
   </wsrm:CreateSequence>  
  </s:Body>  
</s:Envelope>  
```  
  
 `CreateSequenceResponse` 消息的一个示例。  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action s:mustUnderstand="1">  
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequenceResponse  
    </a:Action>  
    <a:RelatesTo>  
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
    </a:RelatesTo>  
    <a:To s:mustUnderstand="1">  
      http://Business456.com/clientA  
    </a:To>  
  </s:Header>  
  <s:Body>  
   <wsrm:CreateSequenceResponse>  
    <Identifier>  
     urn:uuid:eea0a36c-b38a-43e8-8c76-2fabe2d76386  
    </Identifier>  
    <Accept>  
    <AcksTo>  
      <a:Address>  
        http://BusinessABC.com/serviceA  
      </a:Address>  
    </AcksTo>  
    </Accept>  
   </wsrm:CreateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequence"></a>序列  
 以下是适用于序列的约束的列表：  
  
-   B1201:WCF 生成，并访问序列号不高于`xs:long`的最大非独占值，9223372036854775807。  
  
-   B1202:WCF 始终生成的操作 URI 的正文为空的最后一个消息的http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage。  
  
-   B1203: WCF 接收和传送序列标头包含的消息`LastMessage`只要操作 URI 不是元素http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage。  
  
 Sequence 标头的一个示例。  
  
```xml  
<wsrm:Sequence>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
  <wsrm:MessageNumber>  
    10  
  </wsrm:MessageNumber>  
  <wsrm:LastMessage/>  
 </wsrm:Sequence>  
```  
  
### <a name="ackrequested-header"></a>AckRequested 标头  
 WCF 使用`AckRequested`标头作为保持活动状态的机制。 WCF 不会生成可选`MessageNumber`元素。 在收到的消息`AckRequested`标头包含`MessageNumber`元素，WCF 将忽略`MessageNumber`元素的值，如下面的示例中所示。  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a>SequenceAcknowledgement 标头  
 WCF 将非法携带机制用于在 Ws-reliable Messaging 中提供的序列确认。  
  
-   R1401：使用 `Offer` 机制建立两个相反序列时，`SequenceAcknowledgement` 头可能包括在传输到预期接收方的任何应用程序消息中。  
  
-   B1402： 当 WCF 必须生成之前接收到任何序列消息确认时 (例如，若要满足`AckRequested`消息)，WCF 生成`SequenceAcknowledgement`包含范围 0-0，如下面的示例中所示的标头。  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B1403: WCF 不会生成`SequenceAcknowledgement`标头包含`Nack`元素，但支持`Nack`元素。  
  
### <a name="ws-reliablemessaging-faults"></a>WS-ReliableMessaging 错误  
 以下是适用于 WCF 实现的 WS 可靠消息传递故障的约束列表：  
  
-   B1501: WCF 不会生成`MessageNumberRollover`错误。  
  
-   B1502:WCF 终结点可能会生成`CreateSequenceRefused`错误规范中所述。  
  
-   B1503:When 服务终结点达到其连接限制，因此无法处理新连接时，WCF 将生成其他`CreateSequenceRefused`错误子代码`netrm:ConnectionLimitReached`，下面的示例中所示。  
  
    ```xml  
    <s:Envelope>  
      <s:Header>  
        <wsa:Action>  
          http://schemas.xmlsoap.org/ws/2005/08/addressing/fault  
        </wsa:Action>  
      </s:Header>  
      <s:Body>  
        <s:Fault>  
          <s:Code>  
            <s:Value>  
              s:Receiver  
            </s:Value>  
            <s:Subcode>  
              <s:Value>  
                wsrm:CreateSequenceRefused  
              </s:Value>  
              <s:Subcode>  
                <s:Value>  
                  netrm:ConnectionLimitReached  
                </s:Value>  
              </s:Subcode>  
            </s:Subcode>  
          </s:Code>  
          <s:Reason>  
            <s:Text xml:lang="en">  
              [Reason]  
            </s:Text>  
          </s:Reason>  
        </s:Fault>  
      </s:Body>  
    </s:Envelope>  
    ```  
  
### <a name="ws-addressing-faults"></a>WS-Addressing 错误  
 因为 Ws-reliable Messaging 使用 Ws-addressing，WCF Ws-reliable Messaging 实现可能生成 Ws-addressing 错误。 本部分介绍在 Ws-reliable Messaging 层显式生成 WCF Ws-addressing 错误：  
  
-   当满足下列情况之一时，B1601:WCF 生成消息寻址标头所需的错误：  
  
    -   消息缺少 `Sequence` 标头和 `Action` 标头。  
  
    -   `CreateSequence` 消息缺少 `MessageId` 标头。  
  
    -   `CreateSequence` 消息缺少 `ReplyTo` 标头。  
  
-   B1602:WCF 生成错误操作不支持以一条消息，缺少回复`Sequence`标头和具有`Action`不是可识别的 Ws-reliable Messaging 规范中的标头。  
  
-   B1603:WCF 生成终结点不可用，以指示终结点不会处理基于检查序列错误`CreateSequence`消息的寻址标头。  
  
## <a name="protocol-composition"></a>协议组合  
  
### <a name="composition-with-ws-addressing"></a>与 WS-Addressing 组合  
 WCF 支持 Ws-addressing 的两个版本： Ws-addressing 2004/08 [WS-ADDR] 以及 W3C Ws-addressing 1.0 建议 [WS ADDR 核] 和 [WS ADDR SOAP]。  
  
 尽管 WS-Reliable Messaging 规范只提及 WS-Addressing 2004/08，它并未限制要使用的 WS-Addressing 版本。 下面是适用于 WCF 的约束的列表：  
  
-   R2101： 这两个可以与 Ws-reliable Messaging 使用 Ws-addressing 2004/08 和 Ws-addressing 1.0。  
  
-   必须在给定 Ws-reliablemessaging 序列或通过使用相关的相反序列对整个使用 R2102:A 单个版本的 Ws-addressing`wsrm:Offer`机制。  
  
### <a name="composition-with-soap"></a>与 SOAP 组合  
 WCF 支持使用 SOAP 1.1 和 SOAP 1.2 与 Ws-reliable Messaging。  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>与 WS-Security 和 WS-SecureConversation 组合  
 WCF 提供了通过使用 Ws-secure Conversation 安全传输协议 (HTTPS)、 与 Ws-security、 组合和组合的 Ws-reliable Messaging 序列的保护。 下面是适用于 WCF 的约束的列表：  
  
-   R2301： 为了保护单个消息的完整性除了 Ws-reliable Messaging 序列的完整性和保密性，WCF 需要必须使用 Ws-secure Conversation。  
  
-   R2302:AWS-必须建立 Ws-reliable Messaging sequence(s) 前建立安全对话会话。  
  
-   R2303：如果 WS-Reliable Messaging 序列生存期超过了 WS-Secure Conversation 会话的生存期，则通过使用 WS-Secure Conversation 建立的 `SecurityContextToken` 必须通过使用相应的 WS-Secure Conversation 续订绑定来进行续订。  
  
-   B2304:WS 的可靠消息传递序列或一对相关的反向序列始终被绑定到单个 Ws-secureconversation 会话。  
  
     WCF 源生成`wsse:SecurityTokenReference`的元素扩展性节中的元素`CreateSequence`消息。  
  
-   与 Ws-secure Conversation 组合 R2305:When`CreateSequence`消息必须包含`wsse:SecurityTokenReference`元素。  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a>WS-Reliable Messaging WS-Policy 断言  
 WCF 使用 Ws-reliable Messaging Ws-policy 断言`wsrm:RMAssertion`描述终结点功能。 下面是适用于 WCF 的约束的列表：  
  
-   B3001: WCF 将附加`wsrm:RMAssertion`到 Ws-policy 断言`wsdl:binding`元素。 WCF 同时支持附加到`wsdl:binding`和`wsdl:port`元素。  
  
-   B3002: WCF 支持 Ws-reliable Messaging 断言的以下可选属性和对其进行控制了 WCF`ReliableMessagingBindingElement`:  
  
    -   `wsrm:InactivityTimeout`  
  
    -   `wsrm:AcknowledgementInterval`  
  
     下面是一个示例。  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a>流控制 WS-Reliable Messaging 扩展  
 WCF 使用 Ws-reliable Messaging 扩展性提供对序列消息流的可选更紧密控制。  
  
 通过设置启用流控制`ReliableSessionBindingElement`的`FlowControlEnabled``bool`属性`true`。 下面是适用于 WCF 的约束的列表：  
  
-   B4001： 启用可靠消息传递流控制时，WCF 生成`netrm:BufferRemaining`元素的元素扩展性中`SequenceAcknowledgement`标头。  
  
-   B4002： 启用可靠消息传递流控制时，WCF 不需要`netrm:BufferRemaining`元素必须存在于`SequenceAcknowledgement`标头，如下面的示例中所示。  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        http://fabrikam123.com/abc  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>  
        8  
      </netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B4003: WCF 使用`netrm:BufferRemaining`以指示多少条新消息可靠消息传递目标可以缓冲。  
  
-   B4004: WCF 可靠消息传递服务限制的传输时可靠消息传递目标应用程序不能快速接收消息的消息数量。 可靠消息传递目标将缓冲消息，而该元素的值将下降为 0。  
  
-   B4005: WCF 生成`netrm:BufferRemaining`整数值介于 0 和 4096 （含)，并读取介于 0 的整数值和`xs:int`的`maxInclusive`值 214748364 （含)。  
  
## <a name="message-exchange-patterns"></a>消息交换模式  
 Ws-reliable Messaging 用于不同消息交换模式时，本部分将介绍 WCF 的行为。 对于每个消息交换模式，可以考虑下面的两个部署方案：  
  
-   不可寻址发起方：发起方位于防火墙后面；响应方仅可以通过 HTTP 响应向发起方传递消息。  
  
-   可寻址的发起方：发起方和响应方都可以发送 HTTP 请求；换句话说，可以建立两个相反的 HTTP 连接。  
  
### <a name="one-way-non-addressable-initiator"></a>单向、不可寻址的发起方  
  
#### <a name="binding"></a>绑定  
 WCF 提供了通过一个 HTTP 通道使用一个序列的单向消息交换模式。 WCF 使用 HTTP 请求传输所有消息从 RMS 到 RMD，并在 HTTP 响应传输所有消息从 rmd 传输到 RMS。  
  
#### <a name="createsequence-exchange"></a>CreateSequence 交换  
 WCF 发起方生成`CreateSequence`未包含提议的消息。 WCF 响应方确保`CreateSequence`不包含提议之前创建序列。 WCF 响应方回复`CreateSequence`请求与`CreateSequenceResponse`消息。  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 WCF 发起方处理除之外的所有消息答复的确认`CreateSequence`消息和错误消息。 WCF 响应方始终生成这两个序列的响应中的一个独立的确认和`AckRequested`消息。  
  
#### <a name="terminatesequence-message"></a>TerminateSequence 消息  
 WCF 将`TerminateSequence`为单向操作，这意味着，HTTP 响应具有正文为空且 HTTP 202 状态代码。  
  
### <a name="one-way-addressable-initiator"></a>单向、可寻址的发起方  
  
#### <a name="binding"></a>绑定  
 WCF 提供了一个序列通过一个入站和出站 Http 通道使用的单向消息交换模式。 WCF 使用 HTTP 请求传输所有消息。 所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。  
  
#### <a name="createsequence-exchange"></a>CreateSequence 交换  
 WCF 发起方生成`CreateSequence`未包含提议的消息。 WCF 响应方确保`CreateSequence`不包含提议之前创建序列。 WCF 响应方传输`CreateSequenceResponse`消息的 HTTP 请求上发送与`ReplyTo`终结点引用。  
  
### <a name="duplex-addressable-initiator"></a>双工、可寻址的发起方  
  
#### <a name="binding"></a>绑定  
 WCF 提供了通过一个入站和出站 HTTP 通道使用两个序列的完全异步的双向消息交换模式。 WCF 使用 HTTP 请求传输所有消息。 所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。  
  
#### <a name="createsequence-exchange"></a>CreateSequence 交换  
 WCF 发起方生成`CreateSequence`通过提供的消息。 WCF 响应方确保`CreateSequence`包含在创建序列之前提议。 WCF 发送`CreateSequenceResponse`的 HTTP 请求上发送到`CreateSequence`的`ReplyTo`终结点引用。  
  
#### <a name="sequence-lifetime"></a>序列生存期  
 WCF 将两个序列视为一个全双工会话。  
  
 在生成使一个序列出错的错误时，WCF 期望远程终结点中，使这两个序列。 在读取使一个序列出错的错误，WCF 错误这两个序列。  
  
 WCF 可以关闭其出站序列并继续处理其入站序列上的消息。 相反，WCF 可以处理入站序列的关闭，并继续在其出站序列上发送消息。  
  
### <a name="request-reply-non-addressable-initiator"></a>请求-答复、不可寻址的发起方  
  
#### <a name="binding"></a>绑定  
 WCF 提供了单向和请求-答复消息交换模式使用两个序列通过在一个 HTTP 通道。 WCF 使用 HTTP 请求传输请求序列消息，并使用 HTTP 响应传输答复序列的消息。  
  
#### <a name="createsequence-exchange"></a>CreateSequence 交换  
 WCF 发起方生成`CreateSequence`通过提供的消息。 WCF 响应方确保`CreateSequence`包含在创建序列之前提议。 WCF 响应方回复`CreateSequence`请求与`CreateSequenceResponse`消息。  
  
#### <a name="one-way-message"></a>单向消息  
 若要成功完成单向消息交换协议，WCF 发起方传输请求序列消息的 HTTP 请求上和接收独立`SequenceAcknowledgement`HTTP 响应上的消息。 `SequenceAcknowledgement` 必须确认已传输的消息。  
  
 WCF 响应来答复请求通过确认、 错误或正文空且具有 HTTP 202 状态代码的响应。  
  
#### <a name="two-way-messages"></a>双向消息  
 若要成功地完成双向消息交换协议，WCF 发起方传输请求序列消息的 HTTP 请求上和接收 HTTP 响应上的答复序列消息。 响应必须包含一个确认已传输的请求序列消息的 `SequenceAcknowledgement`。  
  
 WCF 响应来答复请求使用的应用程序答复、 错误或正文空且具有 HTTP 202 状态代码的响应。  
  
 由于存在单向消息和应用程序答复的计时，因此请求序列消息的序列号与响应消息的序列号不相关联。  
  
#### <a name="retrying-replies"></a>重试答复  
 WCF 依赖于 HTTP 请求-答复关联来进行双向消息交换协议关联。 因此，WCF 发起程序不会停止重试请求序列消息，而不是在 HTTP 响应携带确认消息、 用户消息或错误时确认请求序列消息。 WCF 响应方重试向其在答复与其相关的请求在 HTTP 请求路线上的答复。  
  
#### <a name="lastmessage-exchange"></a>LastMessage 交换  
 WCF 发起程序生成并传输空空的 HTTP 请求路线上最后一个消息。 WCF 需要一个响应，但忽略实际响应消息。 WCF 响应方答复请求序列的正文为空的最后一条消息与答复序列的最后一条消息正文为空的。  
  
 如果 WCF 响应方接收在其中的操作 URI 不是最后一条消息http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage，WCF 使用最后一条消息进行回复。 在双向消息交换协议中，最后一条消息携带应用程序消息；在单向消息交换协议中，最后一条消息为空。  
  
 WCF 响应方不需要答复序列的正文为空的最后一条消息的确认。  
  
#### <a name="terminatesequence-exchange"></a>TerminateSequence 交换  
 当所有请求已都接收了有效的回复时，WCF 发起程序生成并传输请求序列的`TerminateSequence`HTTP 请求路线上的消息。 WCF 需要一个响应，但忽略实际响应消息。 WCF 响应方答复请求序列的`TerminateSequence`与答复序列消息`TerminateSequence`消息。  
  
 在正常的关闭序列中，两个 `TerminateSequence` 消息都携带一个完整范围的 `SequenceAcknowledgement`。  
  
### <a name="requestreply-addressable-initiator"></a>请求/答复、可寻址的发起方  
  
#### <a name="binding"></a>绑定  
 WCF 提供了使用两个序列通过一个入站和出站 HTTP 通道请求-答复消息交换模式。 WCF 使用 HTTP 请求传输所有消息。 所有 HTTP 响应的正文都为空，并且具有 HTTP 202 状态代码。  
  
#### <a name="createsequence-exchange"></a>CreateSequence 交换  
 WCF 发起方生成`CreateSequence`通过提供的消息。 WCF 响应方确保`CreateSequence`包含在创建序列之前提议。 WCF 发送`CreateSequenceResponse`的 HTTP 请求上发送到`CreateSequence`的`ReplyTo`终结点引用。  
  
#### <a name="requestreply-correlation"></a>请求/答复关联  
 WCF 发起方确保所有应用程序请求消息都具有`MessageId`和`ReplyTo`终结点引用。 WCF 发起程序适用`CreateSequence`消息的`ReplyTo`上每个应用程序请求消息的终结点引用。 WCF 响应方要求传入的请求消息具有`MessageId`和`ReplyTo`。 WCF 响应方确保这两者的终结点引用的 URI`CreateSequence`和所有应用程序请求消息是相同的。
