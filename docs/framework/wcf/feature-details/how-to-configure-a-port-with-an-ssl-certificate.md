---
title: "如何：使用 SSL 证书配置端口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c67ed21a8e4a9170d72ce842505e7695b11c26c9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a>如何：使用 SSL 证书配置端口
使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 类（使用传输安全）创建自承载 <xref:System.ServiceModel.WSHttpBinding> 服务时，还必须使用 X.509 证书配置端口。 如果不是在创建自承载服务，可以在 Internet 信息服务 (IIS) 上承载服务。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][HTTP 传输安全](../../../../docs/framework/wcf/feature-details/http-transport-security.md)。  
  
 若要配置端口，使用的工具取决于计算机运行的操作系统。  
  
 如果运行的是 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 或 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]，则使用 HttpCfg.exe 工具。 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 中已安装该工具。 与[!INCLUDE[wxp](../../../../includes/wxp-md.md)]，您可以下载该工具在[Windows XP Service Pack 2 支持工具](http://go.microsoft.com/fwlink/?LinkId=88606)。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Httpcfg 概述](http://go.microsoft.com/fwlink/?LinkId=88605)。 [Windows 支持工具文档](http://go.microsoft.com/fwlink/?LinkId=94840)说明了 Httpcfg.exe 工具的语法。  
  
 如果运行的是 [!INCLUDE[wv](../../../../includes/wv-md.md)]，则使用已安装的 Netsh.exe 工具。  
  
 本主题介绍如何完成以下一些过程：  
  
-   确定计算机当前的端口配置。  
  
-   获取证书的指纹（以下两个过程需要证书指纹）。  
  
-   将 SSL 证书绑定到端口配置。  
  
-   将 SSL 证书绑定到端口配置并支持客户端证书。  
  
-   从某个端口号删除 SSL 证书。  
  
 请注意，修改存储于计算机上的证书需要管理特权。  
  
### <a name="to-determine-how-ports-are-configured"></a>确定如何配置端口  
  
1.  在[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]或[!INCLUDE[wxp](../../../../includes/wxp-md.md)]，使用 HttpCfg.exe 工具查看当前端口配置，使用**查询**和**ssl**切换，如下面的示例中所示。  
  
    ```  
    httpcfg query ssl  
    ```  
  
2.  在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 中，使用 Netsh.exe 工具查看当前端口配置，如下面的示例所示。  
  
    ```  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a>获取证书的指纹  
  
1.  使用证书 MMC 管理单元查找用于客户端身份验证的 X.509 证书。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][如何： 使用 mmc 管理单元查看证书](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)。  
  
2.  访问证书的指纹。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][如何： 检索证书的指纹](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)。  
  
3.  将证书指纹复制到文本编辑器，如 Notepad。  
  
4.  移除十六进制字符之间的所有空格。 完成此操作的一种方法是使用文本编辑器的“查找和替换”功能，将每个空格替换为空字符。  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a>将 SSL 证书绑定至端口号  
  
1.  在 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 或 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 中，对安全套接字层 (SSL) 存储区使用 HttpCfg.exe 工具的“set”命令将证书绑定至端口号。 该工具使用指纹识别证书，如下面的示例所示。  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    -   **-I**交换机具有的语法`IP`:`port`并指示该工具将证书设置到的计算机的端口 8012。 另外，也可将端口号前面的四个零替换为计算机的实际 IP 地址。  
  
    -   **-H**开关指定证书的指纹。  
  
2.  在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 中使用 Netsh.exe 工具，如下面的示例所示。  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    -   **Certhash**参数指定证书的指纹。  
  
    -   **Ipport**参数指定的 IP 地址和端口，并就像函数**-i**于前述 Httpcfg.exe 工具的开关。  
  
    -   **Appid**参数是一个 GUID，用于标识所属应用程序。  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a>将 SSL 证书绑定至端口号并支持客户端证书  
  
1.  在 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 或 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 中，若要支持在传输层使用 X.509 证书进行身份验证的客户端，请按照前面的步骤进行操作，但要向 HttpCfg.exe 另外传递一个命令行参数，如下面的示例所示。  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     **-F**交换机具有的语法`n`其中 n 是介于 1 和 7 之间的数字。 值为 2 可在传输层启用客户端证书，如上面的示例所示。 值为 3 可启用客户端证书并将这些证书映射至 Windows 帐户。 请参见“HttpCfg.exe 帮助”以获取其他值的行为。  
  
2.  在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 中，若要支持在传输层使用 X.509 证书进行身份验证的客户端，请按照前面的步骤进行操作，但要另外提供一个参数，如下面的示例所示。  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a>删除端口号的 SSL 证书  
  
1.  使用 HttpCfg.exe 或 Netsh.exe 工具查看计算机上的端口和所有绑定的指纹。 若要将信息输出到磁盘，请使用重定向字符“>”，如下面的示例所示。  
  
    ```  
    httpcfg query ssl>myMachinePorts.txt  
    ```  
  
2.  在[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]或[!INCLUDE[wxp](../../../../includes/wxp-md.md)]，使用 HttpCfg.exe 工具以及**删除**和**ssl**关键字。 使用**-i**开关指定`IP`:`port`数，和**-h**开关指定指纹。  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3.  在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 中使用 Netsh.exe 工具，如下面的示例所示。  
  
    ```  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a>示例  
 下面的代码演示如何使用 <xref:System.ServiceModel.WSHttpBinding> 类（设置为传输安全）创建自承载服务。 创建应用程序时，请指定地址中的端口号。  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a>另请参阅  
 [HTTP 传输安全](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
