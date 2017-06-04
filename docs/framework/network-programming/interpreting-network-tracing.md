---
title: "解释网络跟踪 | Microsoft Docs"
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
  - "TraceMode 特性"
  - "十六进制数据，网络跟踪输出"
  - "网络跟踪，分析"
  - "protocolonly"
  - "文本，网络跟踪输出"
  - "includehex"
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 解释网络跟踪
当网络启用跟踪时，您可以使用来获取的跟踪调用您的应用程序会写入各 <xref:System.Net> 选件类成员。  从这些输出的调用可能类似于以下示例。  
  
```  
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61  
```  
  
 在前面的示例中， \[588\]是当前线程的唯一标识符。  \(4357\)和\(4387\)是表示经过的毫秒数时间戳，则应用程序启动。  按照时间戳的数据显示输入并退出方法 **Socket.Send**的应用程序。  执行 **发送** 方法的对象具有33574638作为其唯一标识符。  方法退出跟踪包括返回值\(61在前面的示例中\)。  
  
 网络跟踪可能会发送或您的应用程序接收使用应用程序级别协议\(如超文本传输协议\(ftp\)进行网络通信\(HTTP\)。  此数据，可以选择性地，捕获作为文本，并十六进制数据。  ，在指定 **includehex** 作为 **tracemode** 属性的值时，十六进制数据可用。  \(有关此属性的详细信息，请参见 [如何:配置网络跟踪](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)。\)使用 **includehex**，下面的示例跟踪生成。  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 要忽略的十六进制数据，请指定 **protocolonly** 作为值为 **tracemode** 属性。  ，当 **protocolonly** 指定时，下面的示例演示跟踪。  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## 请参阅  
 [启用网络跟踪](../../../docs/framework/network-programming/enabling-network-tracing.md)   
 [如何:配置网络跟踪](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)   
 [.NET Framework 中的网络跟踪](../../../docs/framework/network-programming/network-tracing.md)