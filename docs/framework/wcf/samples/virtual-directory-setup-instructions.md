---
title: 虚拟目录设置说明
ms.date: 03/30/2017
ms.assetid: 3c62cab5-81a4-48b6-ac8c-9ce33a85a157
ms.openlocfilehash: f755fadf6bef2bdd58fd31f3460a143b8f52eddf
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966741"
---
# <a name="virtual-directory-setup-instructions"></a><span data-ttu-id="6fefc-102">虚拟目录设置说明</span><span class="sxs-lookup"><span data-stu-id="6fefc-102">Virtual Directory Setup Instructions</span></span>
<span data-ttu-id="6fefc-103">Windows Communication Foundation (WCF) 示例旨在共享一个名为 servicemodelsamples 的公共虚拟目录, 该目录映射到%SystemDrive%\inetpub\wwwroot\servicemodelsamples 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6fefc-103">The Windows Communication Foundation (WCF) samples are intended to share a common virtual directory named servicemodelsamples that is mapped to the %SystemDrive%\inetpub\wwwroot\servicemodelsamples folder.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6fefc-104">%SystemDrive% 通常为 C: 或 D:，具体取决于安装 Internet 信息服务 (IIS) 的驱动器位置。</span><span class="sxs-lookup"><span data-stu-id="6fefc-104">%SystemDrive% is usually C: or D:, depending on the drive location where Internet Information Services (IIS) is installed.</span></span>  
  
 <span data-ttu-id="6fefc-105">你可以从 Setupvroot.bat 和 Cleanupvroot.bat 文件运行[Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)来创建虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="6fefc-105">You can run the Setupvroot.bat and Cleanupvroot.bat files from the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) to create the virtual directory.</span></span> <span data-ttu-id="6fefc-106">如果宁愿手动创建虚拟目录，请使用下面的过程。</span><span class="sxs-lookup"><span data-stu-id="6fefc-106">If you prefer to create the virtual directory manually, use the following procedures.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="6fefc-107">过程</span><span class="sxs-lookup"><span data-stu-id="6fefc-107">Procedures</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-70-or-75"></a><span data-ttu-id="6fefc-108">在 IIS 7.0 或7.5 中创建虚拟目录</span><span class="sxs-lookup"><span data-stu-id="6fefc-108">To create a virtual directory in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="6fefc-109">从 "**开始**" 菜单中, 单击 "**运行**", 然后键入**INETMGR**以打开 Internet Information Services (IIS) mmc 管理单元。</span><span class="sxs-lookup"><span data-stu-id="6fefc-109">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="6fefc-110">在左侧窗格中, 展开包含计算机名称的节点, 然后展开 "**站点**" 节点。</span><span class="sxs-lookup"><span data-stu-id="6fefc-110">In the left pane, expand the node with the computer's name, and then expand the **Sites** node.</span></span>  
  
3. <span data-ttu-id="6fefc-111">右键单击 "**默认**网站", 然后选择 "**添加应用程序**" 以打开 "**添加应用程序" 窗口**。</span><span class="sxs-lookup"><span data-stu-id="6fefc-111">Right-click **Default Web Site**, and then select **Add Application** to open the **Add Application window**.</span></span>  
  
4. <span data-ttu-id="6fefc-112">在窗口中, 键入`servicemodelsamples`作为要创建的虚拟目录的别名。</span><span class="sxs-lookup"><span data-stu-id="6fefc-112">In the window, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="6fefc-113">创建以下目录：%SystemDrive%\inetpub\wwwroot\servicemodelsamples</span><span class="sxs-lookup"><span data-stu-id="6fefc-113">Create the following directory: %SystemDrive%\inetpub\wwwroot\servicemodelsamples</span></span>  
  
6. <span data-ttu-id="6fefc-114">将物理路径设置为 %SystemDrive%\inetpub\wwwroot\servicemodelsamples。</span><span class="sxs-lookup"><span data-stu-id="6fefc-114">Set the physical path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  <span data-ttu-id="6fefc-115">大多数 WCF 示例在生成后都将服务可执行文件复制到此位置。</span><span class="sxs-lookup"><span data-stu-id="6fefc-115">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
7. <span data-ttu-id="6fefc-116">单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="6fefc-116">Click **OK**.</span></span> <span data-ttu-id="6fefc-117">现在已为 WCF 示例创建 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6fefc-117">The Web application is now created for the WCF samples.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6fefc-118">此任务仅需执行一次, 因为所有 WCF 示例都使用相同的 servicemodelsamples Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6fefc-118">This task must be performed only once, because all of the WCF samples use the same servicemodelsamples Web application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6fefc-119">在本文档中，术语`virtual directory`和 `Web application`是同义词。</span><span class="sxs-lookup"><span data-stu-id="6fefc-119">For the purpose of this documentation, the term `virtual directory` is synonymous with `Web application`.</span></span>  
  
     <span data-ttu-id="6fefc-120">除了创建虚拟目录以外, 还必须设置其属性以使 WCF 服务能够运行。</span><span class="sxs-lookup"><span data-stu-id="6fefc-120">In addition to creating the virtual directory, you must also set its properties to enable WCF services to run.</span></span> <span data-ttu-id="6fefc-121">有关详细信息，请参见以下内容。</span><span class="sxs-lookup"><span data-stu-id="6fefc-121">See below for details.</span></span>  
  
#### <a name="to-create-a-virtual-directory-in-iis-51-or-60"></a><span data-ttu-id="6fefc-122">在 IIS 5.1 或 6.0 中创建虚拟目录</span><span class="sxs-lookup"><span data-stu-id="6fefc-122">To create a virtual directory in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="6fefc-123">打开 "命令提示符" 窗口并`start inetmgr`键入以打开 Internet Information Services (IIS) mmc 管理单元。</span><span class="sxs-lookup"><span data-stu-id="6fefc-123">Open a command prompt window and type `start inetmgr` to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2. <span data-ttu-id="6fefc-124">在左侧窗格中, 展开包含计算机名称的节点, 然后展开 "网站" 节点 。</span><span class="sxs-lookup"><span data-stu-id="6fefc-124">In the left pane, expand the node with the computer's name, and then expand the **Web Sites** node.</span></span>  
  
3. <span data-ttu-id="6fefc-125">右键单击 "**默认**网站", 然后选择 "**新建虚拟目录",** 打开 "虚拟目录创建向导"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-125">Right-click **Default Web Site** and select **New, Virtual Directory** to open the Virtual Directory Creation wizard.</span></span>  
  
4. <span data-ttu-id="6fefc-126">在向导中, 键入`servicemodelsamples`作为要创建的虚拟目录的别名。</span><span class="sxs-lookup"><span data-stu-id="6fefc-126">In the wizard, type `servicemodelsamples` as the alias for the virtual directory that you are creating.</span></span>  
  
5. <span data-ttu-id="6fefc-127">将路径设置为 %SystemDrive%\inetpub\wwwroot\servicemodelsamples。</span><span class="sxs-lookup"><span data-stu-id="6fefc-127">Set the path to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span> <span data-ttu-id="6fefc-128">大多数 WCF 示例在生成后都将服务可执行文件复制到此位置。</span><span class="sxs-lookup"><span data-stu-id="6fefc-128">Most of the WCF samples copy service executable files to this location when built.</span></span>  
  
6. <span data-ttu-id="6fefc-129">单击 **“下一步”** 。</span><span class="sxs-lookup"><span data-stu-id="6fefc-129">Click **Next**.</span></span>  
  
7. <span data-ttu-id="6fefc-130">默认情况下，已选中以下复选框：</span><span class="sxs-lookup"><span data-stu-id="6fefc-130">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="6fefc-131">**Read**</span><span class="sxs-lookup"><span data-stu-id="6fefc-131">**Read**</span></span>  
  
    - <span data-ttu-id="6fefc-132">**运行脚本 (如 ASP)**</span><span class="sxs-lookup"><span data-stu-id="6fefc-132">**Run scripts (such as ASP)**</span></span>  
  
8. <span data-ttu-id="6fefc-133">单击 "**下一步**", 然后单击 "**完成**" 以完成向导。</span><span class="sxs-lookup"><span data-stu-id="6fefc-133">Click **Next**, and then click **Finish** to complete the wizard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6fefc-134">此任务仅需执行一次, 因为所有 WCF 示例都使用相同的 servicemodelsamples 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="6fefc-134">This task must be performed only once because all of the WCF samples use the same servicemodelsamples virtual directory.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-70-or-75"></a><span data-ttu-id="6fefc-135">在 IIS 7.0 或7.5 中设置附加虚拟目录属性</span><span class="sxs-lookup"><span data-stu-id="6fefc-135">To set additional virtual directory properties in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="6fefc-136">单击 servicemodelsamples 节点。</span><span class="sxs-lookup"><span data-stu-id="6fefc-136">Click the servicemodelsamples node.</span></span> <span data-ttu-id="6fefc-137">窗口的底部列有两个视图。</span><span class="sxs-lookup"><span data-stu-id="6fefc-137">Along the bottom of the window, two views are listed.</span></span> <span data-ttu-id="6fefc-138">如果尚未选择 "**功能视图**", 请选择它。</span><span class="sxs-lookup"><span data-stu-id="6fefc-138">Select **Features View** if it isn’t already selected.</span></span>  
  
2. <span data-ttu-id="6fefc-139">双击**目录浏览**条目。</span><span class="sxs-lookup"><span data-stu-id="6fefc-139">Double-click the entry for **Directory Browsing**.</span></span>  
  
3. <span data-ttu-id="6fefc-140">在 "操作" 窗格中, 选择 "**启用**" 选项。</span><span class="sxs-lookup"><span data-stu-id="6fefc-140">In the Actions pane, select the **Enable** option.</span></span> <span data-ttu-id="6fefc-141">这样，您将能够使用 Internet Explorer 访问目录的目录，这在调试服务时将很有帮助。</span><span class="sxs-lookup"><span data-stu-id="6fefc-141">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
 <span data-ttu-id="6fefc-142">最后，您必须设置 servicemodelsamples 文件夹的安全属性，以允许其他人访问该文件夹。</span><span class="sxs-lookup"><span data-stu-id="6fefc-142">Finally, you must set the security properties of the servicemodelsamples folder to allow it to be accessed by others.</span></span> <span data-ttu-id="6fefc-143">有关详细信息，请参见以下内容。</span><span class="sxs-lookup"><span data-stu-id="6fefc-143">See below for details.</span></span>  
  
#### <a name="to-set-additional-virtual-directory-properties-in-iis-51-or-60"></a><span data-ttu-id="6fefc-144">在 IIS 5.1 或 6.0 中设置附加虚拟目录属性</span><span class="sxs-lookup"><span data-stu-id="6fefc-144">To set additional virtual directory properties in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="6fefc-145">右键单击 "servicemodelsamples" 节点, 然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-145">Right-click the servicemodelsamples node and then click **Properties**.</span></span>  
  
2. <span data-ttu-id="6fefc-146">默认情况下，已选中以下复选框：</span><span class="sxs-lookup"><span data-stu-id="6fefc-146">By default, the following check boxes are selected:</span></span>  
  
    - <span data-ttu-id="6fefc-147">**Read**</span><span class="sxs-lookup"><span data-stu-id="6fefc-147">**Read**</span></span>  
  
    - <span data-ttu-id="6fefc-148">**日志访问**</span><span class="sxs-lookup"><span data-stu-id="6fefc-148">**Log visits**</span></span>  
  
    - <span data-ttu-id="6fefc-149">**为此资源编制索引**</span><span class="sxs-lookup"><span data-stu-id="6fefc-149">**Index this resource**</span></span>  
  
3. <span data-ttu-id="6fefc-150">选中 "**目录浏览**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="6fefc-150">Select the **Directory browsing** check box.</span></span> <span data-ttu-id="6fefc-151">这样，您将能够使用 Internet Explorer 访问目录的目录，这在调试服务时将很有帮助。</span><span class="sxs-lookup"><span data-stu-id="6fefc-151">This enables you to access the directory of the directory by using Internet Explorer, which helps when debugging a service.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-70-or-75"></a><span data-ttu-id="6fefc-152">在 IIS 7.0 或7.5 中设置文件夹的安全属性</span><span class="sxs-lookup"><span data-stu-id="6fefc-152">To set security properties of the folder in IIS 7.0 or 7.5</span></span>  
  
1. <span data-ttu-id="6fefc-153">定位到 %SystemDrive%\inetpub\wwwroot\servicemodelsamples。</span><span class="sxs-lookup"><span data-stu-id="6fefc-153">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="6fefc-154">右键单击 servicemodelsamples 文件夹, 然后单击 "**共享**" 或 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-154">Right-click the servicemodelsamples folder and click **Share** or **Share With**.</span></span>  
  
3. <span data-ttu-id="6fefc-155">单击 "**添加**" 按钮左侧的向下箭头。</span><span class="sxs-lookup"><span data-stu-id="6fefc-155">Click the down arrow to the left of the **Add** button.</span></span>  
  
4. <span data-ttu-id="6fefc-156">选择 "**查找**" 条目。</span><span class="sxs-lookup"><span data-stu-id="6fefc-156">Select the **Find** entry.</span></span> <span data-ttu-id="6fefc-157">此时将打开 "**选择用户或组**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="6fefc-157">The **Select Users or Groups** window opens.</span></span>  
  
5. <span data-ttu-id="6fefc-158">单击 **“高级”** 。</span><span class="sxs-lookup"><span data-stu-id="6fefc-158">Click **Advanced**.</span></span>  
  
6. <span data-ttu-id="6fefc-159">单击 "**位置**"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-159">Click **Locations**.</span></span> <span data-ttu-id="6fefc-160">此时会打开 "**位置**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="6fefc-160">The **Locations** window is now open.</span></span>  
  
7. <span data-ttu-id="6fefc-161">选择对应于所使用计算机的项。</span><span class="sxs-lookup"><span data-stu-id="6fefc-161">Select the entry for the computer being used.</span></span> <span data-ttu-id="6fefc-162">请务必选择本地计算机，而不是对应于所列出的任何域或网络的项。</span><span class="sxs-lookup"><span data-stu-id="6fefc-162">It is important to select the local computer and not an entry for any domains or networks that are listed.</span></span> <span data-ttu-id="6fefc-163">选择计算机后, 单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="6fefc-163">After you have selected the computer, click **OK**.</span></span>  
  
8. <span data-ttu-id="6fefc-164">单击 "**立即查找**"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-164">Click **Find Now**.</span></span> <span data-ttu-id="6fefc-165">此操作将用与本地计算机关联的对象填充搜索结果。</span><span class="sxs-lookup"><span data-stu-id="6fefc-165">This populates the search results with objects associated with the local computer.</span></span>  
  
9. <span data-ttu-id="6fefc-166">在 "**名称 (相对可分辨名称)** " 列中查找 " **IIS_IUSRS** " 条目。</span><span class="sxs-lookup"><span data-stu-id="6fefc-166">Find the **IIS_IUSRS** entry in the **Name (Relative Distinguished Name)** column.</span></span> <span data-ttu-id="6fefc-167">选择该条目, 然后单击 **"确定"** 以关闭 "搜索结果" 窗口。</span><span class="sxs-lookup"><span data-stu-id="6fefc-167">Select that entry and click **OK** to close the search results window.</span></span>  
  
10. <span data-ttu-id="6fefc-168">单击 **"确定"** 以关闭 "**选择用户或组**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="6fefc-168">Click **OK** to close the **Select Users or Groups** window.</span></span>  
  
11. <span data-ttu-id="6fefc-169">单击 "**共享**" 以保存更改。</span><span class="sxs-lookup"><span data-stu-id="6fefc-169">Click **Share** to persist the changes.</span></span>  
  
12. <span data-ttu-id="6fefc-170">完成启用共享的更改后, 单击 "**完成**" 关闭 "**文件共享**" 窗口。</span><span class="sxs-lookup"><span data-stu-id="6fefc-170">After the changes to enable sharing are complete, click **Done** to close the **File Sharing** window.</span></span>  
  
#### <a name="to-set-security-properties-of-the-folder-in-iis-51-or-60"></a><span data-ttu-id="6fefc-171">在 IIS 5.1 或 6.0 中设置文件夹的安全属性</span><span class="sxs-lookup"><span data-stu-id="6fefc-171">To set security properties of the folder in IIS 5.1 or 6.0</span></span>  
  
1. <span data-ttu-id="6fefc-172">定位到 %SystemDrive%\inetpub\wwwroot\servicemodelsamples。</span><span class="sxs-lookup"><span data-stu-id="6fefc-172">Navigate to %SystemDrive%\inetpub\wwwroot\servicemodelsamples.</span></span>  
  
2. <span data-ttu-id="6fefc-173">右键单击**servicemodelsamples**文件夹, 然后单击 "**共享和安全"。**</span><span class="sxs-lookup"><span data-stu-id="6fefc-173">Right-click the **servicemodelsamples** folder and then click **Sharing and Security.**</span></span>  
  
3. <span data-ttu-id="6fefc-174">单击 **“安全”** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6fefc-174">Click the **Security** tab.</span></span>  
  
4. <span data-ttu-id="6fefc-175">如果使用的是 IIS 6.0, 请在 "**组或用户名**" 框中检查是否列出了 " **Internet 来宾帐户**"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-175">If you are using IIS 6.0, in the **Group or user names** box, check whether **Internet Guest Account** is listed.</span></span>  
  
     <span data-ttu-id="6fefc-176">如果该帐户未列出：</span><span class="sxs-lookup"><span data-stu-id="6fefc-176">If it is not listed:</span></span>  
  
    1. <span data-ttu-id="6fefc-177">单击“开始”，然后单击“控制面板”。</span><span class="sxs-lookup"><span data-stu-id="6fefc-177">Click **Start** and then click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="6fefc-178">如果看不到 "**用户帐户**" 图标, 请单击 "**切换到分类视图**"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-178">If you do not see the **User Accounts** icon, click **Switch to Category View**.</span></span>  
  
    3. <span data-ttu-id="6fefc-179">单击 "**用户帐户**" 图标。</span><span class="sxs-lookup"><span data-stu-id="6fefc-179">Click the **User Accounts** icon.</span></span>  
  
    4. <span data-ttu-id="6fefc-180">在 "或选择一个控制面板图标下, 单击"**用户帐户**"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-180">Under "or pick a Control Panel icon," click **User Accounts**.</span></span>  
  
    5. <span data-ttu-id="6fefc-181">在 "**用户帐户**" 对话框中, 单击 "**高级**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="6fefc-181">In the **User Accounts** dialog box, click the **Advanced** tab.</span></span>  
  
    6. <span data-ttu-id="6fefc-182">单击 **“高级”** 。</span><span class="sxs-lookup"><span data-stu-id="6fefc-182">Click **Advanced**.</span></span>  
  
    7. <span data-ttu-id="6fefc-183">在 "**本地用户和组**" 对话框中, 单击以展开 "**用户**" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6fefc-183">In the **Local Users and Groups** dialog box, click to expand the **Users** folder.</span></span>  
  
    8. <span data-ttu-id="6fefc-184">在右侧窗格中, 双击 " **Internet 来宾帐户**"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-184">In the right pane, double-click **Internet Guest Account**.</span></span>  
  
    9. <span data-ttu-id="6fefc-185">在 "**属性**" 对话框中, 复制用作 Internet 来宾帐户的名称。</span><span class="sxs-lookup"><span data-stu-id="6fefc-185">In the **Properties** dialog box, copy the name used as the Internet guest account.</span></span> <span data-ttu-id="6fefc-186">默认情况下，该名称以“USR_”开头，后跟计算机的名称。</span><span class="sxs-lookup"><span data-stu-id="6fefc-186">By default, the name begins with "USR_" followed by the name of the computer.</span></span>  
  
    10. <span data-ttu-id="6fefc-187">关闭“属性” 对话框。</span><span class="sxs-lookup"><span data-stu-id="6fefc-187">Close the **Properties** dialog box.</span></span>  
  
    11. <span data-ttu-id="6fefc-188">关闭 "**本地用户和组**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="6fefc-188">Close the **Local Users and Groups** dialog box.</span></span>  
  
    12. <span data-ttu-id="6fefc-189">关闭 "**用户帐户**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="6fefc-189">Close the **User Accounts** dialog box.</span></span>  
  
    13. <span data-ttu-id="6fefc-190">关闭 "其他**用户帐户**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="6fefc-190">Close the other **User Accounts** dialog box.</span></span>  
  
    14. <span data-ttu-id="6fefc-191">在 " **Servicemodelsamples 属性**" 对话框中的 "**安全**" 选项卡上, 单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-191">In the **servicemodelsamples Properties** dialog box, on the **Security** tab, click **Add**.</span></span>  
  
    15. <span data-ttu-id="6fefc-192">键入后跟反斜杠的计算机名称, 然后粘贴 Internet 用户帐户的名称, 例如, myMachineName\\% InternetGuestAccountName%</span><span class="sxs-lookup"><span data-stu-id="6fefc-192">Type the name of the computer followed by a backslash, then paste the name of the Internet user account, for example, myMachineName\\%InternetGuestAccountName%</span></span>  
  
    16. <span data-ttu-id="6fefc-193">单击 "**检查名称**" 以验证添加。</span><span class="sxs-lookup"><span data-stu-id="6fefc-193">Click **Check Names** to verify the addition.</span></span> <span data-ttu-id="6fefc-194">如果名称有效，名称将变为全大写并带下划线的形式。</span><span class="sxs-lookup"><span data-stu-id="6fefc-194">If it is valid, the name is in all capital letters and is underlined.</span></span>  
  
5. <span data-ttu-id="6fefc-195">对于 IIS 6.0, 还要检查 "**组或用户名**" 框中是否列出了 "网络服务"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-195">For IIS 6.0, also check that NETWORK SERVICE is listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="6fefc-196">如果“NETWORK SERVICE”未列出：</span><span class="sxs-lookup"><span data-stu-id="6fefc-196">If NETWORK SERVICE is not listed:</span></span>  
  
    1. <span data-ttu-id="6fefc-197">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="6fefc-197">Click **Add**.</span></span>  
  
    2. <span data-ttu-id="6fefc-198">在 "**选择用户或组**" 对话框中, 键入计算机名称, 后跟反斜杠。</span><span class="sxs-lookup"><span data-stu-id="6fefc-198">In the **Select Users or Groups** dialog box, type the name of the computer followed by a backslash.</span></span>  
  
    3. <span data-ttu-id="6fefc-199">在反斜杠后键入**service** (不带空格)。</span><span class="sxs-lookup"><span data-stu-id="6fefc-199">Type **service** after the backslash (no space).</span></span>  
  
    4. <span data-ttu-id="6fefc-200">单击 "**检查名称**"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-200">Click **Check names**.</span></span>  
  
    5. <span data-ttu-id="6fefc-201">如果找到多个名称, 请选择 "**网络服务**", 并单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="6fefc-201">If multiple names are found, select **NETWORK SERVICE** and click **OK**.</span></span>  
  
    6. <span data-ttu-id="6fefc-202">单击 **"确定"** 以关闭 "**选择用户或组**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="6fefc-202">Click **OK** to close the **Select Users or Groups** dialog box.</span></span>  
  
6. <span data-ttu-id="6fefc-203">如果使用的是带有 IIS 5.1 的 Windows XP SP2, 请检查 "**组名或用户名**" 框中是否列出了 "Internet 来宾帐户" 和 "ASPNET"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-203">If you are using Windows XP SP2 with IIS 5.1, check that both Internet Guest Account and ASPNET are listed in the **Group or user names** box.</span></span>  
  
     <span data-ttu-id="6fefc-204">请注意, ASPNET 用户可能是内置**用户**安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="6fefc-204">Note that the ASPNET user may be a member of the built-in **Users** security group.</span></span> <span data-ttu-id="6fefc-205">如果是这样, 则在对话框中列出 "**用户**" 组时, 无需将其作为单独的项添加到允许用户列表中。</span><span class="sxs-lookup"><span data-stu-id="6fefc-205">If so, then if the **Users** group is listed in the dialog box, you do not need to add it as a separate item to the list of permitted users.</span></span>  
  
     <span data-ttu-id="6fefc-206">若要检查是否是**用户**安全组的成员, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="6fefc-206">To check if ASPNET is part of the **Users** security group:</span></span>  
  
    1. <span data-ttu-id="6fefc-207">在 "**开始**" 菜单上, 单击 "**控制面板"** 。</span><span class="sxs-lookup"><span data-stu-id="6fefc-207">On the **Start** menu, click **Control Panel**.</span></span>  
  
    2. <span data-ttu-id="6fefc-208">单击 "**用户帐户**" 图标。</span><span class="sxs-lookup"><span data-stu-id="6fefc-208">Click the **User Accounts** icon.</span></span>  
  
    3. <span data-ttu-id="6fefc-209">在 "**组**" 列中, 检查**ASPNET**的值是否为 "用户"。</span><span class="sxs-lookup"><span data-stu-id="6fefc-209">In the **Group** column, check that the value for **ASPNET** is "Users."</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fefc-210">请参阅</span><span class="sxs-lookup"><span data-stu-id="6fefc-210">See also</span></span>

- [<span data-ttu-id="6fefc-211">Internet 信息服务承载说明</span><span class="sxs-lookup"><span data-stu-id="6fefc-211">Internet Information Service Hosting Instructions</span></span>](../../../../docs/framework/wcf/samples/internet-information-service-hosting-instructions.md)
