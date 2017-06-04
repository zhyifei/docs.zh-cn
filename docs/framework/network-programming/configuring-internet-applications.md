---
title: "配置 Internet 应用程序 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "下载 Internet 资源，默认代理"
  - "发送数据，默认代理"
  - "接收数据，默认代理"
  - "下载 Internet 资源，配置 Internet 应用程序"
  - "协议特定模块"
  - "自定义身份验证模块"
  - "接收数据，配置 Internet 应用程序"
  - "配置设置 [.NET Framework]，Internet 应用程序"
  - "从 Internet 请求数据，配置 Internet 应用程序"
  - "从 Internet 请求数据，默认代理"
  - "响应 Internet 请求，默认代理"
  - "Internet，配置 Internet 应用程序"
  - "响应 Internet 请求，配置 Internet 应用程序"
  - "默认代理"
  - "网络资源，默认代理"
  - "发送数据，配置 Internet 应用程序"
  - "网络资源，配置 Internet 应用程序"
  - "Internet，默认代理"
ms.assetid: bb707c72-eed2-4a82-8800-c9e68df2fd4f
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 15
---
# 配置 Internet 应用程序
[\<system.Net\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) 配置元素包含应用程序的网络配置信息。  使用 [\<system.Net\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) 元素，可以设置代理服务器，设置连接管理参数，并包括自定义身份验证并请求应用程序的模块。  
  
 [\<defaultProxy\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) 元素定义 `GlobalProxySelection` 选件类返回的代理服务器。  所有 <xref:System.Net.HttpWebRequest> 没有自己的 <xref:System.Net.HttpWebRequest.Proxy%2A> 的属性设置为特定值使用默认代理。  除了设置代理地址外，还可以生成的服务器地址列表将不使用代理，因此，您可以指示不应对于本地地址使用代理。  
  
 请注意， Microsoft Internet Explorer设置将与配置设置是重要的，该后执行的优先级。  
  
 下面的示例将默认代理服务器地址为http:\/\/proxyserver，指示不应对于本地地址使用代理，并指定任何请求到位于contoso.com域的服务器如果跳过代理。  
  
```  
<configuration>  
    <system.net>  
        <defaultProxy>  
            <proxy  
                usesystemdefault = "false"  
                proxyaddress = "http://proxyserver:80"  
                bypassonlocal = "true"  
            />  
            <bypasslist>  
                <add address="http://[a-z]+\.contoso\.com/" />  
            </bypasslist>  
        </defaultProxy>  
    </system.net>  
</configuration>  
```  
  
 使用 [\<connectionManagement\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) 元素配置可生成到特定服务器或其他服务器、连接数。  下面的示例将应用程序配置为使用与服务器www.contoso.com的两个持久连接，与服务器的四持久连接与IP地址192.168.1.2和与其他服务器的持久性连接。  
  
```  
<configuration>  
    <system.net>  
        <connectionManagement>  
            <add address="http://www.contoso.com" maxconnection="2" />  
            <add address="192.168.1.2" maxconnection="4" />  
            <add address="*" maxconnection="1" />  
        </connectionManagement>  
    </system.net>  
</configuration>  
```  
  
 自定义身份验证模块配置了 [\<authenticationModules\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) 元素。  自定义身份验证模块必须实现 <xref:System.Net.IAuthenticationModule> 接口。  
  
 下面的示例配置自定义身份验证模块。  
  
```  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 可以使用 [\<webRequestModules\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) 元素配置应用程序以使用自定义协议特殊化模块请求Internet资源的信息。  指定的模块必须实现 <xref:System.Net.IWebRequestCreate> 接口。  可以通过指定自定义模块重写默认HTTP、HTTPS和文件请求模块在配置文件中，如下面的示例所示。  
  
```  
<configuration>  
    <system.net>  
        <webRequestModules>  
            <add  
                prefix="HTTP"  
                type = "MyHttpRequest.dll, MyHttpRequestCreator"  
            />  
        </webRequestModules>  
    </system.net>  
</configuration>  
```  
  
## 请参阅  
 [.NET Framework 中的网络编程](../../../docs/framework/network-programming/index.md)   
 [网络设置架构](../../../docs/framework/configure-apps/file-schema/network/index.md)   
 [\<system.Net\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)