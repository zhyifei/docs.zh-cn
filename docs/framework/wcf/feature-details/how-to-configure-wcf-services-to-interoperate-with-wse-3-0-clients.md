---
title: 如何：配置 WCF 服务以便与 WSE 3.0 客户端进行互操作
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: bd9f2bec94ca45f76590f64366428a00edd5d6ea
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141742"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="f32ce-102">如何：配置 WCF 服务以便与 WSE 3.0 客户端进行互操作</span><span class="sxs-lookup"><span data-stu-id="f32ce-102">How to: Configure WCF Services to Interoperate with WSE 3.0 Clients</span></span>

<span data-ttu-id="f32ce-103">当 WCF 服务配置为使用8月2004版的 WS-ADDRESSING 规范时，Windows Communication Foundation （WCF）服务与用于 Microsoft .NET （WSE）客户端的 Web 服务增强3.0 线路级别兼容。</span><span class="sxs-lookup"><span data-stu-id="f32ce-103">Windows Communication Foundation (WCF) services are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) clients when WCF services are configured to use the August 2004 version of the WS-Addressing specification.</span></span>

### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a><span data-ttu-id="f32ce-104">使 WCF 服务与 WSE 3.0 客户端进行互操作</span><span class="sxs-lookup"><span data-stu-id="f32ce-104">To enable a WCF service to interoperate with WSE 3.0 clients</span></span>

1. <span data-ttu-id="f32ce-105">定义 WCF 服务的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="f32ce-105">Define a custom binding for the WCF service.</span></span>

    <span data-ttu-id="f32ce-106">若要指定将 WS-Addressing 规范的 2004 年 8 月版用于消息编码，必须创建自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="f32ce-106">To specify that the August 2004 version of the WS-Addressing specification is used for message encoding, a custom binding must be created.</span></span>

    1. <span data-ttu-id="f32ce-107">将子[\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)添加到服务的配置文件[\<绑定](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="f32ce-107">Add a child [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) of the service's configuration file.</span></span>

    2. <span data-ttu-id="f32ce-108">通过将[\<绑定 >](../../configure-apps/file-schema/wcf/bindings.md)添加到[\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)并设置 `name` 属性，指定绑定的名称。</span><span class="sxs-lookup"><span data-stu-id="f32ce-108">Specify a name for the binding, by adding a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) and setting the `name` attribute.</span></span>

    3. <span data-ttu-id="f32ce-109">通过将子[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)添加到[\<绑定 >](../../configure-apps/file-schema/wcf/bindings.md)，指定身份验证模式和用于保护与 WSE 3.0 兼容的消息的 WS 安全规范的版本。</span><span class="sxs-lookup"><span data-stu-id="f32ce-109">Specify an authentication mode and the version of the WS-Security specifications that are used to secure messages that are compatible with WSE 3.0, by adding a child [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) to the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md).</span></span>

        <span data-ttu-id="f32ce-110">若要设置身份验证模式，请设置[\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)的 `authenticationMode` 属性。</span><span class="sxs-lookup"><span data-stu-id="f32ce-110">To set the authentication mode, set the `authenticationMode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="f32ce-111">身份验证模式大致等效于 WSE 3.0 中的关守安全断言。</span><span class="sxs-lookup"><span data-stu-id="f32ce-111">An authentication mode is roughly equivalent to a turnkey security assertion in WSE 3.0.</span></span> <span data-ttu-id="f32ce-112">下表将 WCF 中的身份验证模式映射到 WSE 3.0 中的交钥匙安全声明。</span><span class="sxs-lookup"><span data-stu-id="f32ce-112">The following table maps authentication modes in WCF to turnkey security assertions in WSE 3.0.</span></span>

        |<span data-ttu-id="f32ce-113">WCF 身份验证模式</span><span class="sxs-lookup"><span data-stu-id="f32ce-113">WCF Authentication Mode</span></span>|<span data-ttu-id="f32ce-114">WSE 3.0 关守安全断言</span><span class="sxs-lookup"><span data-stu-id="f32ce-114">WSE 3.0 turnkey security assertion</span></span>|
        |-----------------------------|----------------------------------------|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|

        <span data-ttu-id="f32ce-115">\* `mutualCertificate10Security` 和 `mutualCertificate11Security` 交钥匙安全声明的主要区别之一是 WSE 用于保护 SOAP 消息的 WS 安全规范的版本。</span><span class="sxs-lookup"><span data-stu-id="f32ce-115">\* One of the primary differences between the `mutualCertificate10Security` and `mutualCertificate11Security` turnkey security assertions is the version of the WS-Security specification that WSE uses to secure the SOAP messages.</span></span> <span data-ttu-id="f32ce-116">`mutualCertificate10Security` 使用 WS-Security 1.0，而 WS-Security 1.1 用于 `mutualCertificate11Security`。</span><span class="sxs-lookup"><span data-stu-id="f32ce-116">For `mutualCertificate10Security`, WS-Security 1.0 is used, whereas WS-Security 1.1 is used for `mutualCertificate11Security`.</span></span> <span data-ttu-id="f32ce-117">对于 WCF，将在[\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)的 `messageSecurityVersion` 特性中指定 WS 安全规范的版本。</span><span class="sxs-lookup"><span data-stu-id="f32ce-117">For WCF, the version of the WS-Security specification is specified in the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>

        <span data-ttu-id="f32ce-118">若要设置用于保护 SOAP 消息的 WS 安全规范的版本，请设置[\<security >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)的 `messageSecurityVersion` 属性。</span><span class="sxs-lookup"><span data-stu-id="f32ce-118">To set the version of the WS-Security specification that is used to secure SOAP messages, set the `messageSecurityVersion` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span> <span data-ttu-id="f32ce-119">若要与 WSE 3.0 进行互操作，请将 `messageSecurityVersion` 属性的值设置为 <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>。</span><span class="sxs-lookup"><span data-stu-id="f32ce-119">To interoperate with WSE 3.0, set the value of the `messageSecurityVersion` attribute to <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>.</span></span>

    4. <span data-ttu-id="f32ce-120">指定 WCF 将使用8月2004版的 WS-ADDRESSING 规范，方法是添加一个[\<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)并将 `messageVersion` 设置为 <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>值。</span><span class="sxs-lookup"><span data-stu-id="f32ce-120">Specify that the August 2004 version of the WS-Addressing specification is used by WCF by adding a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) and set the `messageVersion` to its value to <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f32ce-121">在使用 SOAP 1.2 时，请将 `messageVersion` 属性设置为 <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>。</span><span class="sxs-lookup"><span data-stu-id="f32ce-121">When you are using SOAP 1.2, set the `messageVersion` attribute to <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>.</span></span>

2. <span data-ttu-id="f32ce-122">指定该服务使用自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="f32ce-122">Specify that the service uses the custom binding.</span></span>

    1. <span data-ttu-id="f32ce-123">将[\<终结点 >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)元素的 `binding` 属性设置为 "`customBinding`"。</span><span class="sxs-lookup"><span data-stu-id="f32ce-123">Set the `binding` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to `customBinding`.</span></span>

    2. <span data-ttu-id="f32ce-124">将[\<终结点 >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)元素的 `bindingConfiguration` 特性设置为自定义绑定\<[绑定 >](../../configure-apps/file-schema/wcf/bindings.md)的 `name` 特性中指定的值。</span><span class="sxs-lookup"><span data-stu-id="f32ce-124">Set the `bindingConfiguration` attribute of the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element to the value specified in the `name` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) for the custom binding.</span></span>

## <a name="example"></a><span data-ttu-id="f32ce-125">示例</span><span class="sxs-lookup"><span data-stu-id="f32ce-125">Example</span></span>

<span data-ttu-id="f32ce-126">下面的代码示例指定 `Service.HelloWorldService` 使用自定义绑定与 WSE 3.0 客户端进行互操作。</span><span class="sxs-lookup"><span data-stu-id="f32ce-126">The following code example specifies that the `Service.HelloWorldService` uses a custom binding to interoperate with WSE 3.0 clients.</span></span> <span data-ttu-id="f32ce-127">自定义绑定指定使用 WS-Addressing 的 2004 年 8 月版本和 WS-Security 1.1 规范集对所交换的消息进行编码。</span><span class="sxs-lookup"><span data-stu-id="f32ce-127">The custom binding specifies that the August 2004 version of the WS-Addressing and the WS-Security 1.1 set of specifications are used to encode the exchanged messages.</span></span> <span data-ttu-id="f32ce-128">使用 <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> 身份验证模式保证消息的安全。</span><span class="sxs-lookup"><span data-stu-id="f32ce-128">The messages are secured using the <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate> authentication mode.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f32ce-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="f32ce-129">See also</span></span>

- [<span data-ttu-id="f32ce-130">如何：自定义系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="f32ce-130">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
