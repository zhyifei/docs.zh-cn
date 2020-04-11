---
title: 重写服务标识以便进行身份验证
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d613a22b-07d7-41a4-bada-1adc653b9b5d
ms.openlocfilehash: e7273c1e140e52eb37a30b6cabeb9e9a83a6fa2d
ms.sourcegitcommit: 43cbde34970f5f38f30c43cd63b9c7e2e83717ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2020
ms.locfileid: "81121556"
---
# <a name="override-the-identity-of-a-service-for-authentication"></a>重写服务标识以进行身份验证

通常情况下不需要设置服务上的标识，因为客户端凭据类型的选择即规定了服务元数据中公开的标识的类型。 例如，以下配置代码使用[\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)元素并将`clientCredentialType`属性设置到 Windows。  

 下面的 Web 服务描述语言 (WSDL) 片断演示前面定义的终结点的标识。 在此示例中，服务作为自托管服务在特定用户帐户 （username@contoso.com） 下运行，因此用户主体名称 （UPN） 标识包含帐户名称。 在 Windows 域中，UPN 也称为用户登录名。  

 有关演示标识设置的示例应用程序，请参阅[服务标识示例](../samples/service-identity-sample.md)。 有关服务标识的详细信息，请参阅[服务标识和身份验证](../feature-details/service-identity-and-authentication.md)。  
  
## <a name="kerberos-authentication-and-identity"></a>Kerberos 身份验证和标识  
 默认情况下，当服务配置为使用 Windows 凭据时，在 WSDL 中生成包含[\<用户主体名称>](../../configure-apps/file-schema/wcf/userprincipalname.md)[\<或服务主体名称>](../../configure-apps/file-schema/wcf/serviceprincipalname.md)元素的[\<标识>](../../configure-apps/file-schema/wcf/identity.md)元素。 如果服务`LocalSystem`在 、`LocalService`或`NetworkService`帐户下运行，则默认情况下以`host/`\<*主机名*>形式生成服务主体名称 （SPN），因为这些帐户有权访问计算机的 SPN 数据。 如果服务在不同的帐户下运行，Windows 通信基金会 （WCF） 会以\<*用户名*>@<*域名*`>`的形式生成 UPN。 发生这种情况的原因是 Kerberos 身份验证要求向客户端提供 UPN 或 SPN，以便对服务进行身份验证。  
  
 您还可以使用[Setpn](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731241(v=ws.10)?redirectedfrom=MSDN)工具在域中使用服务的帐户注册其他 SPN。 然后，可以使用该 SPN 作为服务的标识。 有关该工具的详细信息，请参阅[Setpn 概述](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc773257(v=ws.10))。  
  
> [!NOTE]
> 若要使用不带协商的 Windows 凭据类型，服务的用户帐户必须有权访问向 Active Directory 域注册的 SPN。 可以使用下列方式来实现：  
  
- 使用 NetworkService 或 LocalSystem 帐户运行服务。 由于这些帐户有权访问计算机加入 Active Directory 域时建立的计算机 SPN，因此 WCF 会自动在服务的元数据 （WSDL） 中的服务终结点内生成正确的 SPN 元素。  
  
- 使用任意 Active Directory 域帐户运行服务。 在这种情况下，需要为该域帐户建立一个 SPN，这可以使用 Setspn.exe 实用工具来完成。 为服务的帐户创建 SPN 后，将 WCF 配置为通过其元数据 （WSDL） 将该 SPN 发布到服务的客户端。 这可以通过为公开的终结点设置终结点标识（借助于应用程序配置文件或代码）来完成。  
  
 有关 SPN、Kerberos 协议和活动目录的详细信息，请参阅[Windows 的 Kerberos 技术补充](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10))。  
  
### <a name="when-spn-or-upn-equals-the-empty-string"></a>当 SPN 或 UPN 等于空字符串时  
 如果将 SPN 或 UPN 设置为等于空字符串，将出现多种不同的情况，具体取决于所使用的安全级别和身份验证模式：  
  
- 如果使用传输级安全，则会选择 NT LanMan (NTLM) 身份验证。  
  
- 如果使用消息级安全，则根据身份验证模式的不同，身份验证可能会失败：  
  
- 如果使用 `spnego` 模式，并且 `AllowNtlm` 属性设置为 `false`，则身份验证将失败。  
  
- 在使用 `spnego` 模式并且 `AllowNtlm` 属性设置为 `true` 的情况下，如果 UPN 为空，则身份验证将失败；如果 SPN 为空，则身份验证将成功。  
  
- 如果使用 Kerberos direct（也称为“一次完成”），则身份验证将失败。  
  
### <a name="using-the-identity-element-in-configuration"></a>在\<配置中使用标识>元素  
 如果将前面演示的绑定中的客户端凭据类型更改为证书`,`，则生成的 WSDL 将包含一个 Base64 序列化 X.509 证书作为标识值，如下面的代码所示。 这是除 Windows 之外的所有客户端凭据类型的默认值。  

 您可以通过在配置中使用<>`identity`元素或在代码中设置标识来更改默认服务标识的值或更改标识的类型。 下面的配置代码使用值 `contoso.com` 设置域名系统 (DNS) 标识。  

### <a name="setting-identity-programmatically"></a>以编程方式设置标识  
 服务不必显式指定标识，因为 WCF 会自动确定它。 但是，如果需要，WCF 允许您在终结点上指定标识。 下面的代码使用特定的 DNS 标识添加了一个新的服务终结点。  
  
 [!code-csharp[C_Identity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_identity/cs/source.cs#5)]
 [!code-vb[C_Identity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_identity/vb/source.vb#5)]  
  
## <a name="see-also"></a>请参阅

- [如何：创建自定义客户端标识验证工具](how-to-create-a-custom-client-identity-verifier.md)
- [服务标识和身份验证](../feature-details/service-identity-and-authentication.md)
