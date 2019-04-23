---
title: 虚拟目录设置说明
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: fdff88026a49989870ee5c47f9a38a65ecad3c80
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59325340"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="b30e1-102">虚拟目录设置说明</span><span class="sxs-lookup"><span data-stu-id="b30e1-102">Virtual Directory Setup Instructions</span></span>
<span data-ttu-id="b30e1-103">Windows Communication Foundation (WCF) 示例旨在共享公共虚拟目录，名为 servicemodelsamples 的将映射到 %SystemDrive%\inetpub\wwwroot\servicemodelsamples 文件夹。</span><span class="sxs-lookup"><span data-stu-id="b30e1-103">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b30e1-104">%SystemDrive% 通常为 C: 或 D:，具体取决于安装 Internet 信息服务 (IIS) 的驱动器位置。</span><span class="sxs-lookup"><span data-stu-id="b30e1-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="b30e1-105">可以运行 Setupvroot.bat 和 Cleanupvroot.bat 文件[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)创建虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="b30e1-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="b30e1-106">如果宁愿手动创建虚拟目录，请使用下面的过程。</span><span class="sxs-lookup"><span data-stu-id="b30e1-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="b30e1-107">过程</span><span class="sxs-lookup"><span data-stu-id="b30e1-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="b30e1-108">若要在 IIS 7.0 或 7.5 中创建虚拟目录</span><span class="sxs-lookup"><span data-stu-id="b30e1-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="b30e1-109">从**启动**菜单上，单击**运行**，然后键入**inetmgr**以打开 Internet 信息服务 (IIS) MMC 管理单元。</span><span class="sxs-lookup"><span data-stu-id="b30e1-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="b30e1-110">在左窗格中，展开包含计算机的名称的节点，然后展开**站点**节点。</span><span class="sxs-lookup"><span data-stu-id="b30e1-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3. <span data-ttu-id="b30e1-111">右键单击**Default Web Site**，然后选择**添加应用程序**以打开**添加应用程序窗口**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4. <span data-ttu-id="b30e1-112">在窗口中，键入`servicemodelsamples`作为要创建的虚拟目录的别名。</span><span class="sxs-lookup"><span data-stu-id="b30e1-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="b30e1-113">创建以下目录：%SystemDrive%\inetpub\wwwroot\servicemodelsamples</span><span class="sxs-lookup"><span data-stu-id="b30e1-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6. <span data-ttu-id="b30e1-114">将物理路径设置为 %SystemDrive%\inetpub\wwwroot\servicemodelsamples。</span><span class="sxs-lookup"><span data-stu-id="b30e1-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="b30e1-115">大多数 WCF 示例在生成后都将服务可执行文件复制到此位置。</span><span class="sxs-lookup"><span data-stu-id="b30e1-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7. <span data-ttu-id="b30e1-116">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-116">Click **OK**.</span></span> <span data-ttu-id="b30e1-117">现在已为 WCF 示例创建 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b30e1-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b30e1-118">因为所有 WCF 示例都使用相同的 servicemodelsamples Web 应用程序，必须只有一次执行此任务。</span><span class="sxs-lookup"><span data-stu-id="b30e1-118">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b30e1-119">在本文档中，术语`virtual directory`和 `Web application`是同义词。</span><span class="sxs-lookup"><span data-stu-id="b30e1-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="b30e1-120">除了创建虚拟目录，还必须设置其属性以启用要运行 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="b30e1-120">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="b30e1-121">有关详细信息，请参见以下内容。</span><span class="sxs-lookup"><span data-stu-id="b30e1-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="b30e1-122">在 IIS 5.1 或 6.0 中创建虚拟目录</span><span class="sxs-lookup"><span data-stu-id="b30e1-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="b30e1-123">打开命令提示符窗口并键入`start inetmgr`以打开 Internet 信息服务 (IIS) MMC 管理单元。</span><span class="sxs-lookup"><span data-stu-id="b30e1-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="b30e1-124">在左窗格中，展开包含计算机的名称的节点，然后展开**网站**节点。</span><span class="sxs-lookup"><span data-stu-id="b30e1-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3. <span data-ttu-id="b30e1-125">右键单击**Default Web Site** ，然后选择**新的、 虚拟目录**以打开虚拟目录创建向导。</span><span class="sxs-lookup"><span data-stu-id="b30e1-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4. <span data-ttu-id="b30e1-126">在向导中，键入`servicemodelsamples`作为要创建的虚拟目录的别名。</span><span class="sxs-lookup"><span data-stu-id="b30e1-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="b30e1-127">将路径设置为 %SystemDrive%\inetpub\wwwroot\servicemodelsamples。</span><span class="sxs-lookup"><span data-stu-id="b30e1-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="b30e1-128">大多数 WCF 示例在生成后都将服务可执行文件复制到此位置。</span><span class="sxs-lookup"><span data-stu-id="b30e1-128">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6. <span data-ttu-id="b30e1-129">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-129">Click **Next**.</span></span>  
  
7. <span data-ttu-id="b30e1-130">默认情况下，已选中以下复选框：</span><span class="sxs-lookup"><span data-stu-id="b30e1-130">By default, the following check boxes are selected:</span></span>  
  
    -   <span data-ttu-id="b30e1-131">**Read**</span><span class="sxs-lookup"><span data-stu-id="b30e1-131">**Read**</span></span>  
  
    -   <span data-ttu-id="b30e1-132">**运行脚本 （如 ASP)**</span><span class="sxs-lookup"><span data-stu-id="b30e1-132">**Run scripts (such as ASP)**</span></span>  
  
8. <span data-ttu-id="b30e1-133">单击**下一步**，然后单击**完成**以完成向导。</span><span class="sxs-lookup"><span data-stu-id="b30e1-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b30e1-134">因为所有 WCF 示例都使用相同的 servicemodelsamples 虚拟目录，必须一次执行此任务。</span><span class="sxs-lookup"><span data-stu-id="b30e1-134">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="b30e1-135">若要设置附加虚拟目录属性在 IIS 7.0 或 7.5</span><span class="sxs-lookup"><span data-stu-id="b30e1-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="b30e1-136">单击 servicemodelsamples 节点。</span><span class="sxs-lookup"><span data-stu-id="b30e1-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="b30e1-137">窗口的底部列有两个视图。</span><span class="sxs-lookup"><span data-stu-id="b30e1-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="b30e1-138">选择**功能视图**如果尚未选择它。</span><span class="sxs-lookup"><span data-stu-id="b30e1-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2. <span data-ttu-id="b30e1-139">双击的条目**目录浏览**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3. <span data-ttu-id="b30e1-140">在操作窗格中选择**启用**选项。</span><span class="sxs-lookup"><span data-stu-id="b30e1-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="b30e1-141">这样，您将能够使用 Internet Explorer 访问目录的目录，这在调试服务时将很有帮助。</span><span class="sxs-lookup"><span data-stu-id="b30e1-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="b30e1-142">最后，您必须设置 servicemodelsamples 文件夹的安全属性，以允许其他人访问该文件夹。</span><span class="sxs-lookup"><span data-stu-id="b30e1-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="b30e1-143">有关详细信息，请参见以下内容。</span><span class="sxs-lookup"><span data-stu-id="b30e1-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="b30e1-144">在 IIS 5.1 或 6.0 中设置附加虚拟目录属性</span><span class="sxs-lookup"><span data-stu-id="b30e1-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="b30e1-145">右击 servicemodelsamples 节点，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="b30e1-146">默认情况下，已选中以下复选框：</span><span class="sxs-lookup"><span data-stu-id="b30e1-146">By default, the following check boxes are selected:</span></span>  
  
    -   <span data-ttu-id="b30e1-147">**Read**</span><span class="sxs-lookup"><span data-stu-id="b30e1-147">**Read**</span></span>  
  
    -   <span data-ttu-id="b30e1-148">**日志访问**</span><span class="sxs-lookup"><span data-stu-id="b30e1-148">**Log visits**</span></span>  
  
    -   <span data-ttu-id="b30e1-149">**编制此资源的索引**</span><span class="sxs-lookup"><span data-stu-id="b30e1-149">**Index this resource**</span></span>  
  
3. <span data-ttu-id="b30e1-150">选择**目录浏览**复选框。</span><span class="sxs-lookup"><span data-stu-id="b30e1-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="b30e1-151">这样，您将能够使用 Internet Explorer 访问目录的目录，这在调试服务时将很有帮助。</span><span class="sxs-lookup"><span data-stu-id="b30e1-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="b30e1-152">在 IIS 7.0 或 7.5 中设置文件夹的安全属性</span><span class="sxs-lookup"><span data-stu-id="b30e1-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="b30e1-153">定位到 %SystemDrive%\inetpub\wwwroot\servicemodelsamples。</span><span class="sxs-lookup"><span data-stu-id="b30e1-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="b30e1-154">右击 servicemodelsamples 文件夹，单击**共享**或**共享与**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3. <span data-ttu-id="b30e1-155">单击左侧的向下箭头**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="b30e1-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4. <span data-ttu-id="b30e1-156">选择**查找**条目。</span><span class="sxs-lookup"><span data-stu-id="b30e1-156">Select the **Find** entry.</span></span> <span data-ttu-id="b30e1-157">**选择用户或组**窗口随即打开。</span><span class="sxs-lookup"><span data-stu-id="b30e1-157">The **Select Users or Groups** window opens.</span></span>  
  
5. <span data-ttu-id="b30e1-158">单击 **“高级”**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-158">Click **Advanced**.</span></span>  
  
6. <span data-ttu-id="b30e1-159">单击**位置**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-159">Click **Locations**.</span></span> <span data-ttu-id="b30e1-160">**位置**窗口随即打开。</span><span class="sxs-lookup"><span data-stu-id="b30e1-160">The **Locations** window is now open.</span></span>  
  
7. <span data-ttu-id="b30e1-161">选择对应于所使用计算机的项。</span><span class="sxs-lookup"><span data-stu-id="b30e1-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="b30e1-162">请务必选择本地计算机，而不是对应于所列出的任何域或网络的项。</span><span class="sxs-lookup"><span data-stu-id="b30e1-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="b30e1-163">选择计算机之后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-163">After you have selected the computer, click **OK**.</span></span>  
  
8. <span data-ttu-id="b30e1-164">单击**立即查找**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-164">Click **Find Now**.</span></span> <span data-ttu-id="b30e1-165">此操作将用与本地计算机关联的对象填充搜索结果。</span><span class="sxs-lookup"><span data-stu-id="b30e1-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="b30e1-166">查找**IIS_IUSRS**中的条目**名称 （相对可分辨名称）** 列。</span><span class="sxs-lookup"><span data-stu-id="b30e1-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="b30e1-167">选择该条目，然后单击**确定**关闭搜索结果窗口。</span><span class="sxs-lookup"><span data-stu-id="b30e1-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="b30e1-168">单击**确定**以关闭**选择用户或组**窗口。</span><span class="sxs-lookup"><span data-stu-id="b30e1-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="b30e1-169">单击**共享**保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b30e1-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="b30e1-170">若要启用共享的更改完成后，单击**完成**以关闭**文件共享**窗口。</span><span class="sxs-lookup"><span data-stu-id="b30e1-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="b30e1-171">在 IIS 5.1 或 6.0 中设置文件夹的安全属性</span><span class="sxs-lookup"><span data-stu-id="b30e1-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="b30e1-172">定位到 %SystemDrive%\inetpub\wwwroot\servicemodelsamples。</span><span class="sxs-lookup"><span data-stu-id="b30e1-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="b30e1-173">右键单击**servicemodelsamples**文件夹，然后单击**共享和安全。**</span><span class="sxs-lookup"><span data-stu-id="b30e1-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3. <span data-ttu-id="b30e1-174">单击 **“安全”** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b30e1-174">Click the **Security** tab.</span></span>  
  
4. <span data-ttu-id="b30e1-175">如果在使用 IIS 6.0**组或用户名**框中，检查是否**Internet 来宾帐户**列出。</span><span class="sxs-lookup"><span data-stu-id="b30e1-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="b30e1-176">如果该帐户未列出：</span><span class="sxs-lookup"><span data-stu-id="b30e1-176">If it is not listed:</span></span>  
  
    1.  <span data-ttu-id="b30e1-177">单击“开始”，然后单击“控制面板”。</span><span class="sxs-lookup"><span data-stu-id="b30e1-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="b30e1-178">如果没有看到**用户帐户**图标，单击**切换到分类视图**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3.  <span data-ttu-id="b30e1-179">单击**用户帐户**图标。</span><span class="sxs-lookup"><span data-stu-id="b30e1-179">Click the **User Accounts** icon.</span></span>  
  
    4.  <span data-ttu-id="b30e1-180">在"或选择一个控制面板图标，"单击**用户帐户**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5.  <span data-ttu-id="b30e1-181">在中**用户帐户**对话框中，单击**高级**选项卡。</span><span class="sxs-lookup"><span data-stu-id="b30e1-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6.  <span data-ttu-id="b30e1-182">单击 **“高级”**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-182">Click **Advanced**.</span></span>  
  
    7.  <span data-ttu-id="b30e1-183">在中**本地用户和组**对话框中，单击此项可展开**用户**文件夹。</span><span class="sxs-lookup"><span data-stu-id="b30e1-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8.  <span data-ttu-id="b30e1-184">在右窗格中，双击**Internet 来宾帐户**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="b30e1-185">在中**属性**名称对话框中，复制用作 Internet 来宾帐户。</span><span class="sxs-lookup"><span data-stu-id="b30e1-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="b30e1-186">默认情况下，该名称以“USR_”开头，后跟计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="b30e1-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="b30e1-187">关闭“属性”  对话框。</span><span class="sxs-lookup"><span data-stu-id="b30e1-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="b30e1-188">关闭**本地用户和组**对话框。</span><span class="sxs-lookup"><span data-stu-id="b30e1-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="b30e1-189">关闭**用户帐户**对话框。</span><span class="sxs-lookup"><span data-stu-id="b30e1-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="b30e1-190">关闭另**用户帐户**对话框。</span><span class="sxs-lookup"><span data-stu-id="b30e1-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="b30e1-191">在中**servicemodelsamples 属性**对话框中，在**安全**选项卡上，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="b30e1-192">键入一个反斜杠后, 跟计算机的名称，然后粘贴 Internet 用户帐户，例如，myMachineName\\%internetguestaccountname%</span><span class="sxs-lookup"><span data-stu-id="b30e1-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="b30e1-193">单击**检查名称**验证所添加。</span><span class="sxs-lookup"><span data-stu-id="b30e1-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="b30e1-194">如果名称有效，名称将变为全大写并带下划线的形式。</span><span class="sxs-lookup"><span data-stu-id="b30e1-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5. <span data-ttu-id="b30e1-195">对于 IIS 6.0，还检查网络服务列在**组或用户名**框。</span><span class="sxs-lookup"><span data-stu-id="b30e1-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="b30e1-196">如果“NETWORK SERVICE”未列出：</span><span class="sxs-lookup"><span data-stu-id="b30e1-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1.  <span data-ttu-id="b30e1-197">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-197">Click **Add**.</span></span>  
  
    2.  <span data-ttu-id="b30e1-198">在中**选择用户或组**对话框中，键入计算机的名称后跟反斜杠。</span><span class="sxs-lookup"><span data-stu-id="b30e1-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3.  <span data-ttu-id="b30e1-199">类型**服务**后反斜杠 （没有空格）。</span><span class="sxs-lookup"><span data-stu-id="b30e1-199">Type **service** after the backslash (no space).</span></span>  
  
    4.  <span data-ttu-id="b30e1-200">单击**检查名称**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-200">Click **Check names**.</span></span>  
  
    5.  <span data-ttu-id="b30e1-201">如果找到多个名称，选择**网络服务**然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6.  <span data-ttu-id="b30e1-202">单击**确定**以关闭**选择用户或组**对话框。</span><span class="sxs-lookup"><span data-stu-id="b30e1-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6. <span data-ttu-id="b30e1-203">如果使用带 IIS 5.1 的 Windows XP SP2，请检查中列出了 Internet 来宾帐户和 ASPNET**组或用户名**框。</span><span class="sxs-lookup"><span data-stu-id="b30e1-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="b30e1-204">请注意，ASPNET 用户可能属于内置**用户**安全组。</span><span class="sxs-lookup"><span data-stu-id="b30e1-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="b30e1-205">如果是这样，那么，如果**用户**组列在对话框中，不需要将其作为单独的项添加到许可用户的列表。</span><span class="sxs-lookup"><span data-stu-id="b30e1-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="b30e1-206">若要检查 ASPNET 是否属于**用户**安全组：</span><span class="sxs-lookup"><span data-stu-id="b30e1-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1.  <span data-ttu-id="b30e1-207">上**启动**菜单上，单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="b30e1-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="b30e1-208">单击**用户帐户**图标。</span><span class="sxs-lookup"><span data-stu-id="b30e1-208">Click the **User Accounts** icon.</span></span>  
  
    3.  <span data-ttu-id="b30e1-209">在中**组**列中，检查的值**ASPNET**是"用户。</span><span class="sxs-lookup"><span data-stu-id="b30e1-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b30e1-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="b30e1-210">See also</span></span>

- [<span data-ttu-id="b30e1-211">Internet 信息服务承载说明</span><span class="sxs-lookup"><span data-stu-id="b30e1-211">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
