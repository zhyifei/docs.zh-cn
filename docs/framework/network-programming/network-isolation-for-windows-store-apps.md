---
title: "Windows 应用商店应用的网络隔离 | Microsoft Docs"
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
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
caps.latest.revision: 7
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 7
---
# Windows 应用商店应用的网络隔离
在 <xref:System.Net>、 <xref:System.Net.Http>和 <xref:System.Net.Http.Headers> 命名空间的选件类可用于开发Windows存储app或桌面应用程序。  当在Windows存储app，这些命名空间中的类选件受到网络隔离的一部分，应用程序安全模型影响的由 [!INCLUDE[win8](../../../includes/win8-md.md)]改用。  在必须启用相应的网络功能应用单元列表该系统上的Windows存储app的可以允许网络访问。  
  
## 网络隔离的检查表  
 使用此检查表确定网络隔离为您的Windows存储app配置。  
  
1.  确定应用程序需要的网络访问请求的方向。  它可以是或出站客户端启动的请求或入站未请求的请求也可以是这两个web请求类型的组合。  
  
2.  确定的网络资源的类型该应用程序将通信。  app可能需要在家信任的资源通信或工作网络。  app可能需要在Internet的资源进行通信。  app可能需要访问网络资源的两个类型访问。  
  
3.  配置中最少量必需的网络隔离功能应用单元列表。  
  
4.  部署并运行您的应用程序中测试它用于解决问题提供的网络隔离工具。  
  
 有关如何配置网络用于解决问题的网络隔离功能和隔离工具的更多信息，请参见 [如何配置网络隔离功能](http://go.microsoft.com/fwlink/?LinkID=228265) 。 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 开发人员文档。  
  
## 请参阅  
 [连接到web服务](http://go.microsoft.com/fwlink/?LinkID=245696)   
 [准则和检查表网络隔离的](http://go.microsoft.com/fwlink/?LinkID=228265)   
 [快速入门:连接使用HttpClient](http://go.microsoft.com/fwlink/?LinkId=245697)   
 [如何使用HttpClient处理程序](http://go.microsoft.com/fwlink/?LinkId=245699)   
 [如何保护HttpClient连接](http://go.microsoft.com/fwlink/?LinkId=245698)   
 [HttpClient示例](http://go.microsoft.com/fwlink/?LinkId=242550)