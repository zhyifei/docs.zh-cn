---
title: "连接分组 | Microsoft Docs"
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
  - "Internet，连接"
  - "连接 [.NET Framework]，分组"
  - "WebRequest 类，连接分组"
  - "网络资源，连接"
  - "连接池"
ms.assetid: 2ec502e8-4ba0-4c22-9410-f28eaf4eee63
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# 连接分组
连接分组关联在单个应用程序内的特定请求对已定义的连接池。  这可以通过连接到后端服务器委托用户的中间层应用程序需要和使用支持委托，例如Kerberos，或被一中间层应用程序提供自己的凭据，在下面的示例中的身份验证协议。  例如，假设用户， Joe，访问显示他的工资表信息的内部网站。  在验证Joe后，中间层应用程序服务器使用Joe的凭据连接到后端服务器检索他的工资表信息。  接下来，苏珊访问站点请求和她的工资表信息。  使用Joe的凭据，由于中间层应用程序已经连接，后端服务器回答" Joe的信息。  但是，因此，如果应用程序将每个请求发送到后端服务器到生成的连接组从用户名，然后每个用户属于一个单独的连接池，并且不能与另一个用户无意中共享身份验证信息。  
  
 若要分配请求到特定连接组，您必须分配名称。您的 <xref:System.Net.WebRequest><xref:System.Net.WebRequest.ConnectionGroupName%2A> 属性在提交请求之前。  
  
## 请参阅  
 [管理连接](../../../docs/framework/network-programming/managing-connections.md)   
 [如何：将用户信息分配给组连接](../../../docs/framework/network-programming/how-to-assign-user-information-to-group-connections.md)