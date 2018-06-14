---
title: 如何：配置 WCF 服务以便与 WSE 3.0 客户端进行互操作
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 174ecd279f9380136532ce0d5105b7a71b6d88da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495104"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>如何：配置 WCF 服务以便与 WSE 3.0 客户端进行互操作
当 WCF 服务配置为使用 2004 年 8 月版 Ws-addressing 规范时，Windows Communication Foundation (WCF) 服务是与 Web Services Enhancements 3.0 for Microsoft.NET (WSE) 客户端的网络级别兼容性。  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>使 WCF 服务与 WSE 3.0 客户端进行互操作  
  
1.  定义自定义绑定的 WCF 服务。  
  
     若要指定将 WS-Addressing 规范的 2004 年 8 月版用于消息编码，必须创建自定义绑定。  
  
    1.  添加子[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)到[\<绑定 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)的服务的配置文件。  
  
    2.  通过添加指定的绑定，名称[\<绑定 >](../../../../docs/framework/misc/binding.md)到[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)和设置`name`属性。  
  
    3.  指定身份验证模式和用于保护通过添加子级与 WSE 3.0 中，兼容的消息的 Ws-security 规范的版本[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)到[ \<绑定 >](../../../../docs/framework/misc/binding.md)。  
  
         若要设置的身份验证模式，设置`authenicationMode`属性[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)。 身份验证模式大致等效于 WSE 3.0 中的关守安全断言。 下表将映射到在 WSE 3.0 关守安全断言的 WCF 中的身份验证模式。  
  
        |WCF 身份验证模式|WSE 3.0 关守安全断言|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         \* 之间的主要区别之一`mutualCertificate10Security`和`mutualCertificate11Security`关守安全断言是，WSE 用于保护 SOAP 消息的 Ws-security 规范的版本。 `mutualCertificate10Security` 使用 WS-Security 1.0，而 WS-Security 1.1 用于 `mutualCertificate11Security`。 对于 WCF，Ws-security 规范的版本中指定`messageSecurityVersion`属性[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)。  
  
         若要设置用于保护 SOAP 消息的 Ws-security 规范的版本，设置`messageSecurityVersion`属性[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)。 若要与 WSE 3.0 进行互操作，请将 `messageSecurityVersion` 属性的值设置为 <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>。  
  
    4.  指定使用 Ws-addressing 规范的 2004 年 8 月版本是由 WCF 通过添加[ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)并设置`messageVersion`为其值以<xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>。  
  
        > [!NOTE]
        >  在使用 SOAP 1.2 时，请将 `messageVersion` 属性设置为 <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>。  
  
2.  指定该服务使用自定义绑定。  
  
    1.  设置`binding`属性[\<终结点 >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)元素`customBinding`。  
  
    2.  设置`bindingConfiguration`属性[\<终结点 >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)中指定的值的元素`name`属性[\<绑定 >](../../../../docs/framework/misc/binding.md)为自定义绑定。  
  
## <a name="example"></a>示例  
 下面的代码示例指定 `Service.HelloWorldService` 使用自定义绑定与 WSE 3.0 客户端进行互操作。 自定义绑定指定使用 WS-Addressing 的 2004 年 8 月版本和 WS-Security 1.1 规范集对所交换的消息进行编码。 使用 <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> 身份验证模式保证消息的安全。  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        behaviorConfiguration="ServiceBehavior"   
        name="Service.HelloWorldService">  
        <endpoint binding="customBinding" address=""  
          bindingConfiguration="ServiceBinding"  
          contract="Service.IHelloWorld"></endpoint>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="ServiceBinding">  
          <security authenticationMode="AnonymousForCertificate"  
                  messageProtectionOrder="SignBeforeEncrypt"  
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"  
                  requireDerivedKeys="false">  
          </security>  
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">  
        <serviceCredentials>  
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>  
        </serviceCredentials>  
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 [如何：自定义系统提供的绑定](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
