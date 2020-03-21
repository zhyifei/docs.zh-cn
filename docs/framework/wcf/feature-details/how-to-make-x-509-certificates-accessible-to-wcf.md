---
title: 如何：使 X.509 证书可由 WCF 访问
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
ms.openlocfilehash: 14f2242ab55795c74fa169382fef846bc0e60ace
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184898"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a>如何：使 X.509 证书可由 WCF 访问
要使 X.509 证书可供 Windows 通信基础 （WCF） 访问，应用程序代码必须指定证书存储名称和位置。 在某些情况下，进程标识必须具有对包含私钥的文件的访问权限，此私钥与 X.509 证书相关联。 要获取证书存储中与 X.509 证书关联的私钥，WCF 必须具有执行此操作的权限。 默认情况下，只有所有者和“系统”帐户才可以访问证书的私钥。  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a>使 X.509 证书可由 WCF 访问  
  
1. 向 WCF 运行对包含与 X.509 证书关联的私钥的文件的读取访问权限的帐户。  
  
    1. 确定 WCF 是否需要对 X.509 证书的私钥进行读取访问。  
  
         下表详细描述在使用某个 X.509 证书时是否必须提供私钥。  
  
        |X.509 证书用途|私钥|  
        |---------------------------|-----------------|  
        |对出站 SOAP 消息进行数字签名。|是|  
        |验证入站 SOAP 消息的签名。|否|  
        |对出站 SOAP 消息进行加密。|否|  
        |对入站 SOAP 消息进行解密。|是|  
  
    2. 确定在其中存储证书的存储区的位置和名称。  
  
         在其中存储证书的证书存储区要么在应用程序代码中指定，要么在配置中指定。 例如，下面的示例指定证书位于名为 `CurrentUser` 的 `My` 证书存储区中。  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3. 使用[FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)工具确定证书的私钥位于计算机上的位置。  
  
         [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)工具需要证书存储名称、证书存储位置以及唯一标识证书的内容。 此工具接受将证书的主题名称或其指纹作为唯一标识符。 有关如何确定证书的指纹的详细信息，请参阅[如何：检索证书的指纹](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)。  
  
         以下代码示例使用[FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)工具确定`My``CurrentUser`存储中的证书的私钥的位置，并带有 的`46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`指纹。  
  
        ```console
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4. 确定 WCF 正在运行的帐户。  
  
         下表详细介绍了为给定方案运行 WCF 的帐户。  
  
        |场景|进程标识|  
        |--------------|----------------------|  
        |客户端（控制台或 WinForms 应用程序）。|当前登录的用户。|  
        |自承载服务。|当前登录的用户。|  
        |托管在 IIS 6.0（Windows 服务器 2003）或 IIS 7.0（Windows Vista）中的服务。|网络服务|  
        |在 IIS 5.X （Windows XP） 中托管的服务。|由 Machine.config 文件中的 `<processModel>` 元素控制。 默认帐户为 ASPNET。|  
  
    5. 使用 icacls.exe 等工具授予对包含 WCF 运行帐户的私钥的文件的读取访问权限。  
  
         以下代码示例编辑指定文件的可自由访问控制列表 （DACL）， 以授予网络服务帐户对该文件的读取 （：R） 访问权限。  
  
        ```console
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a>另请参阅

- [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)
- [如何：检索证书的指纹](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [使用证书](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
