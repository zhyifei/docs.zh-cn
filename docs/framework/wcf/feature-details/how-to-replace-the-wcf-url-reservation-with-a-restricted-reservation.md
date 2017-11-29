---
title: "如何：用受限保留项替换 WCF URL 保留项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9dd631f08f9367576adf97f9139348bfce69a92f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation"></a><span data-ttu-id="c9ac9-102">如何：用受限保留项替换 WCF URL 保留项</span><span class="sxs-lookup"><span data-stu-id="c9ac9-102">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>
<span data-ttu-id="c9ac9-103">URL 保留项使您能够限制谁可以接收来自某个 URL 或某一组 URL 的消息。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-103">A URL reservation allows you to restrict who can receive messages from a URL or a set of URLs.</span></span> <span data-ttu-id="c9ac9-104">保留项由一个 URL 模板、一个访问控制列表 (ACL) 和一组标志组成。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-104">A reservation consists of a URL template, an access control list (ACL), and a set of flags.</span></span> <span data-ttu-id="c9ac9-105">URL 模板定义保留项所影响的 URL。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-105">The URL template defines which URLs the reservation affects.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c9ac9-106">如何处理 URL 模板的更多信息，请参阅[路由传入请求](http://go.microsoft.com/fwlink/?LinkId=136764)。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-106"> how URL templates are processed, see [Routing Incoming Requests](http://go.microsoft.com/fwlink/?LinkId=136764).</span></span> <span data-ttu-id="c9ac9-107">ACL 控制哪个用户或用户组允许接收来自指定 URL 的消息。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-107">The ACL controls what user or group of users is permitted to receive messages from the specified URLs.</span></span> <span data-ttu-id="c9ac9-108">标志指示保留项是赋予用户或用户组直接侦听 URL 的权限，还是将侦听权限委托给其他进程。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-108">The flags indicate whether the reservation is to give a user or group permission to listen on the URL directly or to delegate the permission to listen to some other process.</span></span>  
  
 <span data-ttu-id="c9ac9-109">在默认的操作系统配置中，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 为端口 80 创建可全局访问的保留项，使所有用户都能够运行应用程序，在该应用程序中使用双向 HTTP 绑定来进行双工通信。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-109">As part of the default operating system configuration, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] creates a globally accessible reservation for port 80 to enable all users to run applications that use a dual HTTP binding for duplex communication.</span></span> <span data-ttu-id="c9ac9-110">由于此保留项的 ACL 适用于所有用户，因此管理员不能显式允许或禁止侦听某个 URL 或某一组 URL 的权限。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-110">Because the ACL on this reservation is for everyone, administrators cannot explicitly allow or disallow permission to listen on a URL or set of URLs.</span></span> <span data-ttu-id="c9ac9-111">本主题介绍如何删除此保留项，以及如何重新创建具有受限 ACL 的保留项。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-111">This topic explains how to delete this reservation and how to re-create the reservation with a restricted ACL.</span></span>  
  
 <span data-ttu-id="c9ac9-112">在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 或 [!INCLUDE[lserver](../../../../includes/lserver-md.md)] 上键入 `netsh http show urlacl`，就可以在具有提升权限的命令提示符中查看所有 HTTP URL 保留项。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-112">On [!INCLUDE[wv](../../../../includes/wv-md.md)] or [!INCLUDE[lserver](../../../../includes/lserver-md.md)] you can view all of the HTTP URL reservations from an elevated command prompt by typing `netsh http show urlacl`.</span></span>  <span data-ttu-id="c9ac9-113">下面的示例演示 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL 保留项的形式。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-113">The following example shows what a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL reservation should resemble.</span></span>  
  
```  
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```  
  
 <span data-ttu-id="c9ac9-114">该保留项包含的 URL 模板在 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 应用程序使用 HTTP 双向绑定进行双工通信时使用。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-114">The reservation consists of a URL template used when a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application is using an HTTP dual binding for duplex communication.</span></span> <span data-ttu-id="c9ac9-115">这种 URL 由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务用于在通过 HTTP 双向绑定进行通信时将消息发送回 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-115">URLs of this form are used for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service to send messages back to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client when communicating over a HTTP dual binding.</span></span> <span data-ttu-id="c9ac9-116">向每个用户授予侦听该 URL 的权限，而不将侦听权限委托给另一个进程。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-116">Everyone is given permission to listen on the URL but not to delegate listening to another process.</span></span> <span data-ttu-id="c9ac9-117">最后，安全描述符定义语言 (SSDL) 中介绍了该 ACL。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-117">Finally, the ACL is described in Security Descriptor Definition Language (SSDL).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c9ac9-118">SSDL，请参阅[SSDL](http://go.microsoft.com/fwlink/?LinkId=136789)</span><span class="sxs-lookup"><span data-stu-id="c9ac9-118"> SSDL, see [SSDL](http://go.microsoft.com/fwlink/?LinkId=136789)</span></span>  
  
### <a name="to-delete-the-wcf-url-reservation"></a><span data-ttu-id="c9ac9-119">删除 WCF URL 保留项</span><span class="sxs-lookup"><span data-stu-id="c9ac9-119">To delete the WCF URL reservation</span></span>  
  
1.  <span data-ttu-id="c9ac9-120">单击**启动**，指向**所有程序**，单击**附件**，右键单击**命令提示符**单击**以运行管理员**上出现上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-120">Click **Start**, point to **All Programs**, click **Accessories**, right-click **Command Prompt** and click **Run as Administrator** on the context menu that comes up.</span></span> <span data-ttu-id="c9ac9-121">单击**继续**上用户帐户控制 (UAC) 窗口请求您权限才能继续。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-121">Click **Continue** on the User Account Control (UAC) window that might ask permissions to continue.</span></span>  
  
2.  <span data-ttu-id="c9ac9-122">键入**netsh http 删除 urlacl url = http: / / +:80/Temporary_Listen_Addresses/**在命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-122">Type in **netsh http delete urlacl url=http://+:80/Temporary_Listen_Addresses/** in the command prompt window.</span></span>  
  
3.  <span data-ttu-id="c9ac9-123">如果成功删除了保留项，将显示以下消息。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-123">If the reservation is deleted successfully, the following message is displayed.</span></span> <span data-ttu-id="c9ac9-124">**已成功删除的 URL 保留项**</span><span class="sxs-lookup"><span data-stu-id="c9ac9-124">**URL reservation successfully deleted**</span></span>  
  
## <a name="creating-a-new-security-group-and-new-restricted-url-reservation"></a><span data-ttu-id="c9ac9-125">创建新的安全组和新的受限 URL 保留项</span><span class="sxs-lookup"><span data-stu-id="c9ac9-125">Creating a New Security Group and New Restricted URL Reservation</span></span>  
 <span data-ttu-id="c9ac9-126">若要用受限保留项替换 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL 保留项，必须先创建新的安全组。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-126">To replace the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL reservation with a restricted reservation you must first create a new security group.</span></span> <span data-ttu-id="c9ac9-127">可以通过两种方法执行此操作：从命令提示符或从计算机管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-127">You can do this in one of two ways: from a command prompt or from the computer management console.</span></span> <span data-ttu-id="c9ac9-128">您只需要执行一次。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-128">You only have to do one.</span></span>  
  
#### <a name="to-create-a-new-security-group-from-a-command-prompt"></a><span data-ttu-id="c9ac9-129">从命令提示符创建新的安全组</span><span class="sxs-lookup"><span data-stu-id="c9ac9-129">To create a new security group from a command prompt</span></span>  
  
1.  <span data-ttu-id="c9ac9-130">单击**启动**，指向**所有程序**，单击**附件**，右键单击**命令提示符**单击**以运行管理员**上出现上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-130">Click **Start**, point to **All Programs**, click **Accessories**, right-click **Command Prompt** and click **Run as Administrator** on the context menu that comes up.</span></span> <span data-ttu-id="c9ac9-131">单击**继续**上用户帐户控制 (UAC) 窗口请求您权限才能继续。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-131">Click **Continue** on the User Account Control (UAC) window that might ask permissions to continue.</span></span>  
  
2.  <span data-ttu-id="c9ac9-132">键入**net localgroup"\<安全组名称 >"/ 注释:"\<安全组的说明 >"添加 /**在命令提示符。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-132">Type in **net localgroup "\<security group name>" /comment:"\<security group description>" /add** at the command prompt.</span></span> <span data-ttu-id="c9ac9-133">替换**\<安全组名称 >**替换为你想要创建的安全组的名称和**\<安全组的说明 >**与具有合适的说明安全组。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-133">Replacing **\<security group name>** with the name of the security group you want to create and **\<security group description>** with a suitable description for the security group.</span></span>  
  
3.  <span data-ttu-id="c9ac9-134">如果成功创建了安全组，将显示以下消息。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-134">If the security group is created successfully, the following message is displayed.</span></span> <span data-ttu-id="c9ac9-135">**已成功完成该命令。**</span><span class="sxs-lookup"><span data-stu-id="c9ac9-135">**The command completed successfully.**</span></span>  
  
#### <a name="to-create-a-new-security-group-from-the-computer-management-console"></a><span data-ttu-id="c9ac9-136">从计算机管理控制台创建新的安全组</span><span class="sxs-lookup"><span data-stu-id="c9ac9-136">To create a new security group from the computer management console</span></span>  
  
1.  <span data-ttu-id="c9ac9-137">单击**启动**，单击**控制面板**，单击**管理工具**，然后单击**计算机管理**以打开计算机管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-137">Click **Start**, click **Control Panel**, click **Administrative Tools**, and click **Computer Management** to open up the Computer Management Console.</span></span> <span data-ttu-id="c9ac9-138">单击**继续**上用户帐户控制 (UAC) 窗口请求您权限才能继续。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-138">Click **Continue** on the User Account Control (UAC) window that might ask permissions to continue.</span></span>  
  
2.  <span data-ttu-id="c9ac9-139">单击**系统工具**，单击**本地用户和组**，右键单击**组**文件夹，然后单击**新建组**上下文菜单上，出现。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-139">Click **System Tools**, click **Local Users and Groups**, right-click **Groups** folder and click **New Group** on the context menu that comes up.</span></span> <span data-ttu-id="c9ac9-140">所需的类型**组名称**，**说明**和其他详细信息的该新的安全组并单击**创建**按钮创建安全组。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-140">Type in the desired **Group Name**, **Description** and other details of this new security group and click the **Create** button to create the security group.</span></span>  
  
#### <a name="to-create-the-restricted-url-reservation"></a><span data-ttu-id="c9ac9-141">创建受限 URL 保留项</span><span class="sxs-lookup"><span data-stu-id="c9ac9-141">To create the restricted URL reservation</span></span>  
  
1.  <span data-ttu-id="c9ac9-142">单击**启动**，指向**所有程序**，单击**附件**，右键单击**命令提示符**单击**以运行管理员**上出现上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-142">Click **Start**, point to **All Programs**, click **Accessories**, right-click **Command Prompt** and click **Run as Administrator** on the context menu that comes up.</span></span> <span data-ttu-id="c9ac9-143">单击**继续**上用户帐户控制 (UAC) 窗口请求您权限才能继续。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-143">Click **Continue** on the User Account Control (UAC) window that might ask permissions to continue.</span></span>  
  
2.  <span data-ttu-id="c9ac9-144">键入**netsh http 添加 urlacl url = http: / / +: 80/Temporary_Listen_Addresses/用户 ="\<计算机名称 >\\< 安全组名称\>**在命令提示符。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-144">Type in **netsh http add urlacl url=http://+:80/Temporary_Listen_Addresses/ user="\<machine name>\\<security group name\>** at the command prompt.</span></span> <span data-ttu-id="c9ac9-145">替换**\<计算机名称 >**与必须在其创建组的计算机名称和**\<安全组名称 >**替换为你创建的安全组的名称以前。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-145">Replacing **\<machine name>** with the computer name on which the group must be created and **\<security group name>** with the name of the security group you created previously.</span></span>  
  
3.  <span data-ttu-id="c9ac9-146">如果成功创建了保留项，将显示以下消息。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-146">If the reservation is created successfully, the following message is displayed.</span></span> <span data-ttu-id="c9ac9-147">**已成功添加的 URL 保留项**。</span><span class="sxs-lookup"><span data-stu-id="c9ac9-147">**URL reservation successfully added**.</span></span>
