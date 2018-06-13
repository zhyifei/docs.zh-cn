---
title: 代理配置
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- adaptive proxies
- static proxies
- Network Resources
- Internet, proxy configuration
- proxies
- network, proxy configuration
- proxies, configuring
ms.assetid: 353c0a8b-4cee-44f6-8e65-60e286743df9
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 41e1dcee90531de605b6bddc1eedc1c44235d8eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397528"
---
# <a name="proxy-configuration"></a><span data-ttu-id="74eba-102">代理配置</span><span class="sxs-lookup"><span data-stu-id="74eba-102">Proxy Configuration</span></span>
<span data-ttu-id="74eba-103">代理服务器处理客户端对资源的请求。</span><span class="sxs-lookup"><span data-stu-id="74eba-103">A proxy server handles client requests for resources.</span></span> <span data-ttu-id="74eba-104">代理可以从其缓存中返回已请求的资源，或将请求转发到资源驻留的服务器。</span><span class="sxs-lookup"><span data-stu-id="74eba-104">A proxy can return a requested resource from its cache or forward the request to the server where the resource resides.</span></span> <span data-ttu-id="74eba-105">代理可以通过减少发送到远程服务器的请求数量来提高网络性能。</span><span class="sxs-lookup"><span data-stu-id="74eba-105">Proxies can improve network performance by reducing the number of requests sent to remote servers.</span></span> <span data-ttu-id="74eba-106">代理还可以用于限制对资源的访问。</span><span class="sxs-lookup"><span data-stu-id="74eba-106">Proxies can also be used to restrict access to resources.</span></span>  
  
## <a name="adaptive-proxies"></a><span data-ttu-id="74eba-107">自适应代理</span><span class="sxs-lookup"><span data-stu-id="74eba-107">Adaptive Proxies</span></span>  
 <span data-ttu-id="74eba-108">在 .NET Framework 中，有两种代理：自适应和静态。</span><span class="sxs-lookup"><span data-stu-id="74eba-108">In the .NET Framework, proxies come in two varieties: adaptive and static.</span></span> <span data-ttu-id="74eba-109">自适应代理会在网络配置更改时调整它们的设置。</span><span class="sxs-lookup"><span data-stu-id="74eba-109">Adaptive proxies adjust their settings when the network configuration changes.</span></span> <span data-ttu-id="74eba-110">例如，如果便携式计算机用户启动拨号网络连接,自适应代理会识别此更改,发现并运行其新配置脚本，然后相应调整其设置。</span><span class="sxs-lookup"><span data-stu-id="74eba-110">For example, if a laptop user starts a dialup network connection, an adaptive proxy would recognize this change, discover and run its new configuration script, and adjust its settings appropriately.</span></span>  
  
 <span data-ttu-id="74eba-111">自适应代理是通过配置脚本配置的（请参阅[自动代理检测](../../../docs/framework/network-programming/automatic-proxy-detection.md)）。</span><span class="sxs-lookup"><span data-stu-id="74eba-111">Adaptive proxies are configured by a configuration script (see [Automatic Proxy Detection](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span></span> <span data-ttu-id="74eba-112">脚本针对每个协议生成一组应用程序协议和一个代理。</span><span class="sxs-lookup"><span data-stu-id="74eba-112">The script generates a set of application protocols and a proxy for each protocol.</span></span>  
  
 <span data-ttu-id="74eba-113">多个选项控制配置脚本的运行方式。</span><span class="sxs-lookup"><span data-stu-id="74eba-113">Several options control how the configuration script is run.</span></span> <span data-ttu-id="74eba-114">可以指定以下各项：</span><span class="sxs-lookup"><span data-stu-id="74eba-114">You can specify the following:</span></span>  
  
-   <span data-ttu-id="74eba-115">下载和运行配置脚本的频率。</span><span class="sxs-lookup"><span data-stu-id="74eba-115">How often the configuration script is downloaded and run.</span></span>  
  
-   <span data-ttu-id="74eba-116">下载脚本需要等待多长时间。</span><span class="sxs-lookup"><span data-stu-id="74eba-116">How long to wait for the script to download.</span></span>  
  
-   <span data-ttu-id="74eba-117">你的系统应使用哪些凭据访问代理。</span><span class="sxs-lookup"><span data-stu-id="74eba-117">Which credentials your system should use to access the proxy.</span></span>  
  
-   <span data-ttu-id="74eba-118">你的系统应使用哪些凭据下载配置脚本。</span><span class="sxs-lookup"><span data-stu-id="74eba-118">Which credentials your system should use to download the configuration script.</span></span>  
  
 <span data-ttu-id="74eba-119">网络环境的变化可能要求系统使用一组新代理。</span><span class="sxs-lookup"><span data-stu-id="74eba-119">Changes in the network environment may require that the system use a new set of proxies.</span></span> <span data-ttu-id="74eba-120">如果网络连接不可用或新的网络连接已初始化，系统必须在新环境中发现相应的配置脚本源并运行新脚本。</span><span class="sxs-lookup"><span data-stu-id="74eba-120">If a network connection goes down or a new network connection is initialized, the system must discover the appropriate source of the configuration script in the new environment and run the new script.</span></span>  
  
 <span data-ttu-id="74eba-121">下表显示了自适应代理的配置选项。</span><span class="sxs-lookup"><span data-stu-id="74eba-121">The following table shows configuration options for an adaptive proxy.</span></span>  
  
|<span data-ttu-id="74eba-122">特性、属性或配置文件设置</span><span class="sxs-lookup"><span data-stu-id="74eba-122">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="74eba-123">描述</span><span class="sxs-lookup"><span data-stu-id="74eba-123">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|`scriptDownloadInterval`|<span data-ttu-id="74eba-124">用秒计算的脚本下载之间的运行时间。</span><span class="sxs-lookup"><span data-stu-id="74eba-124">Elapsed time in seconds between script downloads.</span></span>|  
|`scriptDownloadTimeout`|<span data-ttu-id="74eba-125">下载脚本的等待时间（用秒计算）。</span><span class="sxs-lookup"><span data-stu-id="74eba-125">Time to wait (in seconds) for the script to download.</span></span>|  
|<span data-ttu-id="74eba-126">`useDefaultCredentials` 或 <xref:System.Net.WebProxy.UseDefaultCredentials></span><span class="sxs-lookup"><span data-stu-id="74eba-126">`useDefaultCredentials` or <xref:System.Net.WebProxy.UseDefaultCredentials></span></span>|<span data-ttu-id="74eba-127">控制系统是否使用默认网络凭据访问代理。</span><span class="sxs-lookup"><span data-stu-id="74eba-127">Controls whether the system uses the default network credentials to access a proxy.</span></span>|  
|`useDefaultCredentialForScriptDownload`|<span data-ttu-id="74eba-128">控制系统是否使用默认网络凭据下载配置脚本。</span><span class="sxs-lookup"><span data-stu-id="74eba-128">Controls whether the system uses the default network credentials to download the configuration script.</span></span>|  
|`usesystemdefaults`|<span data-ttu-id="74eba-129">控制是否应从用户的 Internet Explorer 代理设置读取静态代理设置（代理地址、跳过列表和跳过本地）。</span><span class="sxs-lookup"><span data-stu-id="74eba-129">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="74eba-130">如果这个值设置为“true”，那么将使用来自 Internet Explorer 的静态代理设置。</span><span class="sxs-lookup"><span data-stu-id="74eba-130">If this value is set to "true", then the static proxy settings from Internet Explorer will be used.</span></span><br /><br /> <span data-ttu-id="74eba-131">如果这个值设置为“false”或未设置，那么静态代理设置可在配置中指定并将替代 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="74eba-131">If this value is "false" or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="74eba-132">此外，这个值必须设置为“false”或不设置，才能启用自适应代理。</span><span class="sxs-lookup"><span data-stu-id="74eba-132">This value must also be set to "false" or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="74eba-133">以下例子显示了典型的自适应代理配置。</span><span class="sxs-lookup"><span data-stu-id="74eba-133">The following example shows a typical adaptive proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy  scriptDownloadInterval="600"  
              scriptDownloadTimeout="30"  
              useDefaultCredentials="true"  
              usesystemdefaults="true"  
      />  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a><span data-ttu-id="74eba-134">静态代理</span><span class="sxs-lookup"><span data-stu-id="74eba-134">Static Proxies</span></span>  
 <span data-ttu-id="74eba-135">静态代理通常由应用程序显示配置，或者当配置文件被应用程序或系统调用时配置。</span><span class="sxs-lookup"><span data-stu-id="74eba-135">Static proxies are usually configured explicitly by an application, or when a configuration file is invoked by an application or the system.</span></span> <span data-ttu-id="74eba-136">静态代理在拓扑结构更改不频繁的网络中很有用，比如连接到企业网络的台式计算机。</span><span class="sxs-lookup"><span data-stu-id="74eba-136">Static proxies are useful in networks in which the topology changes infrequently, such as a desktop computer connected to a corporate network.</span></span>  
  
 <span data-ttu-id="74eba-137">多个选项控制静态代理的运行方式。</span><span class="sxs-lookup"><span data-stu-id="74eba-137">Several options control how a static proxy operates.</span></span> <span data-ttu-id="74eba-138">可以指定以下各项：</span><span class="sxs-lookup"><span data-stu-id="74eba-138">You can specify the following:</span></span>  
  
-   <span data-ttu-id="74eba-139">代理的地址。</span><span class="sxs-lookup"><span data-stu-id="74eba-139">The address of the proxy.</span></span>  
  
-   <span data-ttu-id="74eba-140">是否应对本地地址不使用代理。</span><span class="sxs-lookup"><span data-stu-id="74eba-140">Whether the proxy should be bypassed for local addresses.</span></span>  
  
-   <span data-ttu-id="74eba-141">是否应对一组地址不使用代理。</span><span class="sxs-lookup"><span data-stu-id="74eba-141">Whether the proxy should be bypassed for a set of addresses.</span></span>  
  
 <span data-ttu-id="74eba-142">下表显示了静态代理的配置选项。</span><span class="sxs-lookup"><span data-stu-id="74eba-142">The following table shows the configuration options for a static proxy.</span></span>  
  
|<span data-ttu-id="74eba-143">特性、属性或配置文件设置</span><span class="sxs-lookup"><span data-stu-id="74eba-143">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="74eba-144">描述</span><span class="sxs-lookup"><span data-stu-id="74eba-144">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|<span data-ttu-id="74eba-145">`proxyaddress` 或 <xref:System.Net.WebProxy.Address></span><span class="sxs-lookup"><span data-stu-id="74eba-145">`proxyaddress` or <xref:System.Net.WebProxy.Address></span></span>|<span data-ttu-id="74eba-146">要使用的代理地址。</span><span class="sxs-lookup"><span data-stu-id="74eba-146">The address of the proxy to use.</span></span>|  
|<span data-ttu-id="74eba-147">`bypassonlocal` 或 <xref:System.Net.WebProxy.BypassProxyOnLocal></span><span class="sxs-lookup"><span data-stu-id="74eba-147">`bypassonlocal` or <xref:System.Net.WebProxy.BypassProxyOnLocal></span></span>|<span data-ttu-id="74eba-148">控制是否对本地地址不使用代理。</span><span class="sxs-lookup"><span data-stu-id="74eba-148">Controls whether the proxy is bypassed for local addresses.</span></span>|  
|<span data-ttu-id="74eba-149">`bypasslist` 或 <xref:System.Net.WebProxy.BypassArrayList></span><span class="sxs-lookup"><span data-stu-id="74eba-149">`bypasslist` or <xref:System.Net.WebProxy.BypassArrayList></span></span>|<span data-ttu-id="74eba-150">用正则表达式描述不使用代理的一组地址。</span><span class="sxs-lookup"><span data-stu-id="74eba-150">Describes, with regular expressions, a set of addresses that bypass the proxy.</span></span>|  
|`usesystemdefaults`|<span data-ttu-id="74eba-151">控制是否应从用户的 Internet Explorer 代理设置读取静态代理设置（代理地址、跳过列表和跳过本地）。</span><span class="sxs-lookup"><span data-stu-id="74eba-151">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="74eba-152">如果这个值设置为“true”，那么将使用来自 Internet Explorer 的静态代理设置。</span><span class="sxs-lookup"><span data-stu-id="74eba-152">If this value is set to "true", then the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="74eba-153">在 .NET Framework 2.0 中，当这个值设置为“true”时，Internet Explorer 代理设置不会被配置文件中的其他代理设置替代。</span><span class="sxs-lookup"><span data-stu-id="74eba-153">On .NET Framework 2.0 when this value is set to "true", the Internet Explorer proxy settings are not overridden by other proxy settings in the configuration file.</span></span> <span data-ttu-id="74eba-154">在 .NET Framework 1.1 中，Internet Explorer 代理设置可以被配置文件中的其他代理设置替代。</span><span class="sxs-lookup"><span data-stu-id="74eba-154">On .NET Framework 1.1, the Internet Explorer proxy settings can be overridden by other proxy settings in the configuration file.</span></span><br /><br /> <span data-ttu-id="74eba-155">如果这个值设置为“false”或未设置，那么静态代理设置可在配置中指定并将替代 Internet Explorer 代理设置。</span><span class="sxs-lookup"><span data-stu-id="74eba-155">If this value is "false" or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="74eba-156">此外，这个值必须设置为“false”或不设置，才能启用自适应代理。</span><span class="sxs-lookup"><span data-stu-id="74eba-156">This value must also be set to "false" or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="74eba-157">以下示例显示了一个典型的静态代理配置。</span><span class="sxs-lookup"><span data-stu-id="74eba-157">The following example shows a typical static proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
        <proxy  proxyaddress="http://proxy.contoso.com:3128"  
                bypassonlocal="true"  
        />  
        <bypasslist>  
            <add address="[a-z]+.blueyonderairlines.com$" />  
        </bypasslist>  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="74eba-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="74eba-158">See Also</span></span>  
 <xref:System.Net.WebProxy>  
 <xref:System.Net.GlobalProxySelection>  
 [<span data-ttu-id="74eba-159">自动代理检测</span><span class="sxs-lookup"><span data-stu-id="74eba-159">Automatic Proxy Detection</span></span>](../../../docs/framework/network-programming/automatic-proxy-detection.md)
