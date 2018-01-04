---
title: "如何：在托管 Windows 服务中承载 WCF 服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8e37363b-4dad-4fb6-907f-73c30fac1d9a
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f4b2c8daa176ef1f9aef24cac3125d59fcc02fa9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-host-a-wcf-service-in-a-managed-windows-service"></a><span data-ttu-id="afa27-102">如何：在托管 Windows 服务中承载 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="afa27-102">How to: Host a WCF Service in a Managed Windows Service</span></span>
<span data-ttu-id="afa27-103">本主题概述了创建由 Windows 服务承载的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务所需的基本步骤。</span><span class="sxs-lookup"><span data-stu-id="afa27-103">This topic outlines the basic steps required to create a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service that is hosted by a Windows Service.</span></span> <span data-ttu-id="afa27-104">此方案可通过托管 Windows 服务承载选项启用，此选项是在没有消息激活的安全环境中在 Internet 信息服务 (IIS) 外部承载的、长时间运行的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="afa27-104">The scenario is enabled by the managed Windows service hosting option that is a long-running [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service hosted outside of Internet Information Services (IIS) in a secure environment that is not message activated.</span></span> <span data-ttu-id="afa27-105">服务的生存期改由操作系统控制。</span><span class="sxs-lookup"><span data-stu-id="afa27-105">The lifetime of the service is controlled instead by the operating system.</span></span> <span data-ttu-id="afa27-106">此宿主选项在 Windows 的所有版本中都是可用的。</span><span class="sxs-lookup"><span data-stu-id="afa27-106">This hosting option is available in all versions of Windows.</span></span>  
  
 <span data-ttu-id="afa27-107">可以使用 Microsoft 管理控制台 (MMC) 中的 Microsoft.ManagementConsole.SnapIn 管理 Windows 服务，并且可以将其配置为在系统启动时自动启动。</span><span class="sxs-lookup"><span data-stu-id="afa27-107">Windows services can be managed with the Microsoft.ManagementConsole.SnapIn in Microsoft Management Console (MMC) and can be configured to start up automatically when the system boots up.</span></span> <span data-ttu-id="afa27-108">此承载选项包括注册承载 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务作为托管 Windows 服务的应用程序域，因此服务的进程生存期由 Windows 服务的服务控制管理器 (SCM) 来控制。</span><span class="sxs-lookup"><span data-stu-id="afa27-108">This hosting option consists of registering the application domain (AppDomain) that hosts a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service as a managed Windows service so that the process lifetime of the service is controlled by the Service Control Manager (SCM) for Windows services.</span></span>  
  
 <span data-ttu-id="afa27-109">服务代码包括服务协定的服务实现、Windows 服务类和安装程序类。</span><span class="sxs-lookup"><span data-stu-id="afa27-109">The service code includes a service implementation of the service contract, a Windows Service class, and an installer class.</span></span> <span data-ttu-id="afa27-110">服务实现类 `CalculatorService` 是 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="afa27-110">The service implementation class, `CalculatorService`, is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="afa27-111">`CalculatorWindowsService` 是 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="afa27-111">The `CalculatorWindowsService` is a Windows service.</span></span> <span data-ttu-id="afa27-112">要符合 Windows 服务的要求，该类继承自 `ServiceBase` 并实现 `OnStart` 和 `OnStop` 方法。</span><span class="sxs-lookup"><span data-stu-id="afa27-112">To qualify as a Windows service, the class inherits from `ServiceBase` and implements the `OnStart` and `OnStop` methods.</span></span> <span data-ttu-id="afa27-113">在 `OnStart` 中，将为 <xref:System.ServiceModel.ServiceHost> 类型创建 `CalculatorService` 并打开它。</span><span class="sxs-lookup"><span data-stu-id="afa27-113">In `OnStart`, a <xref:System.ServiceModel.ServiceHost> is created for the `CalculatorService` type and opened.</span></span> <span data-ttu-id="afa27-114">在 `OnStop` 中，停止并释放服务。</span><span class="sxs-lookup"><span data-stu-id="afa27-114">In `OnStop`, the service is stopped and disposed.</span></span> <span data-ttu-id="afa27-115">主机还负责提供服务主机基址，该基址已在应用程序设置中进行设置。</span><span class="sxs-lookup"><span data-stu-id="afa27-115">The host is also responsible for providing a base address to the service host, which has been configured in application settings.</span></span> <span data-ttu-id="afa27-116">安装程序类继承自 <xref:System.Configuration.Install.Installer>，允许程序通过 Installutil.exe 工具安装为 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="afa27-116">The installer class, which inherits from <xref:System.Configuration.Install.Installer>, allows the program to be installed as a Windows service by the Installutil.exe tool.</span></span>  
  
### <a name="construct-the-service-and-provide-the-hosting-code"></a><span data-ttu-id="afa27-117">构造服务并提供宿主代码</span><span class="sxs-lookup"><span data-stu-id="afa27-117">Construct the service and provide the hosting code</span></span>  
  
1.  <span data-ttu-id="afa27-118">创建称为“Service”的新 Visual Studio 控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="afa27-118">Create a new Visual Studio Console Application project called "Service".</span></span>  
  
2.  <span data-ttu-id="afa27-119">将 Program.cs 重命名为 Service.cs。</span><span class="sxs-lookup"><span data-stu-id="afa27-119">Rename Program.cs to Service.cs.</span></span>  
  
3.  <span data-ttu-id="afa27-120">将命名空间更改为 Microsoft.ServiceModel.Samples。</span><span class="sxs-lookup"><span data-stu-id="afa27-120">Change the namespace to Microsoft.ServiceModel.Samples.</span></span>  
  
4.  <span data-ttu-id="afa27-121">添加对下列程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="afa27-121">Add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="afa27-122">System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="afa27-122">System.ServiceModel.dll</span></span>  
  
    -   <span data-ttu-id="afa27-123">System.ServiceProcess.dll</span><span class="sxs-lookup"><span data-stu-id="afa27-123">System.ServiceProcess.dll</span></span>  
  
    -   <span data-ttu-id="afa27-124">System.Configuration.Install.dll</span><span class="sxs-lookup"><span data-stu-id="afa27-124">System.Configuration.Install.dll</span></span>  
  
5.  <span data-ttu-id="afa27-125">将下面的 using 语句添加到 Service.cs。</span><span class="sxs-lookup"><span data-stu-id="afa27-125">Add the following using statements to Service.cs.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#0)]
     [!code-vb[c_HowTo_HostInNTService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#0)]  
  
6.  <span data-ttu-id="afa27-126">定义 `ICalculator` 服务协定，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="afa27-126">Define the `ICalculator` service contract as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#1)]
     [!code-vb[c_HowTo_HostInNTService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#1)]  
  
7.  <span data-ttu-id="afa27-127">在称为 `CalculatorService` 的类中实现服务协定，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="afa27-127">Implement the service contract in a class called `CalculatorService` as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#2)]
     [!code-vb[c_HowTo_HostInNTService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#2)]  
  
8.  <span data-ttu-id="afa27-128">创建从 `CalculatorWindowsService` 类继承的称为 <xref:System.ServiceProcess.ServiceBase> 的新类。</span><span class="sxs-lookup"><span data-stu-id="afa27-128">Create a new class called `CalculatorWindowsService` that inherits from the <xref:System.ServiceProcess.ServiceBase> class.</span></span> <span data-ttu-id="afa27-129">添加称为 `serviceHost` 的局部变量以引用 <xref:System.ServiceModel.ServiceHost> 实例。</span><span class="sxs-lookup"><span data-stu-id="afa27-129">Add a local variable called `serviceHost` to reference the <xref:System.ServiceModel.ServiceHost> instance.</span></span> <span data-ttu-id="afa27-130">定义调用 `Main` 的 `ServiceBase.Run(new CalculatorWindowsService)` 方法</span><span class="sxs-lookup"><span data-stu-id="afa27-130">Define the `Main` method that calls `ServiceBase.Run(new CalculatorWindowsService)`</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#3)]
     [!code-vb[c_HowTo_HostInNTService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#3)]  
  
9. <span data-ttu-id="afa27-131">通过创建并打开新 <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> 实例重写 <xref:System.ServiceModel.ServiceHost> 方法，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="afa27-131">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> method by creating and opening a new <xref:System.ServiceModel.ServiceHost> instance as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#4)]
     [!code-vb[c_HowTo_HostInNTService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#4)]  
  
10. <span data-ttu-id="afa27-132">通过关闭 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 重写 <xref:System.ServiceModel.ServiceHost> 方法，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="afa27-132">Override the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method closing the <xref:System.ServiceModel.ServiceHost> as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#5)]
     [!code-vb[c_HowTo_HostInNTService#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#5)]  
  
11. <span data-ttu-id="afa27-133">创建称为 `ProjectInstaller` 的新类，该类继承自 <xref:System.Configuration.Install.Installer>，且其 <xref:System.ComponentModel.RunInstallerAttribute> 设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="afa27-133">Create a new class called `ProjectInstaller` that inherits from <xref:System.Configuration.Install.Installer> and that is marked with the <xref:System.ComponentModel.RunInstallerAttribute> set to `true`.</span></span> <span data-ttu-id="afa27-134">这允许 Windows 服务由 Installutil.exe 工具安装。</span><span class="sxs-lookup"><span data-stu-id="afa27-134">This allows the Windows service to be installed by the Installutil.exe tool.</span></span>  
  
     [!code-csharp[c_HowTo_HostInNTService#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#6)]
     [!code-vb[c_HowTo_HostInNTService#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#6)]  
  
12. <span data-ttu-id="afa27-135">移除当您创建项目时生成的 `Service` 类。</span><span class="sxs-lookup"><span data-stu-id="afa27-135">Remove the `Service` class that was generated when you created the project.</span></span>  
  
13. <span data-ttu-id="afa27-136">将应用程序配置文件添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="afa27-136">Add an application configuration file to the project.</span></span> <span data-ttu-id="afa27-137">将文件内容替换为下面的配置 XML。</span><span class="sxs-lookup"><span data-stu-id="afa27-137">Replace the contents of the file with the following configuration XML.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>    <services>  
          <!-- This section is optional with the new configuration model  
               introduced in .NET Framework 4. -->  
          <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
                   behaviorConfiguration="CalculatorServiceBehavior">  
            <host>  
              <baseAddresses>  
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
              </baseAddresses>  
            </host>  
            <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
            <endpoint address=""  
                      binding="wsHttpBinding"  
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />  
            <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->  
            <endpoint address="mex"  
                      binding="mexHttpBinding"  
                      contract="IMetadataExchange" />  
          </service>  
        </services>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="CalculatorServiceBehavior">  
              <serviceMetadata httpGetEnabled="true"/>  
              <serviceDebug includeExceptionDetailInFaults="False"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="afa27-138">右键单击 App.config 文件中的**解决方案资源管理器**和选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="afa27-138">Right click the App.config file in the **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="afa27-139">下**复制到输出目录**选择**如果较新则复制**。</span><span class="sxs-lookup"><span data-stu-id="afa27-139">Under **Copy to Output Directory** select **Copy if Newer**.</span></span>  
  
     <span data-ttu-id="afa27-140">此示例显式指定配置文件中的终结点。</span><span class="sxs-lookup"><span data-stu-id="afa27-140">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="afa27-141">如果您不希望向服务添加任何终结点，则运行时为您添加默认终结点。</span><span class="sxs-lookup"><span data-stu-id="afa27-141">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="afa27-142">在此示例中，由于服务的 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 设置为 `true`，因此服务还启用了发布元数据。</span><span class="sxs-lookup"><span data-stu-id="afa27-142">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, your service also has publishing metadata enabled.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="afa27-143">默认终结点、 绑定和行为，请参阅[简化配置](../../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="afa27-143"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
### <a name="install-and-run-the-service"></a><span data-ttu-id="afa27-144">安装并运行服务</span><span class="sxs-lookup"><span data-stu-id="afa27-144">Install and run the service</span></span>  
  
1.  <span data-ttu-id="afa27-145">生成解决方案以创建 `Service.exe` 可执行文件。</span><span class="sxs-lookup"><span data-stu-id="afa27-145">Build the solution to create the `Service.exe` executable.</span></span>  
  
2.  <span data-ttu-id="afa27-146">打开 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 命令提示，导航到项目目录。</span><span class="sxs-lookup"><span data-stu-id="afa27-146">Open the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt and navigate to the project directory.</span></span> <span data-ttu-id="afa27-147">在命令提示符处键入 `installutil bin\service.exe` 来安装 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="afa27-147">Type `installutil bin\service.exe` at the command prompt to install the Windows service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="afa27-148">如果您不使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 命令提示，请确保 `%WinDir%\Microsoft.NET\Framework\v4.0.<current version>` 目录位于系统路径中。</span><span class="sxs-lookup"><span data-stu-id="afa27-148">If you do not use the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] command prompt, make sure that the `%WinDir%\Microsoft.NET\Framework\v4.0.<current version>` directory is in the system path.</span></span>  
  
     <span data-ttu-id="afa27-149">在命令提示符处键入 `services.msc` 以访问服务控制管理器 (SCM)。</span><span class="sxs-lookup"><span data-stu-id="afa27-149">Type `services.msc` at the command prompt to access the Service Control Manager (SCM).</span></span> <span data-ttu-id="afa27-150">Windows 服务应作为“WCFWindowsServiceSample”出现在服务中。</span><span class="sxs-lookup"><span data-stu-id="afa27-150">The Windows service should appear in Services as "WCFWindowsServiceSample".</span></span> <span data-ttu-id="afa27-151">只有在 Windows 服务正在运行的情况下，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务才能响应客户端。</span><span class="sxs-lookup"><span data-stu-id="afa27-151">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service can only respond to clients if the Windows service is running.</span></span> <span data-ttu-id="afa27-152">要启动服务，请右键单击它在 SCM 和选择"启动"，或类型**net 启动 WCFWindowsServiceSample**在命令提示符。</span><span class="sxs-lookup"><span data-stu-id="afa27-152">To start the service, right-click it in the SCM and select "Start", or type **net start WCFWindowsServiceSample** at the command prompt.</span></span>  
  
3.  <span data-ttu-id="afa27-153">如果对服务进行更改，则必须首先停止并卸载服务。</span><span class="sxs-lookup"><span data-stu-id="afa27-153">If you make changes to the service, you must first stop it and uninstall it.</span></span> <span data-ttu-id="afa27-154">若要停止服务，右键单击该服务在 SCM 中的并选择"停止"，或**类型 net stop WCFWindowsServiceSample**在命令提示符。</span><span class="sxs-lookup"><span data-stu-id="afa27-154">To stop the service, right-click the service in the SCM and select "Stop", or **type net stop WCFWindowsServiceSample** at the command prompt.</span></span> <span data-ttu-id="afa27-155">请注意，如果停止 Windows 服务然后运行客户端，则在客户端尝试访问该服务时，会发生 <xref:System.ServiceModel.EndpointNotFoundException> 异常。</span><span class="sxs-lookup"><span data-stu-id="afa27-155">Note that if you stop the Windows service and then run a client, an <xref:System.ServiceModel.EndpointNotFoundException> exception occurs when a client attempts to access the service.</span></span> <span data-ttu-id="afa27-156">若要卸载 Windows 服务类型**installutil /u bin\service.exe**在命令提示符。</span><span class="sxs-lookup"><span data-stu-id="afa27-156">To uninstall the Windows service type **installutil /u bin\service.exe** at the command prompt.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afa27-157">示例</span><span class="sxs-lookup"><span data-stu-id="afa27-157">Example</span></span>  
 <span data-ttu-id="afa27-158">下面是本主题使用的代码的完整列表。</span><span class="sxs-lookup"><span data-stu-id="afa27-158">The following is a complete listing of the code used by this topic.</span></span>  
  
 [!code-csharp[c_HowTo_HostInNTService#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinntservice/cs/service.cs#8)]
 [!code-vb[c_HowTo_HostInNTService#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostinntservice/vb/service.vb#8)]  
  
 <span data-ttu-id="afa27-159">与“自承载”选项一样，Windows 服务主机环境要求写入一些主机代码作为应用程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="afa27-159">Like the "Self-Hosting" option, the Windows service hosting environment requires that some hosting code be written as part of the application.</span></span> <span data-ttu-id="afa27-160">该服务作为控制台应用程序实现，且包含其自己的宿主代码。</span><span class="sxs-lookup"><span data-stu-id="afa27-160">The service is implemented as a console application and contains its own hosting code.</span></span> <span data-ttu-id="afa27-161">在其他宿主环境（如 Internet 信息服务 (IIS) 中的 Windows 进程激活服务 (WAS) 宿主）中，开发人员没有必要编写宿主代码。</span><span class="sxs-lookup"><span data-stu-id="afa27-161">In other hosting environments, such as Windows Process Activation Service (WAS) hosting in Internet Information Services (IIS), it is not necessary for developers to write hosting code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa27-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="afa27-162">See Also</span></span>  
 [<span data-ttu-id="afa27-163">简化配置</span><span class="sxs-lookup"><span data-stu-id="afa27-163">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="afa27-164">在托管应用程序中承载</span><span class="sxs-lookup"><span data-stu-id="afa27-164">Hosting in a Managed Application</span></span>](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)  
 [<span data-ttu-id="afa27-165">托管服务</span><span class="sxs-lookup"><span data-stu-id="afa27-165">Hosting Services</span></span>](../../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="afa27-166">Windows Server App Fabric 承载功能</span><span class="sxs-lookup"><span data-stu-id="afa27-166">Windows Server App Fabric Hosting Features</span></span>](http://go.microsoft.com/fwlink/?LinkId=201276)
