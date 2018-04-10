---
title: 使用证书
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates [WCF]
ms.assetid: 6ffb8682-8f07-4a45-afbb-8d2487e9dbc3
caps.latest.revision: 26
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ba49d990c9f067ae2c10ae2a60cbad24b30f43eb
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="working-with-certificates"></a>使用证书
对 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 安全进行编程时，通常使用 X.509 数字证书对客户端和服务器进行身份验证，以及对消息进行加密和数字签名。 本主题将简要说明 X.509 数字证书的功能以及如何在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中使用它们，并提供一些主题的链接，这些主题对这些概念进行了深入说明，或揭示了如何使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 和证书来完成常见任务。  
  
 简言之，数字证书是属于*公钥基础结构*(PKI)，这是数字证书、 证书颁发机构和其他注册机构验证和身份验证的有效性的系统使用公钥加密对电子事务所涉及的每一方。 证书颁发机构颁发证书，每个证书都有包含数据，如的字段的一组*主题*（向其颁发证书的实体） 生效日期 （当证书是否有效），颁发者 (颁发证书的实体），和公钥。 在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中，这些属性中的每一个都作为 <xref:System.IdentityModel.Claims.Claim> 进行处理，而每个声明又进一步分为两种类型：标识和权限。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] X.509 证书，请查看[X.509 公钥证书](http://go.microsoft.com/fwlink/?LinkId=209952)[!INCLUDE[crabout](../../../../includes/crabout-md.md)]声明和 WCF 中的授权参见[管理声明和使用标识模型的授权](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 实施 PKI，请参阅[Windows Server 2008 R2-证书服务](http://go.microsoft.com/fwlink/?LinkId=209949)。  
  
 证书的主要功能是向其他各方验证证书所有者的身份。 证书包含*公钥*的所有者，所有者保留的私钥。 公钥可用来对发送给证书所有者的消息进行加密。 只有所有者才能访问私钥，因此，只有所有者才能解密这些消息。  
  
 证书必须由证书颁发机构（通常是第三方证书颁发机构）颁发。 在 Windows 域中，包括一个证书颁发机构，可以用来向域中的计算机颁发证书。  
  
## <a name="viewing-certificates"></a>查看证书  
 若要使用证书，通常需要查看证书并检查其属性。 使用 Microsoft 管理控制台 (MMC) 管理单元工具，很容易实现这一任务。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [如何： 使用 mmc 管理单元查看证书](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)。  
  
## <a name="certificate-stores"></a>证书存储区  
 证书存放在存储区中。 主要的存储区位置有两个，它们进一步分为子存储区。 如果您是计算机的管理员，就可以使用 MMC 管理单元工具查看这两个主要存储区。 非管理员只能查看当前用户存储区。  
  
-   **本地计算机存储**。 该存储区包含计算机进程（例如 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]）访问的证书。 此位置用于存储向客户端验证服务器身份的证书。  
  
-   **当前用户存储区**。 交互式应用程序通常将证书放在此位置，供计算机的当前用户使用。 如果要创建客户端应用程序，通常会将向服务验证用户身份的证书放在此处。  
  
 这两个存储区进一步分为子存储区。 使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 编程时，最重要的子存储区包括：  
  
-   **受信任的根证书颁发机构**。 使用此存储区中的证书可以创建证书链，通过证书链，可以追溯到此存储区中的证书颁发机构证书。  
  
    > [!IMPORTANT]
    >  本地计算机隐式信任放置在此存储区中的任何证书，即使证书不是来自受信任的第三方证书颁发机构，也是如此。 因此，除非完全信任颁发机构并了解后果，否则不要将任何证书放入此存储区。  
  
-   **个人**。 此存储区用于放置与计算机用户关联的证书。 通常，此存储区用于存放在受信任的根证书颁发机构存储区中找到的证书颁发机构证书之一所颁发的证书。 此外，此处还可存放应用程序自行颁发并且信任的证书。  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 证书存储，请参阅[证书存储](http://go.microsoft.com/fwlink/?LinkId=88912)。  
  
### <a name="selecting-a-store"></a>选择存储区  
 证书存储位置的选择，取决于服务或客户端运行的方式和时间。 适用以下一般规则：  
  
-   如果 WCF 服务承载于某个 Windows 服务使用**本地计算机**存储。 请注意，要将证书安装到本地计算机存储区，需要有管理员权限。  
  
-   如果服务或客户端是在用户帐户下运行的应用程序，则使用**当前用户**存储。  
  
### <a name="accessing-stores"></a>访问存储区  
 与计算机上的文件夹一样，存储区也受访问控制列表 (ACL) 保护。 在创建由 Internet 信息服务 (IIS) 承载的服务时，[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 进程运行在 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 帐户下。 该帐户必须有权访问包含服务所用证书的存储区。 每个主要存储区都由一个默认访问列表保护，但这些列表是可以修改的。 如果创建一个单独的角色访问存储区，则必须向该角色授予访问权限。 若要了解如何修改使用 WinHttpCertConfig.exe 工具的访问列表，请参阅[如何： 创建开发期间使用的临时证书](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 向 IIS 使用客户端证书，请参阅[如何通过使用客户端证书进行身份验证 ASP.NET Web 应用程序中调用 Web 服务](http://go.microsoft.com/fwlink/?LinkId=88914)。  
  
## <a name="chain-trust-and-certificate-authorities"></a>链信任和证书颁发机构  
 证书是在某种层次结构中创建的，其中每个证书都链接到颁发该证书的 CA。 该链接指向 CA 的证书。 CA 的证书又链接到颁发原始 CA 证书的 CA。 这一过程不断重复，直至到达根 CA 的证书。 根 CA 的证书将以继承方式受到信任。  
  
 数字证书用于对实体进行身份验证利用此层次结构，也称为*信任链*。 你可以查看通过双击任何证书，再单击 MMC 管理单元中使用的任何证书链**证书路径**选项卡。[!INCLUDE[crabout](../../../../includes/crabout-md.md)]导入的证书颁发机构证书链，请参阅[如何： 指定用于验证签名的证书颁发机构证书链](../../../../docs/framework/wcf/feature-details/specify-the-certificate-authority-chain-verify-signatures-wcf.md)。  
  
> [!NOTE]
>  通过将颁发机构的证书放入受信任的根颁发机构证书存储区中，可以向任何颁发机构指定受信任的根颁发机构。  
  
### <a name="disabling-chain-trust"></a>禁用链信任  
 在创建新服务时，可能会使用不是由受信任的根证书颁发的证书，或者颁发证书本身可能不在受信任的根证书颁发机构存储区中。 如果仅为了开发目的，可以暂时禁用检查证书信任链的机制。 为此，需要将 `CertificateValidationMode` 属性设置为 `PeerTrust` 或 `PeerOrChainTrust`。 这两种模式都指定，证书可以是自行颁发的（对等信任），也可以是信任链的一部分。 在下列所有类上，都可以设置此属性。  
  
|类|属性|  
|-----------|--------------|  
|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>|<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>|<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A?displayProperty=nameWithType>|  
|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential>|<xref:System.ServiceModel.Security.IssuedTokenServiceCredential.CertificateValidationMode%2A?displayProperty=nameWithType>|  
  
 此外，也可以通过配置设置此属性。 下列元素用于指定验证模式：  
  
-   [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)  
  
-   [\<peerAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)  
  
-   [\<messageSenderAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)  
  
## <a name="custom-authentication"></a>自定义身份验证  
 使用 `CertificateValidationMode` 属性，还可以对证书的身份验证方式进行自定义。 默认情况下，级别设置为 `ChainTrust`。 若要使用 <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom> 值，还必须将 `CustomCertificateValidatorType` 属性设置为程序集和用于验证证书的类型。 若要创建自定义验证程序，必须从抽象 <xref:System.IdentityModel.Selectors.X509CertificateValidator> 类继承。  
  
 在创建自定义身份验证器时，要重写的最重要方法是 <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> 方法。 有关自定义身份验证的示例，请参阅[X.509 证书验证程序](../../../../docs/framework/wcf/samples/x-509-certificate-validator.md)示例。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [自定义凭据和凭据验证](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)。  
  
## <a name="using-makecertexe-to-build-a-certificate-chain"></a>使用 Makecert.exe 生成证书链  
 证书创建工具 (Makecert.exe) 可以创建 X.509 证书和私钥/公钥对。 可以将私钥保存在磁盘上，然后用它来颁发和签名新证书，从而模拟链状证书的层次结构。 此工具仅在开发服务时用作辅助手段，决不可以用来为实际部署创建证书。 在开发 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务时，可使用 Makecert.exe 按照下列步骤生成信任链。  
  
#### <a name="to-build-a-chain-of-trust-with-makecertexe"></a>使用 Makecert.exe 生成信任链  
  
1.  使用 MakeCert.exe 工具创建一个临时根证书颁发机构（自签名）证书。 将私钥保存到磁盘上。  
  
2.  使用此新证书颁发另一个包含公钥的证书。  
  
3.  将根颁发机构证书导入到受信任的根证书颁发机构存储区中。  
  
4.  有关分步说明，请参阅[如何： 创建开发期间使用的临时证书](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)。  
  
## <a name="which-certificate-to-use"></a>要使用哪个证书？  
 关于证书的常见问题是要使用哪个证书以及使用它的原因。 答案取决于是对客户端编程还是对服务编程。 下面的信息提供了一个一般准则，但未对这些问题提供详尽解答。  
  
### <a name="service-certificates"></a>服务证书  
 服务证书的主要任务是向客户端验证服务器的身份。 当客户端身份验证服务器的初始检查之一是进行比较的值**主题**字段到统一资源标识符 (URI) 用于连接的服务： 二者的 DNS 必须匹配。 例如，如果服务的 URI 为"http://www.contoso.com/endpoint/"则**主题**字段也必须包含值"www.contoso.com"。  
  
 请注意，该字段可以包含多个值，每个值都以一个起始值前缀来指示其值。 最常见的起始值是以“CN”表示公用名，例如“CN = www.contoso.com”。 也可能是**主题**字段以这种情况下为空白，**使用者备用名称**字段只能包含**DNS 名称**值。  
  
 另请注意的值**预期目的**的证书字段应包括适当的值，例如"服务器身份验证"或"客户端身份验证"。  
  
### <a name="client-certificates"></a>客户端证书  
 客户端证书通常不是由第三方证书颁发机构颁发的。 相反，在当前用户位置的个人存储区中，通常包含由根证书颁发机构存放在此的证书，其预期目的为“客户端身份验证”。 如果需要相互身份验证，则客户端可以使用此类证书。  
  
## <a name="online-revocation-and-offline-revocation"></a>联机吊销和脱机吊销  
  
### <a name="certificate-validity"></a>证书有效性  
 每个证书的有效期仅为给定的一段时间，调用*有效期*。 定义有效期内**有效起始**和**有效终止**的 X.509 证书的字段。 在身份验证过程中，将对证书进行检查以确定证书是否仍在有效期内。  
  
### <a name="certificate-revocation-list"></a>证书吊销列表  
 在有效期内，证书颁发机构随时可以吊销证书。 吊销证书有多种原因，例如危及证书私钥的安全。  
  
 如果证书吊销，则从被吊销证书继承的任何链都将无效，在身份验证过程中也不受信任。 若要了解哪些证书被吊销，每个颁发机构都发布时间和日期-戳*证书吊销列表*(CRL)。 可以使用联机吊销或脱机吊销来查看此列表，方法是将以下类的 `RevocationMode` 或 `DefaultRevocationMode` 属性设置为 <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> 枚举值之一：<xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>、<xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>、<xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> 和 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential> 类。 所有属性的默认值都是 `Online`。  
  
 你还可以通过以下方式设置模式在配置中使用`revocationMode`属性[\<身份验证 >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) (的[ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)) 和[\<身份验证 >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) (的[ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md))。  
  
## <a name="the-setcertificate-method"></a>SetCertificate 方法  
 在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中，必须经常指定一个或一组证书，供服务或客户端用来对消息进行身份验证、加密或数字签名。 使用表示 X.509 证书的各个类的 `SetCertificate` 方法，可以以编程方式实现这一操作。 下面的类使用 `SetCertificate` 方法指定一个证书。  
  
|类|方法|  
|-----------|------------|  
|<xref:System.ServiceModel.Security.PeerCredential>|<xref:System.ServiceModel.Security.PeerCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>|<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>|<xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>|  
|<xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential.SetCertificate%2A>|  
  
 `SetCertificate` 方法通过指定一个存储区位置和存储区、一个指定证书字段的“查找”类型（`x509FindType` 参数）和一个要在字段中查找的值来实现其功能。 例如，下面的代码创建<xref:System.ServiceModel.ServiceHost>实例并设置用于向客户端与服务进行身份验证的服务证书`SetCertificate`方法。  
  
 [!code-csharp[c_WorkingWithCertificates#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_workingwithcertificates/cs/source.cs#1)]
 [!code-vb[c_WorkingWithCertificates#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_workingwithcertificates/vb/source.vb#1)]  
  
### <a name="multiple-certificates-with-the-same-value"></a>具有相同值的多个证书  
 一个存储区可以包含多个具有相同主题名称的证书。 这意味着，如果你指定`x509FindType`是<xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectName>或<xref:System.Security.Cryptography.X509Certificates.X509FindType.FindBySubjectDistinguishedName>，并且多个证书具有相同的值，因为没有方法来区分的证书是必需的则引发异常。 通过将 `x509FindType` 设置为 <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint>，可以缓解这一问题。 指纹字段包含一个唯一值，可以用来查找存储区中的特定证书。 但是，这种方法也有缺点，如果证书已吊销或续订，则 `SetCertificate` 方法会失败，因为指纹也消失了。 或者，如果证书不再有效，则身份验证将失败。 缓解这一问题的方法是将 `x590FindType` 参数设置为 <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByIssuerName> 并指定颁发机构的名称。 如果不需要特定颁发机构，也可以设置一个其他的 <xref:System.Security.Cryptography.X509Certificates.X509FindType> 枚举值，例如 <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByTimeValid>。  
  
## <a name="certificates-in-configuration"></a>配置中的证书  
 此外，通过配置也可以设置证书。 如果要创建的服务，在指定凭据，包括证书， [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)。 在编程客户端时，在指定证书[ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)。  
  
## <a name="mapping-a-certificate-to-a-user-account"></a>将证书映射到用户帐户  
 IIS 和 Active Directory 的一个功能是将证书映射到 Windows 用户帐户。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 该功能，请参阅[将证书映射到用户帐户](http://go.microsoft.com/fwlink/?LinkId=88917)。  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] 使用 Active Directory 映射，请参阅[映射客户端证书与目录服务映射](http://go.microsoft.com/fwlink/?LinkId=88918)。  
  
 如果启用了这一功能，则可以将 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.MapClientCertificateToWindowsAccount%2A> 类的 <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> 属性设置为 `true`。 在配置中，你可以设置`mapClientCertificateToWindowsAccount`属性[\<身份验证 >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)元素`true`，如下面的代码中所示。  
  
```xml  
<serviceBehaviors>  
 <behavior name="MappingBehavior">  
  <serviceCredentials>  
   <clientCertificate>  
    <authentication certificateValidationMode="None" mapClientCertificateToWindowsAccount="true" />  
   </clientCertificate>  
  </serviceCredentials>  
 </behavior>  
</serviceBehaviors>  
```  
  
 将 X.509 证书映射到表示 Windows 用户帐户的令牌，这一过程视为权限提升，这是因为一旦执行了映射，就可使用 Windows 令牌获得对受保护资源的访问权限。 因此，域策略要求 X.509 证书在映射之前符合其策略。 *SChannel*安全包来强制此要求。  
  
 使用 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] 或更高版本时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 可以确保证书在映射到 Windows 帐户之前符合域策略。  
  
 在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 第一版中，执行映射无需考虑域策略。 因此，如果启用了映射，而 X.509 证书不满足域策略，则在第一版下运行正常的早期应用程序，可能会失败。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Channels>  
 <xref:System.ServiceModel.Security>  
 <xref:System.ServiceModel>  
 <xref:System.Security.Cryptography.X509Certificates.X509FindType>  
 [保护服务和客户端的安全](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
