---
title: ".NET Framework 部署指南（针对管理员）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- administrator's guide, deploying .NET Framework
- deployment [.NET Framework], administrator's guide
ms.assetid: bee14036-0436-44e8-89f5-4bc61317977a
caps.latest.revision: "40"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3af5e301e57350b72ac0ea50448c7a46ca6c5387
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="net-framework-deployment-guide-for-administrators"></a><span data-ttu-id="20610-102">.NET Framework 部署指南（针对管理员）</span><span class="sxs-lookup"><span data-stu-id="20610-102">.NET Framework Deployment Guide for Administrators</span></span>
<span data-ttu-id="20610-103">本文分步说明系统管理员可以如何使用 Microsoft System Center Configuration Manager 在网络中部署 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 及其系统依赖项。</span><span class="sxs-lookup"><span data-stu-id="20610-103">This step-by-step article describes how a system administrator can deploy the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] and its system dependencies across a network by using Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="20610-104">本文假定所有目标客户端计算机都满足 .NET Framework 的最低要求。</span><span class="sxs-lookup"><span data-stu-id="20610-104">This article assumes that all target client computers meet the minimum requirements for the .NET Framework.</span></span> <span data-ttu-id="20610-105">有关安装 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的软件和硬件要求列表，请参阅[系统需求](../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20610-105">For a list of the software and hardware requirements for installing the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], see [System Requirements](../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20610-106">本文档中提到的软件（包括但不限于 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]、System Center Configuration Manager 和 Active Directory）均受许可条款和条件的约束。</span><span class="sxs-lookup"><span data-stu-id="20610-106">The software referenced in this document, including, without limitation, the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], System Center Configuration Manager, and Active Directory, are each subject to license terms and conditions.</span></span> <span data-ttu-id="20610-107">下列说明假定，软件的适当被许可方已查看并接受此类许可条款和条件。</span><span class="sxs-lookup"><span data-stu-id="20610-107">These instructions assume that such license terms and conditions have been reviewed and accepted by the appropriate licensees of the software.</span></span> <span data-ttu-id="20610-108">这些说明不免除此类许可协议中的任何条款和条件。</span><span class="sxs-lookup"><span data-stu-id="20610-108">These instructions do not waive any of the terms and conditions of such license agreements.</span></span>  
>   
>  <span data-ttu-id="20610-109">有关对 .NET Framework 的支持的信息，请参阅 Microsoft 支持网站上的 [Microsoft .NET Framework 支持生命周期策略](http://go.microsoft.com/fwlink/?LinkId=196607)。</span><span class="sxs-lookup"><span data-stu-id="20610-109">For information about support for the .NET Framework, see [Microsoft .NET Framework Support Lifecycle Policy](http://go.microsoft.com/fwlink/?LinkId=196607) on the Microsoft Support website.</span></span>  
  
 <span data-ttu-id="20610-110">本主题包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="20610-110">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="20610-111">部署过程</span><span class="sxs-lookup"><span data-stu-id="20610-111">The deployment process</span></span>](#the_deployment_process)  
 [<span data-ttu-id="20610-112">部署 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="20610-112">Deploying the .NET Framework</span></span>](#deploying_in_a_test_environment)  
 [<span data-ttu-id="20610-113">创建集合</span><span class="sxs-lookup"><span data-stu-id="20610-113">Create a collection</span></span>](#creating_a_collection)  
 [<span data-ttu-id="20610-114">创建包和程序</span><span class="sxs-lookup"><span data-stu-id="20610-114">Create a package and program</span></span>](#creating_a_package)  
 [<span data-ttu-id="20610-115">选择分发点</span><span class="sxs-lookup"><span data-stu-id="20610-115">Select a distribution point</span></span>](#select_dist_point)  
 [<span data-ttu-id="20610-116">部署包</span><span class="sxs-lookup"><span data-stu-id="20610-116">Deploy the package</span></span>](#deploying_package)  
[<span data-ttu-id="20610-117">资源</span><span class="sxs-lookup"><span data-stu-id="20610-117">Resources</span></span>](#resources)  
[<span data-ttu-id="20610-118">疑难解答</span><span class="sxs-lookup"><span data-stu-id="20610-118">Troubleshooting</span></span>](#troubleshooting)  
  
<a name="the_deployment_process"></a>   
## <a name="the-deployment-process"></a><span data-ttu-id="20610-119">部署过程</span><span class="sxs-lookup"><span data-stu-id="20610-119">The deployment process</span></span>  
 <span data-ttu-id="20610-120">在设置好支持基础结构之后，可以使用 System Center 2012 Configuration Manager 将 .NET Framework 可再发行组件包部署到网络上的计算机。</span><span class="sxs-lookup"><span data-stu-id="20610-120">When you have the supporting infrastructure in place, you use System Center 2012 Configuration Manager to deploy the .NET Framework redistributable package to computers on the network.</span></span> <span data-ttu-id="20610-121">构建基础结构涉及创建并定义 5 个主要区域：集合、软件的包和程序、分发点以及部署。</span><span class="sxs-lookup"><span data-stu-id="20610-121">Building the infrastructure involves creating and defining five primary areas: collections, a package and program for the software, distribution points, and deployments.</span></span>  
  
-   <span data-ttu-id="20610-122">“集合”是将 .NET Framework 部署到的 Configuration Manager 资源（用户、用户组或计算机）组。</span><span class="sxs-lookup"><span data-stu-id="20610-122">**Collections** are groups of Configuration Manager resources, such as users, user groups, or computers, to which the .NET Framework is deployed.</span></span> <span data-ttu-id="20610-123">有关详细信息，请参阅 Configuration Manager 文档库中的 [Configuration Manager 中的集合](http://technet.microsoft.com/library/gg682169.aspx)。</span><span class="sxs-lookup"><span data-stu-id="20610-123">For more information, see [Collections in Configuration Manager](http://technet.microsoft.com/library/gg682169.aspx) in the Configuration Manager documentation library.</span></span>  
  
-   <span data-ttu-id="20610-124">“包和程序”通常表示要安装在客户端计算机上的软件应用程序，但它们还可能包含单个文件、更新，甚至是单个命令。</span><span class="sxs-lookup"><span data-stu-id="20610-124">**Packages and programs** typically represent software applications to be installed on a client computer, but they might also contain individual files, updates, or even individual commands.</span></span> <span data-ttu-id="20610-125">有关详细信息，请参阅 Configuration Manager 文档库中的 [Configuration Manager 中的包和程序](http://technet.microsoft.com/library/gg699369.aspx)。</span><span class="sxs-lookup"><span data-stu-id="20610-125">For more information, see [Packages and Programs in Configuration Manager](http://technet.microsoft.com/library/gg699369.aspx) in the Configuration Manager documentation library.</span></span>  
  
-   <span data-ttu-id="20610-126">“分发点”是存储在客户端计算机上运行软件所需的文件的 Configuration Manager 站点系统角色。</span><span class="sxs-lookup"><span data-stu-id="20610-126">**Distribution points** are Configuration Manager site system roles that store files required for software to run on client computers.</span></span> <span data-ttu-id="20610-127">在 Configuration Manager 客户端收到并处理软件部署时，该客户端会与分发点联系以下载与相应软件关联的内容并开始安装过程。</span><span class="sxs-lookup"><span data-stu-id="20610-127">When the Configuration Manager client receives and processes a software deployment, it contacts a distribution point to download the content associated with the software and to start the installation process.</span></span> <span data-ttu-id="20610-128">有关详细信息，请参阅 Configuration Manager 文档库中的 [Configuration Manager 中的内容管理简介](http://technet.microsoft.com/library/gg682083.aspx)。</span><span class="sxs-lookup"><span data-stu-id="20610-128">For more information, see [Introduction to content Management in Configuration Manager](http://technet.microsoft.com/library/gg682083.aspx) in the Configuration Manager documentation library.</span></span>  
  
-   <span data-ttu-id="20610-129">“部署”指示指定目标集合的相应成员安装软件包。</span><span class="sxs-lookup"><span data-stu-id="20610-129">**Deployments** instruct applicable members of the specified target collection to install the software package.</span></span> <span data-ttu-id="20610-130">有关详细信息，请参阅 Configuration Manager 文档库中的[如何在 Configuration Manager 中部署应用程序](http://technet.microsoft.com/library/gg682082.aspx)。</span><span class="sxs-lookup"><span data-stu-id="20610-130">For more information, see [How to Deploy Applications in Configuration Manager](http://technet.microsoft.com/library/gg682082.aspx) in the Configuration Manager documentation library.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="20610-131">本主题中的过程包含用于创建及部署包和程序的典型设置，可能不包含所有可能的设置。</span><span class="sxs-lookup"><span data-stu-id="20610-131">The procedures in this topic contain typical settings for creating and deploying a package and program, and might not cover all possible settings.</span></span> <span data-ttu-id="20610-132">有关其他 Configuration Manager 部署选项，请参阅 [Configuration Manager 文档库](http://technet.microsoft.com/library/gg682041.aspx)。</span><span class="sxs-lookup"><span data-stu-id="20610-132">For other Configuration Manager deployment options, see the [Configuration Manager Documentation Library](http://technet.microsoft.com/library/gg682041.aspx).</span></span>  
  
<a name="deploying_in_a_test_environment"></a>   
## <a name="deploying-the-net-framework"></a><span data-ttu-id="20610-133">部署 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="20610-133">Deploying the .NET Framework</span></span>  
 <span data-ttu-id="20610-134">你可以使用 System Center 2012 Configuration Manager 部署 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 的无提示安装（用户不与安装过程进行交互）。</span><span class="sxs-lookup"><span data-stu-id="20610-134">You can use System Center 2012 Configuration Manager to deploy a silent installation of the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], where the users do not interact with the installation process.</span></span> <span data-ttu-id="20610-135">请执行这些步骤：</span><span class="sxs-lookup"><span data-stu-id="20610-135">Follow these steps:</span></span>  
  
1.  <span data-ttu-id="20610-136">[创建集合](#creating_a_collection)。</span><span class="sxs-lookup"><span data-stu-id="20610-136">[Create a collection](#creating_a_collection).</span></span>  
  
2.  <span data-ttu-id="20610-137">[为 .NET Framework 可再发行组件创建包和程序](#creating_a_package)。</span><span class="sxs-lookup"><span data-stu-id="20610-137">[Create a package and program for the .NET Framework redistributable](#creating_a_package).</span></span>  
  
3.  <span data-ttu-id="20610-138">[选择分发点](#select_dist_point)。</span><span class="sxs-lookup"><span data-stu-id="20610-138">[Select a distribution point](#select_dist_point).</span></span>  
  
4.  <span data-ttu-id="20610-139">[部署包](#deploying_package)。</span><span class="sxs-lookup"><span data-stu-id="20610-139">[Deploy the package](#deploying_package).</span></span>  
  
<a name="creating_a_collection"></a>   
### <a name="create-a-collection"></a><span data-ttu-id="20610-140">创建集合</span><span class="sxs-lookup"><span data-stu-id="20610-140">Create a collection</span></span>  
 <span data-ttu-id="20610-141">在此步骤中，选择包和程序将部署到的计算机，并将这些计算机组合到一个设备集合中。</span><span class="sxs-lookup"><span data-stu-id="20610-141">In this step, you select the computers to which you will deploy the package and program, and group them into a device collection.</span></span> <span data-ttu-id="20610-142">若要在 Configuration Manager 中创建集合，可使用直接成员身份规则（手动指定集合成员）或查询规则（Configuration Manager 根据你指定的条件确定集合成员）。</span><span class="sxs-lookup"><span data-stu-id="20610-142">To create a collection in Configuration Manager, you can use direct membership rules (where you manually specify the collection members) or query rules (where Configuration Manager determines the collection members based on criteria you specify).</span></span> <span data-ttu-id="20610-143">有关成员身份规则的更多信息，请参阅 Configuration Manager 文档库中的 [Configuration Manager 中的集合简介](http://technet.microsoft.com/library/gg682177.aspx)。</span><span class="sxs-lookup"><span data-stu-id="20610-143">For more information about membership rules, including queries and direct rules, see [Introduction to Collections in Configuration Manager](http://technet.microsoft.com/library/gg682177.aspx) in the Configuration Manager Documentation Library.</span></span>  
  
 <span data-ttu-id="20610-144">创建集合：</span><span class="sxs-lookup"><span data-stu-id="20610-144">To create a collection:</span></span>  
  
1.  <span data-ttu-id="20610-145">在 Configuration Manager 控制台中，选择“资产和符合性”。</span><span class="sxs-lookup"><span data-stu-id="20610-145">In the Configuration Manager console, choose **Assets and Compliance**.</span></span>  
  
2.  <span data-ttu-id="20610-146">在“资产和符合性”工作区中，选择“设备集合”。</span><span class="sxs-lookup"><span data-stu-id="20610-146">In the **Assets and Compliance** workspace, choose **Device Collections**.</span></span>  
  
3.  <span data-ttu-id="20610-147">在“主页”选项卡上的“创建”组中，选择“创建设备集合”。</span><span class="sxs-lookup"><span data-stu-id="20610-147">On the **Home** tab in the **Create** group, choose **Create Device Collection**.</span></span>  
  
4.  <span data-ttu-id="20610-148">在“创建设备集合向导”的“常规”页上，输入集合的名称。</span><span class="sxs-lookup"><span data-stu-id="20610-148">On the **General** page of the **Create Device Collection Wizard**, enter a name for the collection.</span></span>  
  
5.  <span data-ttu-id="20610-149">选择“浏览”以指定限制集合。</span><span class="sxs-lookup"><span data-stu-id="20610-149">Choose **Browse** to specify a limiting collection.</span></span>  
  
6.  <span data-ttu-id="20610-150">在“成员身份规则”页上，选择“添加规则”，然后选择“直接规则”以打开“创建直接成员身份规则向导”。</span><span class="sxs-lookup"><span data-stu-id="20610-150">On the **Membership Rules** page, choose **Add Rule**, and then choose **Direct Rule** to open the **Create Direct Membership Rule Wizard**.</span></span> <span data-ttu-id="20610-151">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="20610-151">Choose **Next**.</span></span>  
  
7.  <span data-ttu-id="20610-152">在“搜索资源”页上的“资源类”列表中，选择“系统资源”。</span><span class="sxs-lookup"><span data-stu-id="20610-152">On the **Search for Resources** page, in the **Resource class** list, choose **System Resource**.</span></span> <span data-ttu-id="20610-153">在“特性名”列表中，选择“名称”。</span><span class="sxs-lookup"><span data-stu-id="20610-153">In the **Attribute name** list, choose **Name**.</span></span> <span data-ttu-id="20610-154">在“值”字段中，键入 `%`，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="20610-154">In the **Value** field, enter `%`, and then choose **Next**.</span></span>  
  
8.  <span data-ttu-id="20610-155">在“选择资源”页上，选中要将 .NET Framework 部署到的每台计算机所对应的复选框。</span><span class="sxs-lookup"><span data-stu-id="20610-155">On the **Select Resources** page, select the check box for each computer that you want to deploy the .NET Framework to.</span></span> <span data-ttu-id="20610-156">选择“下一步”，然后完成向导。</span><span class="sxs-lookup"><span data-stu-id="20610-156">Choose **Next**, and then complete the wizard.</span></span>  
  
9. <span data-ttu-id="20610-157">在“创建设备集合向导”的“成员身份规则”页上，选择“下一步”，然后完成该向导。</span><span class="sxs-lookup"><span data-stu-id="20610-157">On the **Membership Rules** page of the **Create Device Collection Wizard**, choose **Next**, and then complete the wizard.</span></span>  
  
 <span data-ttu-id="20610-158">有关集合的更多信息，请参阅 Configuration Manager 文档库中的 [Configuration Manager 中的集合](http://technet.microsoft.com/library/bb693730.aspx)。</span><span class="sxs-lookup"><span data-stu-id="20610-158">For more information about collections, see [Collections in Configuration Manager](http://technet.microsoft.com/library/bb693730.aspx) in the Configuration Manager Documentation Library.</span></span>  
  
<a name="creating_a_package"></a>   
### <a name="create-a-package-and-program-for-the-net-framework-redistributable-package"></a><span data-ttu-id="20610-159">为 .NET Framework 可再发行组件包创建包和程序</span><span class="sxs-lookup"><span data-stu-id="20610-159">Create a package and program for the .NET Framework redistributable package</span></span>  
 <span data-ttu-id="20610-160">以下步骤为 .NET Framework 可再发行组件手动创建包。</span><span class="sxs-lookup"><span data-stu-id="20610-160">The following steps create a package for the .NET Framework redistributable manually.</span></span> <span data-ttu-id="20610-161">该包包含用于安装 .NET Framework 的指定参数以及要用于将包分发到目标计算机的位置。</span><span class="sxs-lookup"><span data-stu-id="20610-161">The package contains the specified parameters for installing the .NET Framework and the location from where the package will be distributed to the target computers.</span></span>  
  
 <span data-ttu-id="20610-162">创建包：</span><span class="sxs-lookup"><span data-stu-id="20610-162">To create a package:</span></span>  
  
1.  <span data-ttu-id="20610-163">在 Configuration Manager 控制台中，选择“软件库”。</span><span class="sxs-lookup"><span data-stu-id="20610-163">In the Configuration Manager console, choose **Software Library**..</span></span>  
  
2.  <span data-ttu-id="20610-164">在“软件库”工作区中，展开“应用程序管理”，然后选择“包”。</span><span class="sxs-lookup"><span data-stu-id="20610-164">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>  
  
3.  <span data-ttu-id="20610-165">在“主页”选项卡上的“创建”组中，选择“创建包”。</span><span class="sxs-lookup"><span data-stu-id="20610-165">On the **Home** tab, in the **Create** group, choose **Create Package**.</span></span>  
  
4.  <span data-ttu-id="20610-166">在“创建包和程序向导”的“包”页上，输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="20610-166">On the **Package** page of the **Create Package and Program Wizard**, enter the following information:</span></span>  
  
    -   <span data-ttu-id="20610-167">名称：`.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="20610-167">Name: `.NET Framework 4.5`</span></span>  
  
    -   <span data-ttu-id="20610-168">制造商：`Microsoft`</span><span class="sxs-lookup"><span data-stu-id="20610-168">Manufacturer: `Microsoft`</span></span>  
  
    -   <span data-ttu-id="20610-169">语言：</span><span class="sxs-lookup"><span data-stu-id="20610-169">Language.</span></span> `English (US)`  
  
5.  <span data-ttu-id="20610-170">选择“此包包含源文件”，然后选择“浏览”以选择包含 .NET Framework 安装文件的本地或网络文件夹。</span><span class="sxs-lookup"><span data-stu-id="20610-170">Choose **This package contains source files**, and then choose **Browse** to select the local or network folder that contains the .NET Framework installation files.</span></span> <span data-ttu-id="20610-171">在选择该文件夹后，选择“确定”，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="20610-171">When you have selected the folder, choose **OK**, and then choose **Next**.</span></span>  
  
6.  <span data-ttu-id="20610-172">在向导的“程序类型”页上，选择“标准程序”，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="20610-172">On the **Program Type** page of the wizard, choose **Standard Program**, and then choose **Next**.</span></span>  
  
7.  <span data-ttu-id="20610-173">在“创建包和程序向导”的“程序”页上，输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="20610-173">On the **Program** page of the **Create Package and Program Wizard**, enter the following information:</span></span>  
  
    1.  <span data-ttu-id="20610-174">名称：`.NET Framework 4.5`</span><span class="sxs-lookup"><span data-stu-id="20610-174">**Name:** `.NET Framework 4.5`</span></span>  
  
    2.  <span data-ttu-id="20610-175">命令行：`dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT`（这些步骤后的表中描述了命令行选项）</span><span class="sxs-lookup"><span data-stu-id="20610-175">**Command line:** `dotNetFx45_Full_x86_x64.exe /q /norestart /ChainingPackage ADMINDEPLOYMENT` (command-line options are described in the table after these steps)</span></span>  
  
    3.  <span data-ttu-id="20610-176">运行：选择“隐藏”。</span><span class="sxs-lookup"><span data-stu-id="20610-176">**Run:** Choose **Hidden**.</span></span>  
  
    4.  <span data-ttu-id="20610-177">程序可以运行：选择指定程序可以运行（不管用户是否登录）的选项。</span><span class="sxs-lookup"><span data-stu-id="20610-177">**Program can run:** Choose the option that specifies that the program can run regardless of whether a user is logged on.</span></span>  
  
8.  <span data-ttu-id="20610-178">在“需求”页上，选择“下一步”以接受默认值，然后完成该向导。</span><span class="sxs-lookup"><span data-stu-id="20610-178">On the **Requirements** page, choose **Next** to accept the default values, and then complete the wizard.</span></span>  
  
 <span data-ttu-id="20610-179">下表描述了步骤 7 中指定的命令行选项。</span><span class="sxs-lookup"><span data-stu-id="20610-179">The following table describes the command-line options specified in step 7.</span></span>  
  
|<span data-ttu-id="20610-180">选项</span><span class="sxs-lookup"><span data-stu-id="20610-180">Option</span></span>|<span data-ttu-id="20610-181">描述</span><span class="sxs-lookup"><span data-stu-id="20610-181">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="20610-182">**/q**</span><span class="sxs-lookup"><span data-stu-id="20610-182">**/q**</span></span>|<span data-ttu-id="20610-183">设置安静模式。</span><span class="sxs-lookup"><span data-stu-id="20610-183">Sets quiet mode.</span></span> <span data-ttu-id="20610-184">不需要用户输入，也不显示输出。</span><span class="sxs-lookup"><span data-stu-id="20610-184">No user input is required, and no output is shown.</span></span>|  
|<span data-ttu-id="20610-185">**/norestart**</span><span class="sxs-lookup"><span data-stu-id="20610-185">**/norestart**</span></span>|<span data-ttu-id="20610-186">防止安装程序自动重新启动。</span><span class="sxs-lookup"><span data-stu-id="20610-186">Prevents the Setup program from rebooting automatically.</span></span> <span data-ttu-id="20610-187">如果你使用此选项，则 Configuration Manager 必须处理计算机重新启动。</span><span class="sxs-lookup"><span data-stu-id="20610-187">If you use this option, Configuration Manager must handle the computer restart.</span></span>|  
|<span data-ttu-id="20610-188">/chainingpackage PackageName</span><span class="sxs-lookup"><span data-stu-id="20610-188">**/chainingpackage** *PackageName*</span></span>|<span data-ttu-id="20610-189">指定执行链接的包的名称。</span><span class="sxs-lookup"><span data-stu-id="20610-189">Specifies the name of the package that is doing the chaining.</span></span> <span data-ttu-id="20610-190">该信息与注册了 [Microsoft 客户体验改善计划 (CEIP)](http://go.microsoft.com/fwlink/p/?LinkId=248244) 的用户的其他安装会话信息一起报告。</span><span class="sxs-lookup"><span data-stu-id="20610-190">This information is reported with other installation session information for those who have signed up for the [Microsoft Customer Experience Improvement Program (CEIP)](http://go.microsoft.com/fwlink/p/?LinkId=248244).</span></span> <span data-ttu-id="20610-191">如果包名称包含空格，则可以用双引号作为分隔符；例如：/chainingpackage "Chaining Product"。</span><span class="sxs-lookup"><span data-stu-id="20610-191">If the package name includes spaces, use double quotation marks as delimiters; for example: **/chainingpackage "Chaining Product"**.</span></span>|  
  
 <span data-ttu-id="20610-192">这些步骤创建了一个名为“.NET Framework 4.5”的包。</span><span class="sxs-lookup"><span data-stu-id="20610-192">These steps create a package named .NET Framework 4.5.</span></span> <span data-ttu-id="20610-193">程序将部署 .NET Framework 4.5 的无提示安装。</span><span class="sxs-lookup"><span data-stu-id="20610-193">The program deploys a silent installation of the .NET Framework 4.5.</span></span> <span data-ttu-id="20610-194">在无提示安装中，用户不与安装过程进行交互，并且链接应用程序必须捕获返回代码并处理重启操作；请参阅[从安装软件包获取进度信息](http://go.microsoft.com/fwlink/?LinkId=179606)。</span><span class="sxs-lookup"><span data-stu-id="20610-194">In a silent installation, users do not interact with the installation process, and the chaining application has to capture the return code and handle rebooting; see [Getting Progress Information from an Installation Package](http://go.microsoft.com/fwlink/?LinkId=179606).</span></span>  
 
<a name="select_dist_point"></a>   
### <a name="select-a-distribution-point"></a><span data-ttu-id="20610-195">选择分发点</span><span class="sxs-lookup"><span data-stu-id="20610-195">Select a distribution point</span></span>  
 <span data-ttu-id="20610-196">若要通过服务器将包和程序分发到客户端计算机，你必须先指定一个站点系统为分发点，然后将包分发到该分发点。</span><span class="sxs-lookup"><span data-stu-id="20610-196">To distribute the package and program to client computers from a server, you must first designate a site system as a distribution point and then distribute the package to the distribution point.</span></span>  
  
 <span data-ttu-id="20610-197">使用下列步骤可为你在上一节中创建的 .NET Framework 4.5 包选择分发点：</span><span class="sxs-lookup"><span data-stu-id="20610-197">Use the following steps to select a distribution point for the .NET Framework 4.5 package you created in the previous section:</span></span>  
  
1.  <span data-ttu-id="20610-198">在 Configuration Manager 控制台中，选择“软件库”。</span><span class="sxs-lookup"><span data-stu-id="20610-198">In the Configuration Manager console, choose **Software Library**.</span></span>  
  
2.  <span data-ttu-id="20610-199">在“软件库”工作区中，展开“应用程序管理”，然后选择“包”。</span><span class="sxs-lookup"><span data-stu-id="20610-199">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>  
  
3.  <span data-ttu-id="20610-200">从包列表中，选择在上一节中创建的包“.NET Framework 4.5”。</span><span class="sxs-lookup"><span data-stu-id="20610-200">From the list of packages, select the package **.NET Framework 4.5** that you created in the previous section.</span></span>  
  
4.  <span data-ttu-id="20610-201">在“主页”选项卡上的“部署”组中，选择“分发内容”。</span><span class="sxs-lookup"><span data-stu-id="20610-201">On the **Home** tab, in the **Deployment** group, choose **Distribute Content**.</span></span>  
  
5.  <span data-ttu-id="20610-202">在“分发内容向导”的“常规”选项卡上，选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="20610-202">On the **General** tab of the **Distribute Content Wizard**, choose **Next**.</span></span>  
  
6.  <span data-ttu-id="20610-203">在该向导的“内容目标”页上，选择“添加”，然后选择“分发点”。</span><span class="sxs-lookup"><span data-stu-id="20610-203">On the **Content Destination** page of the wizard, choose **Add**, and then choose **Distribution Point**.</span></span>  
  
7.  <span data-ttu-id="20610-204">在“添加分发点”对话框中，选择将承载包和程序的分发点，然后选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="20610-204">In the **Add Distribution Points** dialog box, select the distribution point(s) that will host the package and program, and then choose **OK**.</span></span>  
  
8.  <span data-ttu-id="20610-205">完成向导。</span><span class="sxs-lookup"><span data-stu-id="20610-205">Complete the wizard.</span></span>  
  
 <span data-ttu-id="20610-206">包现在包含无提示部署 .NET Framework 4.5 所需的所有信息。</span><span class="sxs-lookup"><span data-stu-id="20610-206">The packagenow contains all the information you need to silently deploy the .NET Framework 4.5.</span></span> <span data-ttu-id="20610-207">在部署包和程序之前，请确认已将其安装在分发点上；请参阅 Configuration Manager 文档库中的 [Configuration Manager 中的内容管理的操作和维护](http://technet.microsoft.com/library/gg712694.aspx#BKMK_MonitorContent)的“监视内容”一节。</span><span class="sxs-lookup"><span data-stu-id="20610-207">Before you deploy the package and program, verify that it was installed on the distribution point; see the "Monitor Content" section of [Operations and Maintenance for Content Management in Configuration Manager](http://technet.microsoft.com/library/gg712694.aspx#BKMK_MonitorContent) in the Configuration Manager Documentation Library.</span></span>  
  
<a name="deploying_package"></a>   
### <a name="deploy-the-package"></a><span data-ttu-id="20610-208">部署包</span><span class="sxs-lookup"><span data-stu-id="20610-208">Deploy the package</span></span>  
 <span data-ttu-id="20610-209">部署 .NET Framework 4.5 包和程序：</span><span class="sxs-lookup"><span data-stu-id="20610-209">To deploy the .NET Framework 4.5 package and program:</span></span>  
  
1.  <span data-ttu-id="20610-210">在 Configuration Manager 控制台中，选择“软件库”。</span><span class="sxs-lookup"><span data-stu-id="20610-210">In the Configuration Manager console, choose **Software Library**.</span></span>  
  
2.  <span data-ttu-id="20610-211">在“软件库”工作区中，展开“应用程序管理”，然后选择“包”。</span><span class="sxs-lookup"><span data-stu-id="20610-211">In the **Software Library** workspace, expand **Application Management**, and then choose **Packages**.</span></span>  
  
3.  <span data-ttu-id="20610-212">从包列表中，选择创建的名为“.NET Framework 4.5”的包。</span><span class="sxs-lookup"><span data-stu-id="20610-212">From the list of packages, select the package you created named **.NET Framework 4.5**.</span></span>  
  
4.  <span data-ttu-id="20610-213">在“主页”选项卡上的“部署”组中，选择“部署”。</span><span class="sxs-lookup"><span data-stu-id="20610-213">On the **Home** tab, in the **Deployment** group, choose **Deploy**.</span></span>  
  
5.  <span data-ttu-id="20610-214">在“部署软件向导”的“常规”页上，选择“浏览”，然后选择先前创建的集合。</span><span class="sxs-lookup"><span data-stu-id="20610-214">On the **General** page of the **Deploy Software Wizard**, choose **Browse**, and then select the collection that you created earlier.</span></span> <span data-ttu-id="20610-215">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="20610-215">Choose **Next**.</span></span>  
  
6.  <span data-ttu-id="20610-216">在该向导的“内容”页上，确认已显示要从其分发软件的点，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="20610-216">On the **Content** page of the wizard, verify that the point from which you want to distribute the software is displayed, and then choose **Next**.</span></span>  
  
7.  <span data-ttu-id="20610-217">在该向导的“部署设置”页上，确认“操作”已设置为“安装”，且“目标”设置为“必需”。</span><span class="sxs-lookup"><span data-stu-id="20610-217">On the **Deployment Settings** page of the wizard, confirm that **Action** is set to **Install**, and **Purpose** is set to **Required**.</span></span> <span data-ttu-id="20610-218">这可确保软件包将是目标计算机上的必需安装。</span><span class="sxs-lookup"><span data-stu-id="20610-218">This ensures that the software package will be a mandatory installation on the targeted computers.</span></span> <span data-ttu-id="20610-219">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="20610-219">Choose **Next**.</span></span>  
  
8.  <span data-ttu-id="20610-220">在该向导的“计划”页上，指定希望何时安装 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="20610-220">On the **Scheduling** page of the wizard, specify when you want the .NET Framework to be installed.</span></span> <span data-ttu-id="20610-221">可以选择“新建”以指定安装时间，也可以指示在用户登录或注销时安装软件或尽快安装软件。</span><span class="sxs-lookup"><span data-stu-id="20610-221">You can choose **New** to assign an installation time, or instruct the software to install when the user logs on or off, or as soon as possible.</span></span> <span data-ttu-id="20610-222">选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="20610-222">Choose **Next**.</span></span>  
  
9. <span data-ttu-id="20610-223">在该向导的“用户体验”页上，使用默认值并选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="20610-223">On the **User Experience** page of the wizard, use the default values and choose **Next**.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="20610-224">你的生产环境可能具有需要选择不同的部署计划的策略。</span><span class="sxs-lookup"><span data-stu-id="20610-224">Your production environment might have policies that require different selections for the deployment schedule.</span></span> <span data-ttu-id="20610-225">有关这些选项的信息，请参阅 TechNet 库中的[播发名称属性：“计划”选项卡](http://technet.microsoft.com/library/bb694016.aspx)。</span><span class="sxs-lookup"><span data-stu-id="20610-225">For information about these options, see [Advertisement Name Properties: Schedule Tab](http://technet.microsoft.com/library/bb694016.aspx) in the TechNet Library.</span></span>  
  
10. <span data-ttu-id="20610-226">在该向导的“分发点”页上，使用默认值并选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="20610-226">On the **Distribution Points** page of the wizard, use the default values and choose **Next**.</span></span>  
  
11. <span data-ttu-id="20610-227">完成向导。</span><span class="sxs-lookup"><span data-stu-id="20610-227">Complete the wizard.</span></span> <span data-ttu-id="20610-228">可在“监控”工作区的“部署”节点下监控部署的进度。</span><span class="sxs-lookup"><span data-stu-id="20610-228">You can monitor the progress of the deployment in the **Deployments** node of the **Monitoring** workspace.</span></span>  
  
 <span data-ttu-id="20610-229">包现在将部署到目标集合，并且将开始 .NET Framework 4.5 的无提示安装。</span><span class="sxs-lookup"><span data-stu-id="20610-229">The package will now be deployed to the targeted collection and the silent installation of .NET Framework 4.5 will begin.</span></span> <span data-ttu-id="20610-230">有关 .NET Framework 4.5 安装错误代码的信息，请参阅本主题后面的[返回代码](#return_codes)一节。</span><span class="sxs-lookup"><span data-stu-id="20610-230">For information about .NET Framework 4.5 installation error codes, see the [Return Codes](#return_codes) section later in this topic.</span></span>  
  
<a name="resources"></a>   
## <a name="resources"></a><span data-ttu-id="20610-231">资源</span><span class="sxs-lookup"><span data-stu-id="20610-231">Resources</span></span>  
 <span data-ttu-id="20610-232">有关用于测试 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 可再发行组件包的部署的基础结构的更多信息，请参见下列资源。</span><span class="sxs-lookup"><span data-stu-id="20610-232">For more information about the infrastructure for testing the deployment of the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable package, see the following resources.</span></span>  
  
 <span data-ttu-id="20610-233">**Active Directory、DNS 和 DHCP：**</span><span class="sxs-lookup"><span data-stu-id="20610-233">**Active Directory, DNS, DHCP:**</span></span>  
  
-   [<span data-ttu-id="20610-234">适用于 Windows Server 2008 的 Active Directory 域服务</span><span class="sxs-lookup"><span data-stu-id="20610-234">Active Directory Domain Services for Windows Server 2008</span></span>](http://technet.microsoft.com/library/dd378891.aspx)  
  
-   [<span data-ttu-id="20610-235">DNS 服务器</span><span class="sxs-lookup"><span data-stu-id="20610-235">DNS Server</span></span>](http://technet.microsoft.com/library/cc732997.aspx)  
  
-   [<span data-ttu-id="20610-236">DHCP 服务器</span><span class="sxs-lookup"><span data-stu-id="20610-236">DHCP Server</span></span>](http://technet.microsoft.com/library/cc896553.aspx)  
  
 <span data-ttu-id="20610-237">**SQL Server 2008:**</span><span class="sxs-lookup"><span data-stu-id="20610-237">**SQL Server 2008:**</span></span>  
  
-   [<span data-ttu-id="20610-238">安装 SQL Server 2008（SQL Server 视频）</span><span class="sxs-lookup"><span data-stu-id="20610-238">Installing SQL Server 2008 (SQL Server Video)</span></span>](http://technet.microsoft.com/library/dd299415.aspx)  
  
-   [<span data-ttu-id="20610-239">面向数据库管理员的 SQL Server 2008 安全概述</span><span class="sxs-lookup"><span data-stu-id="20610-239">SQL Server 2008 Security Overview for Database Administrators</span></span>](http://download.microsoft.com/download/a/c/d/acd8e043-d69b-4f09-bc9e-4168b65aaa71/SQL2008SecurityOverviewforAdmins.docx)  
  
 <span data-ttu-id="20610-240">System Center 2012 Configuration Manager（既充当管理点又充当分发点）：</span><span class="sxs-lookup"><span data-stu-id="20610-240">**System Center 2012 Configuration Manager (Management Point, Distribution Point):**</span></span>  
  
-   [<span data-ttu-id="20610-241">System Center 2012 Configuration Manager 的站点管理</span><span class="sxs-lookup"><span data-stu-id="20610-241">Site Administration for System Center 2012 Configuration Manager</span></span>](http://technet.microsoft.com/library/gg681983.aspx)  
  
-   [<span data-ttu-id="20610-242">Configuration Manager 单站点计划和部署</span><span class="sxs-lookup"><span data-stu-id="20610-242">Configuration Manager Single Site Planning and Deployment</span></span>](http://technet.microsoft.com/library/bb680961.aspx)  
  
 <span data-ttu-id="20610-243">适用于 Windows 计算机的 System Center 2012 Configuration Manager 客户端：</span><span class="sxs-lookup"><span data-stu-id="20610-243">**System Center 2012 Configuration Manager client for Windows computers:**</span></span>  
  
-   [<span data-ttu-id="20610-244">部署 System Center 2012 Configuration Manager 的客户端</span><span class="sxs-lookup"><span data-stu-id="20610-244">Deploying Clients for System Center 2012 Configuration Manager</span></span>](http://technet.microsoft.com/library/gg699391.aspx)  
  
<a name="troubleshooting"></a>   
## <a name="troubleshooting"></a><span data-ttu-id="20610-245">疑难解答</span><span class="sxs-lookup"><span data-stu-id="20610-245">Troubleshooting</span></span>  
  
### <a name="log-file-locations"></a><span data-ttu-id="20610-246">日志文件位置</span><span class="sxs-lookup"><span data-stu-id="20610-246">Log file locations</span></span>  
 <span data-ttu-id="20610-247">在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 安装过程中，会生成下列日志文件：</span><span class="sxs-lookup"><span data-stu-id="20610-247">The following log files are generated during [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup:</span></span>  
  
 <span data-ttu-id="20610-248">%temp%\Microsoft .NET Framework 4.5\*.txt</span><span class="sxs-lookup"><span data-stu-id="20610-248">%temp%\Microsoft .NET Framework 4.5\*.txt</span></span>  
 <span data-ttu-id="20610-249">%temp%\Microsoft .NET Framework 4.5\\*.html</span><span class="sxs-lookup"><span data-stu-id="20610-249">%temp%\Microsoft .NET Framework 4.5\\*.html</span></span>  
  
 <span data-ttu-id="20610-250">可使用[日志收集工具](http://www.microsoft.com/download/details.aspx?id=12493)收集 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 日志文件，并创建可减小这些文件的大小的压缩 cabinet (.cab) 文件。</span><span class="sxs-lookup"><span data-stu-id="20610-250">You can use the [log collection tool](http://www.microsoft.com/download/details.aspx?id=12493) to collect the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] log files and to create a compressed cabinet (.cab) file that reduces the size of the files.</span></span>  
  
<a name="return_codes"></a>   
### <a name="return-codes"></a><span data-ttu-id="20610-251">返回代码</span><span class="sxs-lookup"><span data-stu-id="20610-251">Return codes</span></span>  
 <span data-ttu-id="20610-252">下表列出了 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 可再发行安装程序中的最常见的返回代码。</span><span class="sxs-lookup"><span data-stu-id="20610-252">The following table lists the most common return codes from the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable installation program.</span></span> <span data-ttu-id="20610-253">所有版本的安装程序的返回代码都是相同的。</span><span class="sxs-lookup"><span data-stu-id="20610-253">The return codes are the same for all versions of the installer.</span></span>  
  
 <span data-ttu-id="20610-254">有关指向详细信息的链接，请参阅下一节[下载错误代码](#additional_error_codes)。</span><span class="sxs-lookup"><span data-stu-id="20610-254">For links to detailed information, see the next section, [Download error codes](#additional_error_codes).</span></span>  
  
|<span data-ttu-id="20610-255">返回代码</span><span class="sxs-lookup"><span data-stu-id="20610-255">Return code</span></span>|<span data-ttu-id="20610-256">描述</span><span class="sxs-lookup"><span data-stu-id="20610-256">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="20610-257">0</span><span class="sxs-lookup"><span data-stu-id="20610-257">0</span></span>|<span data-ttu-id="20610-258">已成功完成安装。</span><span class="sxs-lookup"><span data-stu-id="20610-258">Installation completed successfully.</span></span>|  
|<span data-ttu-id="20610-259">1602</span><span class="sxs-lookup"><span data-stu-id="20610-259">1602</span></span>|<span data-ttu-id="20610-260">用户已取消安装。</span><span class="sxs-lookup"><span data-stu-id="20610-260">The user canceled installation.</span></span>|  
|<span data-ttu-id="20610-261">1603</span><span class="sxs-lookup"><span data-stu-id="20610-261">1603</span></span>|<span data-ttu-id="20610-262">安装期间发生错误。</span><span class="sxs-lookup"><span data-stu-id="20610-262">A fatal error occurred during installation.</span></span>|  
|<span data-ttu-id="20610-263">1641</span><span class="sxs-lookup"><span data-stu-id="20610-263">1641</span></span>|<span data-ttu-id="20610-264">需要重新启动才能完成安装。</span><span class="sxs-lookup"><span data-stu-id="20610-264">A restart is required to complete the installation.</span></span> <span data-ttu-id="20610-265">此消息指示安装成功。</span><span class="sxs-lookup"><span data-stu-id="20610-265">This message indicates success.</span></span>|  
|<span data-ttu-id="20610-266">3010</span><span class="sxs-lookup"><span data-stu-id="20610-266">3010</span></span>|<span data-ttu-id="20610-267">需要重新启动才能完成安装。</span><span class="sxs-lookup"><span data-stu-id="20610-267">A restart is required to complete the installation.</span></span> <span data-ttu-id="20610-268">此消息指示安装成功。</span><span class="sxs-lookup"><span data-stu-id="20610-268">This message indicates success.</span></span>|  
|<span data-ttu-id="20610-269">5100</span><span class="sxs-lookup"><span data-stu-id="20610-269">5100</span></span>|<span data-ttu-id="20610-270">用户计算机不满足系统要求。</span><span class="sxs-lookup"><span data-stu-id="20610-270">The user's computer does not meet system requirements.</span></span>|  
  
<a name="additional_error_codes"></a>   
### <a name="download-error-codes"></a><span data-ttu-id="20610-271">下载错误代码</span><span class="sxs-lookup"><span data-stu-id="20610-271">Download error codes</span></span>  
  
-   [<span data-ttu-id="20610-272">后台智能传输服务 (BITS) 错误代码</span><span class="sxs-lookup"><span data-stu-id="20610-272">Background Intelligent Transfer Service (BITS) error codes</span></span>](http://msdn.microsoft.com/library/aa362823.aspx)  
  
-   [<span data-ttu-id="20610-273">URL 名字对象错误代码</span><span class="sxs-lookup"><span data-stu-id="20610-273">URL moniker error codes</span></span>](http://msdn.microsoft.com/library/ms775145.aspx)  
  
-   [<span data-ttu-id="20610-274">WinHttp 错误代码</span><span class="sxs-lookup"><span data-stu-id="20610-274">WinHttp error codes</span></span>](http://msdn.microsoft.com/library/aa383770.aspx)  
  
 <span data-ttu-id="20610-275">其他错误代码：</span><span class="sxs-lookup"><span data-stu-id="20610-275">Other error codes:</span></span>  
  
-   [<span data-ttu-id="20610-276">Windows Installer 错误代码</span><span class="sxs-lookup"><span data-stu-id="20610-276">Windows Installer error codes</span></span>](http://msdn.microsoft.com/library/aa368542.aspx)  
  
-   [<span data-ttu-id="20610-277">Windows 更新代理结果代码</span><span class="sxs-lookup"><span data-stu-id="20610-277">Windows Update Agent result codes</span></span>](http://technet.microsoft.com/library/cc720442.aspx)  
  
## <a name="see-also"></a><span data-ttu-id="20610-278">请参阅</span><span class="sxs-lookup"><span data-stu-id="20610-278">See Also</span></span>  
 [<span data-ttu-id="20610-279">面向开发人员的部署指南</span><span class="sxs-lookup"><span data-stu-id="20610-279">Deployment Guide for Developers</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md)  
 [<span data-ttu-id="20610-280">系统要求</span><span class="sxs-lookup"><span data-stu-id="20610-280">System Requirements</span></span>](../../../docs/framework/get-started/system-requirements.md)
