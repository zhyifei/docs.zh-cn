---
title: 如何：使用自定义用户名和密码验证程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 593e3e97ad7e5ae65447d8618caacf22f762f9b4
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960071"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="f4cbb-102">如何：使用自定义用户名和密码验证程序</span><span class="sxs-lookup"><span data-stu-id="f4cbb-102">How to: Use a Custom User Name and Password Validator</span></span>
<span data-ttu-id="f4cbb-103">默认情况下，当用户名和密码用于身份验证，Windows Communication Foundation (WCF) 使用 Windows 来验证用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-103">By default, when a user name and password is used for authentication, Windows Communication Foundation (WCF) uses Windows to validate the user name and password.</span></span> <span data-ttu-id="f4cbb-104">但是，WCF 允许自定义用户名称和密码身份验证方案，也称为*验证程序*。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-104">However, WCF allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="f4cbb-105">若要合并自定义用户名和密码验证程序，请创建一个从 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> 派生的类，然后对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-105">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>  
  
 <span data-ttu-id="f4cbb-106">示例应用程序，请参阅[用户名密码验证程序](../../../../docs/framework/wcf/samples/user-name-password-validator.md)。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-106">For a sample application, see [User Name Password Validator](../../../../docs/framework/wcf/samples/user-name-password-validator.md).</span></span>  
  
### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="f4cbb-107">创建自定义用户名和密码验证程序</span><span class="sxs-lookup"><span data-stu-id="f4cbb-107">To create a custom user name and password validator</span></span>  
  
1. <span data-ttu-id="f4cbb-108">创建一个从 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> 派生的类。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-108">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2. <span data-ttu-id="f4cbb-109">通过重写 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 方法，实现自定义身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-109">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
     <span data-ttu-id="f4cbb-110">请不要使用下面示例中的代码在生产环境中重写 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-110">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="f4cbb-111">请将该代码替换为你的自定义用户名和密码验证方案，这可能会涉及到从数据库检索用户名和密码对。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-111">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>  
  
     <span data-ttu-id="f4cbb-112">若要将身份验证错误返回到客户端，应在 <xref:System.ServiceModel.FaultException> 方法中引发 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-112">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="f4cbb-113">配置服务以使用自定义用户名和密码验证程序</span><span class="sxs-lookup"><span data-stu-id="f4cbb-113">To configure a service to use a custom user name and password validator</span></span>  
  
1. <span data-ttu-id="f4cbb-114">配置一个绑定，该绑定在任何传输上使用消息安全，或者在 HTTP(S) 上使用传输级安全。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-114">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>  
  
     <span data-ttu-id="f4cbb-115">使用消息安全时，添加一个系统提供的绑定，如[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)，或[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)支持消息安全和`UserName`凭据类型。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-115">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>  
  
     <span data-ttu-id="f4cbb-116">使用传输级安全时在 HTTP (S)，添加[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)或[ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)即[ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)或[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)使用 HTTP (S) 和`Basic`身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-116">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f4cbb-117">使用 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] 或更高版本时，可将自定义用户名和密码验证程序与消息和传输安全一起使用。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-117">When [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] or later is used, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="f4cbb-118">对于 WinFX，自定义用户名和密码验证程序可以仅用于消息安全。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-118">With WinFX, a custom username and password validator can only be used with message security.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="f4cbb-119">有关使用的详细信息\<netTcpBinding > 在此上下文中，请参阅[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="f4cbb-119">For more information on using \<netTcpBinding> in this context, see [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span></span>  
  
    1. <span data-ttu-id="f4cbb-120">在配置文件中下, [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)元素中，添加[\<绑定 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)元素。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-120">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
    2. <span data-ttu-id="f4cbb-121">添加[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)或[ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)到绑定节的元素。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-121">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> <span data-ttu-id="f4cbb-122">有关创建 WCF 绑定元素的详细信息，请参阅[如何：在配置中指定服务绑定](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-122">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
    3. <span data-ttu-id="f4cbb-123">设置`mode`的属性[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)或[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)到`Message`， `Transport`，或`TransportWithMessageCredential`。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-123">Set the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>  
  
    4. <span data-ttu-id="f4cbb-124">设置`clientCredentialType`的属性[\<消息 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)或[\<传输 >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-124">Set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>  
  
         <span data-ttu-id="f4cbb-125">使用消息安全时，设置`clientCredentialType`的属性[\<消息 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)到`UserName`。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-125">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>  
  
         <span data-ttu-id="f4cbb-126">使用传输级安全时在 HTTP (S)，设置`clientCredentialType`的属性[\<传输 >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)或[\<传输 >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)到`Basic`。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-126">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f4cbb-127">当 WCF 服务承载在 Internet 信息服务 (IIS) 使用传输级安全和<xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A>属性设置为<xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>，自定义身份验证方案使用 Windows 身份验证的子集。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-127">When a WCF service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="f4cbb-128">这是因为在此方案中，IIS 执行 WCF 调用自定义身份验证器之前的 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-128">That is because in this scenario, IIS performs Windows authentication prior to WCF invoking the custom authenticator.</span></span>  
  
     <span data-ttu-id="f4cbb-129">有关创建 WCF 绑定元素的详细信息，请参阅[如何：在配置中指定服务绑定](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-129">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
     <span data-ttu-id="f4cbb-130">下面的示例显示绑定的配置代码。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-130">The following example shows the configuration code for the binding.</span></span>  
  
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
  
2. <span data-ttu-id="f4cbb-131">配置一个行为，该行为指定使用自定义用户名和密码验证程序来验证传入的 <xref:System.IdentityModel.Tokens.UserNameSecurityToken> 安全令牌的用户名和密码对。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-131">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>  
  
    1. <span data-ttu-id="f4cbb-132">为的子级[ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)元素中，添加[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)元素。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-132">As a child to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
    2. <span data-ttu-id="f4cbb-133">添加[ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)到[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)元素。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-133">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
    3. <span data-ttu-id="f4cbb-134">添加[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)元素，并设置`name`属性为适当的值。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-134">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
    4. <span data-ttu-id="f4cbb-135">添加[ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)到[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)元素。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-135">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>  
  
    5. <span data-ttu-id="f4cbb-136">添加[ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)到[ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-136">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span>  
  
    6. <span data-ttu-id="f4cbb-137">将 `userNamePasswordValidationMode` 设置为 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-137">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="f4cbb-138">如果`userNamePasswordValidationMode`未设置值，WCF 使用 Windows 身份验证而不是自定义用户名称和密码验证程序。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-138">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the custom user name and password validator.</span></span>  
  
    7. <span data-ttu-id="f4cbb-139">将 `customUserNamePasswordValidatorType` 设置为表示自定义用户名和密码验证程序的类型。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-139">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>  
  
     <span data-ttu-id="f4cbb-140">下面的示例演示至此为止的 `<serviceCredentials>` 片段。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-140">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
    ```xml  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## <a name="example"></a><span data-ttu-id="f4cbb-141">示例</span><span class="sxs-lookup"><span data-stu-id="f4cbb-141">Example</span></span>  
 <span data-ttu-id="f4cbb-142">下面的代码示例演示如何创建自定义用户名和密码验证程序。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-142">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="f4cbb-143">请不要使用代码重写生产环境中的 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-143">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="f4cbb-144">请将该代码替换为你的自定义用户名和密码验证方案，这可能会涉及到从数据库检索用户名和密码对。</span><span class="sxs-lookup"><span data-stu-id="f4cbb-144">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f4cbb-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4cbb-145">See also</span></span>

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [<span data-ttu-id="f4cbb-146">如何：使用 ASP.NET 成员资格提供程序</span><span class="sxs-lookup"><span data-stu-id="f4cbb-146">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
- [<span data-ttu-id="f4cbb-147">身份验证</span><span class="sxs-lookup"><span data-stu-id="f4cbb-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
