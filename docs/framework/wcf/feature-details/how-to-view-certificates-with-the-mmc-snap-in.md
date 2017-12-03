---
title: "如何：使用 MMC 管理单元查看证书"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5981e68ebe2870870fff5e92e87d7582ac2c42b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="dab7e-102">如何：使用 MMC 管理单元查看证书</span><span class="sxs-lookup"><span data-stu-id="dab7e-102">How to: View Certificates with the MMC Snap-in</span></span>
<span data-ttu-id="dab7e-103">凭据的一种常见类型是 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="dab7e-103">A common type of credential is the X.509 certificate.</span></span> <span data-ttu-id="dab7e-104">在创建安全服务或客户端时，可以通过使用如 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 这样的方法来指定使用证书作为客户端或服务凭据。</span><span class="sxs-lookup"><span data-stu-id="dab7e-104">When creating secure services or clients, you can specify a certificate be used as the client or service credential by using methods such as the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span> <span data-ttu-id="dab7e-105">该方法需要多个参数，如存储证书的存储位置和搜索证书时使用的值。</span><span class="sxs-lookup"><span data-stu-id="dab7e-105">The method requires various parameters, such as the store where the certificate is stored and a value to use when searching for the certificate.</span></span> <span data-ttu-id="dab7e-106">下面的过程演示如何检查计算机上的存储以查找相应的证书。</span><span class="sxs-lookup"><span data-stu-id="dab7e-106">The following procedure demonstrates how to examine the stores on a computer to find an appropriate certificate.</span></span> <span data-ttu-id="dab7e-107">查找证书指纹的示例，请参阅[如何： 检索证书的指纹](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)。</span><span class="sxs-lookup"><span data-stu-id="dab7e-107">For an example of finding the certificate thumbprint, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
### <a name="to-view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="dab7e-108">在 MMC 管理单元中查看证书</span><span class="sxs-lookup"><span data-stu-id="dab7e-108">To view certificates in the MMC snap-in</span></span>  
  
1.  <span data-ttu-id="dab7e-109">打开一个命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="dab7e-109">Open a Command Prompt window.</span></span>  
  
2.  <span data-ttu-id="dab7e-110">类型`mmc`然后按 ENTER 键。</span><span class="sxs-lookup"><span data-stu-id="dab7e-110">Type `mmc` and press the ENTER key.</span></span> <span data-ttu-id="dab7e-111">请注意，若要查看本地计算机存储中的证书，您必须具有管理员角色。</span><span class="sxs-lookup"><span data-stu-id="dab7e-111">Note that to view certificates in the local machine store, you must be in the Administrator role.</span></span>  
  
3.  <span data-ttu-id="dab7e-112">上**文件**菜单上，单击**添加/删除管理单元中**。</span><span class="sxs-lookup"><span data-stu-id="dab7e-112">On the **File** menu, click **Add/Remove Snap In**.</span></span>  
  
4.  <span data-ttu-id="dab7e-113">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="dab7e-113">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="dab7e-114">在**添加独立管理单元中**对话框中，选择**证书**。</span><span class="sxs-lookup"><span data-stu-id="dab7e-114">In the **Add Standalone Snap-in** dialog box, select **Certificates**.</span></span>  
  
6.  <span data-ttu-id="dab7e-115">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="dab7e-115">Click **Add**.</span></span>  
  
7.  <span data-ttu-id="dab7e-116">在**证书管理单元**对话框中，选择**计算机帐户**单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="dab7e-116">In the **Certificates snap-in** dialog box, select **Computer account** and click **Next**.</span></span> <span data-ttu-id="dab7e-117">或者，您可以选择**我的用户帐户**或**服务帐户**。</span><span class="sxs-lookup"><span data-stu-id="dab7e-117">Optionally, you can select **My User account** or **Service account**.</span></span> <span data-ttu-id="dab7e-118">如果您不是计算机的管理员，则您只能管理您的用户帐户的证书。</span><span class="sxs-lookup"><span data-stu-id="dab7e-118">If you are not an administrator of the computer, you can manage certificates only for your user account.</span></span>  
  
8.  <span data-ttu-id="dab7e-119">在**选择计算机**对话框中，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="dab7e-119">In the **Select Computer** dialog box, click **Finish**.</span></span>  
  
9. <span data-ttu-id="dab7e-120">在**添加独立管理单元中**对话框中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="dab7e-120">In the **Add Standalone Snap-in** dialog box, click **Close**.</span></span>  
  
10. <span data-ttu-id="dab7e-121">上**添加/删除管理单元中**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="dab7e-121">On the **Add/Remove Snap-in** dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="dab7e-122">在**控制台根节点**窗口中，单击**证书 （本地计算机）**以查看证书存储的计算机。</span><span class="sxs-lookup"><span data-stu-id="dab7e-122">In the **Console Root** window, click **Certificates (Local Computer)** to view the certificate stores for the computer.</span></span>  
  
12. <span data-ttu-id="dab7e-123">可选。</span><span class="sxs-lookup"><span data-stu-id="dab7e-123">Optional.</span></span> <span data-ttu-id="dab7e-124">若要查看您的帐户证书，请重复步骤 3 到步骤 6。</span><span class="sxs-lookup"><span data-stu-id="dab7e-124">To view certificates for your account, repeat steps 3 to 6.</span></span> <span data-ttu-id="dab7e-125">在步骤 7，而不是选择**计算机帐户**，单击**我的用户帐户**并重复执行步骤 8 到 10。</span><span class="sxs-lookup"><span data-stu-id="dab7e-125">In step 7, instead of selecting **Computer account**, click **My User account** and repeat steps 8 to 10.</span></span>  
  
13. <span data-ttu-id="dab7e-126">可选。</span><span class="sxs-lookup"><span data-stu-id="dab7e-126">Optional.</span></span> <span data-ttu-id="dab7e-127">上**文件**菜单上，单击**保存**或**另存为**。</span><span class="sxs-lookup"><span data-stu-id="dab7e-127">On the **File** menu, click **Save** or **Save As**.</span></span> <span data-ttu-id="dab7e-128">保存控制台文件供以后重复使用。</span><span class="sxs-lookup"><span data-stu-id="dab7e-128">Save the console file for later reuse.</span></span>  
  
## <a name="viewing-certificates-with-internet-explorer"></a><span data-ttu-id="dab7e-129">使用 Internet Explorer 查看证书</span><span class="sxs-lookup"><span data-stu-id="dab7e-129">Viewing Certificates with Internet Explorer</span></span>  
 <span data-ttu-id="dab7e-130">您也可以通过使用 Internet Explorer 来查看、导出、导入和删除证书。</span><span class="sxs-lookup"><span data-stu-id="dab7e-130">You can also view, export, import, and delete certificates by using Internet Explorer.</span></span>  
  
#### <a name="to-view-certificates-with-internet-explorer"></a><span data-ttu-id="dab7e-131">使用 Internet Explorer 查看证书</span><span class="sxs-lookup"><span data-stu-id="dab7e-131">To view certificates with Internet Explorer</span></span>  
  
1.  <span data-ttu-id="dab7e-132">在 Internet Explorer 中，单击**工具**，然后单击**Internet 选项**以显示**Internet 选项**对话框。</span><span class="sxs-lookup"><span data-stu-id="dab7e-132">In Internet Explorer, click **Tools**, then click **Internet Options** to display the **Internet Options** dialog box.</span></span>  
  
2.  <span data-ttu-id="dab7e-133">单击**内容**选项卡。</span><span class="sxs-lookup"><span data-stu-id="dab7e-133">Click the **Content** tab.</span></span>  
  
3.  <span data-ttu-id="dab7e-134">下**证书**，单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="dab7e-134">Under **Certificates**, click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="dab7e-135">若要查看的任何证书的详细信息，选择的证书，单击**视图**。</span><span class="sxs-lookup"><span data-stu-id="dab7e-135">To view details of any certificate, select the certificate and click **View**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab7e-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dab7e-136">See Also</span></span>  
 [<span data-ttu-id="dab7e-137">使用证书</span><span class="sxs-lookup"><span data-stu-id="dab7e-137">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="dab7e-138">如何： 创建开发期间使用的临时证书</span><span class="sxs-lookup"><span data-stu-id="dab7e-138">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)  
 [<span data-ttu-id="dab7e-139">如何： 检索证书的指纹</span><span class="sxs-lookup"><span data-stu-id="dab7e-139">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
