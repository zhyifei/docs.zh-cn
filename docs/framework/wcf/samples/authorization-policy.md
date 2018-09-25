---
title: 授权策略
ms.date: 03/30/2017
ms.assetid: 1db325ec-85be-47d0-8b6e-3ba2fdf3dda0
ms.openlocfilehash: 78ca42abfd2df56edeeb273fcd8ba585aa16f635
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "47111433"
---
# <a name="authorization-policy"></a><span data-ttu-id="489f7-102">授权策略</span><span class="sxs-lookup"><span data-stu-id="489f7-102">Authorization Policy</span></span>

<span data-ttu-id="489f7-103">此示例演示如何实现一个自定义声明授权策略和一个关联的自定义服务授权管理器。</span><span class="sxs-lookup"><span data-stu-id="489f7-103">This sample demonstrates how to implement a custom claim authorization policy and an associated custom service authorization manager.</span></span> <span data-ttu-id="489f7-104">这在服务对服务操作进行基于声明的访问检查，并在进行访问检查之前授予调用方某些权限时很有用。</span><span class="sxs-lookup"><span data-stu-id="489f7-104">This is useful when the service makes claim-based access checks to service operations and prior to the access checks, grants the caller certain rights.</span></span> <span data-ttu-id="489f7-105">此示例演示添加声明的过程，以及对最终的声明集进行访问检查的过程。</span><span class="sxs-lookup"><span data-stu-id="489f7-105">This sample shows both the process of adding claims as well as the process for doing an access check against the finalized set of claims.</span></span> <span data-ttu-id="489f7-106">客户端与服务器之间的所有应用程序消息均已进行签名和加密。</span><span class="sxs-lookup"><span data-stu-id="489f7-106">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="489f7-107">默认情况下，对于 `wsHttpBinding` 绑定，使用客户端提供的用户名和密码登录有效的 Windows NT 帐户。</span><span class="sxs-lookup"><span data-stu-id="489f7-107">By default with the `wsHttpBinding` binding, a username and password supplied by the client are used to logon to a valid Windows NT account.</span></span> <span data-ttu-id="489f7-108">此示例演示如何利用自定义 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> 对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="489f7-108">This sample demonstrates how to utilize a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> to authenticate the client.</span></span> <span data-ttu-id="489f7-109">此外，此示例还演示使用 X.509 证书对服务进行客户端身份验证。</span><span class="sxs-lookup"><span data-stu-id="489f7-109">In addition this sample shows the client authenticating to the service using an X.509 certificate.</span></span> <span data-ttu-id="489f7-110">此示例演示了 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 和 <xref:System.ServiceModel.ServiceAuthorizationManager> 的实现，该实现在它们之间为特定用户授予对服务的特定方法的访问权限。</span><span class="sxs-lookup"><span data-stu-id="489f7-110">This sample shows an implementation of <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and <xref:System.ServiceModel.ServiceAuthorizationManager>, which between them grant access to specific methods of the service for specific users.</span></span> <span data-ttu-id="489f7-111">此示例基于[用户名消息安全](../../../../docs/framework/wcf/samples/message-security-user-name.md)，但演示了如何执行之前的声明转换<xref:System.ServiceModel.ServiceAuthorizationManager>被调用。</span><span class="sxs-lookup"><span data-stu-id="489f7-111">This sample is based on the [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md), but demonstrates how to perform a claim transformation prior to the <xref:System.ServiceModel.ServiceAuthorizationManager> being called.</span></span>

> [!NOTE]
> <span data-ttu-id="489f7-112">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="489f7-112">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="489f7-113">概括而言，此示例演示：</span><span class="sxs-lookup"><span data-stu-id="489f7-113">In summary, this sample demonstrates how:</span></span>

-   <span data-ttu-id="489f7-114">如何使用用户名和密码对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="489f7-114">The client can be authenticated using a user name-password.</span></span>

-   <span data-ttu-id="489f7-115">如何使用 X.509 证书对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="489f7-115">The client can be authenticated using an X.509 certificate.</span></span>

-   <span data-ttu-id="489f7-116">服务器如何根据自定义 `UsernamePassword` 验证程序验证客户端凭据。</span><span class="sxs-lookup"><span data-stu-id="489f7-116">The server validates the client credentials against a custom `UsernamePassword` validator.</span></span>

-   <span data-ttu-id="489f7-117">如何使用服务器的 X.509 证书对服务器进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="489f7-117">The server is authenticated using the server's X.509 certificate.</span></span>

-   <span data-ttu-id="489f7-118">服务器可以使用 <xref:System.ServiceModel.ServiceAuthorizationManager> 控制对服务中的某些方法的访问。</span><span class="sxs-lookup"><span data-stu-id="489f7-118">The server can use <xref:System.ServiceModel.ServiceAuthorizationManager> to control access to certain methods in the service.</span></span>

-   <span data-ttu-id="489f7-119">如何实现 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>。</span><span class="sxs-lookup"><span data-stu-id="489f7-119">How to implement <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.</span></span>

<span data-ttu-id="489f7-120">服务公开两个终结点，以便与使用配置文件 App.config 定义的服务进行通信。每个终结点由地址、绑定和协定组成。</span><span class="sxs-lookup"><span data-stu-id="489f7-120">The service exposes two endpoints for communicating with the service, defined using the configuration file App.config. Each endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="489f7-121">其中一个绑定是使用标准 `wsHttpBinding` 绑定配置的，该标准绑定使用 WS-Security 和客户端用户名身份验证。</span><span class="sxs-lookup"><span data-stu-id="489f7-121">One binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client username authentication.</span></span> <span data-ttu-id="489f7-122">另一个绑定是使用标准 `wsHttpBinding` 绑定配置的，该标准绑定使用 WS-Security 和客户端证书身份验证。</span><span class="sxs-lookup"><span data-stu-id="489f7-122">The other binding is configured with a standard `wsHttpBinding` binding that uses WS-Security and client certificate authentication.</span></span> <span data-ttu-id="489f7-123">[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)指定要用于服务身份验证的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="489f7-123">The [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) specifies that the user credentials are to be used for service authentication.</span></span> <span data-ttu-id="489f7-124">服务器证书必须包含相同的值`SubjectName`属性设置为`findValue`属性中[ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)。</span><span class="sxs-lookup"><span data-stu-id="489f7-124">The server certificate must contain the same value for the `SubjectName` property as the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <!-- configure base address provided by host -->
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service"/>
        </baseAddresses>
      </host>
      <!-- use base address provided by host, provide two endpoints -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <endpoint address="certificate"
                binding="wsHttpBinding"
                bindingConfiguration="Binding2"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
    <message clientCredentialType="UserName" />
        </security>
      </binding>
      <!-- X509 certificate binding -->
      <binding name="Binding2">
        <security mode="Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior" >
        <serviceDebug includeExceptionDetailInFaults ="true" />
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to specify authentication constraints on client certificates.
          -->
          <clientCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
          <!--
          The serviceCredentials behavior allows one to define a service certificate.
          A service certificate is used by a client to authenticate the service and provide message protection.
          This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
        <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
          <!--
          The serviceAuthorization behavior allows one to specify custom authorization policies.
          -->
          <authorizationPolicies>
            <add policyType="Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary" />
          </authorizationPolicies>
        </serviceAuthorization>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

<span data-ttu-id="489f7-125">每个客户端终结点配置由配置名称、服务终结点的绝对地址、绑定和协定组成。</span><span class="sxs-lookup"><span data-stu-id="489f7-125">Each client endpoint configuration consists of a configuration name, an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="489f7-126">客户端绑定配置为具有适当的安全模式指定在此情况下中[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)并`clientCredentialType`中指定的那样[\<消息 >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="489f7-126">The client binding is configured with the appropriate security mode as specified in this case in the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) and `clientCredentialType` as specified in the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).</span></span>

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
            address="http://localhost:8001/servicemodelsamples/service/username"
    binding="wsHttpBinding"
    bindingConfiguration="Binding1"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator" >
      </endpoint>
      <!-- X509 certificate based endpoint -->
      <endpoint name="Certificate"
                        address="http://localhost:8001/servicemodelsamples/service/certificate"
                binding="wsHttpBinding"
            bindingConfiguration="Binding2"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
        <!-- X509 certificate binding -->
        <binding name="Binding2">
          <security mode="Message">
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
    </wsHttpBinding>
    </bindings>

    <behaviors>
      <behavior name="ClientCertificateBehavior">
        <clientCredentials>
          <serviceCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust
            means that if the certificate
            is in the user's Trusted People store, then it will be
            trusted without performing a
            validation of the certificate's issuer chain. This setting
            is used here for convenience so that the
            sample can be run without having to have certificates
            issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust.
            The security implications of this
            setting should be carefully considered before using
            PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode = "PeerOrChainTrust" />
          </serviceCertificate>
        </clientCredentials>
      </behavior>
    </behaviors>

  </system.serviceModel>
```

<span data-ttu-id="489f7-127">对于基于用户名的终结点，客户端实现设置要使用的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="489f7-127">For the user name-based endpoint, the client implementation sets the user name and password to use.</span></span>

```csharp
// Create a client with Username endpoint configuration
CalculatorClient client1 = new CalculatorClient("Username");

client1.ClientCredentials.UserName.UserName = "test1";
client1.ClientCredentials.UserName.Password = "1tset";

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client1.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client1.Close();
```

<span data-ttu-id="489f7-128">对于基于证书的终结点，客户端实现设置要使用的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="489f7-128">For the certificate-based endpoint, the client implementation sets the client certificate to use.</span></span>

```csharp
// Create a client with Certificate endpoint configuration
CalculatorClient client2 = new CalculatorClient("Certificate");

client2.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client2.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client2.Close();
```

<span data-ttu-id="489f7-129">此示例使用自定义 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> 验证用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="489f7-129">This sample uses a custom <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> to validate user names and passwords.</span></span> <span data-ttu-id="489f7-130">此示例实现从 `MyCustomUserNamePasswordValidator` 派生的 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>。</span><span class="sxs-lookup"><span data-stu-id="489f7-130">The sample implements `MyCustomUserNamePasswordValidator`, derived from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span> <span data-ttu-id="489f7-131">有关更多信息，请参见有关 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> 的文档。</span><span class="sxs-lookup"><span data-stu-id="489f7-131">See the documentation about <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> for more information.</span></span> <span data-ttu-id="489f7-132">为了演示与 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> 的集成，此自定义验证程序示例实现了 <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> 方法，以在用户名与密码匹配时接受用户名/密码对，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="489f7-132">For the purposes of demonstrating the integration with the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, this custom validator sample implements the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method to accept user name/password pairs where the user name matches the password as shown in the following code.</span></span>

```csharp
public class MyCustomUserNamePasswordValidator : UserNamePasswordValidator
{
  // This method validates users. It allows in two users,
  // test1 and test2 with passwords 1tset and 2tset respectively.
  // This code is for illustration purposes only and
  // MUST NOT be used in a production environment because it
  // is NOT secure.
  public override void Validate(string userName, string password)
  {
    if (null == userName || null == password)
    {
      throw new ArgumentNullException();
    }

    if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))
    {
      throw new SecurityTokenException("Unknown Username or Password");
    }
  }
}
```

<span data-ttu-id="489f7-133">在服务代码中实现验证程序后，必须通知服务主机关于要使用的验证程序实例的信息。</span><span class="sxs-lookup"><span data-stu-id="489f7-133">Once the validator is implemented in service code, the service host must be informed about the validator instance to use.</span></span> <span data-ttu-id="489f7-134">这是使用以下代码：</span><span class="sxs-lookup"><span data-stu-id="489f7-134">This is done using the following code:</span></span>

```csharp
Servicehost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials.UserNameAuthentication.CustomUserNamePasswordValidator = new MyCustomUserNamePasswordValidatorProvider();
```

<span data-ttu-id="489f7-135">或者，可以执行在配置中相同的操作：</span><span class="sxs-lookup"><span data-stu-id="489f7-135">Or you can do the same thing in configuration:</span></span>

```xml
<behavior ...>
    <serviceCredentials>
      <!--
      The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
      -->
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
    ...
    </serviceCredentials>
</behavior>
```

<span data-ttu-id="489f7-136">Windows Communication Foundation (WCF) 提供丰富的基于声明的模型，用于执行访问检查。</span><span class="sxs-lookup"><span data-stu-id="489f7-136">Windows Communication Foundation (WCF) provides a rich claims-based model for performing access checks.</span></span> <span data-ttu-id="489f7-137"><xref:System.ServiceModel.ServiceAuthorizationManager> 对象用于执行访问检查，并确定与客户端关联的声明是否满足访问服务方法的必需要求。</span><span class="sxs-lookup"><span data-stu-id="489f7-137">The <xref:System.ServiceModel.ServiceAuthorizationManager> object is used to perform the access check and determine whether the claims associated with the client satisfy the requirements necessary to access the service method.</span></span>

<span data-ttu-id="489f7-138">出于演示目的，此示例演示的实现<xref:System.ServiceModel.ServiceAuthorizationManager>，它实现<xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>方法，以允许对方法的用户的访问权限基于声明的类型 http://example.com/claims/allowedoperation其值是为该操作的操作 URI允许调用。</span><span class="sxs-lookup"><span data-stu-id="489f7-138">For the purposes of demonstration, this sample shows an implementation of <xref:System.ServiceModel.ServiceAuthorizationManager> that implements the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method to allow a user's access to methods based on claims of type http://example.com/claims/allowedoperation whose value is the Action URI of the operation that is allowed to be called.</span></span>

```csharp
public class MyServiceAuthorizationManager : ServiceAuthorizationManager
{
  protected override bool CheckAccessCore(OperationContext operationContext)
  {
    string action = operationContext.RequestContext.RequestMessage.Headers.Action;
    Console.WriteLine("action: {0}", action);
    foreach(ClaimSet cs in operationContext.ServiceSecurityContext.AuthorizationContext.ClaimSets)
    {
      if ( cs.Issuer == ClaimSet.System )
      {
        foreach (Claim c in cs.FindClaims("http://example.com/claims/allowedoperation", Rights.PossessProperty))
        {
          Console.WriteLine("resource: {0}", c.Resource.ToString());
          if (action == c.Resource.ToString())
            return true;
        }
      }
    }
    return false;
  }
}
```

<span data-ttu-id="489f7-139">实现自定义 <xref:System.ServiceModel.ServiceAuthorizationManager> 后，必须通知服务主机关于要使用的 <xref:System.ServiceModel.ServiceAuthorizationManager> 的信息。</span><span class="sxs-lookup"><span data-stu-id="489f7-139">Once the custom <xref:System.ServiceModel.ServiceAuthorizationManager> is implemented, the service host must be informed about the <xref:System.ServiceModel.ServiceAuthorizationManager> to use.</span></span> <span data-ttu-id="489f7-140">这是通过如下所示的代码完成的。</span><span class="sxs-lookup"><span data-stu-id="489f7-140">This is done as shown in the following code.</span></span>

```xml
<behavior ...>
    ...
    <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
        ...
    </serviceAuthorization>
</behavior>
```

<span data-ttu-id="489f7-141">要实现的主要 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 方法是 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 方法。</span><span class="sxs-lookup"><span data-stu-id="489f7-141">The primary <xref:System.IdentityModel.Policy.IAuthorizationPolicy> method to implement is the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method.</span></span>

```csharp
public class MyAuthorizationPolicy : IAuthorizationPolicy
{
    string id;

    public MyAuthorizationPolicy()
    {
    id =  Guid.NewGuid().ToString();
    }

    public bool Evaluate(EvaluationContext evaluationContext,
                                            ref object state)
    {
        bool bRet = false;
        CustomAuthState customstate = null;

        if (state == null)
        {
            customstate = new CustomAuthState();
            state = customstate;
        }
        else
            customstate = (CustomAuthState)state;
        Console.WriteLine("In Evaluate");
        if (!customstate.ClaimsAdded)
        {
           IList<Claim> claims = new List<Claim>();

           foreach (ClaimSet cs in evaluationContext.ClaimSets)
              foreach (Claim c in cs.FindClaims(ClaimTypes.Name,
                                         Rights.PossessProperty))
                  foreach (string s in
                        GetAllowedOpList(c.Resource.ToString()))
                  {
                       claims.Add(new
               Claim("http://example.com/claims/allowedoperation",
                                    s, Rights.PossessProperty));
                            Console.WriteLine("Claim added {0}", s);
                      }
                   evaluationContext.AddClaimSet(this,
                           new DefaultClaimSet(this.Issuer,claims));
                   customstate.ClaimsAdded = true;
                   bRet = true;
                }
         else
         {
              bRet = true;
         }
         return bRet;
     }
...
}
```

<span data-ttu-id="489f7-142">上面的代码演示了 <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> 方法如何检查尚未添加影响处理的新声明，并添加特定的声明。</span><span class="sxs-lookup"><span data-stu-id="489f7-142">The previous code shows how the <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> method checks that no new claims have been added that affect the processing and adds specific claims.</span></span> <span data-ttu-id="489f7-143">允许的声明是从 `GetAllowedOpList` 方法中获得的，实现该方法是为了返回允许用户执行的特定操作的列表。</span><span class="sxs-lookup"><span data-stu-id="489f7-143">The claims that are allowed are obtained from the `GetAllowedOpList` method, which is implemented to return a specific list of operations that the user is allowed to perform.</span></span> <span data-ttu-id="489f7-144">授权策略添加了访问特定操作的声明。</span><span class="sxs-lookup"><span data-stu-id="489f7-144">The authorization policy adds claims for accessing the particular operation.</span></span> <span data-ttu-id="489f7-145"><xref:System.ServiceModel.ServiceAuthorizationManager> 然后使用此授权策略执行访问检查决策。</span><span class="sxs-lookup"><span data-stu-id="489f7-145">This is later used by the <xref:System.ServiceModel.ServiceAuthorizationManager> to perform access check decisions.</span></span>

<span data-ttu-id="489f7-146">实现自定义 <xref:System.IdentityModel.Policy.IAuthorizationPolicy> 后，必须通知服务主机关于要使用的授权策略的信息。</span><span class="sxs-lookup"><span data-stu-id="489f7-146">Once the custom <xref:System.IdentityModel.Policy.IAuthorizationPolicy> is implemented, the service host must be informed about the authorization policies to use.</span></span>

```xml
<serviceAuthorization ...>
       <authorizationPolicies>
            <add policyType='Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary' />
       </authorizationPolicies>
</serviceAuthorization>
```

<span data-ttu-id="489f7-147">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="489f7-147">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="489f7-148">客户端成功调用 Add、Subtract 和 Multiple 方法，在尝试调用 Divide 方法时获得“访问被拒绝”消息。</span><span class="sxs-lookup"><span data-stu-id="489f7-148">The client successfully calls the Add, Subtract and Multiple methods and gets an "Access is denied" message when trying to call the Divide method.</span></span> <span data-ttu-id="489f7-149">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="489f7-149">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="489f7-150">设置批处理文件</span><span class="sxs-lookup"><span data-stu-id="489f7-150">Setup Batch File</span></span>

<span data-ttu-id="489f7-151">通过运行此示例随附的 Setup.bat 批处理文件，可以用相关的证书将服务器配置为运行需要基于服务器证书的安全性的自承载应用程序。</span><span class="sxs-lookup"><span data-stu-id="489f7-151">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span>

<span data-ttu-id="489f7-152">下面提供了批处理文件不同节的简要概述，以便可以修改批处理文件从而在相应的配置中运行：</span><span class="sxs-lookup"><span data-stu-id="489f7-152">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration:</span></span>

-   <span data-ttu-id="489f7-153">创建服务器证书。</span><span class="sxs-lookup"><span data-stu-id="489f7-153">Creating the server certificate.</span></span>

     <span data-ttu-id="489f7-154">Setup.bat 批处理文件中的以下行创建将要使用的服务器证书。</span><span class="sxs-lookup"><span data-stu-id="489f7-154">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="489f7-155">%SERVER_NAME% 变量指定服务器名称。</span><span class="sxs-lookup"><span data-stu-id="489f7-155">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="489f7-156">更改此变量可以指定您自己的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="489f7-156">Change this variable to specify your own server name.</span></span> <span data-ttu-id="489f7-157">默认值为 localhost。</span><span class="sxs-lookup"><span data-stu-id="489f7-157">The default value is localhost.</span></span>

    ```
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

-   <span data-ttu-id="489f7-158">将服务器证书安装到客户端的受信任证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="489f7-158">Installing the server certificate into client's trusted certificate store.</span></span>

     <span data-ttu-id="489f7-159">Setup.bat 批处理文件中的以下行将服务器证书复制到客户端的受信任的人的存储区中。</span><span class="sxs-lookup"><span data-stu-id="489f7-159">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="489f7-160">因为客户端系统不是隐式信任 Makecert.exe 生成的证书，所以需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="489f7-160">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="489f7-161">如果您已经拥有一个证书，该证书来源于客户端的受信任根证书（例如由 Microsoft 颁发的证书），则不需要执行使用服务器证书填充客户端证书存储区这一步骤。</span><span class="sxs-lookup"><span data-stu-id="489f7-161">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

-   <span data-ttu-id="489f7-162">创建客户端证书。</span><span class="sxs-lookup"><span data-stu-id="489f7-162">Creating the client certificate.</span></span>

     <span data-ttu-id="489f7-163">Setup.bat 批处理文件中的以下行创建将要使用的客户端证书。</span><span class="sxs-lookup"><span data-stu-id="489f7-163">The following lines from the Setup.bat batch file create the client certificate to be used.</span></span> <span data-ttu-id="489f7-164">%USER_NAME% 变量指定服务器名称。</span><span class="sxs-lookup"><span data-stu-id="489f7-164">The %USER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="489f7-165">此值设置为“test1”，因为这是 `IAuthorizationPolicy` 查找的名称。</span><span class="sxs-lookup"><span data-stu-id="489f7-165">This value is set to "test1" because this is the name the `IAuthorizationPolicy` looks for.</span></span> <span data-ttu-id="489f7-166">如果更改 %USER_NAME% 的值，必须更改 `IAuthorizationPolicy.Evaluate` 方法中的对应值。</span><span class="sxs-lookup"><span data-stu-id="489f7-166">If you change the value of %USER_NAME% you must change the corresponding value in the `IAuthorizationPolicy.Evaluate` method.</span></span>

     <span data-ttu-id="489f7-167">证书存储在 CurrentUser 存储位置下的 My（个人）存储区中。</span><span class="sxs-lookup"><span data-stu-id="489f7-167">The certificate is stored in My (Personal) store under the CurrentUser store location.</span></span>

    ```
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

-   <span data-ttu-id="489f7-168">将客户端证书安装到服务器的受信任证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="489f7-168">Installing the client certificate into server's trusted certificate store.</span></span>

     <span data-ttu-id="489f7-169">Setup.bat 批处理文件中的以下行将客户端证书复制到受信任的人的存储区中。</span><span class="sxs-lookup"><span data-stu-id="489f7-169">The following lines in the Setup.bat batch file copy the client certificate into the trusted people store.</span></span> <span data-ttu-id="489f7-170">因为服务器系统不是隐式信任 Makecert.exe 生成的证书，所以需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="489f7-170">This step is required because certificates that are generated by Makecert.exe are not implicitly trusted by the server system.</span></span> <span data-ttu-id="489f7-171">如果您已经拥有一个证书，该证书来源于受信任的根证书（例如由 Microsoft 颁发的证书），则不需要执行使用客户端证书填充服务器证书存储区这一步骤。</span><span class="sxs-lookup"><span data-stu-id="489f7-171">If you already have a certificate that is rooted in a trusted root certificate—for example, a Microsoft issued certificate—this step of populating the server certificate store with the client certificate is not required.</span></span>

    ```
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="489f7-172">设置和生成示例</span><span class="sxs-lookup"><span data-stu-id="489f7-172">To set up and build the sample</span></span>

1. <span data-ttu-id="489f7-173">若要生成解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="489f7-173">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

2. <span data-ttu-id="489f7-174">若要用单一计算机配置或跨计算机配置来运行示例，请按照下列说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="489f7-174">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="489f7-175">如果使用 Svcutil.exe 为此示例重新生成配置，请确保在客户端配置中修改终结点名称以与客户端代码匹配。</span><span class="sxs-lookup"><span data-stu-id="489f7-175">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="489f7-176">在同一计算机上运行示例</span><span class="sxs-lookup"><span data-stu-id="489f7-176">To run the sample on the same computer</span></span>

1. <span data-ttu-id="489f7-177">使用管理员特权打开 Visual Studio 开发人员命令提示符并运行*Setup.bat*从示例安装文件夹。</span><span class="sxs-lookup"><span data-stu-id="489f7-177">Open Developer Command Prompt for Visual Studio with administrator privileges and run *Setup.bat* from the sample install folder.</span></span> <span data-ttu-id="489f7-178">这将安装运行示例所需的所有证书。</span><span class="sxs-lookup"><span data-stu-id="489f7-178">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="489f7-179">Setup.bat 批处理文件设计用于 Visual Studio 开发人员命令提示符中运行。</span><span class="sxs-lookup"><span data-stu-id="489f7-179">The Setup.bat batch file is designed to be run from Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="489f7-180">Visual Studio 指向包含所需的可执行文件的目录路径环境变量设置在开发人员命令提示*Setup.bat*脚本。</span><span class="sxs-lookup"><span data-stu-id="489f7-180">The PATH environment variable set within Developer Command Prompt for Visual Studio points to the directory that contains executables required by the *Setup.bat* script.</span></span>

1. <span data-ttu-id="489f7-181">从启动 Service.exe *service\bin*。</span><span class="sxs-lookup"><span data-stu-id="489f7-181">Launch Service.exe from *service\bin*.</span></span>

1. <span data-ttu-id="489f7-182">从启动 Client.exe *\client\bin*。</span><span class="sxs-lookup"><span data-stu-id="489f7-182">Launch Client.exe from *\client\bin*.</span></span> <span data-ttu-id="489f7-183">客户端活动将显示在客户端控制台应用程序上。</span><span class="sxs-lookup"><span data-stu-id="489f7-183">Client activity is displayed on the client console application.</span></span>

  <span data-ttu-id="489f7-184">如果客户端和服务能够进行通信，请参见[故障排除提示](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)。</span><span class="sxs-lookup"><span data-stu-id="489f7-184">If the client and service are not able to communicate, see [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>

### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="489f7-185">跨计算机运行示例</span><span class="sxs-lookup"><span data-stu-id="489f7-185">To run the sample across computers</span></span>

1. <span data-ttu-id="489f7-186">在服务计算机上创建目录。</span><span class="sxs-lookup"><span data-stu-id="489f7-186">Create a directory on the service computer.</span></span>

2. <span data-ttu-id="489f7-187">从服务程序文件复制*\service\bin*到服务计算机上的目录。</span><span class="sxs-lookup"><span data-stu-id="489f7-187">Copy the service program files from *\service\bin* to the directory on the service computer.</span></span> <span data-ttu-id="489f7-188">另外，将 Setup.bat、Cleanup.bat、GetComputerName.vbs 和 ImportClientCert.bat 文件复制到服务计算机上。</span><span class="sxs-lookup"><span data-stu-id="489f7-188">Also copy the Setup.bat, Cleanup.bat, GetComputerName.vbs and ImportClientCert.bat files to the service computer.</span></span>

3. <span data-ttu-id="489f7-189">在客户端计算机上为这些客户端二进制文件创建一个目录。</span><span class="sxs-lookup"><span data-stu-id="489f7-189">Create a directory on the client computer for the client binaries.</span></span>

4. <span data-ttu-id="489f7-190">将客户端程序文件复制到客户端计算机上的客户端目录中。</span><span class="sxs-lookup"><span data-stu-id="489f7-190">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="489f7-191">另外，将 Setup.bat、Cleanup.bat 和 ImportServiceCert.bat 文件复制到客户端上。</span><span class="sxs-lookup"><span data-stu-id="489f7-191">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>

5. <span data-ttu-id="489f7-192">在服务器上运行`setup.bat service`中使用管理员特权打开 Visual Studio 开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="489f7-192">On the server, run `setup.bat service` in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

   <span data-ttu-id="489f7-193">运行`setup.bat`与`service`参数的计算机的完全限定的域名创建一个服务证书，将服务证书导出到名为的文件*Service.cer*。</span><span class="sxs-lookup"><span data-stu-id="489f7-193">Running `setup.bat` with the `service` argument creates a service certificate with the fully qualified domain name of the computer, and exports the service certificate to a file named *Service.cer*.</span></span>

6. <span data-ttu-id="489f7-194">编辑*Service.exe.config*以反映新的证书名称 (在`findValue`属性中[ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) 这是完全限定的域名相同计算机。</span><span class="sxs-lookup"><span data-stu-id="489f7-194">Edit *Service.exe.config* to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) which is the same as the fully qualified domain name of the computer.</span></span> <span data-ttu-id="489f7-195">也会更改**computername**中\<服务 > /\<baseAddresses > 元素从本地主机到服务计算机的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="489f7-195">Also change the **computername** in the \<service>/\<baseAddresses> element from localhost to the fully qualified name of your service computer.</span></span>

7. <span data-ttu-id="489f7-196">复制*Service.cer*文件从服务目录到客户端目录客户端计算机上的。</span><span class="sxs-lookup"><span data-stu-id="489f7-196">Copy the *Service.cer* file from the service directory to the client directory on the client computer.</span></span>

8. <span data-ttu-id="489f7-197">在客户端上运行`setup.bat client`中使用管理员特权打开 Visual Studio 开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="489f7-197">On the client, run `setup.bat client` in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

   <span data-ttu-id="489f7-198">运行`setup.bat`与`client`参数创建一个名为的客户端证书**test1**并将客户端证书导出到名为的文件*Client.cer*。</span><span class="sxs-lookup"><span data-stu-id="489f7-198">Running `setup.bat` with the `client` argument creates a client certificate named **test1** and exports the client certificate to a file named *Client.cer*.</span></span>

9. <span data-ttu-id="489f7-199">在中*Client.exe.config*客户端计算机上文件中，更改要与你的服务的新地址相匹配的终结点的地址值。</span><span class="sxs-lookup"><span data-stu-id="489f7-199">In the *Client.exe.config* file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span> <span data-ttu-id="489f7-200">执行此操作通过替换**localhost**与服务器的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="489f7-200">Do this by replacing **localhost** with the fully qualified domain name of the server.</span></span>

10. <span data-ttu-id="489f7-201">将客户端目录中的 Client.cer 文件复制到服务器上的服务目录中。</span><span class="sxs-lookup"><span data-stu-id="489f7-201">Copy the Client.cer file from the client directory to the service directory on the server.</span></span>

11. <span data-ttu-id="489f7-202">在客户端上运行*ImportServiceCert.bat*中使用管理员特权打开 Visual Studio 开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="489f7-202">On the client, run *ImportServiceCert.bat* in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

   <span data-ttu-id="489f7-203">这会将 Service.cer 文件到中导入的服务证书**CurrentUser-TrustedPeople**存储。</span><span class="sxs-lookup"><span data-stu-id="489f7-203">This imports the service certificate from the Service.cer file into the **CurrentUser - TrustedPeople** store.</span></span>

12. <span data-ttu-id="489f7-204">在服务器上，运行*ImportClientCert.bat*中使用管理员特权打开 Visual Studio 开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="489f7-204">On the server, run *ImportClientCert.bat* in Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span>

   <span data-ttu-id="489f7-205">这会将 Client.cer 文件到中导入客户端证书**LocalMachine-TrustedPeople**存储。</span><span class="sxs-lookup"><span data-stu-id="489f7-205">This imports the client certificate from the Client.cer file into the **LocalMachine - TrustedPeople** store.</span></span>

13. <span data-ttu-id="489f7-206">在服务器计算机上，从命令提示窗口中启动 Service.exe。</span><span class="sxs-lookup"><span data-stu-id="489f7-206">On the server computer, launch Service.exe from the command prompt window.</span></span>

14. <span data-ttu-id="489f7-207">在客户端计算机上，从命令提示窗口中启动 Client.exe。</span><span class="sxs-lookup"><span data-stu-id="489f7-207">On the client computer, launch Client.exe from a command prompt window.</span></span>

   <span data-ttu-id="489f7-208">如果客户端和服务能够进行通信，请参见[故障排除提示](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)。</span><span class="sxs-lookup"><span data-stu-id="489f7-208">If the client and service are not able to communicate, see [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>

### <a name="clean-up-after-the-sample"></a><span data-ttu-id="489f7-209">在此示例后清理</span><span class="sxs-lookup"><span data-stu-id="489f7-209">Clean up after the sample</span></span>

<span data-ttu-id="489f7-210">若要清除运行示例后，运行*Cleanup.bat*完成后运行示例的 samples 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="489f7-210">To clean up after the sample, run *Cleanup.bat* in the samples folder when you have finished running the sample.</span></span> <span data-ttu-id="489f7-211">这将从证书存储区中移除服务器和客户端证书。</span><span class="sxs-lookup"><span data-stu-id="489f7-211">This removes the server and client certificates from the certificate store.</span></span>

> [!NOTE]
> <span data-ttu-id="489f7-212">此脚本不会在跨计算机运行此示例时移除客户端上的服务证书。</span><span class="sxs-lookup"><span data-stu-id="489f7-212">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="489f7-213">如果您运行在计算机之间使用的证书，请确保清除已安装在 CurrentUser-的服务证书的 WCF 示例 TrustedPeople 存储。</span><span class="sxs-lookup"><span data-stu-id="489f7-213">If you have run WCF samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="489f7-214">为此，请使用以下命令：`certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`，例如：`certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="489f7-214">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>