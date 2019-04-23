---
title: 如何：指定用于验证签名 (WCF) 的证书颁发机构证书链
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
ms.openlocfilehash: 43296fad9519a08db5facdd220492ac70dffeca2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59224456"
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a><span data-ttu-id="d583e-102">如何：指定用于验证签名 (WCF) 的证书颁发机构证书链</span><span class="sxs-lookup"><span data-stu-id="d583e-102">How to: Specify the Certificate Authority Certificate Chain Used to Verify Signatures (WCF)</span></span>
<span data-ttu-id="d583e-103">当 Windows Communication Foundation (WCF) 收到使用 X.509 证书签名的 SOAP 消息时，默认情况下它将验证 X.509 证书已颁发由受信任的证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="d583e-103">When Windows Communication Foundation (WCF) receives a SOAP message signed using an X.509 certificate, by default it verifies that the X.509 certificate was issued by a trusted certification authority.</span></span> <span data-ttu-id="d583e-104">通过搜索证书存储区并确定是否已将该证书颁发机构的证书指定为受信任的证书，可以做到这一点。</span><span class="sxs-lookup"><span data-stu-id="d583e-104">This is done by looking in a certificate store and determining if the certificate for that certification authority has been designated as trusted.</span></span> <span data-ttu-id="d583e-105">为了使 WCF 能够做出此判断，必须在正确的证书存储区中安装证书颁发机构证书链。</span><span class="sxs-lookup"><span data-stu-id="d583e-105">In order for WCF to make this determination, the certification authority certificate chain must be installed in the correct certificate store.</span></span>  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a><span data-ttu-id="d583e-106">安装证书颁发机构证书链</span><span class="sxs-lookup"><span data-stu-id="d583e-106">To install a certification authority certificate chain</span></span>  
  
-   <span data-ttu-id="d583e-107">对于 SOAP 消息接收方打算信任其每个证书颁发机构，从颁发的 X.509 证书 WCF 配置为检索从 X.509 证书的证书存储中安装证书颁发机构证书链。</span><span class="sxs-lookup"><span data-stu-id="d583e-107">For each certification authority that a SOAP message recipient intends to trust X.509 certificates issued from, install the certification authority certificate chain into the certificate store that WCF is configured to retrieve X.509 certificates from.</span></span>  
  
     <span data-ttu-id="d583e-108">例如，如果 SOAP 消息接收方打算信任由 Microsoft 颁发的 X.509 证书，Microsoft 证书颁发机构证书链必须安装 WCF 设置以寻找 X.509 证书的证书存储中。</span><span class="sxs-lookup"><span data-stu-id="d583e-108">For instance, if a SOAP message recipient intends to trust X.509 certificates issued by Microsoft, the certification authority certificate chain for Microsoft must be installed in the certificate store that WCF is set up to look for X.509 certificates from.</span></span> <span data-ttu-id="d583e-109">可以在代码或配置中指定 WCF 寻找 X.509 证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="d583e-109">The certificate store in which WCF looks for X.509 certificates can be specified in code or configuration.</span></span> <span data-ttu-id="d583e-110">例如，可以在代码中使用指定此<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>方法或在配置中通过多种方式，包括[ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) 。</span><span class="sxs-lookup"><span data-stu-id="d583e-110">For example, this can be specified in code using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method or in configuration a few ways, including the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .</span></span>  
  
     <span data-ttu-id="d583e-111">因为 Windows 附带有一组默认的用于受信任证书颁发机构的证书链，所以可能不必为所有证书颁发机构安装证书链。</span><span class="sxs-lookup"><span data-stu-id="d583e-111">Because Windows ships with a set of default certificate chains for trusted certificate authorities, it may not be necessary to install the certificate chain for all certificate authorities.</span></span>  
  
    1.  <span data-ttu-id="d583e-112">导出证书颁发机构证书链。</span><span class="sxs-lookup"><span data-stu-id="d583e-112">Export the certification authority certificate chain.</span></span>  
  
         <span data-ttu-id="d583e-113">具体导出方式取决于证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="d583e-113">Exactly how this is done depends on the certification authority.</span></span> <span data-ttu-id="d583e-114">如果证书颁发机构正在运行 Microsoft 证书服务，选择**下载 CA 证书、 证书链或 CRL**，然后选择**下载 CA 证书**。</span><span class="sxs-lookup"><span data-stu-id="d583e-114">If the certification authority is running Microsoft Certificate Services, select **Download a CA certificate, certificate chain, or CRL**, and then choose **Download CA certificate**.</span></span>  
  
    2.  <span data-ttu-id="d583e-115">导入证书颁发机构证书链。</span><span class="sxs-lookup"><span data-stu-id="d583e-115">Import the certification authority certificate chain.</span></span>  
  
         <span data-ttu-id="d583e-116">在 Microsoft 管理控制台 (MMC) 中，打开证书管理单元。</span><span class="sxs-lookup"><span data-stu-id="d583e-116">In the Microsoft Management Console (MMC), open the Certificates snap-in.</span></span> <span data-ttu-id="d583e-117">证书存储区的 WCF 配置为从选择中检索 X.509 证书**受信任的根\*\*\*\*证书颁发机构**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d583e-117">For the certificate store that WCF is configured to retrieve X.509 certificates from, select the **Trusted Root** **Certification Authorities** folder.</span></span> <span data-ttu-id="d583e-118">下**受信任的根证书颁发机构**文件夹中，右键单击**证书**文件夹，指向**所有任务**，然后单击**导入**.</span><span class="sxs-lookup"><span data-stu-id="d583e-118">Under the **Trusted Root Certification Authorities** folder, right-click the **Certificates** folder, point to **All Tasks**, and then click **Import**.</span></span> <span data-ttu-id="d583e-119">提供在步骤 a 中导出的文件。</span><span class="sxs-lookup"><span data-stu-id="d583e-119">Provide the file exported in step a.</span></span>  
  
         <span data-ttu-id="d583e-120">有关使用 MMC 证书管理单元中使用的详细信息，请参阅[如何：使用 MMC 管理单元查看证书](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)。</span><span class="sxs-lookup"><span data-stu-id="d583e-120">For more information about using the Certificates snap-in with MMC, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d583e-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="d583e-121">See also</span></span>

- [<span data-ttu-id="d583e-122">使用证书</span><span class="sxs-lookup"><span data-stu-id="d583e-122">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
