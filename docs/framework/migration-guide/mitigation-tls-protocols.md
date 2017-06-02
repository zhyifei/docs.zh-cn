---
title: "缓解：TLS 协议 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1474aeb0e1be38018f9d27c49e8711800ecb9f01
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-tls-protocols"></a>缓解：TLS 协议
自 .NET Framework 4.6 起，<xref:System.Net.ServicePointManager?displayProperty=fullName> 和 <xref:System.Net.Security.SslStream?displayProperty=fullName> 类可以使用以下三种协议之一：Tls1.0、Tls1.1 或 Tls1.2。 不支持 SSL3.0 协议和 RC4 密码。  
  
## <a name="impact"></a>影响  
 此更改会影响：  
  
-   通过 SSL 使用以下任一类型与 HTTPS 服务器或套接字服务器进行通信的任何应用程序：<xref:System.Net.Http.HttpClient>、<xref:System.Net.HttpWebRequest>、<xref:System.Net.FtpWebRequest>、<xref:System.Net.Mail.SmtpClient> 和 <xref:System.Net.Security.SslStream>。  
  
-   不能升级以支持 Tls1.0、Tls1.1 或 Tls 1.2 的任意服务器端应用。  
  
## <a name="mitigation"></a>缓解操作  
 建议的缓解是将服务器端应用升级到 Tls1.0、Tls1.1 或 Tls 1.2。 如果这不可行或客户端应用程序损坏，可以使用 <xref:System.AppContext> 类通过以下两种方式之一来选择禁用此功能：  
  
-   以编程方式使用如下代码段：  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     由于 <xref:System.Net.ServicePointManager> 对象仅初始化一次，因此应用程序首先必须定义这些兼容性设置。  
  
-   在 app.config 文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加下面的代码行：  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 但请注意，不建议选择退出默认行为，因为这会导致应用程序不太安全。  
  
## <a name="see-also"></a>另请参阅  
 [重定目标更改](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
