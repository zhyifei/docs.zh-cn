---
title: 如何：安装和卸载服务
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Service applications, deploying
- services, uninstalling
- services, installing
- installing Windows Services
- uninstalling applications, Windows Services
- installation, Windows Services
- uninstalling Windows Services
- installutil.exe tool
ms.assetid: c89c5169-f567-4305-9d62-db31a1de5481
author: ghogen
manager: douge
ms.openlocfilehash: 9d8e84280b5821f8d8df36694198bd85fb8470d4
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45673982"
---
# <a name="how-to-install-and-uninstall-services"></a><span data-ttu-id="56cbb-102">如何：安装和卸载服务</span><span class="sxs-lookup"><span data-stu-id="56cbb-102">How to: Install and Uninstall Services</span></span>
<span data-ttu-id="56cbb-103">如果你正使用 .NET Framework 开发 Windows 服务，你可以使用名为 InstallUtil.exe 的命令行实用工具快速安装服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="56cbb-103">If you’re developing a Windows Service by using the .NET Framework, you can quickly install your service application by using a command-line utility called InstallUtil.exe.</span></span> <span data-ttu-id="56cbb-104">如果你是一个想要发布用户可以安装和卸载的 Windows 服务的开发人员，应使用 InstallShield。</span><span class="sxs-lookup"><span data-stu-id="56cbb-104">If you’re a developer who wants to release a Windows Service that users can install and uninstall  you should use InstallShield.</span></span> <span data-ttu-id="56cbb-105">请参阅 [Windows Installer 部署](https://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0)。</span><span class="sxs-lookup"><span data-stu-id="56cbb-105">See [Windows Installer Deployment](https://msdn.microsoft.com/library/121be21b-b916-43e2-8f10-8b080516d2a0).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="56cbb-106">如果你想要从你的计算机卸载服务，不要遵循本文中的步骤。</span><span class="sxs-lookup"><span data-stu-id="56cbb-106">If you want to uninstall a service from your computer, don’t follow the steps in this article.</span></span> <span data-ttu-id="56cbb-107">相反，你应找出哪些程序或软件包安装了该服务，然后在控制面板中选择“添加/删除程序”卸载该程序。</span><span class="sxs-lookup"><span data-stu-id="56cbb-107">Instead, find out which program or software package installed the service, and then choose **Add/Remove Programs** in Control Panel to uninstall that program.</span></span> <span data-ttu-id="56cbb-108">请注意，许多服务是 Windows 不可或缺的部分；如果你删除它们，可能导致系统不稳定。</span><span class="sxs-lookup"><span data-stu-id="56cbb-108">Note that many services are integral parts of Windows; if you remove them, you might cause system instability.</span></span>  
  
 <span data-ttu-id="56cbb-109">要使用本文中的步骤，你首先需要将服务安装程序添加到你的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="56cbb-109">In order to use the steps in this article, you first need to add a service installer to your Windows Service.</span></span> <span data-ttu-id="56cbb-110">请参阅[演练：在组件设计器中创建 Windows 服务应用程序](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="56cbb-110">See [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
 <span data-ttu-id="56cbb-111">无法通过按 F5 从 Visual Studio 开发环境直接运行 Windows 服务项目。</span><span class="sxs-lookup"><span data-stu-id="56cbb-111">Windows Service projects cannot be run directly from the Visual Studio development environment by pressing F5.</span></span> <span data-ttu-id="56cbb-112">这是因为必须先安装项目中的服务，然后才能运行项目。</span><span class="sxs-lookup"><span data-stu-id="56cbb-112">This is because the service in the project must be installed before you can run the project.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="56cbb-113">可以启动“服务器资源管理器”，验证是否已经安装或卸载你的服务。</span><span class="sxs-lookup"><span data-stu-id="56cbb-113">You can launch **Server Explorer** and verify that your service has been installed or uninstalled.</span></span> <span data-ttu-id="56cbb-114">有关详细信息，请参阅如何：访问和初始化服务器资源管理器-数据库资源管理器。</span><span class="sxs-lookup"><span data-stu-id="56cbb-114">For more information, see How to: Access and Initialize Server Explorer-Database Explorer.</span></span>  
  
### <a name="to-install-your-service-manually"></a><span data-ttu-id="56cbb-115">若要手动安装你的服务</span><span class="sxs-lookup"><span data-stu-id="56cbb-115">To install your service manually</span></span>  
  
1.  <span data-ttu-id="56cbb-116">在 Windows“启动”菜单或“启动”屏幕上，依次选择“Visual Studio”、“Visual Studio Tools”、“开发人员命令提示”。</span><span class="sxs-lookup"><span data-stu-id="56cbb-116">On the Windows **Start** menu or **Start** screen, choose **Visual Studio** , **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="56cbb-117">出现 Visual Studio 命令提示。</span><span class="sxs-lookup"><span data-stu-id="56cbb-117">A Visual Studio command prompt appears.</span></span>  
  
2.  <span data-ttu-id="56cbb-118">访问你的项目的已编译可执行文件所在的目录。</span><span class="sxs-lookup"><span data-stu-id="56cbb-118">Access the directory where your project's compiled executable file is located.</span></span>  
  
3.  <span data-ttu-id="56cbb-119">以你的项目的可执行文件作为参数，通过命令提示运行 InstallUtil.exe：</span><span class="sxs-lookup"><span data-stu-id="56cbb-119">Run InstallUtil.exe from the command prompt with your project's executable as a parameter:</span></span>  
  
    ```  
    installutil <yourproject>.exe  
    ```  
  
     <span data-ttu-id="56cbb-120">如果使用 Visual Studio 命令提示，InstallUtil.exe 应该在系统路径上。</span><span class="sxs-lookup"><span data-stu-id="56cbb-120">If you’re using the Visual Studio command prompt, InstallUtil.exe should be on the system path.</span></span> <span data-ttu-id="56cbb-121">如果不在，你可以将其添加到该路径，或使用完全限定的路径来调用它。</span><span class="sxs-lookup"><span data-stu-id="56cbb-121">If not, you can add it to the path, or use the fully qualified path to invoke it.</span></span> <span data-ttu-id="56cbb-122">此工具随 .NET Framework 安装，其路径为 `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`。</span><span class="sxs-lookup"><span data-stu-id="56cbb-122">This tool is installed with the .NET Framework, and its path is `%WINDIR%\Microsoft.NET\Framework[64]\<framework_version>`.</span></span> <span data-ttu-id="56cbb-123">例如，对于 32 位版本的 .NET Framework 4 或 4.5.\*，如果你的 Windows 安装目录为 C:\Windows，则该路径为 `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`。</span><span class="sxs-lookup"><span data-stu-id="56cbb-123">For example, for the 32-bit version of the .NET Framework 4 or 4.5.\*, if your Windows installation directory is C:\Windows, the path is `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span></span> <span data-ttu-id="56cbb-124">对于 64 位版本的 .NET Framework 4 或 4.5.\*，默认路径为 `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`。</span><span class="sxs-lookup"><span data-stu-id="56cbb-124">For the 64-bit version of the .NET Framework 4 or 4.5.\*, the default path is `C:\Windows\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe`.</span></span>  
  
### <a name="to-uninstall-your-service-manually"></a><span data-ttu-id="56cbb-125">若要手动卸载你的服务</span><span class="sxs-lookup"><span data-stu-id="56cbb-125">To uninstall your service manually</span></span>  
  
1.  <span data-ttu-id="56cbb-126">在 Windows“启动”菜单或“启动”屏幕上，依次选择“Visual Studio”、“Visual Studio Tools”、“开发人员命令提示”。</span><span class="sxs-lookup"><span data-stu-id="56cbb-126">On the Windows **Start** menu or **Start** screen, choose **Visual Studio**, **Visual Studio Tools**, **Developer Command Prompt**.</span></span>  
  
     <span data-ttu-id="56cbb-127">出现 Visual Studio 命令提示。</span><span class="sxs-lookup"><span data-stu-id="56cbb-127">A Visual Studio command prompt appears.</span></span>  
  
2.  <span data-ttu-id="56cbb-128">以你的项目的输出作为参数，通过命令提示运行 InstallUtil.exe：</span><span class="sxs-lookup"><span data-stu-id="56cbb-128">Run InstallUtil.exe from the command prompt with your project's output as a parameter:</span></span>  
  
    ```  
    installutil /u <yourproject>.exe  
    ```  
  
3.  <span data-ttu-id="56cbb-129">有时，服务的可执行文件被删除后，该服务可能仍然会出现在注册表中。</span><span class="sxs-lookup"><span data-stu-id="56cbb-129">Sometimes, after the executable for a service is deleted, the service might still be present in the registry.</span></span> <span data-ttu-id="56cbb-130">这种情况下，请使用命令 [sc delete](https://technet.microsoft.com/library/cc742045.aspx) 从注册表中删除服务的条目。</span><span class="sxs-lookup"><span data-stu-id="56cbb-130">In that case, use the command [sc delete](https://technet.microsoft.com/library/cc742045.aspx) to remove the entry for the service from the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56cbb-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="56cbb-131">See Also</span></span>  
 [<span data-ttu-id="56cbb-132">Windows 服务应用程序介绍</span><span class="sxs-lookup"><span data-stu-id="56cbb-132">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="56cbb-133">如何：创建 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="56cbb-133">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="56cbb-134">如何：将安装程序添加到服务应用程序</span><span class="sxs-lookup"><span data-stu-id="56cbb-134">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="56cbb-135">Installutil.exe（安装程序工具）</span><span class="sxs-lookup"><span data-stu-id="56cbb-135">Installutil.exe (Installer Tool)</span></span>](../../../docs/framework/tools/installutil-exe-installer-tool.md)
