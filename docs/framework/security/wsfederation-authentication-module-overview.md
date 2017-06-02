---
title: "WSFederation 身份验证模块概述 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 02c4d5e8-f0a7-49ee-9cf5-3647578510ad
caps.latest.revision: 6
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 6
---
# WSFederation 身份验证模块概述
窗口标识基础 \(WIF\) 在 ASP.NET 应用程序包含联合的身份验证。支持 WS\-Discovery 通过向上的身份验证模块 \(WS\-FAM\)。  本主题有助于了解联合的身份验证的工作方式以及如何使用。  
  
### 向上的简要身份验证  
 在这两个域之间的信任时，关系的联合身份验证允许安全标记服务在受信任域的 \(STS\) 提供身份验证信息。在另受信任域的 STS。  此示例如下图中所示。  
  
 ![联合身份验证方案](../../../docs/framework/security/media/federatedauthentication.png "FederatedAuthentication")  
  
1.  Fabrikam 信任域的客户端发送请求为 Contoso 信任在域中的一方 \(RP\) 应用程序。  
  
2.  RP 将客户端重定向 Contoso，Ltd 信任域的 STS。  此 STS 不了解客户。  
  
3.  Contoso STS 将客户端重定向在 Fabrikam 信任域的 STS，Contoso 信任域都有一种信任关系。  
  
4.  Fabrikam STS 验证客户的标识以及发出安全令牌为 Contoso STS。  
  
5.  Contoso STS Fabrikam 使用标记创建可由 RP 使用自己的标记并将其发送到 RP。  
  
6.  RP 从安全令牌客户的声明并对审定决定。  
  
### 将 ASP.NET 身份验证模块的联合  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> \(WS\-FAM\) 是可以添加联合的身份验证。[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 应用程序的 HTTP 模块。  向上的身份验证使身份验证逻辑。STS 处理并且主要用于编写业务逻辑。  
  
 您配置 WS\-FAM 指定非验证请求应重定向的 STS。  WIF 可以验证用户以两种方式：  
  
1.  被动重定目标：在无身份验证的用户尝试访问受保护的资源时，因此，要重定向到 STS，无需登录页，则需要正确的方法。  STS 验证用户的标识，并发出包含该用户的相应声明的安全标记。  此选项将在 HTTP 模块管线需要 WS\-FAM 添加。  您可以使用 Visual Studio 2012 的标识和访问工具可以修改应用程序的配置文件中使用 WS\-FAM 和结成同盟与 STS。  有关详细信息，请参阅[适用于 Visual Studio 2012 的标识和访问工具](../../../docs/framework/security/identity-and-access-tool-for-vs.md)。  
  
2.  通过调用 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignIn%2A?displayProperty=fullName> 方法或 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectToIdentityProvider%2A> 方法从代码隐藏一个登录页中 RP 应用程序。  
  
 在被动请重定向，所有通信通过响应执行\/从客户端 \(浏览器通常\) 重定向。  可以添加 WS\-FAM 到应用程序的 HTTP 管线，则请注意未验证的用户请求并将用户重定向到 STS 指定。  
  
 WS\-FAM 还引发可以自定义它在 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 应用程序的功能的一些事件。  
  
### WS\-FAM 如何工作  
 WS\-FAM 在 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 类中实现。  通常，您将 WS\-FAM 到 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] RP 应用程序的 HTTP 管线。  在无身份验证的用户尝试访问受保护的资源时，RP 返回 401“授权”拒绝的 HTTP 响应。  WS\-FAM 截获此响应而不是允许客户端收到它，然后它将用户重定向到指定的 STS。  STS 发出安全标记，WS\-FAM 再次截获。  WS\-FAM 使用标记创建 <xref:System.Security.Claims.ClaimsPrincipal> 实例验证的用户，以普通 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 授权机制运行。  
  
 由于 HTTP 是无状态，我们需要避免每次重复此整个进程用户尝试访问其他受保护的资源。  这是 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 中的位置。  当 STS 向用户发出了一个安全标记，<xref:System.IdentityModel.Services.SessionAuthenticationModule> 在 Cookie 也创建用户的会话安全令牌并放置它。  在后续请求中，该 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 来截获此 Cookie 并使用它重建用户的 <xref:System.Security.Claims.ClaimsPrincipal>。  
  
 下图显示总体信息流在被动的重定向情况。  请求通过 STS 自动重定向建立凭据，而无需登录页：  
  
 ![使用被动重定向的登录的执行时间关系图](../../../docs/framework/security/media/signinusingpassiveredirect.png "SignInUsingPassiveRedirect")  
  
 下图显示上出现的内容的更多详细信息，当用户验证对 STS，以及的安全标记由 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>处理：  
  
 ![使用被动重定向的标记处理的执行时间](../../../docs/framework/security/media/signinusingpassiveredirect-tokenprocessing.png "SignInUsingPassiveRedirect\_TokenProcessing")  
  
 下图显示上出现的内容的更多详细信息，当序列化到 Cookie 和 <xref:System.IdentityModel.Services.SessionAuthenticationModule>时用户截获的安全标记：  
  
 ![显示使用控件的登录的 SAM 执行时间关系图](../../../docs/framework/security/media/signinusingconrols-sam.png "SignInUsingConrols\_SAM")  
  
### 事件  
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>、<xref:System.IdentityModel.Services.SessionAuthenticationModule>和它们的父类，<xref:System.IdentityModel.Services.HttpModuleBase>，则引发事件的各个阶段处理 HTTP 请求。  可以在 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 应用程序的 `global.asax` 文件的事件。  
  
-   ASP.NET 基础结构来调用模块的 <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A> 方法中初始化模块。  
  
-   引发 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfigurationCreated?displayProperty=fullName> 事件，当 ASP.NET 基础结构首次调用 <xref:System.IdentityModel.Services.HttpModuleBase.Init%2A> 方法。从 <xref:System.IdentityModel.Services.HttpModuleBase>派生的某个应用程序模块时。  此方法将访问静态 <xref:System.IdentityModel.Services.FederatedAuthentication.FederationConfiguration%2A?displayProperty=fullName> 属性，将导致配置从 Web.config 文件加载。  首次访问此属性，此事件只引发。  从配置初始化的 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration> 对象可通过在事件处理程序中的 <xref:System.IdentityModel.Services.Configuration.FederationConfigurationCreatedEventArgs.FederationConfiguration%2A?displayProperty=fullName> 属性访问。  在应用到所有模块之前，可以使用此事件来修改配置。  可以添加此事件的处理程序在 Application\_Start 方法：  
  
    ```  
    void Application_Start(object sender, EventArgs e)  
    {  
        FederatedAuthentication.FederationConfigurationCreated += new EventHandler<FederationConfigurationCreatedEventArgs>(FederatedAuthentication_FederationConfigurationCreated);  
    }  
    ```  
  
     每模块重写 <xref:System.IdentityModel.Services.HttpModuleBase.InitializeModule%2A?displayProperty=fullName>，并提取 <xref:System.IdentityModel.Services.HttpModuleBase.InitializePropertiesFromConfiguration%2A?displayProperty=fullName> 方法。  第一个方法添加 ASP.NET 会用到模块的管道事件的处理程序。  在许多情况下的默认模块实现将足够了。  第二个方法从其 <xref:System.IdentityModel.Services.HttpModuleBase.FederationConfiguration%2A?displayProperty=fullName> 属性初始化的模块的属性。\(这是以前加载配置复制的。\)可能需要重写第二种方法，如果希望支持新的属性初始化从配置中您从 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 或 <xref:System.IdentityModel.Services.SessionAuthenticationModule>派生的类。  在此类情况下还需要配置从相应的派生对象支持添加的配置属性；例如，从 <xref:System.IdentityModel.Configuration.IdentityConfiguration>、<xref:System.IdentityModel.Services.Configuration.WsFederationConfiguration>或 <xref:System.IdentityModel.Services.Configuration.FederationConfiguration>。  
  
-   WS\-FAM 引发 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenReceived> 事件，该 STS 截获由发出的安全令牌时。  
  
-   则验证标记之后，WS\-FAM 引发 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SecurityTokenValidated> 事件。  
  
-   当创建用户的一个会话时，安全标记 <xref:System.IdentityModel.Services.SessionAuthenticationModule> 将引发 <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenCreated> 事件。  
  
-   <xref:System.IdentityModel.Services.SessionAuthenticationModule> 引发 <xref:System.IdentityModel.Services.SessionAuthenticationModule.SessionSecurityTokenReceived> 事件，该处理使用包含会话安全令牌的 Cookie 中的后续请求。  
  
-   在 WS\-FAM 将用户重定向到发出者之前，将引发 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider> 事件。  WS 联合身份验证登录请求通过传递 <xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs> 的 <xref:System.IdentityModel.Services.RedirectingToIdentityProviderEventArgs.SignInRequestMessage%2A> 属性中提供事件。  可以选择在交付之前此修改请求对发出者。  
  
-   WS\-FAM 引发 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SignedIn> 事件，而 Cookie 成功写入，而用户登录。  
  
-   会话，当为每个用户，WS\-FAM 关闭下引发 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SigningOut> 事件一次每个会话。  不引发，如果客户端会话在关闭下 \(例如，通过删除会话 Cookie\)。  在环境 IP\-STS SSO，可以请求 RP 每个注销，也是。  这也会引发此事件，并且 <xref:System.IdentityModel.Services.SigningOutEventArgs.IsIPInitiated%2A> 设置为 `true`。  
  
> [!NOTE]
>  不应使用 <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=fullName> 属性在 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 或 <xref:System.IdentityModel.Services.SessionAuthenticationModule>中引发的所有事件过程。  这是因为，<xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=fullName> 过程在身份验证之后设置，而身份验证在事件过程中引发。  
  
### 向上的身份验证的配置  
 WS\-FAM、SAM 通过 [\<federationConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 元素中配置。  [\<wsFederation\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/wsfederation.md) 子元素配置 WS\-FAM 属性的默认值；如 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Issuer%2A> 属性和 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.Realm%2A> 属性。\(这些值对可以更改每个请求通过基础提供处理程序的某些 WS\-FAM 事件；例如，<xref:System.IdentityModel.Services.WSFederationAuthenticationModule.RedirectingToIdentityProvider>。\)SAM 使用的 Cookie 处理程序通过 [\<cookieHandler\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md) 子配置元素。  WIF 提供了可以通过 [\<chunkedCookieHandler\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/chunkedcookiehandler.md) 元素设置该块范围的 <xref:System.IdentityModel.Services.ChunkedCookieHandler> 类实现 Cookie 的默认处理程序。  `<federationConfiguration>` 元素引用 <xref:System.IdentityModel.Configuration.IdentityConfiguration>，用于在应用程序其他 WIF 组件提供配置，如 <xref:System.Security.Claims.ClaimsAuthenticationManager> 和 <xref:System.Security.Claims.ClaimsAuthorizationManager>。  标识配置可以通过指定一个 [\<identityConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 元素显式引用在 `<federationConfiguration>` 元素的 `identityConfigurationName` 特性。  如果标识配置不显式引用，则使用默认对标识配置。  
  
 以下 XML 显示 ASP.NET 依赖方 \(RP\) 应用程序的配置。  <xref:System.IdentityModel.Configuration.SystemIdentityModelSection> 和 <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> 配置节将添加在 `<configSections>` 元素下。  SAM 和 WS\-FAM 添加到在 `<system.webServer>`\/`<modules>` 元素下的 HTTP 模块。  WIF 最终配置组件在 `<system.identityModel>`\/`<identityConfiguration>` 和 `<system.identityModel.services>`\/`<federationConfiguration>` 元素下。  指定此配置 chunked Cookie 处理程序，因为它是默认 Cookie 处理程序，而在 `<cookieHandler>` 元素指定 Cookie 处理程序类型。  
  
> [!WARNING]
>  在下面的示例中，两个 `<wsFederation>` 元素的 `requireHttps` 特性和 `<cookieHandler>` 元素的 `requireSsl` 特性设置为 `false`。  这会带来潜在的安全威胁。  在成品，这两个值应设置为 `true`。  
  
```  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  ...  
  
  <system.webServer>  
    <modules>  
      <add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
      <add name="SessionAuthenticationModule" type="System.IdentityModel.Services.SessionAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" preCondition="managedHandler" />  
    </modules>  
  </system.webServer>  
  
  <system.identityModel>  
    <identityConfiguration>  
      <audienceUris>  
        <add value="http://localhost:50969/" />  
      </audienceUris>  
      <certificateValidation certificateValidationMode="None" />  
      <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
        <trustedIssuers>  
          <add thumbprint="9B74CB2F320F7AAFC156E1252270B1DC01EF40D0" name="LocalSTS" />  
        </trustedIssuers>  
      </issuerNameRegistry>  
    </identityConfiguration>  
  </system.identityModel>  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true" issuer="http://localhost:15839/wsFederationSTS/Issue" realm="http://localhost:50969/" reply="http://localhost:50969/" requireHttps="false" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
</configuration>  
```  
  
## 请参阅  
 <xref:System.IdentityModel.Services.SessionAuthenticationModule>   
 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule>   
 [\<federationConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)