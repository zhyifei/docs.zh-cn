---
title: 如何：使用自定义用户名和密码验证程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 98ffad7e717aac949509fa701c77d8ba2b80a695
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834698"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a>如何：使用自定义用户名和密码验证程序

默认情况下，当使用用户名和密码进行身份验证时，Windows Communication Foundation （WCF）使用 Windows 来验证用户名和密码。 不过，WCF 允许使用自定义用户名和密码身份验证方案（也称为*验证*程序）。 若要合并自定义用户名和密码验证程序，请创建一个从 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> 派生的类，然后对其进行配置。

有关示例应用程序，请参阅[用户名密码验证](../samples/user-name-password-validator.md)程序。

### <a name="to-create-a-custom-user-name-and-password-validator"></a>创建自定义用户名和密码验证程序

1. 创建一个从 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> 派生的类。

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. 通过重写 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 方法，实现自定义身份验证方案。

    请不要使用下面示例中的代码在生产环境中重写 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 方法。 请将该代码替换为你的自定义用户名和密码验证方案，这可能会涉及到从数据库检索用户名和密码对。

    若要将身份验证错误返回到客户端，应在 <xref:System.ServiceModel.FaultException> 方法中引发 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>。

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a>配置服务以使用自定义用户名和密码验证程序

1. 配置一个绑定，该绑定在任何传输上使用消息安全，或者在 HTTP(S) 上使用传输级安全。

    使用消息安全时，添加一个系统提供的绑定（例如[\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)）或支持消息安全和 @no__t 4 凭据类型的[\<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 。

    通过 HTTP 使用传输级安全时，请添加[\<wsHttpBinding >](../../configure-apps/file-schema/wcf/wshttpbinding.md)或[\<basicHttpBinding >](../../configure-apps/file-schema/wcf/basichttpbinding.md)， [\<netTcpBinding >](../../configure-apps/file-schema/wcf/nettcpbinding.md)或使用 HTTP （S）的 [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md)和 `Basic` 身份验证方案。

    > [!NOTE]
    > 使用 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] 或更高版本时，可将自定义用户名和密码验证程序与消息和传输安全一起使用。 使用 WinFX，自定义用户名和密码验证程序只能与消息安全一起使用。

    > [!TIP]
    > 有关在此上下文中使用 @no__t 0netTcpBinding > 的详细信息，请参阅[\<security >](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)。

    1. 在配置文件中的[\<system >](../../configure-apps/file-schema/wcf/system-servicemodel.md)元素下，添加一个[@no__t >](../../configure-apps/file-schema/wcf/bindings.md)元素。

    2. 将[@no__t >](../../configure-apps/file-schema/wcf/wshttpbinding.md)或[\<basicHttpBinding >](../../configure-apps/file-schema/wcf/basichttpbinding.md)元素添加到 "绑定" 部分。 有关创建 WCF 绑定元素的详细信息，请参阅 [How to：在配置](../how-to-specify-a-service-binding-in-configuration.md)中指定服务绑定。

    3. 将[@no__t 2security >](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md)或[\<security >](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md)的 `mode` 特性设置为 @no__t、@no__t 或 @no__t。

    4. 设置[@no__t @no__t >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)或[\<transport >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)的-0 属性。

        使用消息安全时，请将[@no__t 2message >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)的 `clientCredentialType` 特性设置为 `UserName`。

        在 HTTP （S）上使用传输级安全时，请将[@no__t @no__t >](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)或[\<transport >](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)的属性设置为 @no__t。

        > [!NOTE]
        > 当 WCF 服务在使用传输级安全性的 Internet Information Services （IIS）中承载时，@no__t 将属性设置为 <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom> 时，自定义身份验证方案将使用 Windows 身份验证的子集。 这是因为在这种情况下，IIS 将在 WCF 调用自定义验证器之前执行 Windows 身份验证。

    有关创建 WCF 绑定元素的详细信息，请参阅 [How to：在配置](../how-to-specify-a-service-binding-in-configuration.md)中指定服务绑定。

    下面的示例演示绑定的配置代码：

    ```xml
    <system.serviceModel>
      <bindings>
      <wsHttpBinding>
          <binding name="Binding1">
            <security mode="Message">
              <message clientCredentialType="UserName" />
            </security>
          </binding>
        </wsHttpBinding>
      </bindings>
    </system.serviceModel>
    ```

2. 配置一个行为，该行为指定使用自定义用户名和密码验证程序来验证传入的 <xref:System.IdentityModel.Tokens.UserNameSecurityToken> 安全令牌的用户名和密码对。

    1. 作为[\<system >](../../configure-apps/file-schema/wcf/system-servicemodel.md)元素的子元素，请添加[\<behaviors >](../../configure-apps/file-schema/wcf/behaviors.md)元素。

    2. 将[\<serviceBehaviors >](../../configure-apps/file-schema/wcf/servicebehaviors.md)添加到[@no__t >](../../configure-apps/file-schema/wcf/behaviors.md)元素。

    3. 添加一个[@no__t 1behavior >](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)元素，并将 `name` 属性设置为合适的值。

    4. 将[\<serviceCredentials >](../../configure-apps/file-schema/wcf/servicecredentials.md)添加到[@no__t >](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)元素。

    5. 将[\<userNameAuthentication >](../../configure-apps/file-schema/wcf/usernameauthentication.md)添加到[@no__t >](../../configure-apps/file-schema/wcf/servicecredentials.md)。

    6. 将 `userNamePasswordValidationMode` 设置为 `Custom`。

        > [!IMPORTANT]
        > 如果未设置 @no__t 值，则 WCF 将使用 Windows 身份验证，而不是自定义用户名和密码验证程序。

    7. 将 `customUserNamePasswordValidatorType` 设置为表示自定义用户名和密码验证程序的类型。

    下面的示例显示了到目前为止 `<serviceCredentials>` 片段：

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a>示例

下面的代码示例演示如何创建自定义用户名和密码验证程序。 请不要使用代码重写生产环境中的 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 方法。 请将该代码替换为你的自定义用户名和密码验证方案，这可能会涉及到从数据库检索用户名和密码对。

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a>请参阅

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [如何：使用 ASP.NET 成员资格提供程序 @ no__t-0
- [身份验证](authentication-in-wcf.md)
