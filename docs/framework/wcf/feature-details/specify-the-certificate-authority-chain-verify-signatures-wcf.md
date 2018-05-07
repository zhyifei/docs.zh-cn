---
title: 如何：指定用于验证签名的证书颁发机构证书链 (WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
ms.openlocfilehash: 14f7691046f9512e25006bd6cd02749eed825003
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a>如何：指定用于验证签名的证书颁发机构证书链 (WCF)
当 Windows Communication Foundation (WCF) 收到使用 X.509 证书签名的 SOAP 消息时，默认情况下它验证，由受信任的证书颁发机构颁发的 X.509 证书。 通过搜索证书存储区并确定是否已将该证书颁发机构的证书指定为受信任的证书，可以做到这一点。 为了使 WCF 来做出此判断，必须在正确的证书存储中安装证书颁发机构证书链。  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a>安装证书颁发机构证书链  
  
-   对于每个 SOAP 消息接收方打算信任的证书颁发机构从，发放的 X.509 证书将证书颁发机构证书链安装到 WCF 配置为从中检索 X.509 证书的证书存储中。  
  
     例如，如果 SOAP 消息接收方打算信任由 Microsoft 颁发的 X.509 证书，必须 WCF 设置以寻找 X.509 证书的证书存储中安装 Microsoft 证书颁发机构证书链。 可以在代码或配置中指定 WCF 寻找 X.509 证书的证书存储区。 例如，这可以指定在代码中使用<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>方法或在配置几种方法，包括[ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) 。  
  
     因为 Windows 附带有一组默认的用于受信任证书颁发机构的证书链，所以可能不必为所有证书颁发机构安装证书链。  
  
    1.  导出证书颁发机构证书链。  
  
         具体导出方式取决于证书颁发机构。 如果证书颁发机构正在运行 Microsoft 证书服务，选择**下载 CA 证书、 证书链或 CRL**，然后选择**下载 CA 证书**。  
  
    2.  导入证书颁发机构证书链。  
  
         在 Microsoft 管理控制台 (MMC) 中，打开证书管理单元。 用于证书存储该 WCF 配置为从选择中检索 X.509 证书**受信任的根****证书颁发机构**文件夹。 下**受信任根证书颁发机构**文件夹中，右键单击**证书**文件夹，指向**所有任务**，然后单击**导入**. 提供在步骤 a 中导出的文件。  
  
         有关 MMC 证书管理单元中使用的信息的详细信息，请参阅[如何： 使用 mmc 管理单元查看证书](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用证书](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
