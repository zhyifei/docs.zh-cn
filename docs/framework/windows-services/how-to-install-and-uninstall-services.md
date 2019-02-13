---
title: 如何：安装和卸载 Windows 服务
ms.date: 02/05/2019
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, apps, Windows services
- installation, Windows services
- uninstalling Windows services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
ms.openlocfilehash: 43b5ad2f346406897e8bcbcce5660a6c9524f9af
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/07/2019
ms.locfileid: "55826249"
---
# <a name="how-to-install-and-uninstall-windows-services"></a><span data-ttu-id="931ab-102">如何：安装和卸载 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="931ab-102">How to: Install and uninstall Windows services</span></span>
<span data-ttu-id="931ab-103">如果正使用 .NET Framework 开发 Windows 服务，可以使用 [InstallUtil.exe](../tools/installutil-exe-installer-tool.md) 的命令行实用工具快速安装服务应用。</span><span class="sxs-lookup"><span data-stu-id="931ab-103">If you’re developing a Windows service with the .NET Framework, you can quickly install your service app by using the [*InstallUtil.exe*](../tools/installutil-exe-installer-tool.md) command-line utility.</span></span> <span data-ttu-id="931ab-104">想要发布用户可以安装和卸载的 Windows 服务的开发者，应使用 InstallShield。</span><span class="sxs-lookup"><span data-stu-id="931ab-104">Developers who want to release a Windows service that users can install and uninstall should use InstallShield.</span></span> <span data-ttu-id="931ab-105">有关详细信息，请参阅[创建安装程序包（Windows 客户端）](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client)。</span><span class="sxs-lookup"><span data-stu-id="931ab-105">For more information, see [Create an installer package (Windows client)](https://docs.microsoft.com/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-client).</span></span>
  
> [!WARNING]
>  <span data-ttu-id="931ab-106">如果你想要从你的计算机卸载服务，不要遵循本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="931ab-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="931ab-107">而是找出安装了该服务的程序或软件包，然后在“设置”中选择“应用”来卸载该程序。</span><span class="sxs-lookup"><span data-stu-id="931ab-107">Instead, find out which program or software package installed the service, and then choose **Apps** in Settings to uninstall that program.</span></span> <span data-ttu-id="931ab-108">请注意，许多服务是 Windows 不可或缺的部分；如果你删除它们，可能导致系统不稳定。</span><span class="sxs-lookup"><span data-stu-id="931ab-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>  
  
 <span data-ttu-id="931ab-109">要使用本文中的步骤，首先需要将服务安装程序添加到 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="931ab-109">To use the steps in this article, you first need to add a service installer to your Windows service.</span></span> <span data-ttu-id="931ab-110">有关详细信息，请参见[演练：创建 Windows 服务应用](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="931ab-110">For more information, see [Walkthrough: Creating a Windows service app](../windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
 <span data-ttu-id="931ab-111">无法通过按 F5 从 Visual Studio 开发环境直接运行 Windows 服务项目。</span><span class="sxs-lookup"><span data-stu-id="931ab-111">You can't run Windows service projects directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="931ab-112">必须先在项目中安装服务，然后才能运行该项目。</span><span class="sxs-lookup"><span data-stu-id="931ab-112">Before you can run the project, you must install the service in the project.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="931ab-113">可以使用“服务器资源管理器”验证是否已安装或卸载服务。</span><span class="sxs-lookup"><span data-stu-id="931ab-113">You can use **Server Explorer** to verify that you've installed or uninstalled your service.</span></span> <span data-ttu-id="931ab-114">有关详细信息，请参阅[如何在 Visual Studio 中使用服务器资源管理器](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="931ab-114">For more information, see [How to use Server Explorer in Visual Studio](https://support.microsoft.com/help/316649/how-to-use-the-server-explorer-in-visual-studio-net-and-visual-studio).</span></span>
  
### <a name="install-your-service-manually"></a><span data-ttu-id="931ab-115">手动安装服务</span><span class="sxs-lookup"><span data-stu-id="931ab-115">Install your service manually</span></span>  
  
1.  <span data-ttu-id="931ab-116">从“开始”菜单中选择“Visual Studio \<版本>”目录，然后选择“VS \<版本>开发人员命令提示”。</span><span class="sxs-lookup"><span data-stu-id="931ab-116">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>
  
     <span data-ttu-id="931ab-117">出现“Visual Studio 开发人员命令提示”。</span><span class="sxs-lookup"><span data-stu-id="931ab-117">The Developer Command Prompt for Visual Studio appears.</span></span> 
  
2.  <span data-ttu-id="931ab-118">访问你的项目的已编译可执行文件所在的目录。</span><span class="sxs-lookup"><span data-stu-id="931ab-118">Access the directory where your project's compiled executable file is located.</span></span>  
  
3.  <span data-ttu-id="931ab-119">将项目的可执行文件作为参数，通过命令提示运行 InstallUtil.exe：</span><span class="sxs-lookup"><span data-stu-id="931ab-119">Run *InstallUtil.exe* from the command prompt with your project's executable as a parameter:</span></span>  
  
    ```console
    installutil <yourproject>.exe  
    ```  

     <span data-ttu-id="931ab-120">如果使用的是 Visual Studio 开发人员命令提示，InstallUtil.exe 应该在系统路径上。</span><span class="sxs-lookup"><span data-stu-id="931ab-120">If you’re using the Developer Command Prompt for Visual Studio, *InstallUtil.exe* should be on the system path.</span></span> <span data-ttu-id="931ab-121">如果不在，可以将其添加到该路径，或使用完全限定的路径来调用它。</span><span class="sxs-lookup"><span data-stu-id="931ab-121">Otherwise, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="931ab-122">此工具随 .NET Framework 安装在 %WINDIR%\Microsoft.NET\Framework[64]\\<framework_version> 中。</span><span class="sxs-lookup"><span data-stu-id="931ab-122">This tool is installed with the .NET Framework in *%WINDIR%\Microsoft.NET\Framework[64]\\<framework_version>*.</span></span>
     
     <span data-ttu-id="931ab-123">例如:</span><span class="sxs-lookup"><span data-stu-id="931ab-123">For example:</span></span>
     - <span data-ttu-id="931ab-124">对于 32 位版的 .NET Framework 4 或 4.5 以及更高版本，如果 Windows 安装目录是 C: \ Windows，则默认路径是 C:\Windows\ Microsoft.NET \ Framework \ v4.0.30319 \ InstallUtil.exe。</span><span class="sxs-lookup"><span data-stu-id="931ab-124">For the 32-bit version of the .NET Framework 4 or 4.5 and later, if your Windows installation directory is *C:\Windows*, the default path is *C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*.</span></span>
     - <span data-ttu-id="931ab-125">对于 64 位版的 .NET Framework 4 或 4.5 以及更高版本，默认路径是 C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe。</span><span class="sxs-lookup"><span data-stu-id="931ab-125">For the 64-bit version of the .NET Framework 4 or 4.5 and later, the default path is *C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>
  
### <a name="uninstall-your-service-manually"></a><span data-ttu-id="931ab-126">手动卸载服务</span><span class="sxs-lookup"><span data-stu-id="931ab-126">Uninstall your service manually</span></span>  
  
1. <span data-ttu-id="931ab-127">从“开始”菜单中选择“Visual Studio \<版本>”目录，然后选择“VS \<版本>开发人员命令提示”。</span><span class="sxs-lookup"><span data-stu-id="931ab-127">From the **Start** menu, select the **Visual Studio \<*version*>** directory, then select **Developer Command Prompt for VS \<*version*>**.</span></span>
  
     <span data-ttu-id="931ab-128">出现“Visual Studio 开发人员命令提示”。</span><span class="sxs-lookup"><span data-stu-id="931ab-128">The Developer Command Prompt for Visual Studio appears.</span></span>  
  
2.  <span data-ttu-id="931ab-129">将项目的输出作为参数，通过命令提示运行 InstallUtil.exe：</span><span class="sxs-lookup"><span data-stu-id="931ab-129">Run *InstallUtil.exe* from the command prompt with your project's output as a parameter:</span></span>  
  
    ```console  
    installutil /u <yourproject>.exe  
    ```  
  
3. <span data-ttu-id="931ab-130">删除服务的可执行文件后，该服务可能仍然会出现在注册表中。</span><span class="sxs-lookup"><span data-stu-id="931ab-130">After the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="931ab-131">如果发生这种情况下，请使用命令 [sc delete](/windows-server/administration/windows-commands/sc-delete) 从注册表中删除服务的条目。</span><span class="sxs-lookup"><span data-stu-id="931ab-131">If that's the case, use the command [sc delete](/windows-server/administration/windows-commands/sc-delete) to remove the entry for the service from the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="931ab-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="931ab-132">See also</span></span>
- [<span data-ttu-id="931ab-133">Windows 服务应用程序简介</span><span class="sxs-lookup"><span data-stu-id="931ab-133">Introduction to Windows service applications</span></span>](../windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="931ab-134">如何：创建 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="931ab-134">How to: Create Windows services</span></span>](../windows-services/how-to-create-windows-services.md)
- [<span data-ttu-id="931ab-135">如何：将安装程序添加到服务应用程序</span><span class="sxs-lookup"><span data-stu-id="931ab-135">How to: Add installers to your service application</span></span>](../windows-services/how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="931ab-136">Installutil.exe（安装程序工具）</span><span class="sxs-lookup"><span data-stu-id="931ab-136">Installutil.exe (Installer tool)</span></span>](../tools/installutil-exe-installer-tool.md)
