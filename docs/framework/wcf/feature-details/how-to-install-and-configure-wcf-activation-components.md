---
title: 如何：安装和配置 WCF 激活组件
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 0a7be97ec157638db3eb2d656fe263b37b8d676c
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837410"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a><span data-ttu-id="09541-102">如何：安装和配置 WCF 激活组件</span><span class="sxs-lookup"><span data-stu-id="09541-102">How to: Install and Configure WCF Activation Components</span></span>

<span data-ttu-id="09541-103">本主题介绍在 Windows Vista 上设置 Windows 进程激活服务（也称为 WAS）以承载不通过 HTTP 网络协议进行通信的 Windows Communication Foundation （WCF）服务所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="09541-103">This topic describes the steps required to set up Windows Process Activation Service (also known as WAS) on Windows Vista to host Windows Communication Foundation (WCF) services that do not communicate over HTTP network protocols.</span></span> <span data-ttu-id="09541-104">下面的部分略述此配置的步骤：</span><span class="sxs-lookup"><span data-stu-id="09541-104">The following sections outline the steps for this configuration:</span></span>

- <span data-ttu-id="09541-105">安装（或确认安装） WCF 激活组件。</span><span class="sxs-lookup"><span data-stu-id="09541-105">Install (or confirm the installation of) the WCF activation components.</span></span>

- <span data-ttu-id="09541-106">配置 WAS 以支持非 HTTP 协议。</span><span class="sxs-lookup"><span data-stu-id="09541-106">Configure WAS to support a non-HTTP protocol.</span></span> <span data-ttu-id="09541-107">以下过程将 Windows Vista 配置为进行 TCP 激活。</span><span class="sxs-lookup"><span data-stu-id="09541-107">The following procedure configures Windows Vista for TCP activation.</span></span>

<span data-ttu-id="09541-108">安装和配置 WAS 之后，请参阅[中的如何：在 WAS 中承载 Wcf 服务](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)，了解如何创建 wcf 服务，该服务公开了采用 WAS 的非 HTTP 终结点。</span><span class="sxs-lookup"><span data-stu-id="09541-108">After installing and configuring WAS, see [How to: Host a WCF Service in WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) for the procedures to create a WCF service that exposes an non-HTTP endpoint that employs WAS.</span></span>

## <a name="to-install-the-wcf-non-http-activation-components"></a><span data-ttu-id="09541-109">安装 WCF 非 HTTP 激活组件</span><span class="sxs-lookup"><span data-stu-id="09541-109">To install the WCF non-HTTP activation components</span></span>

1. <span data-ttu-id="09541-110">单击 "**开始**" 按钮，然后单击 "**控制面板**"。</span><span class="sxs-lookup"><span data-stu-id="09541-110">Click the **Start** button, and then click **Control Panel**.</span></span>

2. <span data-ttu-id="09541-111">单击“程序”，然后单击“程序和功能”。</span><span class="sxs-lookup"><span data-stu-id="09541-111">Click **Programs**, and then click **Programs and Features**.</span></span>

3. <span data-ttu-id="09541-112">在 "**任务**" 菜单上，单击 "**打开或关闭 Windows 功能**"。</span><span class="sxs-lookup"><span data-stu-id="09541-112">On the **Tasks** menu, click **Turn Windows features on or off**.</span></span>

4. <span data-ttu-id="09541-113">找到 WinFX 节点，选择它，然后将其展开。</span><span class="sxs-lookup"><span data-stu-id="09541-113">Find the WinFX node, select and then expand it.</span></span>

5. <span data-ttu-id="09541-114">选择 " **WCF 非 Http 激活组件**" 框并保存设置。</span><span class="sxs-lookup"><span data-stu-id="09541-114">Select the **WCF Non-Http Activation Components** box and save the setting.</span></span>

## <a name="to-configure-the-was-to-support-tcp-activation"></a><span data-ttu-id="09541-115">配置 WAS 以支持 TCP 激活</span><span class="sxs-lookup"><span data-stu-id="09541-115">To configure the WAS to support TCP activation</span></span>

1. <span data-ttu-id="09541-116">若要支持 net.tcp 激活，必须首先将默认的网站绑定到一个 net.tcp 端口。</span><span class="sxs-lookup"><span data-stu-id="09541-116">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="09541-117">可以通过使用随 IIS 7.0 管理工具集安装的 Appcmd.exe 来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="09541-117">You can do this by using Appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="09541-118">在管理员级别命令提示符窗口中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="09541-118">In an administrator-level Command Prompt window, run the following command.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="09541-119">此命令是单行文本。</span><span class="sxs-lookup"><span data-stu-id="09541-119">This command is a single line of text.</span></span> <span data-ttu-id="09541-120">此命令将 net.tcp 网站绑定添加到以任何主机名侦听 TCP 端口 808 的默认网站。</span><span class="sxs-lookup"><span data-stu-id="09541-120">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any host name.</span></span>

2. <span data-ttu-id="09541-121">尽管网站内的所有应用程序共享一个公共 net.tcp 绑定，但是每个应用程序可以单独启用 net.tcp 支持。</span><span class="sxs-lookup"><span data-stu-id="09541-121">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="09541-122">若要启用应用程序的 net.tcp，请从管理员级别命令提示符运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="09541-122">To enable net.tcp for the application, run the following command from an administrator-level command prompt.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp
    ```

    > [!NOTE]
    > <span data-ttu-id="09541-123">此命令是单行文本。</span><span class="sxs-lookup"><span data-stu-id="09541-123">This command is a single line of text.</span></span> <span data-ttu-id="09541-124">此命令启用/\<*WCF 应用*程序 > 使用 `http://localhost/<WCF Application>` 和 `net.tcp://localhost/<WCF Application>`访问该应用程序。</span><span class="sxs-lookup"><span data-stu-id="09541-124">This command enables the /\<*WCF Application*> application to be accessed using both `http://localhost/<WCF Application>` and `net.tcp://localhost/<WCF Application>`.</span></span>

     <span data-ttu-id="09541-125">移除为此示例添加的 net.tcp 网站绑定。</span><span class="sxs-lookup"><span data-stu-id="09541-125">Remove the net.tcp site binding you added for this sample.</span></span>

     <span data-ttu-id="09541-126">为方便起见，在位于示例目录中名为 RemoveNetTcpSiteBinding.cmd 的批处理文件中实现以下两个步骤。</span><span class="sxs-lookup"><span data-stu-id="09541-126">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>

    1. <span data-ttu-id="09541-127">通过在管理员级别命令提示符窗口中运行以下命令，从启用的协议列表移除 net.tcp。</span><span class="sxs-lookup"><span data-stu-id="09541-127">Remove net.tcp from the list of enabled protocols by running the following command in an administrator-level Command Prompt window.</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
        ```

        > [!NOTE]
        > <span data-ttu-id="09541-128">此命令是单行文本。</span><span class="sxs-lookup"><span data-stu-id="09541-128">This command is a single line of text.</span></span>

    2. <span data-ttu-id="09541-129">通过在提升的命令提示符窗口中运行以下命令移除 net.tcp 网站绑定：</span><span class="sxs-lookup"><span data-stu-id="09541-129">Remove the net.tcp site binding by running the following command in an elevated Command Prompt window:</span></span>

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        --bindings.[protocol='net.tcp',bindingInformation='808:*']
        ```

        > [!NOTE]
        > <span data-ttu-id="09541-130">此命令是单行文本。</span><span class="sxs-lookup"><span data-stu-id="09541-130">This command is a single line of text.</span></span>

## <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a><span data-ttu-id="09541-131">从启用的协议列表中移除 net.tcp</span><span class="sxs-lookup"><span data-stu-id="09541-131">To remove net.tcp from the list of enabled protocols</span></span>

1. <span data-ttu-id="09541-132">若要从启用的协议列表中移除 net.tcp，请在管理员级别命令提示符窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="09541-132">To remove net.tcp from the list of enabled protocols, run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http
    ```

    > [!NOTE]
    > <span data-ttu-id="09541-133">此命令是单行文本。</span><span class="sxs-lookup"><span data-stu-id="09541-133">This command is a single line of text.</span></span>

## <a name="to-remove-the-nettcp-site-binding"></a><span data-ttu-id="09541-134">移除 net.tcp 网站绑定</span><span class="sxs-lookup"><span data-stu-id="09541-134">To remove the net.tcp site binding</span></span>

1. <span data-ttu-id="09541-135">要移除 net.tcp 网站绑定，请在管理员级别命令提示窗口中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="09541-135">To remove the net.tcp site binding run the following command in an administrator-level Command Prompt window.</span></span>

    ```console
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
    -bindings.[protocol='net.tcp',bindingInformation='808:*']
    ```

    > [!NOTE]
    > <span data-ttu-id="09541-136">此命令是单行文本。</span><span class="sxs-lookup"><span data-stu-id="09541-136">This command is a single line of text.</span></span>

## <a name="see-also"></a><span data-ttu-id="09541-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09541-137">See also</span></span>

- [<span data-ttu-id="09541-138">TCP 激活</span><span class="sxs-lookup"><span data-stu-id="09541-138">TCP Activation</span></span>](../../../../docs/framework/wcf/samples/tcp-activation.md)
- [<span data-ttu-id="09541-139">MSMQ 激活</span><span class="sxs-lookup"><span data-stu-id="09541-139">MSMQ Activation</span></span>](../../../../docs/framework/wcf/samples/msmq-activation.md)
- [<span data-ttu-id="09541-140">NamedPipe 激活</span><span class="sxs-lookup"><span data-stu-id="09541-140">NamedPipe Activation</span></span>](../../../../docs/framework/wcf/samples/namedpipe-activation.md)
- [<span data-ttu-id="09541-141">Windows Server App Fabric 承载功能</span><span class="sxs-lookup"><span data-stu-id="09541-141">Windows Server App Fabric Hosting Features</span></span>](https://go.microsoft.com/fwlink/?LinkId=201276)
