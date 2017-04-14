---
title: "WIF 和 Web 场 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
caps.latest.revision: 9
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 9
---
# WIF 和 Web 场
当您使用 Windows 身份基础 \(WIF\) 安全的应用程序部署到 web 群中的依赖方 \(RP\) 资源时，必须采取特定的步骤，以确保 WIF 可以处理令牌从 RP 应用程序在服务器场中的不同计算机上运行的实例。  此处理包括验证会话令牌签名、 加密和解密的会话令牌、 缓存会话令牌和检测重播安全令牌。  
  
 在典型的情况下，保护资源的 RP 应用程序\-\-使用 WIF 时是否运行在一台计算机上或在 web 场\-RP 与基于安全令牌从安全令牌服务 \(STS\) 获得的客户建立会话。  这是为了避免强制客户端以进行身份验证在使用 WIF 受保护的每个应用程序资源 STS。  有关 WIF 如何处理会话的详细信息，请参阅[WIF 会话管理](../../../docs/framework/security/wif-session-management.md)。  
  
 当使用默认设置时，WIF 具有以下功能：  
  
-   它使用的实例<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>类读取和写入会话令牌 （实例的<xref:System.IdentityModel.Tokens.SessionSecurityToken>类） 的执行的声明和其他有关安全令牌身份验证所使用的信息，以及有关其自身会话的信息。  会话令牌进行包装和存储在会话 cookie 中。  默认情况下，由<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>使用<xref:System.IdentityModel.ProtectedDataCookieTransform>类，该类用于数据保护 API \(DPAPI\) 保护的会话令牌。  DPAPI 通过使用用户或计算机凭据提供保护，并在用户配置文件中存储密钥数据。  
  
-   它使用默认设置内存中实施的<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>类存储和处理的会话令牌。  
  
 这些默认设置工作的方案，在其中 RP 应用程序部署在一台计算机。 但是，部署在 web 场中，可能会发送到每个 HTTP 请求，并处理由 RP 应用程序运行在另一台计算机上的其他实例。  在此方案中，因为保护令牌和令牌缓存依赖于特定的计算机将无法工作上面描述的默认 WIF 设置。  
  
 若要部署 web 场中的 RP 应用程序，必须确保处理的会话令牌 （以及乱令牌的） 并不依赖于特定计算机上运行的应用程序。  若要执行此操作的一种方法是实现 RP 应用程序，以使其使用 ASP 所提供的功能。NET `<machineKey>`配置元素，并提供了用于处理会话令牌分布式缓存和重播标记。  `<machineKey>`元素使您可以指定验证、 加密和解密在配置文件中，从而使您能够在 web 场中的不同计算机上指定了相同的密钥令牌所需的密钥。  WIF 提供了专用的会话令牌处理程序， <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>，这通过使用中指定的密钥保护令牌`<machineKey>`元素。  若要实现此策略，您可以遵循以下准则：  
  
-   使用 ASP。NET `<machineKey>`中显式指定可以在服务器场中的计算机之间使用的签名和加密密钥的配置元素。  下面的 XML 说明的规范`<machineKey>`元素下的`<system.web>`配置文件中的元素。  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
-   配置应用程序使用<xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>通过将其添加到标记处理程序集合。  您必须首先删除<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> （从派生的任何处理程序或<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>类） 是否存在此类处理程序标记处理程序集合中。  <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>使用<xref:System.IdentityModel.Services.MachineKeyTransform>类中，通过使用指定的加密材料保护的会话 cookie 数据的`<machineKey>`元素。  下面的 XML 说明如何添加<xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>标记处理程序集合。  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
-   从派生<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>和实现分布式缓存，即，可从 RP 可能运行的服务器场中的所有计算机访问缓存。  配置要通过指定使用分布式的缓存 RP [\<sessionSecurityTokenCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)配置文件中的元素。  您可以重写<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=fullName>在派生类实现的子元素的方法`<sessionSecurityTokenCache>`元素，如果需要。  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!—optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     实现分布式缓存的一种方法是为您的自定义缓存提供的 WCF 前端。  有关实现 WCF 缓存服务的详细信息，请参阅[WCF 缓存服务](#BKMK_TheWCFCachingService)。  有关实现 RP 应用程序可以调用缓存服务使用 WCF 客户端的详细信息，请参阅[WCF 缓存客户端](#BKMK_TheWCFClient)。  
  
-   如果您的应用程序检测到重播的标记必须遵循类似分布式缓存标记重放高速缓存的策略，通过从派生<xref:System.IdentityModel.Tokens.TokenReplayCache>和指向您的令牌重放在高速缓存服务[\<tokenReplayCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)配置元素。  
  
> [!IMPORTANT]
>  所有的示例 XML 和本主题中的代码取自[ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408) \) （英文）？LinkID \= 248408） 的示例。  
  
> [!IMPORTANT]
>  本主题中的示例作为提供的是，不适合用在生产代码，而无需修改。  
  
<a name="BKMK_TheWCFCachingService"></a>   
## WCF 缓存服务  
 下面的接口定义缓存 WCF 服务和与其通讯的依赖方应用程序使用 WCF 客户端之间的协定。  它实质上是公开的方法<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>服务操作的类。  
  
```  
[ServiceContract()]  
public interface ISessionSecurityTokenCacheService  
{  
    [OperationContract]  
    void AddOrUpdate(string endpointId, string contextId, string keyGeneration, SessionSecurityToken value, DateTime expiryTime);  
  
    [OperationContract]  
    IEnumerable<SessionSecurityToken> GetAll(string endpointId, string contextId);  
  
    [OperationContract]  
    SessionSecurityToken Get(string endpointId, string contextId, string keyGeneration);  
  
    [OperationContract(Name = "RemoveAll")]  
    void RemoveAll(string endpointId, string contextId);  
  
    [OperationContract(Name = "RemoveAllByEndpointId")]  
    void RemoveAll(string endpointId);  
  
    [OperationContract]  
    void Remove(string endpointId, string contextId, string keyGeneration);  
}  
```  
  
 下面的代码演示如何实现 WCF 服务的缓存。  在此示例中，默认情况下，使用内存中的会话令牌缓存通过 WIF 来实现。  或者，您可以实现持久缓存数据库作为后盾。  `ISessionSecurityTokenCacheService`定义的接口，如上所示。  在此示例中，所需实现接口方法不是所有显示为简洁起见。  
  
```  
using System;  
using System.Collections.Generic;  
using System.IdentityModel.Configuration;  
using System.IdentityModel.Tokens;  
using System.ServiceModel;  
using System.Xml;  
  
namespace WcfSessionSecurityTokenCacheService  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
    public class SessionSecurityTokenCacheService : ISessionSecurityTokenCacheService  
    {  
        SessionSecurityTokenCache internalCache;  
  
        // sets the internal cache used by the service to the default WIF in-memory cache.  
        public SessionSecurityTokenCacheService()  
        {  
            internalCache = new IdentityModelCaches().SessionSecurityTokenCache;  
        }  
  
        ...  
  
        public SessionSecurityToken Get(string endpointId, string contextId, string keyGeneration)  
        {  
            // Delegates to the default, in-memory MruSessionSecurityTokenCache used by WIF  
            SessionSecurityToken token = internalCache.Get(new SessionSecurityTokenCacheKey(endpointId, GetContextId(contextId), GetKeyGeneration(keyGeneration)));  
            return token;  
        }  
  
        ...  
  
        private static UniqueId GetContextId(string contextIdString)  
        {  
            return contextIdString == null ? null : new UniqueId(contextIdString);  
        }  
  
        private static UniqueId GetKeyGeneration(string keyGenerationString)  
        {  
            return keyGenerationString == null ? null : new UniqueId(keyGenerationString);  
        }  
    }  
}  
```  
  
<a name="BKMK_TheWCFClient"></a>   
## WCF 缓存客户端  
 此部分将显示一个从派生的类的实现<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>和高速缓存的服务来调用的委托。  您可以使用此类通过 RP 应用程序配置[\<sessionSecurityTokenCache\>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)作为在下面的 XML 元素  
  
```  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 类重写<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A>方法来获取服务终结点从自定义`<cacheServiceAddress>`的子元素`<sessionSecurityTokenCache>`元素。  它使用该终结点来初始化`ISessionSecurityTokenCacheService` ，它可以与服务通信的通道。  在此示例中，所有的方法才能实现<xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>类显示为简洁起见。  
  
```  
using System;  
using System.Configuration;  
using System.IdentityModel.Configuration;  
using System.IdentityModel.Tokens;  
using System.ServiceModel;  
using System.Xml;  
  
namespace CacheLibrary  
{  
    /// <summary>  
    /// This class acts as a proxy to the WcfSessionSecurityTokenCacheService.  
    /// </summary>  
    public class SharedSessionSecurityTokenCache : SessionSecurityTokenCache, ICustomIdentityConfiguration  
    {  
        private ISessionSecurityTokenCacheService WcfSessionSecurityTokenCacheServiceClient;  
  
        internal SharedSessionSecurityTokenCache()  
        {  
        }  
  
        /// <summary>  
        /// Creates a client channel to call the service host.  
        /// </summary>  
        protected void Initialize(string cacheServiceAddress)  
        {  
            if (this.WcfSessionSecurityTokenCacheServiceClient != null)  
            {  
                return;  
            }  
  
            ChannelFactory<ISessionSecurityTokenCacheService> cf = new ChannelFactory<ISessionSecurityTokenCacheService>(  
                new WS2007HttpBinding(SecurityMode.None),  
                new EndpointAddress(cacheServiceAddress));  
            this.WcfSessionSecurityTokenCacheServiceClient = cf.CreateChannel();  
        }  
  
        #region SessionSecurityTokenCache Members  
        // Delegates the following operations to the centralized session security token cache service in the web farm.  
  
        ...  
  
        public override SessionSecurityToken Get(SessionSecurityTokenCacheKey key)  
        {  
            return this.WcfSessionSecurityTokenCacheServiceClient.Get(key.EndpointId, GetContextIdString(key), GetKeyGenerationString(key));  
        }  
  
        ...  
  
        #endregion  
  
        #region ICustomIdentityConfiguration Members  
        // Called from configuration infrastructure to load custom elements  
        public void LoadCustomConfiguration(XmlNodeList nodeList)  
        {  
            // Retrieve the endpoint address of the centralized session security token cache service running in the web farm  
            if (nodeList.Count == 0)  
            {  
                throw new ConfigurationException("No child config element found under <sessionSecurityTokenCache>.");  
            }  
  
            XmlElement cacheServiceAddressElement = nodeList.Item(0) as XmlElement;  
            if (cacheServiceAddressElement.LocalName != "cacheServiceAddress")  
            {  
                throw new ConfigurationException("First child config element under <sessionSecurityTokenCache> is expected to be <cacheServiceAddress>.");  
            }  
  
            string cacheServiceAddress = null;  
            if (cacheServiceAddressElement.Attributes["url"] != null)  
            {  
                cacheServiceAddress = cacheServiceAddressElement.Attributes["url"].Value;  
            }  
            else  
            {  
                throw new ConfigurationException("<cacheServiceAddress> is expected to contain a 'url' attribute.");  
            }  
  
            // Initialize the proxy to the WebFarmSessionSecurityTokenCacheService  
            this.Initialize(cacheServiceAddress);  
        }  
        #endregion  
  
        private static string GetKeyGenerationString(SessionSecurityTokenCacheKey key)  
        {  
            return key.KeyGeneration == null ? null : key.KeyGeneration.ToString();  
        }  
  
        private static string GetContextIdString(SessionSecurityTokenCacheKey key)  
        {  
            return GetContextIdString(key.ContextId);  
        }  
  
        private static string GetContextIdString(UniqueId contextId)  
        {  
            return contextId == null ? null : contextId.ToString();  
        }  
    }  
}  
```  
  
## 请参阅  
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>   
 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>   
 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>   
 [WIF 会话管理](../../../docs/framework/security/wif-session-management.md)