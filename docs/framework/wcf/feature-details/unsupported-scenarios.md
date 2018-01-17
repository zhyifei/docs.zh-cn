---
title: "不支持的方案"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72027d0f-146d-40c5-9d72-e94392c8bb40
caps.latest.revision: "43"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96ae88fd29391bf173da33398dfb41b3a06441ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="unsupported-scenarios"></a>不支持的方案
由于各种原因，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 不支持某些特定安全方案。 例如，[!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition 没有实现 SSPI 或 Kerberos 身份验证协议，因此 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 在该平台上不支持使用 Windows 身份验证来运行服务。 在 Windows XP Home Edition 下运行 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 时，支持其他身份验证机制，例如用户名/密码和 HTTP/HTTPS 集成身份验证。  
  
## <a name="impersonation-scenarios"></a>模拟方案  
  
### <a name="impersonated-identity-might-not-flow-when-clients-make-asynchronous-calls"></a>当客户端进行异步调用时可能无法流动模拟标识  
 当 WCF 客户端通过模拟使用 Windows 身份验证对 WCF 服务进行异步调用时，可能会使用客户端进程的标识进行身份验证，而不是使用模拟的标识进行身份验证。  
  
### <a name="windows-xp-and-secure-context-token-cookie-enabled"></a>启用了 Windows XP 和安全上下文令牌 Cookie  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不支持模拟。存在下列条件时，将引发 <xref:System.InvalidOperationException>：  
  
-   操作系统为 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]。  
  
-   身份验证模式产生 Windows 标识。  
  
-   <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> 的 <xref:System.ServiceModel.OperationBehaviorAttribute> 属性设置为 <xref:System.ServiceModel.ImpersonationOption.Required>。  
  
-   创建了基于状态的安全上下文令牌 (SCT)。默认情况下禁止创建此类令牌。  
  
 基于状态的 SCT 只能使用自定义绑定来创建。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][如何： 创建安全上下文令牌的安全会话](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)。)在代码中，可通过创建安全绑定元素（<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 或 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>）启用令牌，方法是：使用 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%28System.Boolean%29?displayProperty=nameWithType> 或 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%28System.ServiceModel.Channels.SecurityBindingElement%2CSystem.Boolean%29?displayProperty=nameWithType> 方法，并且将 `requireCancellation` 参数设置为 `false`。 该参数引用 SCT 的缓存。 若将该值设置为 `false`，则启用基于状态的 SCT 功能。  
  
 或者，在配置中，令牌启用通过创建 <`customBinding`>，然后添加 <`security`> 元素，并设置`authenticationMode`属性设为 SecureConversation 和`requireSecurityContextCancellation`属性设为`true`。  
  
> [!NOTE]
>  上述需求是特定的。 例如，<xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> 创建一个产生 Windows 标识的绑定元素，但并不建立一个 SCT。 因此，在 `Required` 上，可以将其与 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 选项一起使用。  
  
### <a name="possible-aspnet-conflict"></a>可能发生 ASP.NET 冲突  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 和 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 都可能启用或禁用模拟。 当 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 承载 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 和 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 配置设置之间可能存在冲突。 如果发生冲突，将优先采用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 设置，除非 <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> 属性设置为 <xref:System.ServiceModel.ImpersonationOption.NotAllowed>（在这种情况下，[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 模拟设置优先）。  
  
### <a name="assembly-loads-may-fail-under-impersonation"></a>程序集加载操作可能在模拟下失败  
 如果所模拟的上下文没有加载程序集的访问权限，并且这是公共语言运行库 (CLR) 第一次试图加载该 AppDomain 的程序集，则 <xref:System.AppDomain> 会缓存失败。 随后进行的加载该程序集（或多个程序集）的尝试仍将失败，即使撤消了模拟，并且恢复之后的上下文具有加载该程序集的访问权限。 这是因为，用户上下文更改后，CLR 不会重新尝试加载。 必须重新启动应用程序域才能从失败中恢复。  
  
> [!NOTE]
>  <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> 类的 <xref:System.ServiceModel.Security.WindowsClientCredential> 属性的默认值为 <xref:System.Security.Principal.TokenImpersonationLevel.Identification>。 大多数情况下，标识级模拟上下文不具有加载任何其他程序集的权限。 这是默认值，因此这是一个需要注意的非常常见的条件。 当模拟进程不具有 `SeImpersonate` 特权时，也会发生标识级模拟。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][委托和模拟](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)。  
  
### <a name="delegation-requires-credential-negotiation"></a>委托要求凭据协商  
 若要将 Kerberos 身份验证协议与委托联合使用，必须实现带有凭据协商的 Kerberos 协议（有时称作多段或多步 Kerberos）。 如果不用凭据协商来实现 Kerberos 协议（有时称作单稳或单路 Kerberos），则会引发异常。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]如何实现凭据协商，请参阅[调试 Windows 身份验证错误](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)。  
  
## <a name="cryptography"></a>密码  
  
### <a name="sha-256-supported-only-for-symmetric-key-usages"></a>仅为对称密钥的使用支持 SHA-256  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 支持多种加密和签名摘要创建算法，可以在系统提供的绑定中使用算法组加以指定。 为了提高安全性，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 支持使用安全哈希算法 (SHA) 2 算法（具体说就是 SHA-256）来创建签名摘要哈希。 此版本仅在使用对称密钥（例如，Kerberos 密钥）并且没有使用 X.509 证书对消息进行签名的情况下才支持 SHA-256。 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不支持使用 SHA-256 哈希进行 RSA 签名（在 X.509 证书中使用），因为 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 中当前缺少对 RSA-SHA256 的支持。  
  
### <a name="fips-compliant-sha-256-hashes-not-supported"></a>不支持与 FIPS 兼容的 SHA-256 哈希  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不支持与 FIPS 兼容的 SHA-256 哈希，因此在要求使用与 FIPS 兼容的算法的系统上，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不支持使用 SHA-256 的算法组。  
  
### <a name="fips-compliant-algorithms-may-fail-if-registry-is-edited"></a>如果编辑注册表，与 FIPS 兼容的算法可能失败  
 使用本地安全设置 Microsoft 管理控制台 (MMC) 管理单元，可以启用和禁用与美国联邦信息处理标准 (FIPS) 兼容的算法。 您还可以在注册表中访问该设置。 但是，请注意，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不支持使用注册表来重置该设置。 如果该值设置为除 1 或 0 之外的任何值，CLR 和操作系统之间就可能出现不一致的结果。  
  
### <a name="fips-compliant-aes-encryption-limitation"></a>与 FIPS 兼容的 AES 加密限制  
 与 FIPS 兼容的 AES 加密无法在标识级模拟下以双工回调模式工作。  
  
### <a name="cngksp-certificates"></a>CNG/KSP 证书  
 *加密 API： 下一代 (CNG)*是 cryptoapi 的长期替代。 此 API 已在上的非托管代码中用[!INCLUDE[wv](../../../../includes/wv-md.md)]，[!INCLUDE[lserver](../../../../includes/lserver-md.md)]和更高版本的 Windows 版本。  
  
 因为它们使用传统的 CryptoAPI 来处理 CNG/KSP 证书，.NET framework 4.6.1 及更早版本不支持这些证书。 使用.NET Framework 4.6.1 及早期版本使用这些证书将导致异常。  
  
 以下是判断证书是否使用 KSP 的两种可行方法：  
  
-   对 `p/invoke` 执行 `CertGetCertificateContextProperty`，并对返回的 `dwProvType` 检查 `CertGetCertificateContextProperty`。  
  
-   使用`certutil`命令从命令行来查询证书。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][证书疑难解答方面的 Certutil 任务](http://go.microsoft.com/fwlink/?LinkId=120056)。  
  
## <a name="message-security-fails-if-using-aspnet-impersonation-and-aspnet-compatibility-is-required"></a>如果要求使用 ASP.NET 模拟和 ASP.NET 兼容性，消息安全将失败  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不支持以下设置组合，因为它们可能阻止客户端身份验证的发生：  
  
-   启用了 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 模拟。 这通过 Web.config 文件中设置`impersonate`属性 <`identity`> 元素`true`。  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]通过设置启用兼容性模式`aspNetCompatibilityEnabled`属性[ \<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)到`true`。  
  
-   使用了消息模式安全。  
  
 解决办法是禁用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 兼容模式。 或者，如果要求使用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 兼容模式，则可以禁用 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 模拟功能，并且改用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 提供的模拟。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][委托和模拟](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)。  
  
## <a name="ipv6-literal-address-failure"></a>IPv6 文本地址失败  
 当客户端和服务位于同一台计算机上，并且为服务使用了 IPv6 文本地址时，安全请求将失败。  
  
 如果服务和客户端位于不同的计算机上，IPv6 文本地址有效。  
  
## <a name="wsdl-retrieval-failures-with-federated-trust"></a>涉及联合信任的 WSDL 检索失败问题  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 要求联合信任链中的每个节点都恰好有一个对应的 WSDL 文档。 指定终结点时，务必不要设置循环。 可能导致循环的一种情形是，将联合信任链的 WSDL 下载用于同一 WSDL 文档中的两个或多个链接。 可能产生此问题的一个常见方案是联合服务，其中安全令牌服务器和服务包含在同一 ServiceHost 内。  
  
 举例来说，若某个服务具有以下三个终结点地址，便可能出现此情况：  
  
-   http://localhost/CalculatorService/service（服务）  
  
-   http://localhost/CalculatorService/issue_ticket (STS)  
  
-   http://localhost/CalculatorService/mex（元数据终结点）  
  
 这将引发异常。  
  
 若将 `issue_ticket` 终结点放在其他地方，此方案便可正常工作。  
  
## <a name="wsdl-import-attributes-can-be-lost"></a>WSDL 导入属性可能会丢失  
 执行 WSDL 导入时，WCF 丢失了对 `<wst:Claims>` 模板中 `RST` 元素的属性的跟踪。 如果在 `<Claims>` 或 `WSFederationHttpBinding.Security.Message.TokenRequestParameters` 中直接指定 `IssuedSecurityTokenRequestParameters.AdditionalRequestParameters`，而不是直接使用声明类型集合，则在 WSDL 导入期间会发生此情况。  由于导入丢失了特性，绑定没有通过 WSDL 正确地往返，因此它在客户端上是不正确的。  
  
 解决方法是，导入完毕后直接在客户端上修改绑定。  
  
## <a name="see-also"></a>请参阅  
 [安全注意事项](../../../../docs/framework/wcf/feature-details/security-considerations-in-wcf.md)  
 [信息泄漏](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 [特权提升](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 [拒绝服务](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 [篡改](../../../../docs/framework/wcf/feature-details/tampering.md)  
 [重放攻击](../../../../docs/framework/wcf/feature-details/replay-attacks.md)
