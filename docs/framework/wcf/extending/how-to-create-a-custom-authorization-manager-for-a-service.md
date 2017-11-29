---
title: "如何：为服务创建自定义授权管理器"
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
helpviewer_keywords:
- Windows Communication Foundation, extending
- OperationRequirement class
ms.assetid: 6214afde-44c1-4bf5-ba07-5ad6493620ea
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b8d934509940bf712ccb7463156c88540027407
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-authorization-manager-for-a-service"></a><span data-ttu-id="2c903-102">如何：为服务创建自定义授权管理器</span><span class="sxs-lookup"><span data-stu-id="2c903-102">How to: Create a Custom Authorization Manager for a Service</span></span>
<span data-ttu-id="2c903-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中的标识模型基础结构支持基于声明的可扩展授权模型。</span><span class="sxs-lookup"><span data-stu-id="2c903-103">The Identity Model infrastructure in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] supports an extensible claims-based authorization model.</span></span> <span data-ttu-id="2c903-104">声明是从令牌中提取的，自定义授权策略将有选择地对其进行处理，然后放入 <xref:System.IdentityModel.Policy.AuthorizationContext> 中。</span><span class="sxs-lookup"><span data-stu-id="2c903-104">Claims are extracted from tokens and optionally processed by custom authorization policies and then placed into an <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="2c903-105">授权管理器检查 <xref:System.IdentityModel.Policy.AuthorizationContext> 中的声明，从而作出授权决策。</span><span class="sxs-lookup"><span data-stu-id="2c903-105">An authorization manager examines the claims in the <xref:System.IdentityModel.Policy.AuthorizationContext> to make authorization decisions.</span></span>  
  
 <span data-ttu-id="2c903-106">默认情况下，授权决策由 <xref:System.ServiceModel.ServiceAuthorizationManager> 类作出；但是，可通过创建自定义授权管理器来覆盖这些决策。</span><span class="sxs-lookup"><span data-stu-id="2c903-106">By default, authorization decisions are made by the <xref:System.ServiceModel.ServiceAuthorizationManager> class; however these decisions can be overridden by creating a custom authorization manager.</span></span> <span data-ttu-id="2c903-107">若要创建自定义授权管理器，请创建一个从 <xref:System.ServiceModel.ServiceAuthorizationManager> 派生的类，并实现 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="2c903-107">To create a custom authorization manager, create a class that derives from <xref:System.ServiceModel.ServiceAuthorizationManager> and implement <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="2c903-108">授权决策是在 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 方法中作出的，如果允许访问，该方法返回 `true`，如果拒绝访问，则返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="2c903-108">Authorization decisions are made in the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method, which returns `true` when access is granted and `false` when access is denied.</span></span>  
  
 <span data-ttu-id="2c903-109">如果授权决策取决于消息正文的内容，请使用 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="2c903-109">If the authorization decision depends on the contents of the message body, use the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method.</span></span>  
  
 <span data-ttu-id="2c903-110">由于性能问题，如有可能，应重新设计应用程序，使授权决策不需要访问消息正文。</span><span class="sxs-lookup"><span data-stu-id="2c903-110">Because of performance issues, if possible you should redesign your application so that the authorization decision does not require access to the message body.</span></span>  
  
 <span data-ttu-id="2c903-111">在代码或配置中，可以进行服务的自定义授权管理器注册。</span><span class="sxs-lookup"><span data-stu-id="2c903-111">Registration of the custom authorization manager for a service can be done in code or configuration.</span></span>  
  
### <a name="to-create-a-custom-authorization-manager"></a><span data-ttu-id="2c903-112">创建自定义授权管理器</span><span class="sxs-lookup"><span data-stu-id="2c903-112">To create a custom authorization manager</span></span>  
  
1.  <span data-ttu-id="2c903-113">从 <xref:System.ServiceModel.ServiceAuthorizationManager> 类派生一个类。</span><span class="sxs-lookup"><span data-stu-id="2c903-113">Derive a class from the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
     [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]  
  
2.  <span data-ttu-id="2c903-114">重写 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> 方法。</span><span class="sxs-lookup"><span data-stu-id="2c903-114">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method.</span></span>  
  
     <span data-ttu-id="2c903-115">使用传给 <xref:System.ServiceModel.OperationContext> 方法的 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> 进行授权决策。</span><span class="sxs-lookup"><span data-stu-id="2c903-115">Use the <xref:System.ServiceModel.OperationContext> that is passed to the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method to make authorization decisions.</span></span>  
  
     <span data-ttu-id="2c903-116">下面的代码示例使用 <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> 方法查找自定义声明 `http://www.contoso.com/claims/allowedoperation`，从而做出授权决策。</span><span class="sxs-lookup"><span data-stu-id="2c903-116">The following code example uses the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> method to find the custom claim `http://www.contoso.com/claims/allowedoperation` to make an authorization decision.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
     [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]  
  
### <a name="to-register-a-custom-authorization-manager-using-code"></a><span data-ttu-id="2c903-117">使用代码注册自定义授权管理器</span><span class="sxs-lookup"><span data-stu-id="2c903-117">To register a custom authorization manager using code</span></span>  
  
1.  <span data-ttu-id="2c903-118">创建自定义授权管理器的一个实例，然后将其分配给 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="2c903-118">Create an instance of the custom authorization manager and assign it to the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A> property.</span></span>  
  
     <span data-ttu-id="2c903-119">使用 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> 属性可以访问 <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>。</span><span class="sxs-lookup"><span data-stu-id="2c903-119">The <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> can be accessed using <xref:System.ServiceModel.ServiceHostBase.Authorization%2A> property.</span></span>  
  
     <span data-ttu-id="2c903-120">下面的代码示例注册 `MyServiceAuthorizationManager` 自定义授权管理器。</span><span class="sxs-lookup"><span data-stu-id="2c903-120">The following code example registers the `MyServiceAuthorizationManager` custom authorization manager.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
     [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]  
  
### <a name="to-register-a-custom-authorization-manager-using-configuration"></a><span data-ttu-id="2c903-121">使用配置注册自定义授权管理器</span><span class="sxs-lookup"><span data-stu-id="2c903-121">To register a custom authorization manager using configuration</span></span>  
  
1.  <span data-ttu-id="2c903-122">打开服务的配置文件。</span><span class="sxs-lookup"><span data-stu-id="2c903-122">Open the configuration file for the service.</span></span>  
  
2.  <span data-ttu-id="2c903-123">添加[ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)到[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)。</span><span class="sxs-lookup"><span data-stu-id="2c903-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).</span></span>  
  
     <span data-ttu-id="2c903-124">到[ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)，添加`serviceAuthorizationManagerType`属性，并将其值设置为表示自定义授权管理器的类型。</span><span class="sxs-lookup"><span data-stu-id="2c903-124">To the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), add a `serviceAuthorizationManagerType` attribute and set its value to the type that represents the custom authorization manager.</span></span>  
  
3.  <span data-ttu-id="2c903-125">添加一个保护客户端和服务之间的通信的绑定。</span><span class="sxs-lookup"><span data-stu-id="2c903-125">Add a binding that secures the communication between the client and service.</span></span>  
  
     <span data-ttu-id="2c903-126">为此通信选择的绑定决定了添加到 <xref:System.IdentityModel.Policy.AuthorizationContext> 的声明，自定义授权管理器使用这些声明来进行授权决策。</span><span class="sxs-lookup"><span data-stu-id="2c903-126">The binding that is chosen for this communication determines the claims that are added to the <xref:System.IdentityModel.Policy.AuthorizationContext>, which the custom authorization manager uses to make authorization decisions.</span></span> <span data-ttu-id="2c903-127">系统提供的绑定有关的更多详细信息，请参阅[系统提供的绑定](../../../../docs/framework/wcf/system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="2c903-127">For more details about the system-provided bindings, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
4.  <span data-ttu-id="2c903-128">通过添加关联到服务终结点，行为[\<服务 >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md)元素并将的值设置`behaviorConfiguration`属性的名称属性的值为[\<行为>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)元素。</span><span class="sxs-lookup"><span data-stu-id="2c903-128">Associate the behavior to a service endpoint, by adding a [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) element and set the value of the `behaviorConfiguration` attribute to the value of the name attribute for the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>  
  
     <span data-ttu-id="2c903-129">有关配置服务终结点的详细信息，请参阅[如何： 在配置中创建服务终结点](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="2c903-129">For more information about configuring a service endpoint, see [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).</span></span>  
  
     <span data-ttu-id="2c903-130">下面的代码示例注册自定义授权管理器 `Samples.MyServiceAuthorizationManager`。</span><span class="sxs-lookup"><span data-stu-id="2c903-130">The following code example registers the custom authorization manager `Samples.MyServiceAuthorizationManager`.</span></span>  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service   
              name="Microsoft.ServiceModel.Samples.CalculatorService"  
              behaviorConfiguration="CalculatorServiceBehavior">  
            <host>  
              <baseAddresses>  
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
              </baseAddresses>  
            </host>  
            <endpoint address=""  
                      binding="wsHttpBinding_Calculator"  
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <WSHttpBinding>  
           <binding name = "wsHttpBinding_Calculator">  
             <security mode="Message">  
               <message clientCredentialType="Windows"/>  
             </security>  
            </binding>  
          </WSHttpBinding>  
    </bindings>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="CalculatorServiceBehavior">  
              <serviceAuthorization serviceAuthorizationManagerType="Samples.MyServiceAuthorizationManager,MyAssembly" />  
             </behavior>  
         </serviceBehaviors>  
       </behaviors>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
    > [!WARNING]
    >  <span data-ttu-id="2c903-131">请注意，当您指定了 serviceAuthorizationManagerType 时，字符串必须包含完全限定的类型名称、</span><span class="sxs-lookup"><span data-stu-id="2c903-131">Note that when you specify the serviceAuthorizationManagerType, the string must contain the fully qualified type name.</span></span> <span data-ttu-id="2c903-132">一个逗号，以及在其中定义类型的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="2c903-132">a comma, and the name of the assembly in which the type is defined.</span></span> <span data-ttu-id="2c903-133">如果您忽略了程序集名称，WCF 会尝试从 System.ServiceModel.dll 加载类型。</span><span class="sxs-lookup"><span data-stu-id="2c903-133">If you leave out the assembly name, WCF will attempt to load the type from System.ServiceModel.dll.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c903-134">示例</span><span class="sxs-lookup"><span data-stu-id="2c903-134">Example</span></span>  
 <span data-ttu-id="2c903-135">下面的代码示例演示 <xref:System.ServiceModel.ServiceAuthorizationManager> 类的一个基本实现，包括重写 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="2c903-135">The following code example demonstrates a basic implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class that includes overriding the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="2c903-136">该示例代码检查某个自定义声明的 <xref:System.IdentityModel.Policy.AuthorizationContext>，如果该自定义声明的资源与 `true` 中的操作值匹配，则返回 <xref:System.ServiceModel.OperationContext>。</span><span class="sxs-lookup"><span data-stu-id="2c903-136">The example code examines the <xref:System.IdentityModel.Policy.AuthorizationContext> for a custom claim and returns `true` when the resource for that custom claim matches the action value from the <xref:System.ServiceModel.OperationContext>.</span></span> <span data-ttu-id="2c903-137">有关更完整实现<xref:System.ServiceModel.ServiceAuthorizationManager>类，请参阅[授权策略](../../../../docs/framework/wcf/samples/authorization-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="2c903-137">For a more complete implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class, see [Authorization Policy](../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
 [!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
 [!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="2c903-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c903-138">See Also</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [<span data-ttu-id="2c903-139">授权策略</span><span class="sxs-lookup"><span data-stu-id="2c903-139">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)  
 [<span data-ttu-id="2c903-140">授权策略</span><span class="sxs-lookup"><span data-stu-id="2c903-140">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)
