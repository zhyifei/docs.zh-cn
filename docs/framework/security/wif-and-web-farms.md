---
title: WIF 和 Web 场
ms.date: 03/30/2017
ms.assetid: fc3cd7fa-2b45-4614-a44f-8fa9b9d15284
author: BrucePerlerMS
ms.openlocfilehash: 2f95213390187648c9f58b9b2bf2d5e3f49fb860
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135351"
---
# <a name="wif-and-web-farms"></a><span data-ttu-id="ff792-102">WIF 和 Web 场</span><span class="sxs-lookup"><span data-stu-id="ff792-102">WIF and Web Farms</span></span>
<span data-ttu-id="ff792-103">使用 Windows Identity Foundation (WIF) 保护 Web 场中部署的信赖方 (RP) 应用程序的资源时，必须采取特定的步骤确保 WIF 能处理场中不同计算机上运行的信赖方应用程序实例的令牌。</span><span class="sxs-lookup"><span data-stu-id="ff792-103">When you use Windows Identity Foundation (WIF) to secure the resources of a relying party (RP) application that is deployed in a web farm, you must take specific steps to ensure that WIF can process tokens from instances of the RP application running on different computers in the farm.</span></span> <span data-ttu-id="ff792-104">处理过程包括验证会话令牌签名、加密和解密会话令牌、缓存会话令牌以及检测重播的安全令牌。</span><span class="sxs-lookup"><span data-stu-id="ff792-104">This processing includes validating session token signatures, encrypting and decrypting session tokens, caching session tokens, and detecting replayed security tokens.</span></span>  
  
 <span data-ttu-id="ff792-105">通常情况下，使用 WIF 保护信赖方应用程序的资源时 – 无论 RP 是在单一计算机上运行还是在 Web 场中运行 – 都会基于从安全令牌服务 (STS) 获取的安全令牌与客户端创建一个会话。</span><span class="sxs-lookup"><span data-stu-id="ff792-105">In the typical case, when WIF is used to secure resources of an RP application – whether the RP is running on a single computer or in a web farm -- a session is established with the client based on the security token that was obtained from the security token service (STS).</span></span> <span data-ttu-id="ff792-106">这是为了避免强制客户端在 STS 对每个使用 WIF 保护的应用程序资源进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="ff792-106">This is to avoid forcing the client to have to authenticate at the STS for every application resource that is secured using WIF.</span></span> <span data-ttu-id="ff792-107">有关 WIF 如何处理会话的详细信息，请参阅 [WIF 会话管理](../../../docs/framework/security/wif-session-management.md)。</span><span class="sxs-lookup"><span data-stu-id="ff792-107">For more information about how WIF handles sessions, see [WIF Session Management](../../../docs/framework/security/wif-session-management.md).</span></span>  
  
 <span data-ttu-id="ff792-108">使用默认设置时，WIF 会执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ff792-108">When default settings are used, WIF does the following:</span></span>  
  
-   <span data-ttu-id="ff792-109">它使用 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 类的实例读取和写入会话令牌（<xref:System.IdentityModel.Tokens.SessionSecurityToken> 类的实例），此会话令牌传送声明、其他用于身份验证的安全令牌的相关信息和关于会话自身的信息。</span><span class="sxs-lookup"><span data-stu-id="ff792-109">It uses an instance of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class to read and write a session token (an instance of the <xref:System.IdentityModel.Tokens.SessionSecurityToken> class) that carries the claims and other information about the security token that was used for authentication as well as information about the session itself.</span></span> <span data-ttu-id="ff792-110">会话令牌打包并存储在会话 cookie 中。</span><span class="sxs-lookup"><span data-stu-id="ff792-110">The session token is packaged and stored in a session cookie.</span></span> <span data-ttu-id="ff792-111">默认情况下，<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 使用 <xref:System.IdentityModel.ProtectedDataCookieTransform> 类，使用数据保护 API (DPAPI) 保护会话令牌。</span><span class="sxs-lookup"><span data-stu-id="ff792-111">By default, <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> uses the <xref:System.IdentityModel.ProtectedDataCookieTransform> class, which uses the Data Protection API (DPAPI), to protect the session token.</span></span> <span data-ttu-id="ff792-112">DPAPI 使用用户或计算机凭据提供保护并将关键数据存储在用户配置文件中。</span><span class="sxs-lookup"><span data-stu-id="ff792-112">The DPAPI provides protection by using the user or machine credentials and stores the key data in the user profile.</span></span>  
  
-   <span data-ttu-id="ff792-113">它使用 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 类的默认内存中实现来存储和处理会话令牌。</span><span class="sxs-lookup"><span data-stu-id="ff792-113">It uses a default, in-memory implementation of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class to store and process the session token.</span></span>  
  
 <span data-ttu-id="ff792-114">这些默认设置在信赖方应用程序部署于单台计算机上的方案中工作，但部署在 Web 场中时 ，每个 HTTP 请求都可能发送到不同计算机上运行的信赖方应用程序的不同实例并由这些实例处理。</span><span class="sxs-lookup"><span data-stu-id="ff792-114">These default settings work in scenarios in which the RP application is deployed on a single computer; however, when deployed in a web farm, each HTTP request may be sent to and processed by a different instance of the RP application running on a different computer.</span></span> <span data-ttu-id="ff792-115">在此方案中，以上所示的默认 WIF 设置将不会工作，因为令牌保护和令牌都依赖于特定的计算机。</span><span class="sxs-lookup"><span data-stu-id="ff792-115">In this scenario, the default WIF settings described above will not work because both token protection and token caching are dependent on a specific computer.</span></span>  
  
 <span data-ttu-id="ff792-116">若要在 Web 场中部署信赖方应用程序，必须确保会话令牌（以及重播令牌）的处理不依赖于特定计算机上运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ff792-116">To deploy an RP application in a web farm, you must ensure that the processing of session tokens (as well as of replayed tokens) is not dependent on the application running on a specific computer.</span></span> <span data-ttu-id="ff792-117">一种方法是实现信赖方应用程序，以便它使用 ASP.NET `<machineKey>` 配置元素提供的功能并提供分布式缓存处理会话令牌和重播令牌。</span><span class="sxs-lookup"><span data-stu-id="ff792-117">One way to do this is to implement your RP application so that it uses the functionality provided by the ASP.NET `<machineKey>` configuration element and provides distributed caching for processing session tokens and replayed tokens.</span></span> <span data-ttu-id="ff792-118">通过 `<machineKey>` 元素可以在配置文件中指定需要验证、加密和解密令牌的密钥，可在 Web 场中的不同计算机上指定相同的密钥。</span><span class="sxs-lookup"><span data-stu-id="ff792-118">The `<machineKey>` element allows you to specify the keys needed to validate, encrypt, and decrypt tokens in a configuration file, which enables you to specify the same keys on different computers in the web farm.</span></span> <span data-ttu-id="ff792-119">WIF 提供专用的会话令牌处理程序 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>该处理程序使用 `<machineKey>` 元素中指定的密钥保护令牌。</span><span class="sxs-lookup"><span data-stu-id="ff792-119">WIF provides a specialized session token handler, the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>, that protects tokens by using the keys specified in the `<machineKey>` element.</span></span> <span data-ttu-id="ff792-120">若要实现此策略，请遵循这些指导：</span><span class="sxs-lookup"><span data-stu-id="ff792-120">To implement this strategy, you can follow these guidelines:</span></span>  
  
-   <span data-ttu-id="ff792-121">使用配置中的 ASP.NET `<machineKey>` 元素显式指定可以在场中不同计算机上使用的签名和加密密钥。</span><span class="sxs-lookup"><span data-stu-id="ff792-121">Use the ASP.NET `<machineKey>` element in configuration to explicitly specify signing and encryption keys that can be used across computers in the farm.</span></span> <span data-ttu-id="ff792-122">以下 XML 显示配置文件中 `<system.web>` 元素下的 `<machineKey>` 元素的规范。</span><span class="sxs-lookup"><span data-stu-id="ff792-122">The following XML shows the specification of the `<machineKey>` element under the `<system.web>` element in a configuration file.</span></span>  
  
    ```xml  
    <machineKey compatibilityMode="Framework45" decryptionKey="CC510D … 8925E6" validationKey="BEAC8 … 6A4B1DE" />  
    ```  
  
-   <span data-ttu-id="ff792-123">配置应用程序使用 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>，方法是将它添加到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="ff792-123">Configure the application to use the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> by adding it to the token handler collection.</span></span> <span data-ttu-id="ff792-124">如果此类处理程序存在，必须先从令牌处理程序集合中删除 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>（或者任何派生自 <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> 类的处理程序）。</span><span class="sxs-lookup"><span data-stu-id="ff792-124">You must first remove the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> (or any handler derived from the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class) from the token handler collection if such a handler is present.</span></span> <span data-ttu-id="ff792-125"><xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> 使用 <xref:System.IdentityModel.Services.MachineKeyTransform> 类，通过使用 `<machineKey>` 元素中指定的加密材料保护会话 cookie 数据。</span><span class="sxs-lookup"><span data-stu-id="ff792-125">The <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> uses the <xref:System.IdentityModel.Services.MachineKeyTransform> class, which protects the session cookie data by using the cryptographic material specified in the `<machineKey>` element.</span></span> <span data-ttu-id="ff792-126">以下 XML 显示如何添加 <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> 到令牌处理程序集合。</span><span class="sxs-lookup"><span data-stu-id="ff792-126">The following XML shows how to add the <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler> to a token handler collection.</span></span>  
  
    ```xml  
    <securityTokenHandlers>  
      <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
      <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
    </securityTokenHandlers>  
    ```  
  
-   <span data-ttu-id="ff792-127">派生自 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 并实现分布式缓存，即可从运行 RP 的场中所有计算机访问的缓存。</span><span class="sxs-lookup"><span data-stu-id="ff792-127">Derive from <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> and implement distributed caching, that is, a cache that is accessible from all computers in the farm on which the RP might run.</span></span> <span data-ttu-id="ff792-128">通过指定配置文件中的 [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) 元素配置 RP 使用分布式缓存。</span><span class="sxs-lookup"><span data-stu-id="ff792-128">Configure the RP to use your distributed cache by specifying the [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) element in the configuration file.</span></span> <span data-ttu-id="ff792-129">可以替代派生类中的 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType> 方法以按需实现 `<sessionSecurityTokenCache>` 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="ff792-129">You can override the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A?displayProperty=nameWithType> method in your derived class to implement child elements of the `<sessionSecurityTokenCache>` element if they are required.</span></span>  
  
    ```xml  
    <caches>  
      <sessionSecurityTokenCache type="MyCacheLibrary.MySharedSessionSecurityTokenCache, MyCacheLibrary">  
        <!--optional child configuration elements, if implemented by the derived class -->  
      </sessionSecurityTokenCache>  
    </caches>  
    ```  
  
     <span data-ttu-id="ff792-130">实现分布式缓存的方法之一是为自定义缓存提供 WCF 前端。</span><span class="sxs-lookup"><span data-stu-id="ff792-130">One way to implement distributed caching is to provide a WCF front end for your custom cache.</span></span> <span data-ttu-id="ff792-131">有关实现 WCF 缓存服务的详细信息，请参阅 [WCF 缓存服务](#BKMK_TheWCFCachingService)。</span><span class="sxs-lookup"><span data-stu-id="ff792-131">For more information about implementing a WCF caching service, see [The WCF Caching Service](#BKMK_TheWCFCachingService).</span></span> <span data-ttu-id="ff792-132">有关实现信赖方应用程序可用于调用缓存服务的 WCF 客户端的详细信息，请参阅 [WCF 缓存客户端](#BKMK_TheWCFClient)。</span><span class="sxs-lookup"><span data-stu-id="ff792-132">For more information about implementing a WCF client that the RP application can use to call the caching service, see [The WCF Caching Client](#BKMK_TheWCFClient).</span></span>  
  
-   <span data-ttu-id="ff792-133">如果应用程序检测到重播令牌，则必须为令牌重播缓存采用相似的分布式缓存策略，方法是从 <xref:System.IdentityModel.Tokens.TokenReplayCache> 派生并在 [\<tokenReplayCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) 配置元素中指向令牌重播缓存服务。</span><span class="sxs-lookup"><span data-stu-id="ff792-133">If your application detects replayed tokens you must follow a similar distributed caching strategy for the token replay cache by deriving from <xref:System.IdentityModel.Tokens.TokenReplayCache> and pointing to your token replay caching service in the [\<tokenReplayCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) configuration element.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ff792-134">所有示例 XML 和本主题中的代码摘自[ClaimsAwareWebFarm](https://go.microsoft.com/fwlink/?LinkID=248408)示例。</span><span class="sxs-lookup"><span data-stu-id="ff792-134">All of the example XML and code in this topic is taken from the [ClaimsAwareWebFarm](https://go.microsoft.com/fwlink/?LinkID=248408) sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ff792-135">本主题中的示例按原样提供，不建议在生产代码中不经修改直接使用。</span><span class="sxs-lookup"><span data-stu-id="ff792-135">The examples in this topic are provided as-is and are not intended to be used in production code without modification.</span></span>  
  
<a name="BKMK_TheWCFCachingService"></a>   
## <a name="the-wcf-caching-service"></a><span data-ttu-id="ff792-136">WCF 缓存服务</span><span class="sxs-lookup"><span data-stu-id="ff792-136">The WCF Caching Service</span></span>  
 <span data-ttu-id="ff792-137">以下接口定义 WCF 缓存服务和信赖方应用程序用来通信的 WCF 客户端之间的协定。</span><span class="sxs-lookup"><span data-stu-id="ff792-137">The following interface defines the contract between the WCF caching service and the WCF client used by the relying party application to communicate with it.</span></span> <span data-ttu-id="ff792-138">它实质上公开作为服务操作的 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 类的方法。</span><span class="sxs-lookup"><span data-stu-id="ff792-138">It essentially exposes the methods of the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class as service operations.</span></span>  
  
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
  
 <span data-ttu-id="ff792-139">下面的代码演示 WCF 缓存服务的实现。</span><span class="sxs-lookup"><span data-stu-id="ff792-139">The following code shows the implementation of the WCF caching service.</span></span> <span data-ttu-id="ff792-140">此示例中使用由 WIF 实现的默认的内存中会话令牌缓存。</span><span class="sxs-lookup"><span data-stu-id="ff792-140">In this example, the default, in-memory session token cache implemented by WIF is used.</span></span> <span data-ttu-id="ff792-141">此外，可以实现数据库提供支持的持久缓存。</span><span class="sxs-lookup"><span data-stu-id="ff792-141">Alternatively, you could implement a durable cache backed by a database.</span></span> `ISessionSecurityTokenCacheService` <span data-ttu-id="ff792-142">定义如上所示的接口。</span><span class="sxs-lookup"><span data-stu-id="ff792-142">defines the interface shown above.</span></span> <span data-ttu-id="ff792-143">此示例中，为简洁起见，未演示实现接口所需的所有方法。</span><span class="sxs-lookup"><span data-stu-id="ff792-143">In this example, not all of the methods required to implement the interface are shown for brevity.</span></span>  
  
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
## <a name="the-wcf-caching-client"></a><span data-ttu-id="ff792-144">WCF 缓存客户端</span><span class="sxs-lookup"><span data-stu-id="ff792-144">The WCF Caching Client</span></span>  
 <span data-ttu-id="ff792-145">此部分演示派生自 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 并委托调用缓存服务的类的实现。</span><span class="sxs-lookup"><span data-stu-id="ff792-145">This section shows the implementation of a class that derives from <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> and that delegates calls to the caching service.</span></span> <span data-ttu-id="ff792-146">通过 [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) 元素配置信赖方应用程序以使用此类，如下 XML 所示</span><span class="sxs-lookup"><span data-stu-id="ff792-146">You configure the RP application to use this class through the [\<sessionSecurityTokenCache>](../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md) element as in the following XML</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```  
  
 <span data-ttu-id="ff792-147">此类替代 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> 方法以从 `<sessionSecurityTokenCache>` 元素的自定义 `<cacheServiceAddress>` 子元素中获取服务终结点。</span><span class="sxs-lookup"><span data-stu-id="ff792-147">The class overrides the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache.LoadCustomConfiguration%2A> method to get the service endpoint from the custom `<cacheServiceAddress>` child element of the `<sessionSecurityTokenCache>` element.</span></span> <span data-ttu-id="ff792-148">它使用此终结点初始化用来与服务通信的 `ISessionSecurityTokenCacheService` 通道。</span><span class="sxs-lookup"><span data-stu-id="ff792-148">It uses this endpoint to initialize an `ISessionSecurityTokenCacheService` channel over which it can communicate with the service.</span></span>  <span data-ttu-id="ff792-149">此示例中，为简洁起见，未演示实现 <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> 类所需的所有方法。</span><span class="sxs-lookup"><span data-stu-id="ff792-149">In this example, not all of the methods required to implement the <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache> class are shown for brevity.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ff792-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff792-150">See also</span></span>

- <xref:System.IdentityModel.Tokens.SessionSecurityTokenCache>
- <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>
- <xref:System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler>
- [<span data-ttu-id="ff792-151">WIF 会话管理</span><span class="sxs-lookup"><span data-stu-id="ff792-151">WIF Session Management</span></span>](../../../docs/framework/security/wif-session-management.md)
