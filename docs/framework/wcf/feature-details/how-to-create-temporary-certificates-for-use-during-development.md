---
title: 如何：创建开发期间使用的临时证书
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: d45f18b0b8fe4e0cc9667091e166c80691faa2d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773290"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="fc5a4-102">如何：创建开发期间使用的临时证书</span><span class="sxs-lookup"><span data-stu-id="fc5a4-102">How to: Create Temporary Certificates for Use During Development</span></span>

<span data-ttu-id="fc5a4-103">开发时的安全服务或使用 Windows Communication Foundation (WCF) 客户端，它通常是需要提供要用作凭据的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-103">When developing a secure service or client using Windows Communication Foundation (WCF), it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="fc5a4-104">该证书通常是证书链的一部分，在计算机的受信任的根证书颁发机构存储区中可找到根证书颁发机构。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-104">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="fc5a4-105">拥有一个证书链，使您可以限定一组证书，其中根证书颁发机构通常来自于您的组织或业务单元。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-105">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="fc5a4-106">若要在开发时模拟此情况，请创建两个证书以满足安全要求。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-106">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="fc5a4-107">第一个证书是自签名证书，放置在受信任的根证书颁发机构存储区中；第二个证书是从第一个证书创建的，放置在本地计算机位置的个人存储区中或当前用户位置的个人存储区中。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-107">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="fc5a4-108">本主题将指导完成创建使用 Powershell 这两个证书的步骤[New-selfsignedcertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-108">This topic walks through the steps to create these two certificates using the Powershell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fc5a4-109">仅用于测试目的提供 New-selfsignedcertificate cmdlet 生成的证书。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-109">The certificates that the New-SelfSignedCertificate cmdlet generates are provided for testing purposes only.</span></span> <span data-ttu-id="fc5a4-110">部署服务或客户程序时，请确保使用证书颁发机构提供的适当证书。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-110">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="fc5a4-111">这可能是从你的组织中的 Windows Server 证书服务器，或第三方。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-111">This could either be from a Windows Server certificate server in your organization or a third party.</span></span>
>
> <span data-ttu-id="fc5a4-112">默认情况下[New-selfsignedcertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet 创建的是自签名证书和这些证书将不安全。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-112">By default, the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet creates certificates that are self-signed and these certificates are insecure.</span></span> <span data-ttu-id="fc5a4-113">将自签名的证书放入受信任的根证书颁发机构存储区，可创建更紧密地模拟你的部署环境的开发环境。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-113">Placing the self-signed certificates in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>

 <span data-ttu-id="fc5a4-114">有关创建和使用证书的详细信息，请参阅[Working with Certificates](working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-114">For more information about creating and using certificates, see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="fc5a4-115">有关使用证书作为凭据的详细信息，请参阅[保护服务和客户端](securing-services-and-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-115">For more information about using a certificate as a credential, see [Securing Services and Clients](securing-services-and-clients.md).</span></span> <span data-ttu-id="fc5a4-116">有关使用 Microsoft Authenticode 技术的教程，请参阅 [Authenticode Overviews and Tutorials](https://go.microsoft.com/fwlink/?LinkId=88919)（Authenticode 概述和教程）。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-116">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](https://go.microsoft.com/fwlink/?LinkId=88919).</span></span>

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="fc5a4-117">创建一个自签名根证书颁发机构证书并导出私钥</span><span class="sxs-lookup"><span data-stu-id="fc5a4-117">To create a self-signed root authority certificate and export the private key</span></span>

<span data-ttu-id="fc5a4-118">以下命令创建一个自签名的证书的主题名称为"RootCA"当前用户个人存储区中。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-118">The following command creates a self-signed certificate with a subject name of "RootCA" in the Current User Personal store.</span></span>

```powershell
PS $rootCert = New-SelfSignedCertificate -CertStoreLocation cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("1.3.6.1.4.1.311.21.10={text}1.3.6.1.5.5.7.3.1,1.3.6.1.5.5.7.3.2")
```

<span data-ttu-id="fc5a4-119">我们需要将证书导出到 PFX 文件，以便可以导入到其中需要在后面的步骤。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-119">We need to export the certificate to a PFX file so that it can be imported to where it's needed in a later step.</span></span> <span data-ttu-id="fc5a4-120">时使用私钥导出的证书，需要密码以对其进行保护。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-120">When exporting a certificate with the private key, a password is needed to protect it.</span></span> <span data-ttu-id="fc5a4-121">我们将密码存入`SecureString`，并使用[Export-pfxcertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet 将证书导出到 PFX 文件关联的私钥。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-121">We save the password in a `SecureString` and use the [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet to export the certificate with the associated private key to a PFX file.</span></span> <span data-ttu-id="fc5a4-122">我们还将只需公共证书保存到 CRT 文件使用[导出证书](/powershell/module/pkiclient/export-certificate)cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-122">We also save just the public certificate into a CRT file using the [Export-Certificate](/powershell/module/pkiclient/export-certificate) cmdlet.</span></span>

```powershell
PS [System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
PS [String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
PS Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
PS Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="fc5a4-123">创建一个由根证书颁发机构证书签名的新证书</span><span class="sxs-lookup"><span data-stu-id="fc5a4-123">To create a new certificate signed by a root authority certificate</span></span>

<span data-ttu-id="fc5a4-124">以下命令将创建由签名的证书`RootCA`使用者名称为"SignedByRootCA"使用颁发者的私钥。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-124">The following command creates a certificate signed by the `RootCA` with a subject name of "SignedByRootCA" using the private key of the issuer.</span></span>

```powershell
PS $testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

<span data-ttu-id="fc5a4-125">同样，我们将保存的签名的证书使用私钥到 PFX 文件，并只是到 CRT 文件的公共密钥。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-125">Similarly, we save the signed certificate with private key into a PFX file and just the public key into a CRT file.</span></span>

```powershell
PS [String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
PS Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword
PS Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="fc5a4-126">在受信任的根证书颁发机构存储区中安装证书</span><span class="sxs-lookup"><span data-stu-id="fc5a4-126">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>

<span data-ttu-id="fc5a4-127">创建自签名证书后，您可以将它安装到受信任的根证书颁发机构存储区中。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-127">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="fc5a4-128">任何使用该证书签名的证书在此处都受计算机的信任。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-128">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="fc5a4-129">为此，当您不再需要该证书时可立即将它从存储区中删除。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-129">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="fc5a4-130">当您删除此根证书颁发机构证书时，则由它签名的所有其他证书将成为未经授权的。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-130">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="fc5a4-131">根证书颁发机构证书只是一种机制，必要时可限定一组证书。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-131">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="fc5a4-132">例如，在对等应用程序中，通常不需要根证书颁发机构，因为您只信任由对方提供的证书的个体标识。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-132">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="fc5a4-133">在受信任的根证书颁发机构中安装自签名证书</span><span class="sxs-lookup"><span data-stu-id="fc5a4-133">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>

1. <span data-ttu-id="fc5a4-134">打开证书管理单元。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-134">Open the certificate snap-in.</span></span> <span data-ttu-id="fc5a4-135">有关详细信息，请参阅[如何：使用 MMC 管理单元查看证书](how-to-view-certificates-with-the-mmc-snap-in.md)。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-135">For more information, see [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

2. <span data-ttu-id="fc5a4-136">打开要存储证书的文件夹， **“本地计算机”** 或 **“当前用户”**。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-136">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>

3. <span data-ttu-id="fc5a4-137">打开 **“受信任的根证书颁发机构”** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-137">Open the **Trusted Root Certification Authorities** folder.</span></span>

4. <span data-ttu-id="fc5a4-138">右击 **“证书”** 文件夹，再单击 **“所有任务”**，然后单击 **“导入”**。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-138">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>

5. <span data-ttu-id="fc5a4-139">按照屏幕向导说明 RootCA.pfx 导入的存储。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-139">Follow the on-screen wizard instructions to import the RootCA.pfx into the store.</span></span>

## <a name="using-certificates-with-wcf"></a><span data-ttu-id="fc5a4-140">使用证书与 WCF</span><span class="sxs-lookup"><span data-stu-id="fc5a4-140">Using certificates With WCF</span></span>

<span data-ttu-id="fc5a4-141">一旦安装了临时证书，就可以使用这些证书开发指定证书作为客户端凭据类型的 WCF 解决方案。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-141">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="fc5a4-142">例如，下面的 XML 配置指定消息安全模式，并指定证书作为客户端凭据类型。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-142">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>

### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="fc5a4-143">指定证书作为客户端凭据类型</span><span class="sxs-lookup"><span data-stu-id="fc5a4-143">To specify a certificate as the client credential type</span></span>

1. <span data-ttu-id="fc5a4-144">在服务的配置文件中，使用下面的 XML 将安全模式设置为消息，并将客户端凭据类型设置为证书。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-144">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>

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

2. <span data-ttu-id="fc5a4-145">在客户端的配置文件，使用下面的 XML 指定的证书位于用户的存储，以及可以通过搜索"CohoWinery。"的值在 SubjectName 字段中找到</span><span class="sxs-lookup"><span data-stu-id="fc5a4-145">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>

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

<span data-ttu-id="fc5a4-146">有关在 WCF 中使用证书的详细信息，请参阅 [Working with Certificates](working-with-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-146">For more information about using certificates in WCF, see [Working with Certificates](working-with-certificates.md).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="fc5a4-147">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="fc5a4-147">.NET Framework security</span></span>

<span data-ttu-id="fc5a4-148">请确保通过右击证书，再单击 **“删除”** ，从 **“受信任的根证书颁发机构”** 和 **“个人”** 文件夹中删除所有临时根证书颁发机构证书。</span><span class="sxs-lookup"><span data-stu-id="fc5a4-148">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="fc5a4-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc5a4-149">See also</span></span>

- [<span data-ttu-id="fc5a4-150">使用证书</span><span class="sxs-lookup"><span data-stu-id="fc5a4-150">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="fc5a4-151">如何：使用 MMC 管理单元查看证书</span><span class="sxs-lookup"><span data-stu-id="fc5a4-151">How to: View Certificates with the MMC Snap-in</span></span>](how-to-view-certificates-with-the-mmc-snap-in.md)
- [<span data-ttu-id="fc5a4-152">保护服务和客户端的安全</span><span class="sxs-lookup"><span data-stu-id="fc5a4-152">Securing Services and Clients</span></span>](securing-services-and-clients.md)
