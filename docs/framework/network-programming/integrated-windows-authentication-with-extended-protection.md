---
title: "带有扩展保护的集成 Windows 身份验证 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 81731998-d5e7-49e4-ad38-c8e6d01689d0
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# 带有扩展保护的集成 Windows 身份验证
改进来影响集成Windows身份验证方式。 <xref:System.Net.HttpWebRequest>处理、 <xref:System.Net.HttpListener>、 <xref:System.Net.Mail.SmtpClient>、 <xref:System.Net.Security.SslStream>、 <xref:System.Net.Security.NegotiateStream>和相关的选件类在 <xref:System.Net> 和相关的命名空间。  已添加以扩展保护可以增强安全性。  
  
 这些更改会影响使用这些选件类进行web请求和接收答复使用集成Windows身份验证的应用程序。  此更改也会影响配置为使用集成Windows身份验证的web服务器和客户端应用程序。  
  
 这些更改也会影响使用这些选件类进行其他类型请求和接收答复使用集成Windows身份验证的应用程序。  
  
 支持扩展保护的更改为在Windows 7和Windows server 2008 R2的应用程序可用。  扩展的保护功能在早期版本的 Windows 上不可用。  
  
## 概述  
 集成 Windows 身份验证 \(IWA\) 的设计允许某些凭据质询响应是通用的，这意味着它们可以被重用或转发。  最好也是构造质询\-响应在最小与目标特定的信息和一些通道特定信息。  服务可以提供扩展保护确保凭据质询\-响应包含服务特定的信息\(如服务主体名称\(SPN\)。  在凭据交换的此信息，服务可以更好地防范可能错误地使用了对凭据质询\-响应的恶意用途。  
  
 扩展保护模型是增强功能旨在的身份验证协议缓解身份验证出现攻击。  它包含通道和服务绑定信息的概念。  
  
 总体目标如下:  
  
1.  如果更新客户端支持扩展保护，应用程序应提供通道绑定和服务绑定信息。所有支持的身份验证协议。  只能提供通道的绑定信息时，将会绑定的通道\(TLS时\)。  应始终提供服务绑定信息。  
  
2.  正确配置的更新服务器可以验证通道和服务绑定信息，则存在于客户端身份验证标记时和拒绝身份验证尝试，如果通道绑定不匹配。  根据部署方案，服务器可能会验证通道绑定，服务绑定或两个。  
  
3.  更新服务器能够接受或拒绝未包含基于策略的通道的绑定信息的下级客户端请求。  
  
 扩展保护使用的信息包括以下两个部件一个或两个:  
  
1.  通道约束标记或CBT。  
  
2.  在服务主体名称或SPN的形式服务绑定信息。  
  
 服务绑定信息是客户端的目的表示验证对特定服务终结点。  它从客户端传递到服务器具有以下属性:  
  
-   SPN值必须可用于执行客户端身份验证的服务器以明文形式。  
  
-   SPN的值是公共的。  
  
-   必须密码保护SPN在传输过程中这样的中间人攻击不能插入，移除或修改它的值。  
  
 CBT是属性之外安全通道\(例如TLS\)用于对关系\(绑定\)它可在一个内部，客户端验证的通道。  CBT必须具有以下特性\(还定义是IETF RFC 5056\):  
  
-   当一个外部类型的通道时， CBT的值必须是标识外部或服务器通道终结点的属性，独立达到由对话的客户端和服务器端。  
  
-   客户端发送的CBT的值不能为攻击者可能影响的操作。  
  
-   确保没有对CBT值的保密。  但这并不意味着服务绑定以及通道的绑定信息的值可以由任何其他，但执行身份验证的服务器始终检查，作为带有CBT的协议可以进行加密。  
  
-   CBT必须密码来保护在传输过程中这样的完整性攻击者不能插入，移除或修改它的值。  
  
 通道绑定由调用SPN和CBT的客户端完成到服务器可防作弊的方式。  服务器验证通道的绑定信息与其策略与并拒绝它不认为自己是预期目标的身份验证尝试。  这样，两个通道变为。密码绑定。  
  
 若要保留与现有的客户端和应用程序的兼容性，服务器可能不支持扩展保护的客户端配置为允许身份验证尝试。  与“完整地硬化的”配置不同，这称为“部分已硬化的”配置，。  
  
 在 <xref:System.Net> 和 <xref:System.Net.Security> 命名空间的多个元素委托调用的应用程序执行集成Windows身份验证。  本节介绍针对System.Net元素的更改添加到集成Windows身份验证的其用法的扩展保护。  
  
 扩展保护在Windows 7.当前支持。  提供一种机制，使应用程序可以确定操作系统是否支持扩展保护。  
  
## 支持扩展保护的更改  
 身份验证过程使用集成Windows身份验证，具体取决于使用的身份验证协议，通常包括挑战由atlduck.exe目标计算机和发送回客户端计算机。  扩展保护添加新功能。此身份验证过程  
  
 <xref:System.Security.Authentication.ExtendedProtection> 命名空间使用应用程序扩展保护为身份验证提供支持。  此命名空间中的 <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> 选件类表示通道绑定。  此命名空间中的 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> 选件类表示服务器中的扩展保护策略验证传入的客户端连接。  其他选件类成员用于扩展保护。  
  
 对服务器应用程序，这些选件类包括:  
  
 具有下列元素的 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> :  
  
-   指示的 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.OSSupportsExtendedProtection%2A> 属性操作系统是否支持与扩展保护的集成windows身份验证。  
  
-   一个 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 值，指示应何时强制实施扩展的保护策略。  
  
-   指示部署方案的 <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> 值。  这会影响扩展保护如何进行检查。  
  
-   包含的选项 <xref:System.Security.Authentication.ExtendedProtection.ServiceNameCollection> 用于匹配客户端提供的SPN的自定义SPN列表，身份验证的预期目标。  
  
-   包含自定义通道绑定用于验证的选项 <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> 。  此方案不是一种常见情况  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration> 命名空间使用应用程序扩展保护为身份验证配置提供支持。  
  
 给定数的功能更改支持在现有 <xref:System.Net> 命名空间的扩展保护。  这些更改包括:  
  
-   新 <xref:System.Net.TransportContext> 选件类添加到表示传输上下文的 <xref:System.Net> 命名空间。  
  
-   新 <xref:System.Net.HttpWebRequest.EndGetRequestStream%2A> 和 <xref:System.Net.HttpWebRequest.GetRequestStream%2A> 重载允许检索 <xref:System.Net.TransportContext> 支持客户端应用程序的扩展保护在 <xref:System.Net.HttpWebRequest> 选件类的方法。  
  
-   对于支持服务器应用程序的 <xref:System.Net.HttpListener> 和 <xref:System.Net.HttpListenerRequest> 选件类的添加。  
  
 函数做出支持SMTP客户端应用程序的扩展保护在现有 <xref:System.Net.Mail> 命名空间:  
  
-   在表示SPN进行身份验证使用，在使用时的 <xref:System.Net.Mail.SmtpClient> 选件类的一个 <xref:System.Net.Mail.SmtpClient.TargetName%2A> 属性扩展的SMTP客户端应用程序的保护。  
  
 给定数的功能更改支持在现有 <xref:System.Net.Security> 命名空间的扩展保护。  这些更改包括:  
  
-   新 <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsClient%2A> 和 <xref:System.Net.Security.NegotiateStream.AuthenticateAsClient%2A> 重载允许通过CBT支持客户端应用程序的扩展保护在 <xref:System.Net.Security.NegotiateStream> 选件类的方法。  
  
-   新 <xref:System.Net.Security.NegotiateStream.BeginAuthenticateAsServer%2A> 和 <xref:System.Net.Security.NegotiateStream.AuthenticateAsServer%2A> 重载允许通过 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> 支持服务器应用程序的扩展保护在 <xref:System.Net.Security.NegotiateStream> 选件类的方法。  
  
-   在支持客户端和服务器应用程序的扩展保护的 <xref:System.Net.Security.SslStream> 选件类的新 <xref:System.Net.Security.SslStream.TransportContext%2A> 属性。  
  
 <xref:System.Net.Configuration.SmtpNetworkElement> 属性添加支持扩展保护的配置SMTP客户端的 <xref:System.Net.Security> 命名空间的。  
  
## 客户端应用程序的扩展保护  
 扩展保护对于大多数客户端应用程序支持自动发生。  <xref:System.Net.HttpWebRequest> 和 <xref:System.Net.Mail.SmtpClient> 选件类支持扩展保护，只要Windows的基础版本支持扩展保护。  <xref:System.Net.HttpWebRequest> 实例从 <xref:System.Uri>发送构造的SPN。  默认情况下， <xref:System.Net.Mail.SmtpClient> 实例从SMTP邮件服务器的主机名发送构造的SPN。  
  
 为自定义身份验证，客户端应用程序可以使用 <xref:System.Net.HttpWebRequest.EndGetRequestStream%28System.IAsyncResult%2CSystem.Net.TransportContext%40%29?displayProperty=fullName> 或使用 <xref:System.Net.TransportContext.GetChannelBinding%2A> 方法，允许检索 <xref:System.Net.TransportContext> 和CBT在 <xref:System.Net.HttpWebRequest> 的 <xref:System.Net.HttpWebRequest.GetRequestStream%28System.Net.TransportContext%40%29?displayProperty=fullName> 方法类别。  
  
 使用的SPN为 <xref:System.Net.HttpWebRequest> 实例发送的集成Windows身份验证到特定服务可以通过设置 <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A> 属性重写。  
  
 <xref:System.Net.Mail.SmtpClient.TargetName%2A> 属性可用于SMTP连接用于设置自定义SPN使用集成Windows身份验证。  
  
## 服务器应用程序的扩展保护  
 ，在执行HTTP身份验证时，<xref:System.Net.HttpListener> 为验证服务绑定自动提供结构。  
  
 最安全的情况是启用HTTPS:\/\/标题的扩展保护。  在这种情况下，将 <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=fullName> 到 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> 和 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 设置为 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 或 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement>，并且， <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> 设置为 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 的 <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> 的值在部分已硬化模式中， <xref:System.Net.HttpListener> ，而 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 对应于完整地硬化模式。  
  
 在此配置中，当请求对服务器通过外时安全通道，外部通道的通道绑定查询。  此通道绑定传递给身份验证SSPI调用，验证将身份验证blob的通道匹配。  有三个可能的结果:  
  
1.  服务器的基础操作系统不支持扩展保护。  该请求不会显示在应用程序，并且，一种未经授权的\(401个\)响应将返回到客户端。  消息将记录到指定的根源的 <xref:System.Net.HttpListener> 跟踪源。该失败。  
  
2.  SSPI调用失败表明一客户端指定了没有与从外部通道或客户端检索的预期值未提供通道绑定的通道绑定，当服务器上的扩展保护策略在 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement>配置了。  在这两种情况下，该请求不会显示在应用程序，并且，一种未经授权的\(401个\)响应将返回到客户端。  消息将记录到指定的根源的 <xref:System.Net.HttpListener> 跟踪源。该失败。  
  
3.  客户端指定正确的通道的绑定或允许连接，而无需指定通道绑定，因为对服务器的扩展保护策略配置为该请求返回到处理应用程序的 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 。  服务名检查不会自动执行。  使用 <xref:System.Net.HttpListenerRequest.ServiceName%2A> 属性，应用程序可以选择执行自己的服务名称验证，但是，在这些情况下它是多余的。  
  
 如果应用程序执行自己的SSPI调用根据blob的身份验证来回传递在HTTP请求体内并希望支持通道绑定，需要从外部检索绑定所需的通道安全通道使用 <xref:System.Net.HttpListener> 以传递给本机Win32 [AcceptSecurityContext](http://go.microsoft.com/fwlink/?LinkId=147021) 函数。  为此，请使用 <xref:System.Net.HttpListenerRequest.TransportContext%2A> 属性并调用 <xref:System.Net.TransportContext.GetChannelBinding%2A> 方法检索CBT。  仅终结点绑定的支持。  如果任何其他 <xref:System.Security.Authentication.ExtendedProtection.ChannelBindingKind> 指定， <xref:System.NotSupportedException> 将引发异常。  如果基础操作系统支持通道绑定， <xref:System.Net.TransportContext.GetChannelBinding%2A> 方法将返回 <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding> 包装指针的 <xref:System.Runtime.InteropServices.SafeHandle> 到通道绑定应用于传递给 [AcceptSecurityContext](http://go.microsoft.com/fwlink/?LinkId=147021) 函数为 `pInput` 参数传递的SecBuffer结构的pvBuffer成员。  <xref:System.Security.Authentication.ExtendedProtection.ChannelBinding.Size%2A> 属性以字节为单位\)，通道绑定包含该长度，。  如果基础操作系统不支持通道绑定，函数返回 `null`。  
  
 ，在不使用时，另一个可能的方案是使HTTP:\/\/标题的扩展保护代理。  在这种情况下，将 <xref:System.Net.HttpListener.ExtendedProtectionPolicy%2A?displayProperty=fullName> 到 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> 和 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 设置为 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 或 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement>，并且， <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> 设置为 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 的 <xref:System.Security.Authentication.ExtendedProtection.ProtectionScenario> 的值在部分已硬化模式中， <xref:System.Net.HttpListener> ，而 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 对应于完整地硬化模式。  
  
 默认名称基于前缀将创建一 <xref:System.Net.HttpListener>注册的列表允许的服务。  此默认列出了可以通过 <xref:System.Net.HttpListener.DefaultServiceNames%2A> 属性中检查。  如果此列表不全面，应用程序可以指定自定义集合 <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> 选件类上使用而不是默认服务列表在构造函数的名称。  
  
 在此配置中，那么，当请求对服务器，而无需外时通常安全通道身份验证提升，没有通道绑定检查。  如果身份验证成功，上下文可用于客户端提供和验证接受服务名列表的服务名称将查询。  有四种可能的结果:  
  
1.  服务器的基础操作系统不支持扩展保护。  该请求不会显示在应用程序，并且，一种未经授权的\(401个\)响应将返回到客户端。  消息将记录到指定的根源的 <xref:System.Net.HttpListener> 跟踪源。该失败。  
  
2.  客户端的基础操作系统不支持扩展保护。  在 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 配置，身份验证尝试将成功，并且该请求将返回到应用程序。  在 <xref:System.Security.Authentication.ExtendedProtection.PolicyEnforcement> 配置，身份验证尝试将失败。  该请求不会显示在应用程序，并且，一种未经授权的\(401个\)响应将返回到客户端。  消息将记录到指定的根源的 <xref:System.Net.HttpListener> 跟踪源。该失败。  
  
3.  客户端的基础操作系统支持扩展保护，但是，应用程序没有指定服务绑定。  该请求不会显示在应用程序，并且，一种未经授权的\(401个\)响应将返回到客户端。  消息将记录到指定的根源的 <xref:System.Net.HttpListener> 跟踪源。该失败。  
  
4.  客户端指定了服务绑定。  服务绑定与允许的服务绑定比较列表。  如果匹配，请求返回给应用程序。  否则，该请求不会显示在应用程序，并且，一种未经授权的\(401个\)响应将自动返回到客户端。  消息将记录到指定的根源的 <xref:System.Net.HttpListener> 跟踪源。该失败。  
  
 如果使用允许的此简单的方法名称都是不够的列表接受服务，应用程序可以通过查询 <xref:System.Net.HttpListenerRequest.ServiceName%2A> 属性提供自己的服务名称验证。  在情况1和2上，此属性将返回 `null`。  在第3种情况中，将返回空字符串。  在第4种情况中，客户端指定的服务名称将返回。  
  
 这些扩展保护功能可以通过身份验证的服务器应用程序还用于请求的其他类型，所以，当使用受信任的代理。  
  
## 请参阅  
 <xref:System.Security.Authentication.ExtendedProtection>   
 <xref:System.Security.Authentication.ExtendedProtection.Configuration>