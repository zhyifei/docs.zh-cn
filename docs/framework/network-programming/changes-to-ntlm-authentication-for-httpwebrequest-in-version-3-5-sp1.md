---
title: "3.5 SP1 版本中对 HttpWebRequest 的 NTLM 身份验证的更改 | Microsoft Docs"
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
ms.assetid: 8bf0b428-5a21-4299-8d6e-bf8251fd978a
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# 3.5 SP1 版本中对 HttpWebRequest 的 NTLM 身份验证的更改
安全更改进行了.NET Framework版本3.5 SP1和之后影响集成Windows身份验证方式。 <xref:System.Net.HttpWebRequest>、 <xref:System.Net.HttpListener>、 <xref:System.Net.Security.NegotiateStream>和相关的选件类处理在System.Net命名空间。  这些更改会影响使用这些选件类进行web请求和接收答复使用基于NTLM的集成Windows身份验证的应用程序。  此更改会影响配置为使用集成Windows身份验证的web服务器和客户端应用程序。  
  
## 概述  
 集成Windows身份验证模型允许某些凭据响应是泛型的，这意味着它们可以重用或转发的。  如果此特定设计功能不是必需的，则身份验证协议应传播目标特定信息和引导特定信息。  服务可以提供扩展保护确保凭据响应包含服务特定的信息\(如服务主体名称\(SPN\)。  在凭据交换的此信息，服务可以更好地防范可能不正确地获取了对凭据响应的恶意用途。  
  
 在 <xref:System.Net> 和 <xref:System.Net.Security> 命名空间的多个元素委托调用的应用程序执行集成Windows身份验证。  本节介绍针对System.Net元素的更改添加到集成Windows身份验证的其用法的扩展保护。  
  
## 更改  
 NTLM身份验证过程使用集成Windows身份验证包括挑战由atlduck.exe目标计算机和发送回客户端计算机。  在生成自己的计算机接收问题，身份验证将失败，除非连接已启用连接\(例如IPv4地址， 127.0.0.1\)。  
  
 当访问运行在内部Web服务器上的服务，它访问共有的服务使用URL类似于http:\/\/contoso\/service或https:\/\/contoso\/service。  该名称“contoso”通常不是服务部署计算机的计算机名称。  使用Active Directory、DNS、NetBios、本地计算机的宿主文件\(例如通常WINDOWS \\ system32 \\ drive \\等\\宿主，\)，或本地计算机的lmhosts文件\(例如通常WINDOWS \\ system32 \\ drive \\等\\ lmhosts， <xref:System.Net> 和相关命名空间支持，\)解决名称中添加。  该名称“contoso”已解决"，以便请求发送到“contoso”发送到相应的服务器计算机。  
  
 在配置为大型部署，也很常见的做法是让一个虚拟服务器名称可以将产生与客户端应用程序和最终用户从不使用的基础设备名称的部署。  例如，可以调用在内部网络使用“contoso”的服务器， www.contoso.com，但。  此名称调用客户端web请求的宿主标头。  为指定由HTTP协议，宿主请求标头字段指定请求的资源的Internet宿主和端口号。  此信息从给定用户或引用资源\(通常HTTP URL\)的原始URI获取。  在.NET Framework 4版中，此信息可通过使用新 <xref:System.Net.HttpWebRequest.Host%2A> 属性的客户端可以设置。  
  
 <xref:System.Net.AuthenticationManager> 选件类控件 <xref:System.Net.WebRequest> 等派生选件类和 <xref:System.Net.WebClient> 选件类使用托管身份验证元素\(“模块”\)。  <xref:System.Net.AuthenticationManager> 选件类为应用程序提供在身份验证期间使用的自定义SPN字符串提供演示 <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=fullName> 对象的属性，标记由URI字符串，。  
  
 若未设置 <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A> 属性，则默认情况下，版本 3.5 SP1 将指定在 NTLM \(NT LAN Manager\) 身份验证交换中的 SPN 的请求 URL 中使用的主机名。  在请求 URL 中使用主机名可能不同于客户端请求的 <xref:System.Net.HttpRequestHeader?displayProperty=fullName> 中指定的主机标头。  在请求 URL 中使用的主机名可能不同于服务器的实际主机名、服务器的计算机名称、计算机的 IP 地址或环回地址。  在这些情况下，Windows 将会让身份验证请求失败。  若要解决此问题，我们需要通知Windows在客户端请求\(例如“contoso”的请求URL的主机名，\)实际上是一个替代名称。本地计算机。  
  
 具有服务器应用程序的若干种可能的方法可以在此更改处理。  该建议的方法是将映射用于请求URL的主机名对于注册表的 `BackConnectionHostNames` 键在服务器。  `BackConnectionHostNames` 注册表项通常用于映射主机名到启用地址。  步骤下面列出。  
  
 若要指定映射到启用地址，并且可以连接到本地计算机的网站的主机名，请执行以下步骤:  
  
 1.  依次单击“开始”和“运行”，键入 regedit，然后单击“确定”。  
  
 2.  在注册表编辑器中，找到并单击以下注册表项:  
  
 `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\MSV1_0`  
  
 3.  右击MSV1\_0，指向新的，然后单击多字符串值。  
  
 4.  键入 `BackConnectionHostNames`，然后按 Enter。  
  
 5.  右击 `BackConnectionHostNames`，然后单击修改。  
  
 6.  在值数据框中，键入主机名或主机名站点\(用于请求URL的主机名\)在本地计算机，然后单击"确定"。  
  
 7.  出注册表编辑器，然后重新启动IISAdmin服务并运行IISReset。  
  
 较不安全工作是禁用启用检查，如中所 [http:\/\/support.microsoft.com\/kb\/896861](http://go.microsoft.com/fwlink/?LinkID=179657)述。  这将禁用保护反射攻击。  因此绑定的设置备用名称设置为希望设备实际使用的那些最好。  
  
## 请参阅  
 <xref:System.Net.AuthenticationManager.CustomTargetNameDictionary%2A?displayProperty=fullName>   
 <xref:System.Net.HttpRequestHeader?displayProperty=fullName>   
 <xref:System.Net.HttpWebRequest.Host%2A?displayProperty=fullName>