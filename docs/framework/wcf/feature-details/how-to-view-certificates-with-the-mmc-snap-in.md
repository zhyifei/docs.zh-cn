---
title: 如何：使用 MMC 卡入式查看证书
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 35048c24e838c513909fae8bedcba287001f5cef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184784"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="63a87-102">如何：使用 MMC 卡入式查看证书</span><span class="sxs-lookup"><span data-stu-id="63a87-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="63a87-103">创建安全客户端或服务时，可以使用[证书](working-with-certificates.md)作为凭据。</span><span class="sxs-lookup"><span data-stu-id="63a87-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="63a87-104">例如，常用类型的凭据是 X.509 证书，您可以使用 方法<xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType>创建该证书。</span><span class="sxs-lookup"><span data-stu-id="63a87-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="63a87-105">在 Windows 系统上可以使用 Microsoft 管理控制台 （MMC） 检查三种不同类型的证书存储：</span><span class="sxs-lookup"><span data-stu-id="63a87-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="63a87-106">本地计算机：存储是设备的本地存储，并且对设备上的所有用户是全局的。</span><span class="sxs-lookup"><span data-stu-id="63a87-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="63a87-107">当前用户：存储是设备上当前用户帐户的本地存储。</span><span class="sxs-lookup"><span data-stu-id="63a87-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="63a87-108">服务帐户：存储是设备上特定服务的本地存储。</span><span class="sxs-lookup"><span data-stu-id="63a87-108">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="63a87-109">在 MMC 管理单元中查看证书</span><span class="sxs-lookup"><span data-stu-id="63a87-109">View certificates in the MMC snap-in</span></span>

<span data-ttu-id="63a87-110">以下过程演示如何检查本地设备上的存储以查找适当的证书：</span><span class="sxs-lookup"><span data-stu-id="63a87-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span>
  
1. <span data-ttu-id="63a87-111">选择"从**开始"** 菜单**中运行**，然后输入*mmc*。</span><span class="sxs-lookup"><span data-stu-id="63a87-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span>

    <span data-ttu-id="63a87-112">将显示 MMC。</span><span class="sxs-lookup"><span data-stu-id="63a87-112">The MMC appears.</span></span>
  
2. <span data-ttu-id="63a87-113">从 **"文件**"菜单中，选择 **"添加/删除对齐入"。**</span><span class="sxs-lookup"><span data-stu-id="63a87-113">From the **File** menu, select **Add/Remove Snap In**.</span></span>

    <span data-ttu-id="63a87-114">将显示 **"添加或删除对齐"** 窗口。</span><span class="sxs-lookup"><span data-stu-id="63a87-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="63a87-115">从 **"可用管理单元**"列表中，选择 **"证书**"，然后选择 **"添加**"。</span><span class="sxs-lookup"><span data-stu-id="63a87-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![添加证书管理单元](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="63a87-117">在 **"证书入驻"** 窗口中，选择 **"计算机帐户**"，然后选择 **"下一步**"。</span><span class="sxs-lookup"><span data-stu-id="63a87-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span>
  
    <span data-ttu-id="63a87-118">或者，您可以选择特定服务的当前用户或服务**帐户\*\*\*\*的"我的用户帐户**"。</span><span class="sxs-lookup"><span data-stu-id="63a87-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="63a87-119">如果您不是设备的管理员，则只能管理用户帐户的证书。</span><span class="sxs-lookup"><span data-stu-id="63a87-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="63a87-120">在 **"选择计算机"** 窗口中，保持**本地计算机**选中状态，然后选择 **"完成**"。</span><span class="sxs-lookup"><span data-stu-id="63a87-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="63a87-121">在 **"添加或删除对齐"** 窗口中，选择 **"确定**"。</span><span class="sxs-lookup"><span data-stu-id="63a87-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![添加证书管理单元](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="63a87-123">可选：从 **"文件**"菜单中，选择 **"保存\*\*\*\*"或"保存为"** 以保存 MMC 控制台文件以供以后使用。</span><span class="sxs-lookup"><span data-stu-id="63a87-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="63a87-124">要在 MMC 管理单元中查看证书，请在左侧窗格中选择 **"控制台根"，** 然后展开**证书（本地计算机）。**</span><span class="sxs-lookup"><span data-stu-id="63a87-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="63a87-125">将显示每种类型的证书的目录列表。</span><span class="sxs-lookup"><span data-stu-id="63a87-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="63a87-126">在每个证书目录中，您可以查看、导出、导入和删除其证书。</span><span class="sxs-lookup"><span data-stu-id="63a87-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="63a87-127">使用证书管理器工具查看证书</span><span class="sxs-lookup"><span data-stu-id="63a87-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="63a87-128">您还可以使用证书管理器工具查看、导出、导入和删除证书。</span><span class="sxs-lookup"><span data-stu-id="63a87-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="63a87-129">查看本地设备的证书</span><span class="sxs-lookup"><span data-stu-id="63a87-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="63a87-130">选择"**从开始"** 菜单**中运行**，然后输入*certlm.msc*。</span><span class="sxs-lookup"><span data-stu-id="63a87-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span>

    <span data-ttu-id="63a87-131">将显示本地设备的证书管理器工具。</span><span class="sxs-lookup"><span data-stu-id="63a87-131">The Certificate Manager tool for the local device appears.</span></span>
  
2. <span data-ttu-id="63a87-132">要查看证书，在左侧窗格中的 **"证书 - 本地计算机**"下，请展开要查看的证书类型的目录。</span><span class="sxs-lookup"><span data-stu-id="63a87-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="63a87-133">查看当前用户的证书</span><span class="sxs-lookup"><span data-stu-id="63a87-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="63a87-134">选择"**从开始"** 菜单**中运行**，然后输入*certmgr.msc*。</span><span class="sxs-lookup"><span data-stu-id="63a87-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span>

    <span data-ttu-id="63a87-135">将显示当前用户的证书管理器工具。</span><span class="sxs-lookup"><span data-stu-id="63a87-135">The Certificate Manager tool for the current user appears.</span></span>
  
2. <span data-ttu-id="63a87-136">要查看证书，在左侧窗格中的 **"证书 - 当前用户**"下，请展开要查看的证书类型的目录。</span><span class="sxs-lookup"><span data-stu-id="63a87-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="63a87-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63a87-137">See also</span></span>

- [<span data-ttu-id="63a87-138">使用证书</span><span class="sxs-lookup"><span data-stu-id="63a87-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="63a87-139">如何：创建临时证书，供开发期间使用</span><span class="sxs-lookup"><span data-stu-id="63a87-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="63a87-140">如何：检索证书的指纹</span><span class="sxs-lookup"><span data-stu-id="63a87-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
