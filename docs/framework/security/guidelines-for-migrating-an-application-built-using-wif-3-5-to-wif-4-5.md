---
title: "使用 WIF 3.5 至 WIF 4.5 构建的应用程序迁移指南 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a32fe6e-5f68-4693-9371-19411fa8063c
caps.latest.revision: 12
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 12
---
# 使用 WIF 3.5 至 WIF 4.5 构建的应用程序迁移指南
## 适用于  
  
-   Microsoft® Windows® 标识基础 \(WIF\) 3.5 和 4.5。  
  
## 概述  
 窗口标识基础 \(WIF\) 在 .NET 3.5 SP1 时间最初发布。  WIF 该版本引用 WIF 3.5。  释放它作为单独运行时和 SDK，这意味着一 WIF 启用运行的应用程序必须具有 WIF 运行时安装，并且开发人员必须下载和安装 WIF SDK 获取 Visual Studio 模板和工具启用的装饰 WIF 启用应用程序的开发过程的每台计算机。  从 .NET 4.5 开始，WIF 完全集成 .NET Framework。  单独运行时不再需要使用 Visual Studio 外接程序管理器，并且，WIF 工具的修饰。Visual Studio 2012 可以安装。  WIF 此版本引用 WIF 4.5。  
  
 WIF 的集成到中了 WIF 需要 .NET API 图面的若干更改。  WIF 4.5 包含了新命名空间、一些更改配置元素和新进行修整。Visual Studio 中。  本主题提供可以使用有助于您迁移 WIF WIF 使用 3.5 到 4.5 生成的应用程序的指南。可能您需要运行使用计算机上 WIF 生成的旧版应用程序在 3.5 运行 Windows 8 或 Windows Server 2012 中的方案。  此主题还提供的指南使这些操作系统 WIF 3.5。  
  
## WIF 需要 4.5 的更改。  
 本节描述了迁移 WIF 3.5 应用程序。WIF 4.5 的更改。  
  
### 程序集和命名空间更改  
 WIF 在 3.5，所有 WIF 类位于 `Microsoft.IdentityModel` 程序集中 \(microsoft.identitymicrosoft.identitymodel.dll\) 包含了。  WIF 在 4.5 中，类在以下 WIF 程序集之间拆分：`mscorlib` \(mscorlib.dll\)，`System.IdentityModel` \(System.IdentityModel.dll\)，`System.IdentityModel.Services` \(System.IdentityModel.Services.dll\) 和 `System.ServiceModel` \(System.ServiceModel.dll\)。  
  
 WIF 3.5 类都在其中一个 `Microsoft.IdentityModel` 命名空间中包含了；例如，`Microsoft.IdentityModel`，`Microsoft.IdentityModel.Tokens`，`Microsoft.IdentityModel.Web`，依此类推。  WIF WIF 在 4.5 中，类现在是在命名空间之间分布的 [System.IdentityModel](http://go.microsoft.com/fwlink/?LinkId=272004)，<xref:System.Security.Claims?displayProperty=fullName> 命名空间和 <xref:System.ServiceModel.Security?displayProperty=fullName> 命名空间。  除了此重新组织外，某种 WIF 3.5 类在 WIF 4.5 删除。  
  
 下表以显示它们包含的一些更重要的 4.5 这 WIF 命名空间和类。  有关命名空间映射。WIF WIF 3.5 和 4.5 之间以及 WIF 4.5 删除的命名空间和类，如何安装的更详细信息请参见 [WIF 3.5 和 WIF 4.5 之间的命名空间映射](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)。  
  
|WIF 4.5 命名空间|说明|  
|------------------|--------|  
|<xref:System.IdentityModel?displayProperty=fullName>|Cookie 包含表示变换，安全令牌服务和专用化的 XML 字典读取器的类。  包含从以下 WIF 3.5 命名空间的类：`Microsoft.IdentityModel`、`Microsoft.IdentityModel.SecurityTokenService`和 `Microsoft.IdentityModel.Threading`。|  
|<xref:System.Security.Claims?displayProperty=fullName>|包含表示声明、基于的声明标识、声明基于用户和其他声明标识基于模型项目中的类。  包含 `Microsoft.IdentityModel.Claims` 命名空间的类。|  
|<xref:System.IdentityModel.Tokens?displayProperty=fullName>|表示安全令牌、安全令牌处理程序和安全令牌其他项目中的类。  包含从以下 WIF 3.5 命名空间的类：`Microsoft.IdentityModel.Tokens`、`Microsoft.IdentityModel.Tokens.Saml11`和 `Microsoft.IdentityModel.Tokens.Saml2`。|  
|<xref:System.IdentityModel.Services?displayProperty=fullName>|包含在被动的类 \(联合 WS 身份验证方案。\)  包含 `Microsoft.IdentityModel.Web` 命名空间的类。|  
|<xref:System.ServiceModel.Security?displayProperty=fullName>|表示 WCF、协定、通道服务主机和其他利益在可用的类。\) WS\-Trust 方案现在此命名空间。  WIF 在 3.5 中，这些类是在 `Microsoft.IdentityModel.Protocols.WSTrust` 命名空间。|  
  
> [!IMPORTANT]
>  以下 `System.IdentityModel` 命名空间实现包含 WCF 从声明的标识模型的类：<xref:System.IdentityModel.Claims?displayProperty=fullName>、<xref:System.IdentityModel.Policy?displayProperty=fullName>和 <xref:System.IdentityModel.Selectors?displayProperty=fullName>。  WCF 从声明的标识模型由 WIF 取代。  当生成基于 WIF 时解决方案，在这三个命名空间不应使用类。  
  
### 由于 .NET 集成更改  
 WIF 现在集成 .NET Framework。  大多数 .NET 标识和主体类现在从 <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> 和 <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName>派生。  以下更改的结果。WIF 4.5 上：  
  
-   WIF 的表示形式声明标识和主体类，现在虽然存在于 <xref:System.Security.Claims?displayProperty=fullName> 命名空间。  
  
    > [!IMPORTANT]
    >  <xref:System.IdentityModel.Claims?displayProperty=fullName> 命名空间包含表示在 WCF 从声明的标识模型的项目的类中。  许多这些类具有与 WIF 类的名称；例如，`Claims`。  当生成基于 WIF 时解决方案，则不要使用这些类。  
  
-   .NET 标识和主体类直接从 <xref:System.Security.Claims.ClaimsIdentity?displayProperty=fullName> 和 <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=fullName>派生，现在表示基于的声明标识和主体。  WIF 3.5 `IClaimsIdentity` 和 `IClaimsPrincipal` 接口因此，不再需要且不可用。WIF 4.5。  
  
-   Because.NET 标识和主体类 \(如 <xref:System.Security.Principal.WindowsIdentity?displayProperty=fullName> 和 <xref:System.Security.Principal.WindowsPrincipal?displayProperty=fullName> \) 现在从 <xref:System.Security.Claims.ClaimsIdentity> 派生，并声明 <xref:System.Security.Claims.ClaimsPrincipal>，因此具有内置功能。  因此，位于 WIF 3.5 中声明特定标识和主体类 \(如 `WindowsClaimsIdentity` 和 `WindowsClaimsPrincipal` \) 不再需要和不存在 WIF 4.5。  
  
### WIF 变为其他功能  
 除了命名空间更改和更改之外因为带有 .NET 的集成，指向 WIF 功能的下列一般将 WIF 4.5。  
  
-   提供功能可以映射到异常的 SOAP 错误，请移除 `Microsoft.IdentityModel.ExceptionMapper` 类。  
  
-   异常图面显著降低。  
  
-   定义协议或 WS\-\* 特定常数取消了的大部分类；例如，`Microsoft.IdentityModel.WSAddressing10Constants` 类，定义常数与 WS\-Addressing\) 1.0。  
  
-   `Microsoft.IdentityModel.WindowsTokenService` 命名空间中的 Windows 服务移除对标记 \(c2wts\) 及其关联类的声明。  
  
### WIF 配置更改  
 很多在配置文件中更改命名空间由更新引起的。WIF 4.5。例如，请考虑在 `<httpModules>` 节中输入以下 WIF 3.5 添加 WS 联合身份验证身份验证管理器向应用程序：  
  
```  
<add name="WSFederationAuthenticationModule" type="Microsoft.IdentityModel.Web.WSFederationAuthenticationModule, Microsoft.IdentityModel, Version=3.5.0.0, Culture=neutral, PublicKeyToken=abcd … 5678" />  
```  
  
 此博文为包括新的命名空间和程序集版本的 WIF 4.5 更新：  
  
```  
<add name="WSFederationAuthenticationModule" type="System.IdentityModel.Services.WSFederationAuthenticationModule, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=abcd … 5678"/>  
```  
  
 以下枚举列表对配置文件进行的主要更改 WIF 的 4.5。  
  
-   `<microsoft.identityModel>` 节现在是 [\<system.identityModel\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel.md) 一节。  
  
-   `<service>` 元素现在是 [\<identityConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 元素。  
  
-   一个新节，[\<system.identityModel.services\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/system-identitymodel-services.md)，在被动 WS \(联合\) 身份验证方案中添加指定设置该控件的行为。  
  
-   [\<federationConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) 元素及其子元素来自针对 WIF 3.5 的 `<service>` 元素将设置为新的 `<system.identityModel.services>` 元素。  
  
-   可能指定的服务级别直接在 `<service>` 元素下。WIF 3.5 的若干元素限制到指定在元素下。[\<securityTokenHandlerConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)\(它们仍然指定在 [\<identityConfiguration\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) 元素下。WIF 4.5 用于向后兼容性。\)  
  
 WIF 有关 4.5 配置元素的完整列表，请参见 [WIF 配置架构](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md)。  
  
### 更改工具的 Visual Studio  
 WIF 3.5 SDK 提供独立联合实用工具，FedUtil.exe \(FedUtil\)，可以使用外包 WIF 在启用应用程序的身份管理到安全令牌服务 \(STS\)。  此工具位于 Visual Studio 添加 WIF 设置为应用程序配置文件以允许应用程序与一个或多个获取安全标记 STSs 和显示了通过 **添加 STS 服务引用** 按钮。  FedUtil 不附带 WIF 4.5。WIF，而 4.5 支持名为可以使用修改使用需要的 WIF 设置的应用程序的配置文件外包身份管理到 STS 的 Visual Studio 2012 标识的一个新的 Visual Studio 扩展并访问工具。  标识和访问工具还实现调用可使用测试 WIF 启用应用程序的 STS 中 Local STS。  在许多情况下，此功能消除生成经常需要在 WIF 3.5 开发中测试解决方案的自定义 STSs。  因此，STS 模板在 Visual Studio 2012 中不再支持；但是，支持 STSs 的开发的类可用在 WIF 4.5。  
  
 可以从命扩展的标识和访问工具并更新 Visual Studio 的管理器也可以下载它基于代码库上的以下页面：[Visual Studio 2012 的标识以及工具在访问代码库](http://go.microsoft.com/fwlink/?LinkID=245849).  更改工具的 Visual Studio 在下面的列表总结：  
  
-   取消添加 STS 服务引用功能。  替换是标识和访问工具。  
  
-   移除 Visual Studio STS 模板。  通过标识和访问工具可为测试标识解决方案时开发。WIF 的可以使用本地 STS。  可以修改局部 STS 配置自定义服务它的声明。  
  
-   独立联合实用工具 \(FedUtil\) 不可用。WIF 4.5。可以使用身份和访问工具修改配置文件外包身份管理到 STS。  
  
 有关身份和访问工具的更多信息，请参见 [适用于 Visual Studio 2012 的标识和访问工具](../../../docs/framework/security/identity-and-access-tool-for-vs.md)  
  
<a name="BKMK_ToolingChanges"></a>   
### 被动 WS 联合 \(身份验证\) 的方案：  
  
-   被动支持方案的类移动到 <xref:System.IdentityModel.Services?displayProperty=fullName> 命名空间。  WIF 3.5 在这些类位于 `Microsoft.IdentityModel.Web` 命名空间中。  
  
-   命名空间中 `Microsoft.IdentityModel.Web.Configuration` 类移到 <xref:System.IdentityModel.Services.Configuration?displayProperty=fullName>。  这些类表示的特定对象。在被动方案的配置。  
  
-   `FederatedPasssiveSignInControl` 不再受支持；`Microsoft.IdentityModel.Web.Controls` 命名空间中的类所有。WIF 4.5 中移除。  
  
-   WS 联合身份验证身份验证模块 \(<xref:System.IdentityModel.Services.WSFederationAuthenticationModule>\) 与 3.5 WIF 注销功能不同。  有关详细信息请注销 WIF 有关如何在 4.5 中工作，请参见 <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> 类主题。  
  
### 活动 \(WCF\/WS 信任的方案：  
  
-   `Microsoft.IdentityModel.Protocols.WSTrust` 命名空间的主拆分到 WIF 4.5 的两个命名空间。表示项目所针对 WS\-Trust 协议的类现在位于 <xref:System.IdentityModel.Protocols.WSTrust?displayProperty=fullName>。  这包括诸如 <xref:System.IdentityModel.Protocols.WSTrust.RequestSecurityToken>的类。  表示服务协定、通道、服务主机和其他项目。使用涉及 WS\-Trust 在 WCF 应用程序的类移到 <xref:System.ServiceModel.Security?displayProperty=fullName>;例如，<xref:System.ServiceModel.Security.IWSTrust13AsyncContract> 接口。  
  
-   配置 WCF 应用程序使用 WIF 大大简化。  `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement` 过去必须将作为扩展行为，并指定 `<federatedServiceHostConfiguration>` 元素并使用该功能楔住 WIF 到服务行为。  WIF 4.5 紧密集成与 WCF。  现在可以通过指定 `useIdentityConfiguration` 特性上启用 WCF 服务的 WIF 在 `<system.serviceModel>`\/`<behaviors>`\/`<serviceBehaviors>`\/`<serviceCredentials>` 元素以下 XML:  
  
    ```xml  
    <serviceCredentials useIdentityConfiguration="true">  
        <!--Certificate added by Identity And Access VS Package.  Subject='CN=localhost', Issuer='CN=localhost'. Make sure you have this certificate installed. The Identity and Access tool does not install this certificate.-->  
        <serviceCertificate findValue="CN=localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName" />  
    </serviceCredentials>  
    ```  
  
-   WIF 在 4.5。服务主机必须指定活动 \(WCF 服务的服务证书。\)  如前面的示例所示，在配置中，可以通过 `<system.serviceModel>`\/`<behaviors>`\/`<serviceBehaviors>`\/`<serviceCredentials>`\/`<serviceCertificate>` 元素执行此操作。  WIF 在 3.5 服务证书可以通过 WIF `<service>` 元素的 `<serviceCertificate>` 子元素指定。  此功能不存在 WIF 4.5;指定 `<serviceCertificate>` 元素在 `<serviceCredentials>` 元素下。  
  
-   用于类的楔住 WIF 3.5 到 WCF 不再存在。  这在 `Microsoft.IdentityModel.Tokens` 命名空间中包含了以下类：`FederatedSecurityTokenManager`、`FederatedServiceCredentials`和 `IdentityModelServiceAuthorizationManager`，以及 `Microsoft.IdentityModel.Configuration.ConfigureServiceHostBehaviorExtensionElement` 类。  
  
## 在 Windows 8 上 WIF 3.5  
 WIF 因为 4.5 是 .NET 4.5 的一部分，在运行 Windows 8 的计算机自动启用，并且生成使用 WIF 4.5 的 Windows Server 2012 及该应用程序将运行在 Windows 8 下或 Windows Server 2012 的默认方式。  但是，您可能需要使用计算机上运行生成的 WIF 3.5 运行 Windows 8 或 Windows Server 2012 中的应用程序。  在这种情况下，您需要可以在目标计算机的 WIF 3.5。  使用部署和管理映像服务 \(DISM\)，工具在运行 Windows 8 的计算机上，您也可以执行这些操作。  在计算机运行 Windows Server 2012，可以使用轮胎工具也可以使用 Windows PowerShell `Add-WindowsFeature` cmdlet。  在这两种情况下，若要正确的命令可调用命令行或从 Windows PowerShell 环境内部。  
  
 下面的命令演示如何使用轮胎工具从命令行或从 Windows PowerShell 环境内部。  默认情况下，DISM PowerShell 模块包含在 Windows 8 和 Windows Server 2012 及不需要导入。  有关用于 Windows PowerShell 的 DISM 的更多信息，请 [如何使用 DISM Windows PowerShell。](http://go.microsoft.com/fwlink/?LinkId=254419)参见。  
  
 使用 DISM，启用 WIF 3.5:  
  
```  
dism /online /enable-feature:windows-identity-foundation  
```  
  
 使用 DISM，禁用 WIF 3.5:  
  
```  
dism /online /disable-feature:windows-identity-foundation  
```  
  
 检查使用 DISM，哪些功能启用或禁用：  
  
```  
dism /online /get-features  
```  
  
 或者，使用 Windows PowerShell `Add-WindowsFeature` cmdlet，运行 Windows Server 2012 的计算机中，可以启用 WIF 3.5。  从命令行这样做，您可以键入以下命令：  
  
```  
powershell "add-windowsfeature windows-identity-foundation"  
```  
  
 从 Windows PowerShell 环境内部，可以直接输入命令：  
  
```  
add-windowsfeature windows-identity-foundation  
```  
  
> [!NOTE]
>  由于很多在 WIF WIF 3.5 和 4.5 的类共享同样名称，那么，当您处理 WIF WIF 3.5 和 4.5，确保为使用完全限定的类名或使用命名空间别名区分 WIF 在 3.5 和 4.5 之间。WIF 的类  
  
## 请参阅  
 [WIF 配置架构](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/index.md)   
 [WIF 3.5 和 WIF 4.5 之间的命名空间映射](../../../docs/framework/security/namespace-mapping-between-wif-3-5-and-wif-4-5.md)   
 [Windows Identity Foundation 4.5 中的新增功能](../../../docs/framework/security/whats-new-in-wif.md)   
 [适用于 Visual Studio 2012 的标识和访问工具](../../../docs/framework/security/identity-and-access-tool-for-vs.md)