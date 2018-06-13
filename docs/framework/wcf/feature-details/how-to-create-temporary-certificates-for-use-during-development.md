---
title: 如何：创建开发期间使用的临时证书
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: 8310e7c465d0e3494482b6a38a7b2a67b67ae842
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495361"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="b73d1-102">如何：创建开发期间使用的临时证书</span><span class="sxs-lookup"><span data-stu-id="b73d1-102">How to: Create Temporary Certificates for Use During Development</span></span>
<span data-ttu-id="b73d1-103">时开发安全服务或使用 Windows Communication Foundation (WCF) 客户端，它通常是需要提供 X.509 证书以用作凭据。</span><span class="sxs-lookup"><span data-stu-id="b73d1-103">When developing a secure service or client using Windows Communication Foundation (WCF), it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="b73d1-104">该证书通常是证书链的一部分，在计算机的受信任的根证书颁发机构存储区中可找到根证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="b73d1-104">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="b73d1-105">拥有一个证书链，使您可以限定一组证书，其中根证书颁发机构通常来自于您的组织或业务单元。</span><span class="sxs-lookup"><span data-stu-id="b73d1-105">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="b73d1-106">若要在开发时模拟此情况，请创建两个证书以满足安全要求。</span><span class="sxs-lookup"><span data-stu-id="b73d1-106">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="b73d1-107">第一个证书是自签名证书，放置在受信任的根证书颁发机构存储区中；第二个证书是从第一个证书创建的，放置在本地计算机位置的个人存储区中或当前用户位置的个人存储区中。</span><span class="sxs-lookup"><span data-stu-id="b73d1-107">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="b73d1-108">本主题指导你逐步完成使用 [证书创建工具 (MakeCert.exe)](http://go.microsoft.com/fwlink/?LinkId=248185)创建这两个证书的步骤，该工具由 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK 提供。</span><span class="sxs-lookup"><span data-stu-id="b73d1-108">This topic walks through the steps to create these two certificates using the [Certificate Creation Tool (MakeCert.exe)](http://go.microsoft.com/fwlink/?LinkId=248185), which is provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b73d1-109">证书创建工具生成的证书仅供测试使用。</span><span class="sxs-lookup"><span data-stu-id="b73d1-109">The certificates the Certification Creation tool generates are provided for testing purposes only.</span></span> <span data-ttu-id="b73d1-110">部署服务或客户程序时，请确保使用证书颁发机构提供的适当证书。</span><span class="sxs-lookup"><span data-stu-id="b73d1-110">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="b73d1-111">这可能是来自于组织或第三方的 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 证书服务器。</span><span class="sxs-lookup"><span data-stu-id="b73d1-111">This could either be from a [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] certificate server in your organization or a third party.</span></span>  
>   
>  <span data-ttu-id="b73d1-112">默认情况下， [Makecert.exe （证书创建工具）](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d)创建的证书的根证书颁发机构称为"根证书代理 **。"**</span><span class="sxs-lookup"><span data-stu-id="b73d1-112">By default, the [Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) creates certificates whose root authority is called "Root Agency **."**</span></span> <span data-ttu-id="b73d1-113">的证书。由于“根证书代理”不是受信任的根证书颁发机构存储区，这会使这些证书不安全。</span><span class="sxs-lookup"><span data-stu-id="b73d1-113">Because the "Root Agency" is not in the Trusted Root Certification Authorities store, this makes these certificates insecure.</span></span> <span data-ttu-id="b73d1-114">创建一个放置在受信任的根证书颁发机构存储区的自签名证书，您可以创建一个与您的部署环境极其类似的开发环境。</span><span class="sxs-lookup"><span data-stu-id="b73d1-114">Creating a self-signed certificate that is placed in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>  
  
 <span data-ttu-id="b73d1-115">有关创建和使用证书的详细信息，请参阅[使用证书](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="b73d1-115">For more information about creating and using certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="b73d1-116">有关使用证书作为凭据的详细信息，请参阅[保护服务和客户端](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="b73d1-116">For more information about using a certificate as a credential, see [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="b73d1-117">有关使用 Microsoft Authenticode 技术的教程，请参阅 [Authenticode Overviews and Tutorials](http://go.microsoft.com/fwlink/?LinkId=88919)（Authenticode 概述和教程）。</span><span class="sxs-lookup"><span data-stu-id="b73d1-117">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](http://go.microsoft.com/fwlink/?LinkId=88919).</span></span>  
  
### <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="b73d1-118">创建一个自签名根证书颁发机构证书并导出私钥</span><span class="sxs-lookup"><span data-stu-id="b73d1-118">To create a self-signed root authority certificate and export the private key</span></span>  
  
1.  <span data-ttu-id="b73d1-119">使用 MakeCert.exe 工具和以下开关：</span><span class="sxs-lookup"><span data-stu-id="b73d1-119">Use the MakeCert.exe tool with the following switches:</span></span>  
  
    1.  <span data-ttu-id="b73d1-120">`-n` `subjectName`。</span><span class="sxs-lookup"><span data-stu-id="b73d1-120">`-n` `subjectName`.</span></span> <span data-ttu-id="b73d1-121">指定主题名称。</span><span class="sxs-lookup"><span data-stu-id="b73d1-121">Specifies the subject name.</span></span> <span data-ttu-id="b73d1-122">约定是为主题名的“公用名”添加前缀“CN = ”。</span><span class="sxs-lookup"><span data-stu-id="b73d1-122">The convention is to prefix the subject name with "CN = " for "Common Name".</span></span>  
  
    2.  <span data-ttu-id="b73d1-123">`-r`。</span><span class="sxs-lookup"><span data-stu-id="b73d1-123">`-r`.</span></span> <span data-ttu-id="b73d1-124">指定证书将自签名。</span><span class="sxs-lookup"><span data-stu-id="b73d1-124">Specifies that the certificate will be self-signed.</span></span>  
  
    3.  <span data-ttu-id="b73d1-125">`-sv` `privateKeyFile`。</span><span class="sxs-lookup"><span data-stu-id="b73d1-125">`-sv` `privateKeyFile`.</span></span> <span data-ttu-id="b73d1-126">指定包含私钥容器的文件。</span><span class="sxs-lookup"><span data-stu-id="b73d1-126">Specifies the file that contains the private key container.</span></span>  
  
     <span data-ttu-id="b73d1-127">例如，下面的命令创建一个主题名称为“CN=TempCA”的自签名证书。</span><span class="sxs-lookup"><span data-stu-id="b73d1-127">For example, the following command creates a self-signed certificate with a subject name of "CN=TempCA."</span></span>  
  
    ```  
    makecert -n "CN=TempCA" -r -sv TempCA.pvk TempCA.cer  
    ```  
  
     <span data-ttu-id="b73d1-128">系统将提示您提供一个密码以保护私钥。</span><span class="sxs-lookup"><span data-stu-id="b73d1-128">You will be prompted to provide a password to protect the private key.</span></span> <span data-ttu-id="b73d1-129">在创建由此根证书签名的证书时需要此密码。</span><span class="sxs-lookup"><span data-stu-id="b73d1-129">This password is required when creating a certificate signed by this root certificate.</span></span>  
  
### <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="b73d1-130">创建一个由根证书颁发机构证书签名的新证书</span><span class="sxs-lookup"><span data-stu-id="b73d1-130">To create a new certificate signed by a root authority certificate</span></span>  
  
1.  <span data-ttu-id="b73d1-131">使用 MakeCert.exe 工具和以下开关：</span><span class="sxs-lookup"><span data-stu-id="b73d1-131">Use the MakeCert.exe tool with the following switches:</span></span>  
  
    1.  <span data-ttu-id="b73d1-132">`-sk` `subjectKey`。</span><span class="sxs-lookup"><span data-stu-id="b73d1-132">`-sk` `subjectKey`.</span></span> <span data-ttu-id="b73d1-133">保存私钥的主题密钥容器的位置。</span><span class="sxs-lookup"><span data-stu-id="b73d1-133">The location of the subject's key container that holds the private key.</span></span> <span data-ttu-id="b73d1-134">如果密钥容器不存在，则将创建一个。</span><span class="sxs-lookup"><span data-stu-id="b73d1-134">If a key container does not exist, one is created.</span></span> <span data-ttu-id="b73d1-135">如果既没有使用 -sk 选项，也没有使用 -sv 选项，则默认创建名为 JoeSoft 的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="b73d1-135">If neither of the -sk or -sv options is used, a key container called JoeSoft is created by default.</span></span>  
  
    2.  <span data-ttu-id="b73d1-136">`-n` `subjectName`。</span><span class="sxs-lookup"><span data-stu-id="b73d1-136">`-n` `subjectName`.</span></span> <span data-ttu-id="b73d1-137">指定主题名称。</span><span class="sxs-lookup"><span data-stu-id="b73d1-137">Specifies the subject name.</span></span> <span data-ttu-id="b73d1-138">约定是为主题名的“公用名”添加前缀“CN = ”。</span><span class="sxs-lookup"><span data-stu-id="b73d1-138">The convention is to prefix the subject name with "CN = " for "Common Name".</span></span>  
  
    3.  <span data-ttu-id="b73d1-139">`-iv` `issuerKeyFile`。</span><span class="sxs-lookup"><span data-stu-id="b73d1-139">`-iv` `issuerKeyFile`.</span></span> <span data-ttu-id="b73d1-140">指定颁发者的私钥文件。</span><span class="sxs-lookup"><span data-stu-id="b73d1-140">Specifies the issuer's private key file.</span></span>  
  
    4.  <span data-ttu-id="b73d1-141">`-ic` `issuerCertFile`。</span><span class="sxs-lookup"><span data-stu-id="b73d1-141">`-ic` `issuerCertFile`.</span></span> <span data-ttu-id="b73d1-142">指定颁发者的证书位置。</span><span class="sxs-lookup"><span data-stu-id="b73d1-142">Specifies the location of the issuer's certificate.</span></span>  
  
     <span data-ttu-id="b73d1-143">例如，下面的命令使用颁发者的私钥创建一个由 `TempCA` 根证书颁发机构证书签名的证书，其主题名称为 `"CN=SignedByCA"` 。</span><span class="sxs-lookup"><span data-stu-id="b73d1-143">For example, the following command creates a certificate signed by the `TempCA` root authority certificate with a subject name of `"CN=SignedByCA"` using the private key of the issuer.</span></span>  
  
    ```  
    makecert -sk SignedByCA -iv TempCA.pvk -n "CN=SignedByCA" -ic TempCA.cer SignedByCA.cer -sr currentuser -ss My  
    ```  
  
## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="b73d1-144">在受信任的根证书颁发机构存储区中安装证书</span><span class="sxs-lookup"><span data-stu-id="b73d1-144">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>  
 <span data-ttu-id="b73d1-145">创建自签名证书后，您可以将它安装到受信任的根证书颁发机构存储区中。</span><span class="sxs-lookup"><span data-stu-id="b73d1-145">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="b73d1-146">任何使用该证书签名的证书在此处都受计算机的信任。</span><span class="sxs-lookup"><span data-stu-id="b73d1-146">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="b73d1-147">为此，当您不再需要该证书时可立即将它从存储区中删除。</span><span class="sxs-lookup"><span data-stu-id="b73d1-147">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="b73d1-148">当您删除此根证书颁发机构证书时，则由它签名的所有其他证书将成为未经授权的。</span><span class="sxs-lookup"><span data-stu-id="b73d1-148">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="b73d1-149">根证书颁发机构证书只是一种机制，必要时可限定一组证书。</span><span class="sxs-lookup"><span data-stu-id="b73d1-149">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="b73d1-150">例如，在对等应用程序中，通常不需要根证书颁发机构，因为您只信任由对方提供的证书的个体标识。</span><span class="sxs-lookup"><span data-stu-id="b73d1-150">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>  
  
#### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="b73d1-151">在受信任的根证书颁发机构中安装自签名证书</span><span class="sxs-lookup"><span data-stu-id="b73d1-151">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>  
  
1.  <span data-ttu-id="b73d1-152">打开证书管理单元。</span><span class="sxs-lookup"><span data-stu-id="b73d1-152">Open the certificate snap-in.</span></span> <span data-ttu-id="b73d1-153">有关详细信息，请参阅[如何： 使用 mmc 管理单元查看证书](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)。</span><span class="sxs-lookup"><span data-stu-id="b73d1-153">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2.  <span data-ttu-id="b73d1-154">打开要存储证书的文件夹， **“本地计算机”** 或 **“当前用户”**。</span><span class="sxs-lookup"><span data-stu-id="b73d1-154">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>  
  
3.  <span data-ttu-id="b73d1-155">打开 **“受信任的根证书颁发机构”** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b73d1-155">Open the **Trusted Root Certification Authorities** folder.</span></span>  
  
4.  <span data-ttu-id="b73d1-156">右击 **“证书”** 文件夹，再单击 **“所有任务”**，然后单击 **“导入”**。</span><span class="sxs-lookup"><span data-stu-id="b73d1-156">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>  
  
5.  <span data-ttu-id="b73d1-157">按照屏幕向导说明，将 TempCa.cer 导入到存储区中。</span><span class="sxs-lookup"><span data-stu-id="b73d1-157">Follow the on-screen wizard instructions to import the TempCa.cer into the store.</span></span>  
  
## <a name="using-certificates-with-wcf"></a><span data-ttu-id="b73d1-158">在 WCF 中使用证书</span><span class="sxs-lookup"><span data-stu-id="b73d1-158">Using Certificates With WCF</span></span>  
 <span data-ttu-id="b73d1-159">一旦安装了临时证书，就可以使用这些证书开发指定证书作为客户端凭据类型的 WCF 解决方案。</span><span class="sxs-lookup"><span data-stu-id="b73d1-159">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="b73d1-160">例如，下面的 XML 配置指定消息安全模式，并指定证书作为客户端凭据类型。</span><span class="sxs-lookup"><span data-stu-id="b73d1-160">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>  
  
#### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="b73d1-161">指定证书作为客户端凭据类型</span><span class="sxs-lookup"><span data-stu-id="b73d1-161">To specify a certificate as the client credential type</span></span>  
  
-   <span data-ttu-id="b73d1-162">在服务的配置文件中，使用下面的 XML 将安全模式设置为消息，并将客户端凭据类型设置为证书。</span><span class="sxs-lookup"><span data-stu-id="b73d1-162">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>  
  
    ```xml  
    <bindings>       
      <wsHttpBinding>  
        <binding name="CertificateForClient">  
          <security>  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
 <span data-ttu-id="b73d1-163">在客户端的配置文件，使用下面的 XML 指定证书在用户的存储中找到，并且可以通过搜索"CohoWinery。"的值在 SubjectName 字段中找到</span><span class="sxs-lookup"><span data-stu-id="b73d1-163">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>  
  
```xml  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="CertForClient">  
      <clientCredentials>  
        <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />  
       </clientCredentials>  
     </behavior>  
   </endpointBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="b73d1-164">有关在 WCF 中使用证书的详细信息，请参阅 [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="b73d1-164">For more information about using certificates in WCF, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b73d1-165">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="b73d1-165">.NET Framework Security</span></span>  
 <span data-ttu-id="b73d1-166">请确保通过右击证书，再单击 **“删除”** ，从 **“受信任的根证书颁发机构”** 和 **“个人”** 文件夹中删除所有临时根证书颁发机构证书。</span><span class="sxs-lookup"><span data-stu-id="b73d1-166">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b73d1-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="b73d1-167">See Also</span></span>  
 [<span data-ttu-id="b73d1-168">使用证书</span><span class="sxs-lookup"><span data-stu-id="b73d1-168">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="b73d1-169">如何：使用 MMC 管理单元查看证书</span><span class="sxs-lookup"><span data-stu-id="b73d1-169">How to: View Certificates with the MMC Snap-in</span></span>](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [<span data-ttu-id="b73d1-170">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="b73d1-170">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
