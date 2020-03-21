---
title: Internet 信息服务承载最佳实践
ms.date: 03/30/2017
ms.assetid: 0834768e-9665-46bf-86eb-d4b09ab91af5
ms.openlocfilehash: 3be9d4c81f891ad898099ba9041a09b16388b7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184722"
---
# <a name="internet-information-services-hosting-best-practices"></a>Internet 信息服务承载最佳实践
本主题概述了托管 Windows 通信基础 （WCF） 服务的一些最佳做法。  
  
## <a name="implementing-wcf-services-as-dlls"></a>将 WCF 服务实现为 DLL  
 将 WCF 服务作为 DLL 部署到 Web 应用程序的 \bin 目录，允许您在 Web 应用程序模型之外重用该服务，例如，在可能没有部署 Internet 信息服务 （IIS） 的测试环境中重用该服务。  
  
## <a name="service-hosts-in-iis-hosted-applications"></a>承载于 IIS 中的应用程序中的服务主机  
 不要使用命令式自主机 API 来创建新的服务主机，这些主机侦听 IIS 托管环境不支持的本机传输（例如，IIS 6.0 承载 TCP 服务，因为 IIS 6.0 上不支持本机通信）。 建议不要使用此方法。 强制创建的服务主机在 IIS 承载环境内是未知的。 很重要的一点是，在 IIS 确定承载应用程序池是否空闲时，它未说明强制创建的服务所进行的处理。 结果是具有这样强制创建的服务主机的应用程序具有主动处置 IIS 托管进程的 IIS 承载环境。  
  
## <a name="uris-and-iis-hosted-endpoints"></a>URI 和承载于 IIS 中的终结点  
 承载于 IIS 中的服务的终结点应该使用相对统一资源标识符 (URI) 而不是绝对地址进行配置。 这保证终结点地址在属于承载应用程序的 URI 地址集范围内，并确保像预期的那样发生基于消息的激活。  
  
## <a name="state-management-and-process-recycling"></a>状态管理和进程回收  
 为不在内存中维护本地状态的服务优化了 IIS 承载环境。 IIS 回收托管进程以响应各种外部和内部事件，导致仅存储在内存中的任何可变状态丢失。 寄宿在 IIS 中的服务应该在进程外存储其状态（例如，在数据库中），或者在出现应用程序回收事件时可以轻松重新创建的内存中缓存中存储其状态。  
  
> [!NOTE]
> WCF 用于消息层可靠性和安全性的协议利用了易失性内存状态。 由于应用程序回收，WCF 可靠的会话和安全会话可能会意外终止。 使用这些协议的 IIS 托管应用程序应依赖于 WCF 提供的会话密钥以外的内容来关联应用程序层状态（例如，应用程序层构造或自定义关联标头），或禁用IIS 进程回收托管应用程序。  
  
## <a name="optimizing-performance-in-middle-tier-scenarios"></a>在中间层方案中优化性能  
 为了在*中间层方案中*获得最佳性能（一种响应传入消息而调用其他服务的服务），将 WCF 服务客户端实例化到远程服务一次，并在多个传入请求中重用它。 相对于对预先存在的客户端实例进行服务调用，实例化 WCF 服务客户端是一项昂贵的操作，中间层方案通过跨请求缓存远程客户端来产生显著的性能提升。 WCF 服务客户端是线程安全的，因此不必跨多个线程同步对客户端的访问。  
  
 中间层方案还通过使用由 `svcutil /a` 选项生成的异步 API 来产生性能提升。 该`/a`选项使[ServiceModel 元数据实用程序工具 （Svcutil.exe）](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)为每个服务操作生成`BeginXXX/EndXXX`方法，从而允许在后台线程上对远程服务进行可能长时间运行的调用。  
  
## <a name="wcf-in-multi-homed-or-multi-named-scenarios"></a>多宿主或多名称方案中的 WCF  
 可以在 IIS Web 场内部署 WCF 服务，其中一组计算机共享一个公共外部名称（`http://www.contoso.com`如），但由不同的主机名单独寻址（例如，`http://www.contoso.com`可能会将流量定向到两台名为`http://machine1.internal.contoso.com`和`http://machine2.internal.contoso.com`的计算机。 此部署方案完全支持 WCF，但需要托管 WCF 服务的 IIS 网站的特殊配置才能在服务的元数据（Web 服务描述语言）中显示正确的（外部）主机名。  
  
 为确保正确的主机名出现在 WCF 生成的服务元数据中，请为承载 WCF 服务的 IIS 网站配置默认标识以使用显式主机名。 例如，驻留在`www.contoso.com`服务器场内的计算机应使用用于 HTTP 的 IIS 网站绑定 ：80：www.contoso.com\*和 ：443：www.contoso.com 用于 HTTPS。  
  
 可以使用 IIS Microsoft 管理控制台 (MMC) 管理单元配置 IIS 网站绑定。  
  
## <a name="application-pools-running-in-different-user-contexts-overwrite-assemblies-from-other-accounts-in-the-temporary-folder"></a>在不同用户上下文中运行的应用程序池覆盖来自临时文件夹中其他帐户的程序集  
 为了确保在不同用户上下文中运行的应用程序池不能覆盖临时ASP.NET文件文件夹中其他帐户的程序集，请使用不同应用程序的不同标识和临时文件夹。 例如，如果具有两个虚拟应用程序 /Application1 和 / Application2，则可以创建两个应用程序池 A 和 B，它们具有不同的标识。 应用程序池 A 可以使用一个用户标识 (user1) 运行，而应用程序池 B 可以使用其他用户标识 (user2) 运行，并将 /Application1 配置为使用 A，将 /Application2 配置为使用 B。  
  
 在 Web.config 中，您可以使用\<system.web/compilation/@tempFolder>配置临时文件夹。 对于 /Application1，它可以是"c：\tempForUser1"，对于应用程序2，它可以是"c：\tempForUser2"。 将相应的写入权限授予两个标识的这些文件夹。  
  
 之后，user2 无法更改 /application2 的代码生成文件夹（在 c:\tempForUser1 下）。  
  
## <a name="enabling-asynchronous-processing"></a>启用异步处理  
 默认情况下，发送到 IIS 6.0 和更早版本的 WCF 服务的消息以同步方式处理。 ASP.NET在其自己的线程（ASP.NET工作线程）上调用 WCF，WCF 使用另一个线程来处理请求。 WCF 在完成其处理之前会保持 ASP.NET 工作线程。 这将导致同步处理请求。 异步处理请求可异地实现更大的可伸缩性，因为它减少了处理请求所需的线程数 —WCF 在处理请求时不会保留ASP.NET线程。 不建议对运行 IIS 6.0 的计算机使用异步行为，因为无法限制打开服务器的传入请求以拒绝*服务*（DOS） 攻击。 从 IIS 7.0 开始，引入了并发请求限制：`[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ASP.NET\2.0.50727.0]"MaxConcurrentRequestsPerCpu`。 借助这一新的限制，可安全地使用异步处理。  默认情况下，在 IIS 7.0 中会注册异步处理程序和模块。 如果关闭了此功能，可在应用程序的 Web.config 文件中手动启用对请求的异步处理。 所使用的设置取决于 `aspNetCompatibilityEnabled` 设置。 如果已将 `aspNetCompatibilityEnabled` 设置为 `false`，请按照下面的配置代码段所示配置 `System.ServiceModel.Activation.ServiceHttpModule`。  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="false" />
  </system.serviceModel>  
  <system.webServer>  
    <modules>  
      <remove name="ServiceModel"/>  
      <add name="ServiceModel"
           preCondition="integratedMode,runtimeVersionv2.0"
           type="System.ServiceModel.Activation.ServiceHttpModule, System.ServiceModel,Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
    </modules>  
    </system.webServer>  
```  
  
 如果已将 `aspNetCompatibilityEnabled` 设置为 `true`，请按照下面的配置代码段所示配置 `System.ServiceModel.Activation.ServiceHttpHandlerFactory`。  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
  </system.serviceModel>  
  <system.webServer>  
    <handlers>  
          <clear/>  
          <add name="TestAsyncHttpHandler"
               path="*.svc"
               verb="*"
               type="System.ServiceModel.Activation.ServiceHttpHandlerFactory, System.ServiceModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"
               />  
    </handlers>
  </system.webServer>  
```  
  
## <a name="see-also"></a>另请参阅

- [服务承载示例](../samples/hosting.md)
- [Windows Server App Fabric 承载功能](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
