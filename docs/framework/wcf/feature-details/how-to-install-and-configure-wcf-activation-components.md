---
title: 如何：安装和配置 WCF 激活组件
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 8b516bb4603f33828069b5356676d8b35dc961d2
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46530084"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="9e4bc-102">如何：安装和配置 WCF 激活组件</span><span class="sxs-lookup"><span data-stu-id="9e4bc-102">How to: Install and Configure WCF Activation Components</span></span>
<span data-ttu-id="9e4bc-103">本主题介绍在设置 Windows 进程激活服务 (也称为 WAS) 所需的步骤[!INCLUDE[wv](../../../../includes/wv-md.md)]来承载 Windows Communication Foundation (WCF) 服务未通过 HTTP 进行通信的网络协议。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on [!INCLUDE[wv](../../../../includes/wv-md.md)] to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="9e4bc-104">下面的部分略述此配置的步骤：</span><span class="sxs-lookup"><span data-stu-id="9e4bc-104">The following sections outline the steps for this configuration:</span></span>  
  
-   <span data-ttu-id="9e4bc-105">安装 （或确认安装） WCF 激活组件。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-105">Install (or confirm the installation of) the WCF activation components.</span></span>  
  
-   <span data-ttu-id="9e4bc-106">配置 WAS 以支持非 HTTP 协议。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-106">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="9e4bc-107">下面的过程对 [!INCLUDE[wv](../../../../includes/wv-md.md)] 进行 TCP 激活配置。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-107">The following procedure configures [!INCLUDE[wv](../../../../includes/wv-md.md)] for TCP activation.</span></span>  
  
 <span data-ttu-id="9e4bc-108">安装和配置 WAS，请参阅后[如何： 承载在 WAS 中的 WCF 服务](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)用于创建公开使用 WAS 的非 HTTP 终结点的 WCF 服务的过程。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-108">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="9e4bc-109">安装 WCF 非 HTTP 激活组件</span><span class="sxs-lookup"><span data-stu-id="9e4bc-109">To install the WCF non-HTTP activation components</span></span>  
  
1.  <span data-ttu-id="9e4bc-110">单击**启动**按钮，然后依次**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-110">Click the **Start** button, and then click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="9e4bc-111">单击**程序**，然后单击**程序和功能**。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-111">Click **Programs**, and then click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="9e4bc-112">上**任务**菜单上，单击**打开或关闭打开的 Windows 功能**。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-112">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>  
  
4.  <span data-ttu-id="9e4bc-113">查找 [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] 节点，选中该节点然后将其展开。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-113">Find the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] node, select and then expand it.</span></span>  
  
5.  <span data-ttu-id="9e4bc-114">选择**WCF 非 Http 激活组件**框并保存设置。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-114">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="9e4bc-115">配置 WAS 以支持 TCP 激活</span><span class="sxs-lookup"><span data-stu-id="9e4bc-115">To configure the WAS to support TCP activation</span></span>  
  
1.  <span data-ttu-id="9e4bc-116">若要支持 net.tcp 激活，必须首先将默认的网站绑定到一个 net.tcp 端口。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-116">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="9e4bc-117">可以通过使用随 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 管理工具集安装的 Appcmd.exe 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-117">You can do this by using Appcmd.exe, which is installed with the [!INCLUDE[iisver](../../../../includes/iisver-md.md)] management toolset.</span></span> <span data-ttu-id="9e4bc-118">在管理员级别命令提示符窗口中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-118">In an administrator-level Command Prompt window, run the following command.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="9e4bc-119">此命令是单行文本。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-119">This command is a single line of text.</span></span> <span data-ttu-id="9e4bc-120">此命令将 net.tcp 网站绑定添加到以任何主机名侦听 TCP 端口 808 的默认网站。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-120">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>  
  
2.  <span data-ttu-id="9e4bc-121">尽管网站内的所有应用程序共享一个公共 net.tcp 绑定，但是每个应用程序可以单独启用 net.tcp 支持。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-121">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="9e4bc-122">若要启用应用程序的 net.tcp，请从管理员级别命令提示符运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-122">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="9e4bc-123">此命令是单行文本。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-123">This command is a single line of text.</span></span> <span data-ttu-id="9e4bc-124">此命令启用 /\<*WCF 应用程序*> 应用程序使用同时访问`http://localhost/<WCF Application>`和`net.tcp://localhost/<WCF Application>`。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-124">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>
  
     <span data-ttu-id="9e4bc-125">移除为此示例添加的 net.tcp 网站绑定。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-125">Remove the net.tcp site binding you added for this sample.</span></span>  
  
     <span data-ttu-id="9e4bc-126">为方便起见，在位于示例目录中名为 RemoveNetTcpSiteBinding.cmd 的批处理文件中实现以下两个步骤。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-126">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>  
  
    1.  <span data-ttu-id="9e4bc-127">通过在管理员级别命令提示符窗口中运行以下命令，从启用的协议列表移除 net.tcp。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-127">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="9e4bc-128">此命令是单行文本。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-128">This command is a single line of text.</span></span>  
  
    2.  <span data-ttu-id="9e4bc-129">通过在提升的命令提示符窗口中运行以下命令移除 net.tcp 网站绑定：</span><span class="sxs-lookup"><span data-stu-id="9e4bc-129">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="9e4bc-130">此命令是单行文本。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-130">This command is a single line of text.</span></span>  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="9e4bc-131">从启用的协议列表中移除 net.tcp</span><span class="sxs-lookup"><span data-stu-id="9e4bc-131">To remove net.tcp from the list of enabled protocols</span></span>  
  
1.  <span data-ttu-id="9e4bc-132">若要从启用的协议列表中移除 net.tcp，请在管理员级别命令提示符窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-132">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="9e4bc-133">此命令是单行文本。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-133">This command is a single line of text.</span></span>  
  
### <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="9e4bc-134">移除 net.tcp 网站绑定</span><span class="sxs-lookup"><span data-stu-id="9e4bc-134">To remove the net.tcp site binding</span></span>  
  
1.  <span data-ttu-id="9e4bc-135">要移除 net.tcp 网站绑定，请在管理员级别命令提示窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-135">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="9e4bc-136">此命令是单行文本。</span><span class="sxs-lookup"><span data-stu-id="9e4bc-136">This command is a single line of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e4bc-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e4bc-137">See Also</span></span>  
 [<span data-ttu-id="9e4bc-138">TCP 激活</span><span class="sxs-lookup"><span data-stu-id="9e4bc-138">TCP Activation</span></span>](../../../../docs/framework/wcf/samples/tcp-activation.md)  
 [<span data-ttu-id="9e4bc-139">MSMQ 激活</span><span class="sxs-lookup"><span data-stu-id="9e4bc-139">MSMQ Activation</span></span>](../../../../docs/framework/wcf/samples/msmq-activation.md)  
 [<span data-ttu-id="9e4bc-140">NamedPipe 激活</span><span class="sxs-lookup"><span data-stu-id="9e4bc-140">NamedPipe Activation</span></span>](../../../../docs/framework/wcf/samples/namedpipe-activation.md)  
 [<span data-ttu-id="9e4bc-141">Windows Server App Fabric 承载功能</span><span class="sxs-lookup"><span data-stu-id="9e4bc-141">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
