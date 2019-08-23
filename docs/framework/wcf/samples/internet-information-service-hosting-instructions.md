---
title: Internet 信息服务承载说明
ms.date: 03/30/2017
ms.assetid: 959a21c8-9d9d-4757-b255-4e57793ae9d6
ms.openlocfilehash: 226b47bfd90dc4cffb0a364a804016043cc25d02
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929115"
---
# <a name="internet-information-service-hosting-instructions"></a><span data-ttu-id="2795a-102">Internet 信息服务承载说明</span><span class="sxs-lookup"><span data-stu-id="2795a-102">Internet Information Service Hosting Instructions</span></span>
<span data-ttu-id="2795a-103">若要运行由 Internet 信息服务 (IIS) 承载的示例，必须确保 IIS 已正确安装且正在运行。</span><span class="sxs-lookup"><span data-stu-id="2795a-103">To run the samples that are hosted by Internet Information Services (IIS), you must make sure that IIS is properly installed and is running.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-server-2008-r2"></a><span data-ttu-id="2795a-104">在 Windows Server 2008 R2 上安装 IIS 7.5 版</span><span class="sxs-lookup"><span data-stu-id="2795a-104">To install IIS version 7.5 on Windows Server 2008 R2</span></span>  
  
1. <span data-ttu-id="2795a-105">在**服务器管理器**中, 选择 "**角色"。**</span><span class="sxs-lookup"><span data-stu-id="2795a-105">From **Server Manager**, select **Roles.**</span></span> <span data-ttu-id="2795a-106">在 "**角色摘要**" 下, 单击 "**添加角色**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-106">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="2795a-107">单击 "**下一步**" 以显示 "**选择服务器角色**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2795a-107">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="2795a-108">从 "**角色**" 列表中选择 "**应用程序服务器**", 然后单击 "**下一步**" 两次, 以显示应用程序服务器角色的 "**选择角色服务**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2795a-108">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="2795a-109">选中 " **Web 服务器 (IIS)** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="2795a-109">Select the **Web Server (IIS)** check box.</span></span> <span data-ttu-id="2795a-110">如果系统提示你安装其他角色服务和功能, 请单击 "**添加所需功能**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-110">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="2795a-111">单击 "**下一步**" 两次, 显示 Web 服务器 (IIS) 角色的 "**选择角色服务**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2795a-111">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="2795a-112">展开 "**管理工具**", 然后展开 " **IIS 6 管理兼容性**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-112">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="2795a-113">选择 " **IIS 6 脚本工具**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-113">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="2795a-114">如果系统提示你安装其他角色服务和功能, 请单击 "**添加必需的角色服务**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-114">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="2795a-115">单击 **“下一步”** 。</span><span class="sxs-lookup"><span data-stu-id="2795a-115">Click **Next**.</span></span>  
  
6. <span data-ttu-id="2795a-116">如果选择的摘要正确, 请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-116">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="2795a-117">安装完成后, 单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-117">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-75-on-windows-7"></a><span data-ttu-id="2795a-118">在 Windows 7 上安装 IIS 7.5 版</span><span class="sxs-lookup"><span data-stu-id="2795a-118">To install IIS version 7.5 on Windows 7</span></span>  
  
1. <span data-ttu-id="2795a-119">单击 "**开始**", 然后单击 **"控制面板**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-119">Click **Start**, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="2795a-120">打开 "**程序**" 组。</span><span class="sxs-lookup"><span data-stu-id="2795a-120">Open the **Programs** group.</span></span>  
  
3. <span data-ttu-id="2795a-121">在 "**程序和功能**" 下, 单击 **"打开或关闭 Windows 功能**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-121">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="2795a-122">将显示 "**用户帐户控制**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2795a-122">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="2795a-123">单击 **“继续”** 。</span><span class="sxs-lookup"><span data-stu-id="2795a-123">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="2795a-124">将显示 " **Windows 功能**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2795a-124">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="2795a-125">展开标记为 " **Internet Information Services**" 的项。</span><span class="sxs-lookup"><span data-stu-id="2795a-125">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="2795a-126">展开标记为 "**万维网服务**" 的项。</span><span class="sxs-lookup"><span data-stu-id="2795a-126">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="2795a-127">展开标记为 "**应用程序开发功能**" 的项。</span><span class="sxs-lookup"><span data-stu-id="2795a-127">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="2795a-128">请确保以下各项处于选中状态：</span><span class="sxs-lookup"><span data-stu-id="2795a-128">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="2795a-129">**.NET 扩展性**</span><span class="sxs-lookup"><span data-stu-id="2795a-129">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="2795a-130">**ASP.NET 2.0**</span><span class="sxs-lookup"><span data-stu-id="2795a-130">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="2795a-131">**ISAPI 扩展**</span><span class="sxs-lookup"><span data-stu-id="2795a-131">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="2795a-132">**ISAPI 筛选器**</span><span class="sxs-lookup"><span data-stu-id="2795a-132">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="2795a-133">在标记为 "**万维网服务**" 的项下, 展开 "**常见 Http 功能**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-133">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
10. <span data-ttu-id="2795a-134">请确保选择 "**静态内容**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-134">Make sure **Static Content** is selected.</span></span>  
  
11. <span data-ttu-id="2795a-135">在标记为 "**万维网服务**" 的项下, 展开 "**安全性**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-135">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
12. <span data-ttu-id="2795a-136">请确保已选择 " **Windows 身份验证**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-136">Make sure that **Windows Authentication** is selected.</span></span>  
  
13. <span data-ttu-id="2795a-137">在**Internet Information Services**目录下, 展开标记为 " **Web 管理工具**" 的项, 然后选择 " **IIS 管理控制台**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-137">Under the **Internet Information Services** directory, expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
14. <span data-ttu-id="2795a-138">展开标记为 " **iis 6 管理兼容性**" 的项, 然后选择 " **Iis 6 脚本工具**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-138">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="2795a-139">在**Internet Information Services**目录下, 展开标记为 " **Microsoft .NET Framework 3.5.1**" 的项, 然后选择 " **Windows Communication Foundation Http 激活**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-139">Under the **Internet Information Services** directory, expand the item labeled **Microsoft .NET Framework 3.5.1**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="2795a-140">单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="2795a-140">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-server-2008"></a><span data-ttu-id="2795a-141">在 Windows Server 2008 上安装 IIS 7.0 版</span><span class="sxs-lookup"><span data-stu-id="2795a-141">To install IIS version 7.0 on Windows Server 2008</span></span>  
  
1. <span data-ttu-id="2795a-142">在**服务器管理器**中, 选择 "**角色**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-142">From **Server Manager**, select **Roles**.</span></span> <span data-ttu-id="2795a-143">在 "**角色摘要**" 下, 单击 "**添加角色**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-143">Under **Roles Summary**, click **Add Roles**.</span></span>  
  
2. <span data-ttu-id="2795a-144">单击 "**下一步**" 以显示 "**选择服务器角色**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2795a-144">Click **Next** to display the **Select Server Roles** dialog.</span></span>  
  
3. <span data-ttu-id="2795a-145">从 "**角色**" 列表中选择 "**应用程序服务器**", 然后单击 "**下一步**" 两次, 以显示应用程序服务器角色的 "**选择角色服务**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2795a-145">Select **Application Server** from the **Roles** list, and then click **Next** twice to display the **Select Role Services** dialog for the Application Server role.</span></span>  
  
4. <span data-ttu-id="2795a-146">选中 " **Web 服务器 (IIS)** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="2795a-146">Select **Web Server (IIS)** check box.</span></span> <span data-ttu-id="2795a-147">如果系统提示你安装其他角色服务和功能, 请单击 "**添加所需功能**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-147">If you are prompted to install additional role services and features, click **Add Required Features**.</span></span> <span data-ttu-id="2795a-148">单击 "**下一步**" 两次, 显示 Web 服务器 (IIS) 角色的 "**选择角色服务**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2795a-148">Click **Next** twice to display the **Select Role Services** dialog for the Web Server (IIS) role.</span></span>  
  
5. <span data-ttu-id="2795a-149">展开 "**管理工具**", 然后展开 " **IIS 6 管理兼容性**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-149">Expand **Management Tools**, and then expand **IIS 6 Management Compatibility**.</span></span> <span data-ttu-id="2795a-150">选择 " **IIS 6 脚本工具**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-150">Select **IIS 6 Scripting Tools**.</span></span> <span data-ttu-id="2795a-151">如果系统提示你安装其他角色服务和功能, 请单击 "**添加必需的角色服务**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-151">If you are prompted to install additional role services and features, click **Add Required Role Services**.</span></span> <span data-ttu-id="2795a-152">单击 **“下一步”** 。</span><span class="sxs-lookup"><span data-stu-id="2795a-152">Click **Next**.</span></span>  
  
6. <span data-ttu-id="2795a-153">如果选择的摘要正确, 请单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-153">If the summary of selections is correct, click **Install**.</span></span>  
  
7. <span data-ttu-id="2795a-154">安装完成后, 单击 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-154">When installation completes, click **Close**.</span></span>  
  
### <a name="to-install-iis-version-70-on-windows-vista"></a><span data-ttu-id="2795a-155">在 Windows Vista 上安装 IIS 7.0 版</span><span class="sxs-lookup"><span data-stu-id="2795a-155">To install IIS version 7.0 on Windows Vista</span></span>  
  
1. <span data-ttu-id="2795a-156">单击“开始”，然后单击“控制面板”。</span><span class="sxs-lookup"><span data-stu-id="2795a-156">Click Start, and then click Control Panel.</span></span>  
  
2. <span data-ttu-id="2795a-157">选择 "**程序**" 组。</span><span class="sxs-lookup"><span data-stu-id="2795a-157">Select the **Programs** group.</span></span>  
  
3. <span data-ttu-id="2795a-158">在 "**程序和功能**" 下, 单击 **"打开或关闭 Windows 功能**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-158">Under **Programs and Features**, click **Turn Windows Features on or off**.</span></span>  
  
4. <span data-ttu-id="2795a-159">将显示 "**用户帐户控制**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2795a-159">The **User Account Control** dialog is displayed.</span></span> <span data-ttu-id="2795a-160">单击 **“继续”** 。</span><span class="sxs-lookup"><span data-stu-id="2795a-160">Click **Continue**.</span></span>  
  
5. <span data-ttu-id="2795a-161">将显示 " **Windows 功能**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="2795a-161">The **Windows Features** dialog is displayed.</span></span> <span data-ttu-id="2795a-162">展开标记为 " **Internet Information Services**" 的项。</span><span class="sxs-lookup"><span data-stu-id="2795a-162">Expand the item labeled **Internet Information Services**.</span></span>  
  
6. <span data-ttu-id="2795a-163">展开标记为 "**万维网服务**" 的项。</span><span class="sxs-lookup"><span data-stu-id="2795a-163">Expand the item labeled **World Wide Web Services**.</span></span>  
  
7. <span data-ttu-id="2795a-164">展开标记为 "**应用程序开发功能**" 的项。</span><span class="sxs-lookup"><span data-stu-id="2795a-164">Expand the item labeled **Application Development Features**.</span></span>  
  
8. <span data-ttu-id="2795a-165">请确保以下各项处于选中状态：</span><span class="sxs-lookup"><span data-stu-id="2795a-165">Make sure the following items are selected:</span></span>  
  
    1. <span data-ttu-id="2795a-166">**.NET 扩展性**</span><span class="sxs-lookup"><span data-stu-id="2795a-166">**.NET Extensibility**</span></span>  
  
    2. <span data-ttu-id="2795a-167">**ASP.NET 2.0**</span><span class="sxs-lookup"><span data-stu-id="2795a-167">**ASP.NET**</span></span>  
  
    3. <span data-ttu-id="2795a-168">**ISAPI 扩展**</span><span class="sxs-lookup"><span data-stu-id="2795a-168">**ISAPI Extensions**</span></span>  
  
    4. <span data-ttu-id="2795a-169">**ISAPI 筛选器**</span><span class="sxs-lookup"><span data-stu-id="2795a-169">**ISAPI Filters**</span></span>  
  
9. <span data-ttu-id="2795a-170">展开标记为 " **Web 管理工具**" 的项, 然后选择 " **IIS 管理控制台**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-170">Expand the item labeled **Web Management Tools**, and then select **IIS Management Console**.</span></span>  
  
10. <span data-ttu-id="2795a-171">在标记为 "**万维网服务**" 的项下, 展开 "**常见 Http 功能**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-171">Under the item labeled **World Wide Web Services**, expand **Common Http Features**.</span></span>  
  
11. <span data-ttu-id="2795a-172">请确保选择 "**静态内容**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-172">Make sure **Static Content** is selected.</span></span>  
  
12. <span data-ttu-id="2795a-173">在标记为 "**万维网服务**" 的项下, 展开 "**安全性**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-173">Under the item labeled **World Wide Web Services**, expand **Security**.</span></span>  
  
13. <span data-ttu-id="2795a-174">请确保已选择 " **Windows 身份验证**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-174">Make sure **Windows Authentication** is selected.</span></span>  
  
14. <span data-ttu-id="2795a-175">展开标记为 " **iis 6 管理兼容性**" 的项, 然后选择 " **Iis 6 脚本工具**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-175">Expand the item labeled **IIS 6 Management Compatibility**, and then select **IIS 6 Scripting Tools**.</span></span>  
  
15. <span data-ttu-id="2795a-176">展开标记为**Microsoft .NET Framework 3.0**"的项, 然后选择" **Windows Communication Foundation Http 激活**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-176">Expand the item labeled **Microsoft .NET Framework 3.0**, and then select **Windows Communication Foundation Http Activation**.</span></span>  
  
16. <span data-ttu-id="2795a-177">单击 **“确定”** 。</span><span class="sxs-lookup"><span data-stu-id="2795a-177">Click **OK**.</span></span>  
  
### <a name="to-install-iis-version-60-on-windows-server-2003"></a><span data-ttu-id="2795a-178">在 Windows Server 2003 上安装 IIS 6.0 版</span><span class="sxs-lookup"><span data-stu-id="2795a-178">To install IIS version 6.0 on Windows Server 2003</span></span>  
  
1. <span data-ttu-id="2795a-179">从 "**管理您的服务器**" 中, 单击 "**添加或删除角色**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-179">From **Manage Your Server**, click **Add or remove a role**, and then click **Next**.</span></span>  
  
2. <span data-ttu-id="2795a-180">从 "**服务器角色**" 列表中选择 "**应用程序服务器 (IIS, ASP.NET)** ", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-180">Select **Application server (IIS, ASP.NET)** from the **Server Role** list, and then click **Next**.</span></span>  
  
3. <span data-ttu-id="2795a-181">选择 "**启用 ASP.NET** " 复选框, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-181">Select **Enable ASP.NET** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="2795a-182">如果选项摘要正确无误，请单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="2795a-182">If the summary of selections is correct, click Next.</span></span>  
  
### <a name="to-install-iis-version-51-on-windows-xp-with-service-pack-2-and-service-pack-3-installed"></a><span data-ttu-id="2795a-183">在装有 Service Pack 2 和 Service Pack 3 的 Windows XP 上安装 IIS 5.1 版</span><span class="sxs-lookup"><span data-stu-id="2795a-183">To install IIS version 5.1 on Windows XP with Service Pack 2 and Service Pack 3 installed</span></span>  
  
1. <span data-ttu-id="2795a-184">在控制面板中, 单击 "**添加或删除程序**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-184">In Control Panel, click **Add or Remove Programs**.</span></span>  
  
2. <span data-ttu-id="2795a-185">在 "**添加或删除程序**" 对话框中, 单击 "**添加/删除 Windows 组件**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-185">In the **Add or Remove Programs** dialog box, click **Add/Remove Windows Components**.</span></span>  
  
3. <span data-ttu-id="2795a-186">在**Windows 组件向导**中, 选中 " **Internet Information Services (IIS)** " 复选框, 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-186">In the **Windows Components Wizard**, select the **Internet Information Services (IIS)** check box, and then click **Next**.</span></span>  
  
4. <span data-ttu-id="2795a-187">如果显示 "**所需文件**" 对话框, 请插入操作系统安装光盘, 浏览到 i386 文件夹, 然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="2795a-187">If the **Files Needed** dialog box is displayed, insert your operating system installation disc, browse to the i386 folder, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="2795a-188">安装完成后, 单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="2795a-188">When installation completes, click **Finish**.</span></span>  
  
6. <span data-ttu-id="2795a-189">关闭 "**添加或删除程序**" 对话框, 然后关闭 "**控制面板"** 。</span><span class="sxs-lookup"><span data-stu-id="2795a-189">Close the **Add or Remove Programs** dialog box, and then close **Control Panel**.</span></span>  
  
### <a name="to-verify-the-installation-of-iis-and-aspnet"></a><span data-ttu-id="2795a-190">检验 IIS 和 ASP.NET 的安装</span><span class="sxs-lookup"><span data-stu-id="2795a-190">To verify the installation of IIS and ASP.NET</span></span>  
  
1. <span data-ttu-id="2795a-191">将本主题末尾的 HTML 文件保存到 \InetPub\wwwroot 根目录中并将其命名为 Default.aspx。</span><span class="sxs-lookup"><span data-stu-id="2795a-191">Save the HTML file found at the end of this topic in the root \InetPub\wwwroot directory and name it Default.aspx.</span></span>  
  
2. <span data-ttu-id="2795a-192">打开一个浏览器窗口。</span><span class="sxs-lookup"><span data-stu-id="2795a-192">Open a browser window.</span></span>  
  
3. <span data-ttu-id="2795a-193">在`http://localhost/Default.aspx` "地址" 框中键入, 然后按 enter。</span><span class="sxs-lookup"><span data-stu-id="2795a-193">Type `http://localhost/Default.aspx` in the address box, and then press ENTER.</span></span>  
  
4. <span data-ttu-id="2795a-194">应当会出现一个包含“Hello World”文本的网页。</span><span class="sxs-lookup"><span data-stu-id="2795a-194">A Web page with the text "Hello World" should appear.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2795a-195">每次安装 .NET Framework 的新版本时, 必须将 aspnet_isapi 重新注册为 IIS 的 Web 服务扩展。</span><span class="sxs-lookup"><span data-stu-id="2795a-195">Each time you install a new version of the .NET Framework, you must re-register aspnet_isapi as a Web service extension for IIS.</span></span> <span data-ttu-id="2795a-196">为此，发出 `aspnet_regiis –I –enable` 命令。</span><span class="sxs-lookup"><span data-stu-id="2795a-196">To do so, issue the `aspnet_regiis –I –enable` command.</span></span>  
  
## <a name="sample-code"></a><span data-ttu-id="2795a-197">代码示例</span><span class="sxs-lookup"><span data-stu-id="2795a-197">Sample Code</span></span>  
  
```xml  
<html>  
   <body>  
       <form >  
           <h3> Hello World  
           </h3>  
       </form>  
   </body>  
</html>  
```
