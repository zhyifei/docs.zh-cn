---
title: 如何：使用 MMC 管理单元查看证书
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 69f79b64250ff46524e7b4720d13351774875a3f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972704"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="af03c-102">如何：使用 MMC 管理单元查看证书</span><span class="sxs-lookup"><span data-stu-id="af03c-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="af03c-103">当您创建安全的客户端或服务时，可以使用[证书](working-with-certificates.md)作为凭据。</span><span class="sxs-lookup"><span data-stu-id="af03c-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="af03c-104">例如，常见的凭据类型是 X.509 证书，创建具有<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="af03c-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span> 

<span data-ttu-id="af03c-105">有三种不同类型的可以检查 Windows 系统上使用 Microsoft 管理控制台 (MMC) 的证书存储：</span><span class="sxs-lookup"><span data-stu-id="af03c-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="af03c-106">本地计算机：存储是在设备本地和全局上设备的所有用户。</span><span class="sxs-lookup"><span data-stu-id="af03c-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="af03c-107">当前用户：在存储区是本地的设备上的当前用户帐户。</span><span class="sxs-lookup"><span data-stu-id="af03c-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="af03c-108">服务帐户：在存储区是本地的设备上的特定服务。</span><span class="sxs-lookup"><span data-stu-id="af03c-108">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="af03c-109">在 MMC 管理单元中查看证书</span><span class="sxs-lookup"><span data-stu-id="af03c-109">View certificates in the MMC snap-in</span></span> 

<span data-ttu-id="af03c-110">下面的过程演示如何检查本地设备以查找相应的证书上的存储区：</span><span class="sxs-lookup"><span data-stu-id="af03c-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span> 
  
1. <span data-ttu-id="af03c-111">选择**运行**从**启动**菜单中，然后输入*mmc*。</span><span class="sxs-lookup"><span data-stu-id="af03c-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span> 

    <span data-ttu-id="af03c-112">将显示在 MMC。</span><span class="sxs-lookup"><span data-stu-id="af03c-112">The MMC appears.</span></span> 
  
2. <span data-ttu-id="af03c-113">从**文件**菜单中，选择**添加/删除管理单元**。</span><span class="sxs-lookup"><span data-stu-id="af03c-113">From the **File** menu, select **Add/Remove Snap In**.</span></span> 
    
    <span data-ttu-id="af03c-114">**添加或删除管理单元**窗口会显示。</span><span class="sxs-lookup"><span data-stu-id="af03c-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="af03c-115">从**可用的管理单元**列表中，选择**证书**，然后选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="af03c-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![添加证书管理单元](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="af03c-117">在中**管理单元中的证书**窗口中，选择**计算机帐户**，然后选择**下一步**。</span><span class="sxs-lookup"><span data-stu-id="af03c-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span> 
  
    <span data-ttu-id="af03c-118">或者，您可以选择**我的用户帐户**当前用户或**服务帐户**针对特定服务。</span><span class="sxs-lookup"><span data-stu-id="af03c-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="af03c-119">如果您不管理员为你的设备，你可以仅对你的用户帐户的管理证书。</span><span class="sxs-lookup"><span data-stu-id="af03c-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="af03c-120">在中**选择计算机**窗口中，保留**本地计算机**选择，并选择**完成**。</span><span class="sxs-lookup"><span data-stu-id="af03c-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="af03c-121">在中**管理单元中添加或删除**窗口中，选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="af03c-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![添加证书管理单元](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="af03c-123">可选：从**文件**菜单中，选择**保存**或**另存为**保存 MMC 控制台文件以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="af03c-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="af03c-124">若要查看你的证书 MMC 管理单元中，选择**控制台根节点**在左窗格中，然后展开**证书 （本地计算机）**。</span><span class="sxs-lookup"><span data-stu-id="af03c-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="af03c-125">将显示每种类型的证书的目录的列表。</span><span class="sxs-lookup"><span data-stu-id="af03c-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="af03c-126">从每个证书目录中，可以查看、 导出、 导入，并删除其证书。</span><span class="sxs-lookup"><span data-stu-id="af03c-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="af03c-127">使用证书管理器工具查看证书</span><span class="sxs-lookup"><span data-stu-id="af03c-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="af03c-128">您还可以查看、 导出、 导入，和使用证书管理器工具中删除证书。</span><span class="sxs-lookup"><span data-stu-id="af03c-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="af03c-129">若要查看本地设备的证书</span><span class="sxs-lookup"><span data-stu-id="af03c-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="af03c-130">选择**运行**从**启动**菜单中，然后输入*certlm.msc*。</span><span class="sxs-lookup"><span data-stu-id="af03c-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span> 

    <span data-ttu-id="af03c-131">将显示本地设备的证书管理器工具。</span><span class="sxs-lookup"><span data-stu-id="af03c-131">The Certificate Manager tool for the local device appears.</span></span> 
  
2. <span data-ttu-id="af03c-132">若要查看您的证书，在**证书-本地计算机**在左窗格中，展开你想要查看的证书的类型的目录。</span><span class="sxs-lookup"><span data-stu-id="af03c-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="af03c-133">若要查看当前用户证书</span><span class="sxs-lookup"><span data-stu-id="af03c-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="af03c-134">选择**运行**从**启动**菜单中，然后输入*certmgr.msc*。</span><span class="sxs-lookup"><span data-stu-id="af03c-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span> 

    <span data-ttu-id="af03c-135">当前用户的证书管理器工具会显示。</span><span class="sxs-lookup"><span data-stu-id="af03c-135">The Certificate Manager tool for the current user appears.</span></span> 
  
2. <span data-ttu-id="af03c-136">若要查看您的证书，在**证书-当前用户**在左窗格中，展开你想要查看的证书的类型的目录。</span><span class="sxs-lookup"><span data-stu-id="af03c-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="af03c-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="af03c-137">See also</span></span>

- [<span data-ttu-id="af03c-138">使用证书</span><span class="sxs-lookup"><span data-stu-id="af03c-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="af03c-139">如何：创建开发期间使用的临时证书</span><span class="sxs-lookup"><span data-stu-id="af03c-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="af03c-140">如何：检索证书的指纹</span><span class="sxs-lookup"><span data-stu-id="af03c-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
