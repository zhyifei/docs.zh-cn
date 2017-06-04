---
title: "了解 WebRequest 问题和异常 | Microsoft Docs"
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
ms.assetid: 74a361a5-e912-42d3-8f2e-8e9a96880a2b
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# 了解 WebRequest 问题和异常
<xref:System.Net.WebRequest> 及其派生类\(<xref:System.Net.HttpWebRequest>、 <xref:System.Net.FtpWebRequest>和 <xref:System.Net.FileWebRequest>\)引发异常触发异常状态。  有时这些问题的解决方法不是透明的。  
  
## 解决方案  
 检查 <xref:System.Net.WebException> 的 <xref:System.Net.WebException.Status%2A> 属性确定问题。  下表显示多个状态值和一些可能的解决方法。  
  
|状态|详细信息|解决方案|  
|--------|----------|----------|  
|<xref:System.Net.WebExceptionStatus><br /><br /> \- 或 \-<br /><br /> <xref:System.Net.WebExceptionStatus>|具有基础套接字的问题。  可以重置连接。|重新连接并重新发送请求。<br /><br /> 确定安装最新的Service Pack。<br /><br /> 增加 <xref:System.Net.ServicePointManager.MaxServicePointIdleTime%2A?displayProperty=fullName> 属性的值。<br /><br /> 将 <xref:System.Net.HttpWebRequest.KeepAlive%2A?displayProperty=fullName> 设置为 `false`。<br /><br /> 增加最大连接数的数目。 <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> 属性。<br /><br /> 检查代理配置。<br /><br /> 如果使用SSL，请确保服务器进程有权访问的证书存储区。<br /><br /> 如果发送大量数据，设置 <xref:System.Net.HttpWebRequest.AllowWriteStreamBuffering%2A> 到 `false`。|  
|<xref:System.Net.WebExceptionStatus>|服务器证书未能验证。|使用Internet Explorer，尝试打开URI。  解决IE显示的所有安全警报。  如果无法解决安全警报，则可以创建实现 <xref:System.Net.ICertificatePolicy> 返回 `true`，并将其传递给 <xref:System.Net.ServicePointManager.CertificatePolicy%2A>的证书策略选件类。<br /><br /> 请参见 [http:\/\/support.microsoft.com\/?id\=823177](http://go.microsoft.com/fwlink/?LinkID=179653)。<br /><br /> 确保服务器证书签名证书颁发机构的证书在Internet Explorer中添加到受信任的证书颁发机构列表。<br /><br /> 确保URL中的主机名与服务器证书的通用名称。|  
|<xref:System.Net.WebExceptionStatus>|错误在SSL事务生成的，或者具有证书问题。|.NET Framework 1.1版只支持SSL 3.0版。  如果服务器使用TLS 1.0版或仅SSL 2.0版，将引发异常。  升级到.NET Framework 2.0版中，并将 <xref:System.Net.ServicePointManager.SecurityProtocol%2A> 与服务器。<br /><br /> 客户端证书由服务器不信任的证书颁发机构\(CA\)签名。  安装CA证书在服务器。  请参见 [http:\/\/support.microsoft.com\/?id\=332077](http://go.microsoft.com/fwlink/?LinkID=179654)。<br /><br /> 确保您具有最新的Service Pack安装。|  
|<xref:System.Net.WebExceptionStatus>|连接失败。|firewall或proxy块连接。  修改该firewall或代理允许连接。<br /><br /> 通过调用 <xref:System.Net.WebProxy> 构造函数显式指定在客户端应用程序中 <xref:System.Net.WebProxy> \(WebServiceProxyClass.Proxy \= new WebProxy \([http:\/\/server:80](http://server/)， true\)。<br /><br /> 运行Filemon或确保的Regmon辅助进程标识具有必要的权限访问WSPWSP.dll、HKLM \\ SYSTEM \\ CurrentControlSet \\ services \\ DnsCache或HKLM \\ SYSTEM \\ CurrentControlSet \\ services \\ WinSock2。|  
|<xref:System.Net.WebExceptionStatus>|域名服务无法解析主机名。|正确配置代理。  请参见 [http:\/\/support.microsoft.com\/?id\=318140](http://go.microsoft.com/fwlink/?LinkID=179655)。<br /><br /> 确保任何安装的防病毒软件或firewall不阻止连接。|  
|<xref:System.Net.WebExceptionStatus>|<xref:System.Net.WebRequest.Abort%2A> 调用，或者发生错误。|此问题可能由客户端或服务器上重新生成。  减少加载。<br /><br /> 增加 <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> 设置。<br /><br /> 请参见 [http:\/\/support.microsoft.com\/?id\=821268](http://go.microsoft.com/fwlink/?LinkID=179656) 修改Web服务性能设置。|  
|<xref:System.Net.WebExceptionStatus>|应用程序尝试写入已关闭的套接字。|重载客户端或服务器。  减少加载。<br /><br /> 增加 <xref:System.Net.ServicePointManager.DefaultConnectionLimit%2A> 设置。<br /><br /> 请参见 [http:\/\/support.microsoft.com\/?id\=821268](http://go.microsoft.com/fwlink/?LinkID=179656) 修改Web服务性能设置。|  
|<xref:System.Net.WebExceptionStatus>|在信息长度设置的\(<xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>\)限制超过了。|增加 <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A> 属性的值。|  
|<xref:System.Net.WebExceptionStatus>|域名服务无法解析代理主机名。|正确配置代理。  请参见 [http:\/\/support.microsoft.com\/?id\=318140](http://go.microsoft.com/fwlink/?LinkID=179655)。<br /><br /> 不要强制 <xref:System.Net.HttpWebRequest> 通过设置 <xref:System.Net.HttpWebRequest.Proxy%2A> 属性使用代理到 `null`。|  
|<xref:System.Net.WebExceptionStatus>|来自服务器的响应不是有效的HTTP响应。  发生此问题，在将.NET Framework检测服务器响应不符合HTTP 1.1 RFC。  ，则会出现此问题。响应包含不正确标头时或不正确标头delimiters.RFC 2616定义HTTP 1.1和响应的格式有效从服务器。  有关更多信息，请参见 [http:\/\/www.ietf.org](http://go.microsoft.com/fwlink/?LinkID=147388)。|获取事务的网络跟踪并在响应中标头。<br /><br /> 如果应用程序需要服务器响应，而不分析\(这可能存在安全问题\)，将 `useUnsafeHeaderParsing` 对配置文件的 `true` 。  请参见 [\<httpWebRequest\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/httpwebrequest-element-network-settings.md)。|  
  
## 请参阅  
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.HttpWebResponse>   
 <xref:System.Net.Dns>