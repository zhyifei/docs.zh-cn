---
title: "自动代理检测 | Microsoft Docs"
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
  - "自动代理检测"
  - "Web 代理自动发现"
  - "Web 代理"
  - "自动检测代理"
  - "WebProxy 类，自动代理检测"
  - "代理，自动检测"
  - "网络"
  - "WPAD（Web 代理自动发现）"
ms.assetid: fcd9c3bd-93de-4c92-8ff3-837327ad18de
caps.latest.revision: 18
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 18
---
# 自动代理检测
自动代理检测是Web代理服务器是由系统确定的用于代表客户端发送请求的处理。  此功能也称为 Web Proxy Auto\-Discovery \(WPAD\)。  当自动检测代理启用时，系统会尝试定位到返回负责将代理可用于该请求的代理配置脚本。  如果找到代理配置脚本，该脚本在本地计算机上下载，编译，然后运行，当代理信息、请求流或响应用于 <xref:System.Net.WebProxy> 实例的请求期间获得。  
  
 自动代理检测由 <xref:System.Net.WebProxy> 选件类执行，并且可以使用请求级设置、使用Internet Explorer **局域网\(LAN\)** 对话框中指定的设置在配置文件和设置。  
  
> [!NOTE]
>  通过选择 **工具** 从Internet Explorer然后选择 **Internet选项**显示Internet Explorer **局域网 \(LAN\) 设置** 对话框。  然后，选择 **连接** 选项，然后单击 **局域网设置**。  
  
 当自动检测代理启用时， <xref:System.Net.WebProxy> 选件类尝试定位代理配置脚本如下:  
  
1.  WinINet `InternetQueryOption` 功能用于定位Internet Explorer最近检测的代理配置脚本。  
  
2.  如果没有找到该脚本， <xref:System.Net.WebProxy> 选件类使用宿主动态配置协议\(DHCP\)找到该脚本。  DHCP服务器可以响应具有位置\(主机名\)此脚本或与该脚本的完整URL。  
  
3.  如果、不确定WPAD宿主， DNS对于WPAD的宿主将查询另存为其姓名或别名。  
  
4.  如果宿主未标识，并且代理配置脚本的位置由Internet Explorer LAN设置或配置文件中指定，使用此位置。  
  
> [!NOTE]
>  运行作为NT服务或作为ASP.NET应用程序的一部分使用Internet Explorer代理服务器设置\(如果有\)所调用的用户。  这些设置可能不适用于所有服务应用程序。  
  
 代理在每connectoid基类型的配置。  connectoid位于网络连接对话框的项目，并可以是物理网络设备\(调制解调器或以太网\)纸牌\)或虚拟接口\(例如运行在网络设备\)的VPN连接。  当connectoid更改\(例如，无线连接更改访问点时，或者VPN启用\)，代理检测算法再次运行。  
  
 默认情况下， Internet Explorer代理设置用于检测代理。  如果您的应用程序运行在非交互式的帐户\(没有一种简便方式配置IE代理设置\)，或者，如果您与IE设置若要使用代理设置不同，可以通过创建配置文件来配置代理以定义的 [\<defaultProxy\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) 和 [\<proxy\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md) 元素。  
  
 使用选择了您的请求，的空 <xref:System.Net.WebRequest.Proxy%2A> 如下面的代码示例所示，对于您创建的请求，您可以在请求下禁用自动代理检测级别，。  
  
```csharp  
public static void DisableForMyRequest (Uri resource)  
{  
    WebRequest request = WebRequest.Create (resource);  
    request.Proxy = null;  
    WebResponse response = request.GetResponse ();  
}  
```  
  
```vb  
Public Shared Sub DisableForMyRequest(ByVal resource As Uri)  
    Dim request As WebRequest = WebRequest.Create(resource)  
    request.Proxy = Nothing  
    Dim response As WebResponse = request.GetResponse()  
    End Sub   
```  
  
 请求没有代理使用应用程序域的默认代理，可在 <xref:System.Net.WebRequest.DefaultWebProxy%2A> 属性。  
  
## 请参阅  
 <xref:System.Net.WebProxy>   
 <xref:System.Net.WebRequest>   
 [\<system.Net\> 元素（网络设置）](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)