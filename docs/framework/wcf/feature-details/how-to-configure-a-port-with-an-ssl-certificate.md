---
title: 如何：使用 SSL 证书配置端口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: 90d5424e12bb770dc3da85e1b2738206f4777c0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185112"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a>如何：使用 SSL 证书配置端口

使用使用传输安全性<xref:System.ServiceModel.WSHttpBinding>的类创建自托管的 Windows 通信基础 （WCF） 服务时，还必须配置具有 X.509 证书的端口。 如果不是在创建自承载服务，可以在 Internet 信息服务 (IIS) 上承载服务。 有关详细信息，请参阅[HTTP 传输安全](../../../../docs/framework/wcf/feature-details/http-transport-security.md)。  
  
 若要配置端口，使用的工具取决于计算机运行的操作系统。  
  
 如果您正在运行 Windows Server 2003，请使用 HttpCfg.exe 工具。 在 Windows 服务器 2003 上，将安装此工具。 有关详细信息，请参阅[Httpcfg 概述](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10))。 [Windows 支持工具文档](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10))解释了 Httpcfg.exe 工具的语法。  
  
 如果您正在运行 Windows Vista，请使用已安装的 Netsh.exe 工具。
  
> [!NOTE]
> 修改存储在计算机上的证书需要管理权限。  
  
## <a name="determine-how-ports-are-configured"></a>确定端口的配置方式  
  
1. 在 Windows 服务器 2003 或 Windows XP 中，使用 HttpCfg.exe 工具使用**查询**和**ssl**开关查看当前端口配置，如以下示例所示。  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. 在 Windows Vista 中，使用 Netsh.exe 工具查看当前端口配置，如以下示例所示。  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a>获取证书的指纹  
  
1. 使用证书 MMC 管理单元查找用于客户端身份验证的 X.509 证书。 有关详细信息，请参阅[如何：使用 MMC 管理单元查看证书](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)。  
  
2. 访问证书的指纹。 有关详细信息，请参阅[如何：检索证书的指纹](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)。  
  
3. 将证书指纹复制到文本编辑器，如 Notepad。  
  
4. 移除十六进制字符之间的所有空格。 完成此操作的一种方法是使用文本编辑器的“查找和替换”功能，将每个空格替换为空字符。  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a>将 SSL 证书绑定到端口号  
  
1. 在 Windows 服务器 2003 或 Windows XP 中，在安全套接字层 （SSL） 存储的"设置"模式下使用 HttpCfg.exe 工具将证书绑定到端口号。 该工具使用指纹识别证书，如下面的示例所示。  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - **-i**开关的语法为`IP`：`port`并指示工具将证书设置为计算机的端口 8012。 另外，也可将端口号前面的四个零替换为计算机的实际 IP 地址。  
  
    - **-h**开关指定证书的指纹。  
  
2. 在 Windows Vista 中，请使用 Netsh.exe 工具，如以下示例所示。  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}
    ```  
  
    - **证书**参数指定证书的指纹。  
  
    - **ipport**参数指定 IP 地址和端口，其功能与描述的 Httpcfg.exe 工具的 **-i**开关类似。  
  
    - **appid**参数是一个 GUID，可用于标识所属应用程序。  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a>将 SSL 证书绑定到端口号并支持客户端证书  
  
1. 在 Windows Server 2003 或 Windows XP 中，为了支持在传输层使用 X.509 证书进行身份验证的客户端，请按照上述过程操作，但将附加命令行参数传递给 HttpCfg.exe，如以下示例所示。  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     **-f**开关的语法`n`是 n 是介于 1 和 7 之间的数字。 值为 2 可在传输层启用客户端证书，如上面的示例所示。 值为 3 可启用客户端证书并将这些证书映射至 Windows 帐户。 请参见“HttpCfg.exe 帮助”以获取其他值的行为。  
  
2. 在 Windows Vista 中，为了支持在传输层使用 X.509 证书进行身份验证的客户端，请遵循前面的过程，但使用附加参数，如以下示例所示。  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a>从端口号中删除 SSL 证书  
  
1. 使用 HttpCfg.exe 或 Netsh.exe 工具查看计算机上的端口和所有绑定的指纹。 要将信息打印到磁盘，请使用重定向字符">"，如以下示例所示。  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. 在 Windows 服务器 2003 或 Windows XP 中，使用 HttpCfg.exe 工具**删除和****ssl**关键字。 使用 **-i**开关指定`IP`：`port`编号和 **-h**开关来指定指纹。  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. 在 Windows Vista 中，请使用 Netsh.exe 工具，如以下示例所示。  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a>示例  

 下面的代码演示如何使用 <xref:System.ServiceModel.WSHttpBinding> 类（设置为传输安全）创建自承载服务。 创建应用程序时，请指定地址中的端口号。  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a>另请参阅

- [HTTP 传输安全性](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
