---
title: "如何：使用自定义用户名和密码验证程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9086489d7b48b459ad92f1712809406cbde7e074
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="27541-102">如何：使用自定义用户名和密码验证程序</span><span class="sxs-lookup"><span data-stu-id="27541-102">How to: Use a Custom User Name and Password Validator</span></span>
<span data-ttu-id="27541-103">默认情况下，当用户名和密码用于身份验证时，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 会使用 Windows 来验证用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="27541-103">By default, when a user name and password is used for authentication, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uses Windows to validate the user name and password.</span></span> <span data-ttu-id="27541-104">但是，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]允许为自定义用户名称和密码身份验证方案，也称为*验证程序*。</span><span class="sxs-lookup"><span data-stu-id="27541-104">However, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="27541-105">若要合并自定义用户名和密码验证程序，请创建一个从 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> 派生的类，然后对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="27541-105">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>  
  
 <span data-ttu-id="27541-106">有关示例应用程序，请参阅[用户密码验证程序](../../../../docs/framework/wcf/samples/user-name-password-validator.md)。</span><span class="sxs-lookup"><span data-stu-id="27541-106">For a sample application, see [User Name Password Validator](../../../../docs/framework/wcf/samples/user-name-password-validator.md).</span></span>  
  
### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="27541-107">创建自定义用户名和密码验证程序</span><span class="sxs-lookup"><span data-stu-id="27541-107">To create a custom user name and password validator</span></span>  
  
1.  <span data-ttu-id="27541-108">创建一个从 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> 派生的类。</span><span class="sxs-lookup"><span data-stu-id="27541-108">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2.  <span data-ttu-id="27541-109">通过重写 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 方法，实现自定义身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="27541-109">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
     <span data-ttu-id="27541-110">请不要使用下面示例中的代码在生产环境中重写 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="27541-110">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="27541-111">请将该代码替换为您的自定义用户名和密码验证方案，这可能会涉及到从数据库检索用户名和密码对。</span><span class="sxs-lookup"><span data-stu-id="27541-111">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>  
  
     <span data-ttu-id="27541-112">若要将身份验证错误返回到客户端，应在 <xref:System.ServiceModel.FaultException> 方法中引发 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>。</span><span class="sxs-lookup"><span data-stu-id="27541-112">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="27541-113">配置服务以使用自定义用户名和密码验证程序</span><span class="sxs-lookup"><span data-stu-id="27541-113">To configure a service to use a custom user name and password validator</span></span>  
  
1.  <span data-ttu-id="27541-114">配置一个绑定，该绑定在任何传输上使用消息安全，或者在 HTTP(S) 上使用传输级安全。</span><span class="sxs-lookup"><span data-stu-id="27541-114">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>  
  
     <span data-ttu-id="27541-115">使用消息安全时，添加一个系统提供的绑定，如[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)，或[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)支持消息安全与`UserName`凭据类型。</span><span class="sxs-lookup"><span data-stu-id="27541-115">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>  
  
     <span data-ttu-id="27541-116">在使用传输级安全在 HTTP (S)，将[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)或[ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)、 [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)或[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) ，它使用 HTTP (S) 和`Basic`身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="27541-116">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="27541-117">使用 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] 或更高版本时，可将自定义用户名和密码验证程序与消息和传输安全一起使用。</span><span class="sxs-lookup"><span data-stu-id="27541-117">When [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] or later is used, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="27541-118">使用 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 时，自定义用户名和密码验证程序只能与消息安全一起使用。</span><span class="sxs-lookup"><span data-stu-id="27541-118">With [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], a custom username and password validator can only be used with message security.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="27541-119">有关详细信息使用\<netTcpBinding > 在此上下文中，请参阅[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="27541-119">For more information on using \<netTcpBinding> in this context, see [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span></span>  
  
    1.  <span data-ttu-id="27541-120">在配置文件中，在[ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)元素中，添加[\<绑定 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)元素。</span><span class="sxs-lookup"><span data-stu-id="27541-120">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
    2.  <span data-ttu-id="27541-121">添加[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)或[ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)绑定节的元素。</span><span class="sxs-lookup"><span data-stu-id="27541-121">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="27541-122">创建[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]绑定元素，请参阅[如何： 在配置中指定服务绑定](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="27541-122"> creating an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
    3.  <span data-ttu-id="27541-123">设置`mode`属性[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)或[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)到`Message`， `Transport`， `or``TransportWithMessageCredential`。</span><span class="sxs-lookup"><span data-stu-id="27541-123">Set the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, `or``TransportWithMessageCredential`.</span></span>  
  
    4.  <span data-ttu-id="27541-124">设置`clientCredentialType`属性[\<消息 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)或[\<传输 >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)。</span><span class="sxs-lookup"><span data-stu-id="27541-124">Set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>  
  
         <span data-ttu-id="27541-125">使用消息安全时，设置`clientCredentialType`属性[\<消息 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md)到`UserName`。</span><span class="sxs-lookup"><span data-stu-id="27541-125">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>  
  
         <span data-ttu-id="27541-126">当使用传输级安全在 HTTP (S)，设置`clientCredentialType`属性[\<传输 >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)或[\<传输 >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md)到`Basic`。</span><span class="sxs-lookup"><span data-stu-id="27541-126">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="27541-127">如果使用传输级安全在 Internet 信息服务(IIS) 中承载 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务，并且将 <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> 属性设置为 <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>，则自定义身份验证方案会使用 Windows 身份验证的子集。</span><span class="sxs-lookup"><span data-stu-id="27541-127">When a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="27541-128">这是因为在此情况下，IIS 会在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 调用自定义验证器之前执行 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="27541-128">That is because in this scenario, IIS performs Windows authentication prior to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] invoking the custom authenticator.</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="27541-129">创建[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]绑定元素，请参阅[如何： 在配置中指定服务绑定](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="27541-129"> creating an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
     <span data-ttu-id="27541-130">下面的示例显示绑定的配置代码。</span><span class="sxs-lookup"><span data-stu-id="27541-130">The following example shows the configuration code for the binding.</span></span>  
  
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
  
2.  <span data-ttu-id="27541-131">配置一个行为，该行为指定使用自定义用户名和密码验证程序来验证传入的 <xref:System.IdentityModel.Tokens.UserNameSecurityToken> 安全令牌的用户名和密码对。</span><span class="sxs-lookup"><span data-stu-id="27541-131">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>  
  
    1.  <span data-ttu-id="27541-132">为的子级[ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)元素中，添加[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)元素。</span><span class="sxs-lookup"><span data-stu-id="27541-132">As a child to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
    2.  <span data-ttu-id="27541-133">添加[ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)到[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)元素。</span><span class="sxs-lookup"><span data-stu-id="27541-133">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
    3.  <span data-ttu-id="27541-134">添加[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)元素，并设置`name`属性设为适当的值。</span><span class="sxs-lookup"><span data-stu-id="27541-134">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
    4.  <span data-ttu-id="27541-135">添加[ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)到[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)元素。</span><span class="sxs-lookup"><span data-stu-id="27541-135">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>  
  
    5.  <span data-ttu-id="27541-136">添加[ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)到[ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)。</span><span class="sxs-lookup"><span data-stu-id="27541-136">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span>  
  
    6.  <span data-ttu-id="27541-137">将 `userNamePasswordValidationMode` 设置为 `Custom`。</span><span class="sxs-lookup"><span data-stu-id="27541-137">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="27541-138">如果未设置 `userNamePasswordValidationMode` 值，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 会使用 Windows 身份验证而不是自定义用户名和密码验证程序。</span><span class="sxs-lookup"><span data-stu-id="27541-138">If the `userNamePasswordValidationMode` value is not set, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses Windows authentication instead of the custom user name and password validator.</span></span>  
  
    7.  <span data-ttu-id="27541-139">将 `customUserNamePasswordValidatorType` 设置为表示自定义用户名和密码验证程序的类型。</span><span class="sxs-lookup"><span data-stu-id="27541-139">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>  
  
     <span data-ttu-id="27541-140">下面的示例演示至此为止的 `<serviceCredentials>` 片段。</span><span class="sxs-lookup"><span data-stu-id="27541-140">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
    ```xml  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## <a name="example"></a><span data-ttu-id="27541-141">示例</span><span class="sxs-lookup"><span data-stu-id="27541-141">Example</span></span>  
 <span data-ttu-id="27541-142">下面的代码示例演示如何创建自定义用户名和密码验证程序。</span><span class="sxs-lookup"><span data-stu-id="27541-142">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="27541-143">请不要使用代码重写生产环境中的 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="27541-143">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="27541-144">请将该代码替换为您的自定义用户名和密码验证方案，这可能会涉及到从数据库检索用户名和密码对。</span><span class="sxs-lookup"><span data-stu-id="27541-144">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="27541-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27541-145">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>  
 [<span data-ttu-id="27541-146">如何： 使用 ASP.NET 成员资格提供程序</span><span class="sxs-lookup"><span data-stu-id="27541-146">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 [<span data-ttu-id="27541-147">身份验证</span><span class="sxs-lookup"><span data-stu-id="27541-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
