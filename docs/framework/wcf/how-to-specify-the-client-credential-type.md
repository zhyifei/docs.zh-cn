---
title: 如何：指定客户端凭据类型
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: df18f89ee18bfa33ecc0aced617d168c805e3515
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74138573"
---
# <a name="how-to-specify-the-client-credential-type"></a>如何：指定客户端凭据类型
设置安全模式（传输或消息）后，您可以设置客户端凭据类型。 此属性指定客户端必须向服务提供以进行身份验证的凭据类型。 有关设置安全模式（设置客户端凭据类型前的必需步骤）的详细信息，请参阅[如何：设置安全模式](how-to-set-the-security-mode.md)。  
  
### <a name="to-set-the-client-credential-type-in-code"></a>在代码中设置客户端凭据类型  
  
1. 创建服务将使用的绑定的实例。 本示例使用 <xref:System.ServiceModel.WSHttpBinding> 绑定。  
  
2. 将 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> 属性设置为适当的值。 本示例使用 Message 模式。  
  
3. 将 <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> 属性设置为适当的值。 本示例将其设置为使用 Windows 身份验证 (<xref:System.ServiceModel.MessageCredentialType.Windows>)。  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a>在配置中设置客户端凭据类型  
  
1. 向配置文件添加一个[\<system 的 >](../configure-apps/file-schema/wcf/system-servicemodel.md)元素。  
  
2. 作为子元素，添加一个[\<bindings >](../configure-apps/file-schema/wcf/bindings.md)元素。  
  
3. 添加一个相应的绑定。 此示例使用[\<wsHttpBinding >](../configure-apps/file-schema/wcf/wshttpbinding.md)元素。  
  
4. 添加一个[\<binding >](../configure-apps/file-schema/wcf/bindings.md)元素，并将 `name` 特性设置为合适的值。 本示例使用名称“SecureBinding”。  
  
5. 添加一个 `<security>` 绑定。 将 `mode` 属性设置为适当的值。 本示例将其设置为 `"Message"`。  
  
6. 添加一个 `<message>` 或 `<transport>` 元素，具体由安全模式确定。 将 `clientCredentialType` 属性设置为适当的值。 本示例使用 `"Windows"`。  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a>请参阅

- [保护服务](securing-services.md)
- [如何：设置安全模式](how-to-set-the-security-mode.md)
