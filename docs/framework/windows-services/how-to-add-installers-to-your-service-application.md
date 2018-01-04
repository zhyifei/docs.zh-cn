---
title: "如何：将安装程序添加到服务应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Service applications, deploying
- installation components, adding to services
- installers, adding to services
- Windows Service applications, adding installers
- services, adding installers
- ServiceInstaller class, adding installers to services
- ServiceProcessInstaller class, adding installers to services
ms.assetid: 8b698e9a-b88e-4f44-ae45-e0c5ea0ae5a8
caps.latest.revision: "14"
author: ghogen
ms.author: ghogen
manager: douge
ms.workload: dotnet
ms.openlocfilehash: 0dcb666f317ab285ae0156d2df16947f71665aee
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-installers-to-your-service-application"></a><span data-ttu-id="bc1fe-102">如何：将安装程序添加到服务应用程序</span><span class="sxs-lookup"><span data-stu-id="bc1fe-102">How to: Add Installers to Your Service Application</span></span>
<span data-ttu-id="bc1fe-103">Visual Studio 会安装组件，可以安装与你的服务应用程序关联的资源。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-103">Visual Studio ships installation components that can install resources associated with your service applications.</span></span> <span data-ttu-id="bc1fe-104">安装组件注册到它正在安装并让服务控制管理器知道存在该服务在系统上的某一项服务。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-104">Installation components register an individual service on the system to which it is being installed and let the Services Control Manager know that the service exists.</span></span> <span data-ttu-id="bc1fe-105">当与服务应用程序时，你可以在属性窗口，自动将适当的安装程序添加到你的项目中选择一个链接。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-105">When you work with a service application, you can select a link in the Properties window to automatically add the appropriate installers to your project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc1fe-106">你的服务的属性值将服务类中复制到安装程序类。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-106">Property values for your service are copied from the service class to the installer class.</span></span> <span data-ttu-id="bc1fe-107">如果你更新服务类上的属性值，它们不会自动更新在安装程序。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-107">If you update the property values on the service class, they are not automatically updated in the installer.</span></span>  
  
 <span data-ttu-id="bc1fe-108">将安装程序添加到项目中，新类 (其中，默认情况下，名为`ProjectInstaller`) 中的项目，以及适当的安装选项在其中创建组件的实例创建。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-108">When you add an installer to your project, a new class (which, by default, is named `ProjectInstaller`) is created in the project, and instances of the appropriate installation components are created within it.</span></span> <span data-ttu-id="bc1fe-109">此类的所有安装组件的中心点充当你的项目需要。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-109">This class acts as a central point for all of the installation components your project needs.</span></span> <span data-ttu-id="bc1fe-110">例如，如果您将第二个服务添加到你的应用程序，并单击添加安装程序链接，并不会创建第二个安装程序类;相反，第二个服务的必需的其他安装组件将添加到现有的类。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-110">For example, if you add a second service to your application and click the Add Installer link, a second installer class is not created; instead, the necessary additional installation component for the second service is added to the existing class.</span></span>  
  
 <span data-ttu-id="bc1fe-111">不需要在要使您正确安装的服务的安装程序中任何特殊编码。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-111">You do not need to do any special coding within the installers to make your services install correctly.</span></span> <span data-ttu-id="bc1fe-112">但是，你有时可能需要修改安装程序的内容，如果你需要将特殊的功能添加到安装过程。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-112">However, you may occasionally need to modify the contents of the installers if you need to add special functionality to the installation process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc1fe-113">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bc1fe-114">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bc1fe-115">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-installers-to-your-service-application"></a><span data-ttu-id="bc1fe-116">将安装程序添加到服务应用程序</span><span class="sxs-lookup"><span data-stu-id="bc1fe-116">To add installers to your service application</span></span>  
  
1.  <span data-ttu-id="bc1fe-117">在**解决方案资源管理器**，访问**设计**你想要添加的安装组件服务的视图。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-117">In **Solution Explorer**, access **Design** view for the service for which you want to add an installation component.</span></span>  
  
2.  <span data-ttu-id="bc1fe-118">本身，而不是它的任何内容，请单击要选择的服务的设计器的背景。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-118">Click the background of the designer to select the service itself, rather than any of its contents.</span></span>  
  
3.  <span data-ttu-id="bc1fe-119">与设计器中焦点，右键单击，然后单击**添加安装程序**。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-119">With the designer in focus, right-click, and then click **Add Installer**.</span></span>  
  
     <span data-ttu-id="bc1fe-120">一个新的类， `ProjectInstaller`，和两个安装组件，<xref:System.ServiceProcess.ServiceProcessInstaller>和<xref:System.ServiceProcess.ServiceInstaller>，为服务复制到组件添加到你的项目，然后属性值。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-120">A new class, `ProjectInstaller`, and two installation components, <xref:System.ServiceProcess.ServiceProcessInstaller> and <xref:System.ServiceProcess.ServiceInstaller>, are added to your project, and property values for the service are copied to the components.</span></span>  
  
4.  <span data-ttu-id="bc1fe-121">单击<xref:System.ServiceProcess.ServiceInstaller>组件并验证的值<xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A>属性设置为相同的值<xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A>服务本身上的属性。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-121">Click the <xref:System.ServiceProcess.ServiceInstaller> component and verify that the value of the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to the same value as the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property on the service itself.</span></span>  
  
5.  <span data-ttu-id="bc1fe-122">若要确定你的服务将启动方式如何，请单击<xref:System.ServiceProcess.ServiceInstaller>组件，并且已设置<xref:System.ServiceProcess.ServiceInstaller.StartType%2A>为适当的值的属性。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-122">To determine how your service will be started, click the <xref:System.ServiceProcess.ServiceInstaller> component and set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to the appropriate value.</span></span>  
  
    |<span data-ttu-id="bc1fe-123">“值”</span><span class="sxs-lookup"><span data-stu-id="bc1fe-123">Value</span></span>|<span data-ttu-id="bc1fe-124">结果</span><span class="sxs-lookup"><span data-stu-id="bc1fe-124">Result</span></span>|  
    |-----------|------------|  
    |<xref:System.ServiceProcess.ServiceStartMode.Manual>|<span data-ttu-id="bc1fe-125">安装后必须手动启动该服务。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-125">The service must be manually started after installation.</span></span> <span data-ttu-id="bc1fe-126">有关详细信息，请参阅[如何： 启动服务](../../../docs/framework/windows-services/how-to-start-services.md)。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-126">For more information, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Automatic>|<span data-ttu-id="bc1fe-127">该服务将启动时，计算机重新启动。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-127">The service will start by itself whenever the computer reboots.</span></span>|  
    |<xref:System.ServiceProcess.ServiceStartMode.Disabled>|<span data-ttu-id="bc1fe-128">无法启动服务。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-128">The service cannot be started.</span></span>|  
  
6.  <span data-ttu-id="bc1fe-129">若要确定你的服务将在其中运行的安全上下文，请单击<xref:System.ServiceProcess.ServiceProcessInstaller>组件，并设置适当的属性值。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-129">To determine the security context in which your service will run, click the <xref:System.ServiceProcess.ServiceProcessInstaller> component and set the appropriate property values.</span></span> <span data-ttu-id="bc1fe-130">有关详细信息，请参阅[如何： 指定服务的安全上下文](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-130">For more information, see [How to: Specify the Security Context for Services](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md).</span></span>  
  
7.  <span data-ttu-id="bc1fe-131">重写任何方法，你需要执行自定义处理。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-131">Override any methods for which you need to perform custom processing.</span></span>  
  
8.  <span data-ttu-id="bc1fe-132">为你的项目中每项附加服务执行步骤 1 至 7。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-132">Perform steps 1 through 7 for each additional service in your project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc1fe-133">对于你的项目中每个其他服务，必须添加其他<xref:System.ServiceProcess.ServiceInstaller>到项目的组件`ProjectInstaller`类。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-133">For each additional service in your project, you must add an additional <xref:System.ServiceProcess.ServiceInstaller> component to the project's `ProjectInstaller` class.</span></span> <span data-ttu-id="bc1fe-134"><xref:System.ServiceProcess.ServiceProcessInstaller>组件添加在步骤 3 中适用于所有项目中的单个服务安装程序。</span><span class="sxs-lookup"><span data-stu-id="bc1fe-134">The <xref:System.ServiceProcess.ServiceProcessInstaller> component added in step three works with all of the individual service installers in the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc1fe-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc1fe-135">See Also</span></span>  
 [<span data-ttu-id="bc1fe-136">Windows 服务应用程序介绍</span><span class="sxs-lookup"><span data-stu-id="bc1fe-136">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="bc1fe-137">如何：安装和卸载服务</span><span class="sxs-lookup"><span data-stu-id="bc1fe-137">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)  
 [<span data-ttu-id="bc1fe-138">如何：启动服务</span><span class="sxs-lookup"><span data-stu-id="bc1fe-138">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)  
 [<span data-ttu-id="bc1fe-139">如何：为服务指定安全上下文</span><span class="sxs-lookup"><span data-stu-id="bc1fe-139">How to: Specify the Security Context for Services</span></span>](../../../docs/framework/windows-services/how-to-specify-the-security-context-for-services.md)
