---
title: "如何：创建安全会话"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: cd4f91ef5389dd4b8ecb63c1148d3a86918f2d10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-secure-session"></a>如何：创建安全会话
除[ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)绑定、 中的系统提供绑定[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]自动使用安全会话中启用消息安全时。  
  
 默认情况下，安全会话不会在已回收的 Web 服务器中存在。 建立安全会话时，客户端和服务将缓存与安全会话关联的密钥。 交换消息时，只交换已缓存密钥的标识符。 如果回收了 Web 服务器，则也会回收缓存，因此 Web 服务器将无法检索该标识符的已缓存密钥。 如果发生这种情况，将会引发异常并返回至客户端。 使用有状态安全上下文令牌 (SCT) 的安全会话可以在回收 Web 服务器后存在。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]在安全会话中，使用有状态 SCT，请参阅[如何： 为安全会话创建安全上下文令牌](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)。  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a>通过使用系统提供的一个绑定指定服务使用安全会话  
  
-   配置服务以使用支持消息安全的系统提供的绑定。  
  
     除[ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)绑定，当系统提供的绑定配置为使用消息安全，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]自动使用安全会话。 下表列出了支持消息安全的系统提供的绑定以及消息安全是否是默认的安全机制。  
  
    |系统提供的绑定|配置元素|默认情况下是否启用消息安全|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|否|  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|是|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|是|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|是|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|否|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|否|  
  
     下面的代码示例使用配置来指定一个名为绑定`wsHttpBinding_Calculator`使用[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)、 消息安全性，和安全会话。  
  
    ```xml  
    <bindings>  
      <WSHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </WSHttpBinding>  
    </bindings>  
    ```  
  
     下面的代码示例指定[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)、 消息安全性，和安全会话用于保护`secureCalculator`服务。  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  可以关闭安全会话的[ <wsHttpBinding> ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)通过设置`establishSecurityContext`属性设为`false`。 对于其他系统提供的绑定，只能通过创建自定义绑定来关闭安全会话。  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a>通过使用自定义绑定来指定服务使用安全会话  
  
-   创建一个自定义绑定，该绑定指定由安全会话保护 SOAP 消息。  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]创建自定义绑定，请参阅[如何： 自定义系统提供的绑定](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)。  
  
     下面的代码示例使用配置来指定使用安全会话的消息的自定义绑定。  
  
    ```xml  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="customBinding_Calculator">  
          <security authenticationMode="SecureConversation" />  
          <secureConversationBootstrap authenticationMode="SspiNegotiated" />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
     下面的代码示例创建一个自定义绑定，该绑定使用 <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> 身份验证模式启动安全会话。  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a>请参阅  
 [WCF 绑定概述](../../../../docs/framework/wcf/bindings-overview.md)
