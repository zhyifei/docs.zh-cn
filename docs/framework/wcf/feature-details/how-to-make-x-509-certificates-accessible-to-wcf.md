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
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="6b807-102">如何：使 X.509 证书可由 WCF 访问</span><span class="sxs-lookup"><span data-stu-id="6b807-102">How to: Make X.509 Certificates Accessible to WCF</span></span>
<span data-ttu-id="6b807-103">要使 X.509 证书可供 Windows 通信基础 （WCF） 访问，应用程序代码必须指定证书存储名称和位置。</span><span class="sxs-lookup"><span data-stu-id="6b807-103">To make an X.509 certificate accessible to Windows Communication Foundation (WCF), application code must specify the certificate store name and location.</span></span> <span data-ttu-id="6b807-104">在某些情况下，进程标识必须具有对包含私钥的文件的访问权限，此私钥与 X.509 证书相关联。</span><span class="sxs-lookup"><span data-stu-id="6b807-104">In certain circumstances, the process identity must have access to the file that contains the private key associated with the X.509 certificate.</span></span> <span data-ttu-id="6b807-105">要获取证书存储中与 X.509 证书关联的私钥，WCF 必须具有执行此操作的权限。</span><span class="sxs-lookup"><span data-stu-id="6b807-105">To obtain the private key associated with an X.509 certificate in a certificate store, WCF must have permission to do so.</span></span> <span data-ttu-id="6b807-106">默认情况下，只有所有者和“系统”帐户才可以访问证书的私钥。</span><span class="sxs-lookup"><span data-stu-id="6b807-106">By default, only the owner and the System account can access the private key of a certificate.</span></span>  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="6b807-107">使 X.509 证书可由 WCF 访问</span><span class="sxs-lookup"><span data-stu-id="6b807-107">To make X.509 certificates accessible to WCF</span></span>  
  
1. <span data-ttu-id="6b807-108">向 WCF 运行对包含与 X.509 证书关联的私钥的文件的读取访问权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="6b807-108">Give the account under which WCF is running read access to the file that contains the private key associated with the X.509 certificate.</span></span>  
  
    1. <span data-ttu-id="6b807-109">确定 WCF 是否需要对 X.509 证书的私钥进行读取访问。</span><span class="sxs-lookup"><span data-stu-id="6b807-109">Determine whether WCF requires read access to the private key for the X.509 certificate.</span></span>  
  
         <span data-ttu-id="6b807-110">下表详细描述在使用某个 X.509 证书时是否必须提供私钥。</span><span class="sxs-lookup"><span data-stu-id="6b807-110">The following table details whether a private key must be available when using an X.509 certificate.</span></span>  
  
        |<span data-ttu-id="6b807-111">X.509 证书用途</span><span class="sxs-lookup"><span data-stu-id="6b807-111">X.509 certificate use</span></span>|<span data-ttu-id="6b807-112">私钥</span><span class="sxs-lookup"><span data-stu-id="6b807-112">Private key</span></span>|  
        |---------------------------|-----------------|  
        |<span data-ttu-id="6b807-113">对出站 SOAP 消息进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="6b807-113">Digitally signing an outbound SOAP message.</span></span>|<span data-ttu-id="6b807-114">是</span><span class="sxs-lookup"><span data-stu-id="6b807-114">Yes</span></span>|  
        |<span data-ttu-id="6b807-115">验证入站 SOAP 消息的签名。</span><span class="sxs-lookup"><span data-stu-id="6b807-115">Verifying the signature of an inbound SOAP message.</span></span>|<span data-ttu-id="6b807-116">否</span><span class="sxs-lookup"><span data-stu-id="6b807-116">No</span></span>|  
        |<span data-ttu-id="6b807-117">对出站 SOAP 消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="6b807-117">Encrypting an outbound SOAP message.</span></span>|<span data-ttu-id="6b807-118">否</span><span class="sxs-lookup"><span data-stu-id="6b807-118">No</span></span>|  
        |<span data-ttu-id="6b807-119">对入站 SOAP 消息进行解密。</span><span class="sxs-lookup"><span data-stu-id="6b807-119">Decrypting an inbound SOAP message.</span></span>|<span data-ttu-id="6b807-120">是</span><span class="sxs-lookup"><span data-stu-id="6b807-120">Yes</span></span>|  
  
    2. <span data-ttu-id="6b807-121">确定在其中存储证书的存储区的位置和名称。</span><span class="sxs-lookup"><span data-stu-id="6b807-121">Determine the certificate store location and name in which the certificate is stored.</span></span>  
  
         <span data-ttu-id="6b807-122">在其中存储证书的证书存储区要么在应用程序代码中指定，要么在配置中指定。</span><span class="sxs-lookup"><span data-stu-id="6b807-122">The certificate store in which the certificate is stored is specified either in application code or in configuration.</span></span> <span data-ttu-id="6b807-123">例如，下面的示例指定证书位于名为 `CurrentUser` 的 `My` 证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="6b807-123">For example, the following example specifies that the certificate is located in the `CurrentUser` certificate store named `My`.</span></span>  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3. <span data-ttu-id="6b807-124">使用[FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)工具确定证书的私钥位于计算机上的位置。</span><span class="sxs-lookup"><span data-stu-id="6b807-124">Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool.</span></span>  
  
         <span data-ttu-id="6b807-125">[FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)工具需要证书存储名称、证书存储位置以及唯一标识证书的内容。</span><span class="sxs-lookup"><span data-stu-id="6b807-125">The [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate.</span></span> <span data-ttu-id="6b807-126">此工具接受将证书的主题名称或其指纹作为唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6b807-126">The tool accepts either the certificate's subject name or its thumbprint as a unique identifier.</span></span> <span data-ttu-id="6b807-127">有关如何确定证书的指纹的详细信息，请参阅[如何：检索证书的指纹](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)。</span><span class="sxs-lookup"><span data-stu-id="6b807-127">For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
         <span data-ttu-id="6b807-128">以下代码示例使用[FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)工具确定`My``CurrentUser`存储中的证书的私钥的位置，并带有 的`46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`指纹。</span><span class="sxs-lookup"><span data-stu-id="6b807-128">The following code example uses the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span></span>  
  
        ```console
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4. <span data-ttu-id="6b807-129">确定 WCF 正在运行的帐户。</span><span class="sxs-lookup"><span data-stu-id="6b807-129">Determine the account that WCF is running under.</span></span>  
  
         <span data-ttu-id="6b807-130">下表详细介绍了为给定方案运行 WCF 的帐户。</span><span class="sxs-lookup"><span data-stu-id="6b807-130">The following table details the account under which WCF is running for a given scenario.</span></span>  
  
        |<span data-ttu-id="6b807-131">场景</span><span class="sxs-lookup"><span data-stu-id="6b807-131">Scenario</span></span>|<span data-ttu-id="6b807-132">进程标识</span><span class="sxs-lookup"><span data-stu-id="6b807-132">Process identity</span></span>|  
        |--------------|----------------------|  
        |<span data-ttu-id="6b807-133">客户端（控制台或 WinForms 应用程序）。</span><span class="sxs-lookup"><span data-stu-id="6b807-133">Client (console or WinForms application).</span></span>|<span data-ttu-id="6b807-134">当前登录的用户。</span><span class="sxs-lookup"><span data-stu-id="6b807-134">Currently logged in user.</span></span>|  
        |<span data-ttu-id="6b807-135">自承载服务。</span><span class="sxs-lookup"><span data-stu-id="6b807-135">Service that is self-hosted.</span></span>|<span data-ttu-id="6b807-136">当前登录的用户。</span><span class="sxs-lookup"><span data-stu-id="6b807-136">Currently logged in user.</span></span>|  
        |<span data-ttu-id="6b807-137">托管在 IIS 6.0（Windows 服务器 2003）或 IIS 7.0（Windows Vista）中的服务。</span><span class="sxs-lookup"><span data-stu-id="6b807-137">Service that is hosted in IIS 6.0 (Windows Server 2003) or IIS 7.0 (Windows Vista).</span></span>|<span data-ttu-id="6b807-138">网络服务</span><span class="sxs-lookup"><span data-stu-id="6b807-138">NETWORK SERVICE</span></span>|  
        |<span data-ttu-id="6b807-139">在 IIS 5.X （Windows XP） 中托管的服务。</span><span class="sxs-lookup"><span data-stu-id="6b807-139">Service that is hosted in IIS 5.X (Windows XP).</span></span>|<span data-ttu-id="6b807-140">由 Machine.config 文件中的 `<processModel>` 元素控制。</span><span class="sxs-lookup"><span data-stu-id="6b807-140">Controlled by the `<processModel>` element in the Machine.config file.</span></span> <span data-ttu-id="6b807-141">默认帐户为 ASPNET。</span><span class="sxs-lookup"><span data-stu-id="6b807-141">The default account is ASPNET.</span></span>|  
  
    5. <span data-ttu-id="6b807-142">使用 icacls.exe 等工具授予对包含 WCF 运行帐户的私钥的文件的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="6b807-142">Grant read access to the file that contains the private key to the account that WCF is running under, using a tool such as icacls.exe.</span></span>  
  
         <span data-ttu-id="6b807-143">以下代码示例编辑指定文件的可自由访问控制列表 （DACL）， 以授予网络服务帐户对该文件的读取 （：R） 访问权限。</span><span class="sxs-lookup"><span data-stu-id="6b807-143">The following code example edits the discretionary access control list (DACL) for the specified file to grant the NETWORK SERVICE account read (:R) access to the file.</span></span>  
  
        ```console
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="6b807-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b807-144">See also</span></span>

- [<span data-ttu-id="6b807-145">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="6b807-145">FindPrivateKey</span></span>](../../../../docs/framework/wcf/samples/findprivatekey.md)
- [<span data-ttu-id="6b807-146">如何：检索证书的指纹</span><span class="sxs-lookup"><span data-stu-id="6b807-146">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [<span data-ttu-id="6b807-147">使用证书</span><span class="sxs-lookup"><span data-stu-id="6b807-147">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
