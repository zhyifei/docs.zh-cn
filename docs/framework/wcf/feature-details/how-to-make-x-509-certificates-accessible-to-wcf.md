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
ms.openlocfilehash: abd074701ca667abe4590f4f17a044b34325e874
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837397"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a>如何：使 X.509 证书可由 WCF 访问
To make an X.509 certificate accessible to Windows Communication Foundation (WCF), application code must specify the certificate store name and location. 在某些情况下，进程标识必须具有对包含私钥的文件的访问权限，此私钥与 X.509 证书相关联。 To obtain the private key associated with an X.509 certificate in a certificate store, WCF must have permission to do so. 默认情况下，只有所有者和“系统”帐户才可以访问证书的私钥。  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a>使 X.509 证书可由 WCF 访问  
  
1. Give the account under which WCF is running read access to the file that contains the private key associated with the X.509 certificate.  
  
    1. Determine whether WCF requires read access to the private key for the X.509 certificate.  
  
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
  
    3. Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool.  
  
         The [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate. 此工具接受将证书的主题名称或其指纹作为唯一标识符。 For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
         The following code example uses the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.  
  
        ```console
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4. Determine the account that WCF is running under.  
  
         The following table details the account under which WCF is running for a given scenario.  
  
        |方案|进程标识|  
        |--------------|----------------------|  
        |客户端（控制台或 WinForms 应用程序）。|当前登录的用户。|  
        |自承载服务。|当前登录的用户。|  
        |Service that is hosted in IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) or IIS 7.0 (Windows Vista).|NETWORK SERVICE|  
        |在 IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]) 中承载的服务。|由 Machine.config 文件中的 `<processModel>` 元素控制。 默认帐户为 ASPNET。|  
  
    5. Grant read access to the file that contains the private key to the account that WCF is running under, using a tool such as icacls.exe.  
  
         The following code example edits the discretionary access control list (DACL) for the specified file to grant the NETWORK SERVICE account read (:R) access to the file.  
  
        ```console 
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a>另请参阅

- [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)
- [如何：检索证书的指纹](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [使用证书](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
