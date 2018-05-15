---
title: WCF 服务主机 (WcfSvcHost.exe)
ms.date: 03/30/2017
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
ms.openlocfilehash: e1e258015adc34edd4a109f3bc5a32b4bf6f0296
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="wcf-service-host-wcfsvchostexe"></a><span data-ttu-id="a5eba-102">WCF 服务主机 (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="a5eba-102">WCF Service Host (WcfSvcHost.exe)</span></span>
<span data-ttu-id="a5eba-103">Windows Communication Foundation (WCF) 服务主机 (WcfSvcHost.exe) 允许您启动 Visual Studio 调试器 (F5) 以自动承载和测试已实现的服务。</span><span class="sxs-lookup"><span data-stu-id="a5eba-103">Windows Communication Foundation (WCF) Service Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="a5eba-104">你随后可以测试使用 WCF 测试客户端 (WcfTestClient.exe) 或你自己的客户端，以查找并解决任何潜在错误的服务。</span><span class="sxs-lookup"><span data-stu-id="a5eba-104">You can then test the service using WCF Test Client (WcfTestClient.exe), or your own client, to find and fix any potential errors.</span></span>  
  
## <a name="wcf-service-host"></a><span data-ttu-id="a5eba-105">WCF 服务主机</span><span class="sxs-lookup"><span data-stu-id="a5eba-105">WCF Service Host</span></span>  
 <span data-ttu-id="a5eba-106">WCF 服务主机枚举 WCF 服务项目中的服务、 加载项目的配置，并为它找到的每个服务主机进行实例化。</span><span class="sxs-lookup"><span data-stu-id="a5eba-106">WCF Service Host enumerates the services in a WCF service project, loads the project’s configuration, and instantiates a host for each service that it finds.</span></span> <span data-ttu-id="a5eba-107">该工具通过 WCF 服务模板集成到 Visual Studio，并在你开始调试项目时调用。</span><span class="sxs-lookup"><span data-stu-id="a5eba-107">The tool is integrated into Visual Studio through the WCF Service template and is invoked when you start to debug your project.</span></span>  
  
 <span data-ttu-id="a5eba-108">通过使用 WCF 服务主机，可以承载 WCF 服务 （在 WCF 服务库项目中），而无需额外编写代码或在开发过程中提交到特定的主机。</span><span class="sxs-lookup"><span data-stu-id="a5eba-108">By using WCF Service Host, you can host a WCF service (in a WCF service library project) without writing extra code or committing to a specific host during development.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5eba-109">WCF 服务主机不支持部分信任。</span><span class="sxs-lookup"><span data-stu-id="a5eba-109">WCF Service Host does not support Partial Trust.</span></span> <span data-ttu-id="a5eba-110">如果你想要使用部分信任环境中的 WCF 服务，不要使用 WCF 服务库项目模板在 Visual Studio 中生成服务。</span><span class="sxs-lookup"><span data-stu-id="a5eba-110">If you want to use a WCF Service in Partial Trust, do not use the WCF Service Library Project template in Visual Studio to build your service.</span></span> <span data-ttu-id="a5eba-111">相反，新的网站在 Visual Studio 中通过选择创建 WCF 服务网站模板，其中可托管服务在其支持 WCF 部分信任的 WebServer 中。</span><span class="sxs-lookup"><span data-stu-id="a5eba-111">Instead, create a New WebSite in Visual Studio by choosing the WCF Service WebSite template, which can host the service in a WebServer on which WCF Partial Trust is supported.</span></span>  
  
## <a name="project-types-hosted-by-wcf-service-host"></a><span data-ttu-id="a5eba-112">WCF 服务主机承载的项目类型</span><span class="sxs-lookup"><span data-stu-id="a5eba-112">Project Types hosted by WCF Service Host</span></span>  
 <span data-ttu-id="a5eba-113">WCF 服务主机可以承载以下的 WCF 服务库项目类型： WCF 服务库、 顺序工作流服务库、 状态机工作流服务库和联合服务库。</span><span class="sxs-lookup"><span data-stu-id="a5eba-113">WCF Service Host can host the following WCF service library project types: WCF Service Library, Sequential Workflow Service Library, State Machine Workflow Service Library and Syndication Service Library.</span></span> <span data-ttu-id="a5eba-114">WCF 服务主机也可以承载这些服务可以添加到服务库项目使用**添加项**功能。</span><span class="sxs-lookup"><span data-stu-id="a5eba-114">WCF Service Host can also host those services that can be added to a service library project using the **Add Item** functionality.</span></span> <span data-ttu-id="a5eba-115">这包括 WCF 服务、 WF 状态机服务、 WF 顺序服务、 XAML WF 状态机服务和 XAML WF 顺序服务。</span><span class="sxs-lookup"><span data-stu-id="a5eba-115">This includes WCF Service, WF State Machine Service, WF Sequential Service, XAML WF State Machine Service and XAML WF Sequential Service.</span></span>  
  
 <span data-ttu-id="a5eba-116">但是，应该注意到该工具将不会帮助您配置主机。</span><span class="sxs-lookup"><span data-stu-id="a5eba-116">You should note, however, that the tool will not help you to configure a host.</span></span> <span data-ttu-id="a5eba-117">对于此项任务，必须手动编辑 App.config 文件。</span><span class="sxs-lookup"><span data-stu-id="a5eba-117">For this task, you must manually edit the App.config file.</span></span> <span data-ttu-id="a5eba-118">另外，此工具也不会验证用户定义的配置文件。</span><span class="sxs-lookup"><span data-stu-id="a5eba-118">The tool also does not validate user-defined configuration files.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a5eba-119">不应使用为承载服务的 WCF 服务主机在生产环境中，因为其设计初衷并不为了实现此目的。</span><span class="sxs-lookup"><span data-stu-id="a5eba-119">You should not use WCF Service Host to host services in a production environment, as it was not engineered for this purpose.</span></span>  <span data-ttu-id="a5eba-120">WCF 服务主机不支持可靠性、 安全性和可管理性要求此类环境。</span><span class="sxs-lookup"><span data-stu-id="a5eba-120">WCF Service Host does not support the reliability, security, and manageability requirements of such an environment.</span></span> <span data-ttu-id="a5eba-121">请改用 IIS，因为它可以提供卓越的可靠性和监视功能，并且是承载服务的首选解决方案。</span><span class="sxs-lookup"><span data-stu-id="a5eba-121">Instead, use IIS since it provides superior reliability and monitoring features, and is the preferred solution for hosting services.</span></span> <span data-ttu-id="a5eba-122">服务开发完成后，你应将服务迁移到 IIS 的 WCF 服务主机中。</span><span class="sxs-lookup"><span data-stu-id="a5eba-122">Once development of your services is complete, you should migrate the services from WCF Service Host to IIS.</span></span>  
  
## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a><span data-ttu-id="a5eba-123">在 Visual Studio 中使用 WCF 服务主机的方案</span><span class="sxs-lookup"><span data-stu-id="a5eba-123">Scenarios for Using WCF Service Host inside Visual Studio</span></span>  
 <span data-ttu-id="a5eba-124">下表列出了中的所有参数**命令行自变量**对话框中，可通过右键单击你的项目中找到**解决方案资源管理器**在 Visual Studio 中，选择**属性**，然后选择**调试**选项卡上，单击**启动项目**。</span><span class="sxs-lookup"><span data-stu-id="a5eba-124">The following table lists all the parameters in the **Command line arguments** dialog box, which can be found by right-clicking your project in **Solutions Explorer** in Visual Studio, selecting **Properties**, then selecting the **Debug** tab and clicking **Start Project**.</span></span> <span data-ttu-id="a5eba-125">这些参数可用于配置 WCF 服务主机。</span><span class="sxs-lookup"><span data-stu-id="a5eba-125">These parameters are useful in configuring WCF Service Host.</span></span>  
  
|<span data-ttu-id="a5eba-126">参数</span><span class="sxs-lookup"><span data-stu-id="a5eba-126">Parameter</span></span>|<span data-ttu-id="a5eba-127">含义</span><span class="sxs-lookup"><span data-stu-id="a5eba-127">Meaning</span></span>|  
|---------------|-------------|  
|`/client`|<span data-ttu-id="a5eba-128">一个可选参数，用于指定要在承载服务后运行的可执行文件的路径。</span><span class="sxs-lookup"><span data-stu-id="a5eba-128">An optional parameter that specifies the path to an executable to run after the services are hosted.</span></span> <span data-ttu-id="a5eba-129">这将启动 WCF 测试客户端承载后。</span><span class="sxs-lookup"><span data-stu-id="a5eba-129">This launches WCF Test Client following hosting.</span></span>|  
|`/clientArg`|<span data-ttu-id="a5eba-130">将字符串指定为传递给自定义客户端应用程序的自变量。</span><span class="sxs-lookup"><span data-stu-id="a5eba-130">Specify a string as an argument that is passed to the custom client application.</span></span>|  
|`/?`|<span data-ttu-id="a5eba-131">显示帮助文本。</span><span class="sxs-lookup"><span data-stu-id="a5eba-131">Displays the help text.</span></span>|  
  
#### <a name="using-wcf-test-client"></a><span data-ttu-id="a5eba-132">使用 WCF 测试客户端</span><span class="sxs-lookup"><span data-stu-id="a5eba-132">Using WCF Test Client</span></span>  
 <span data-ttu-id="a5eba-133">在创建新的 WCF 服务项目并按 F5 启动调试器后，WCF 服务主机将开始承载它在项目中找到的所有服务。</span><span class="sxs-lookup"><span data-stu-id="a5eba-133">After you create a new WCF service project and press F5 to start the debugger, WCF Service Host starts hosting all the services it finds in your project.</span></span> <span data-ttu-id="a5eba-134">WCF 测试客户端自动打开，并显示在配置文件中定义的服务终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="a5eba-134">WCF Test Client automatically opens and displays a list of service endpoints defined in the configuration file.</span></span> <span data-ttu-id="a5eba-135">可以从主窗口中测试参数并调用服务。</span><span class="sxs-lookup"><span data-stu-id="a5eba-135">From the main window, you can test the parameters and invoke your service.</span></span>  
  
 <span data-ttu-id="a5eba-136">若要确保使用 WCF 测试客户端，右键单击你的项目中**解决方案资源管理器**在 Visual Studio 中，选择**属性**，然后选择**调试**选项卡。单击**启动项目**并确保中显示以下**命令行自变量**对话框。</span><span class="sxs-lookup"><span data-stu-id="a5eba-136">To make sure that WCF Test Client is used, right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab. Click **Start Project** and ensure that the following appears in the **Command line arguments** dialog box.</span></span>  
  
 `/client:WcfTestClient.exe`  
  
#### <a name="using-a-custom-client"></a><span data-ttu-id="a5eba-137">使用自定义客户端</span><span class="sxs-lookup"><span data-stu-id="a5eba-137">Using a Custom Client</span></span>  
 <span data-ttu-id="a5eba-138">若要使用自定义客户端，右键单击你的项目中**解决方案资源管理器**在 Visual Studio 中，选择**属性**，然后选择**调试**选项卡。单击**启动项目**和编辑`/client`中的参数**命令行自变量**对话框中，以指向自定义客户端，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a5eba-138">To use a custom client, right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab. Click **Start Project** and edit the `/client` parameter in the **Command line arguments** dialog box to point to your custom client, as indicated in the following example.</span></span>  
  
 `/client:"path/CustomClient.exe"`  
  
 <span data-ttu-id="a5eba-139">按 F5 再次启动服务时，WCF 服务主机将启动调试器时自动启动你的自定义客户端。</span><span class="sxs-lookup"><span data-stu-id="a5eba-139">When you press F5 to start the service again, WCF Service Host automatically starts your custom client when you launch the debugger.</span></span>  
  
 <span data-ttu-id="a5eba-140">也可以按照以下示例中的指示使用 `/clientArg:` 形参将字符串指定为传递给自定义客户端应用程序的实参。</span><span class="sxs-lookup"><span data-stu-id="a5eba-140">You can also use the `/clientArg:` parameter to specify a string as an argument that is passed to the custom client application, as indicated in the following example.</span></span>  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 <span data-ttu-id="a5eba-141">例如，如果使用的是联合服务库模板，则可以使用以下命令行自变量：</span><span class="sxs-lookup"><span data-stu-id="a5eba-141">For example, if you are using the Syndication Service Library template, you can use the following command line arguments,</span></span>  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### <a name="specifying-no-client"></a><span data-ttu-id="a5eba-142">指定无客户端</span><span class="sxs-lookup"><span data-stu-id="a5eba-142">Specifying No Client</span></span>  
 <span data-ttu-id="a5eba-143">若要指定无客户端，将使用 WCF 服务主机后，右键单击你的项目中**解决方案资源管理器**在 Visual Studio 中，选择**属性**，然后选择**调试**选项卡。单击**启动项目**并使**命令行自变量**对话框留空。</span><span class="sxs-lookup"><span data-stu-id="a5eba-143">To specify that no client will be used after WCF service hosting, right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab. Click **Start Project** and leave the **Command line arguments** dialog box blank.</span></span>  
  
#### <a name="using-a-custom-host"></a><span data-ttu-id="a5eba-144">使用自定义主机</span><span class="sxs-lookup"><span data-stu-id="a5eba-144">Using a Custom Host</span></span>  
 <span data-ttu-id="a5eba-145">若要使用自定义主机，右键单击你的项目中**解决方案资源管理器**在 Visual Studio 中，选择**属性**，然后选择**调试**选项卡。单击**启动外部程序**并输入自定义宿主的完整路径。</span><span class="sxs-lookup"><span data-stu-id="a5eba-145">To use a custom host, right-click your project in **Solutions Explorer** in Visual Studio, select **Properties**, then select the **Debug** tab. Click **Start External Program** and enter the full path to the custom host.</span></span> <span data-ttu-id="a5eba-146">你还可以使用**命令行自变量**对话框中，指定要传递给该主机自变量。</span><span class="sxs-lookup"><span data-stu-id="a5eba-146">You can also use the **Command line arguments** dialog box to specify arguments to be passed to the host.</span></span>  
  
## <a name="wcf-service-host-user-interface"></a><span data-ttu-id="a5eba-147">WCF 服务主机用户界面</span><span class="sxs-lookup"><span data-stu-id="a5eba-147">WCF Service Host User Interface</span></span>  
 <span data-ttu-id="a5eba-148">当最初调用 WCF 服务主机 （通过按 F5 在 Visual Studio）， **WCF 服务主机**窗口将自动打开。</span><span class="sxs-lookup"><span data-stu-id="a5eba-148">When you initially invoke WCF Service Host (by pressing F5 inside Visual Studio), the **WCF Service Host** window automatically opens.</span></span> <span data-ttu-id="a5eba-149">当运行 WCF 服务主机时，程序的图标将出现在通知区域中。</span><span class="sxs-lookup"><span data-stu-id="a5eba-149">When WCF Service Host is running, the program's icon appears in the notification area.</span></span> <span data-ttu-id="a5eba-150">双击该图标可以打开**WCF 服务主机**窗口</span><span class="sxs-lookup"><span data-stu-id="a5eba-150">Double-click the icon to open the **WCF Service Host** window</span></span>  
  
 <span data-ttu-id="a5eba-151">如果承载服务过程中发生错误，WCF 服务主机对话框将打开以显示相关信息。</span><span class="sxs-lookup"><span data-stu-id="a5eba-151">When errors occur during service hosting, WCF Service Host dialog box will open to display relevant information.</span></span>  
  
 <span data-ttu-id="a5eba-152">**WCF 服务主机**主窗口包含以下两个菜单：</span><span class="sxs-lookup"><span data-stu-id="a5eba-152">The **WCF Service Host** main window contains two menus:</span></span>  
  
-   <span data-ttu-id="a5eba-153">**文件**： 包含**关闭**和**退出**命令。</span><span class="sxs-lookup"><span data-stu-id="a5eba-153">**File**: Contains the **Close** and **Exit** commands.</span></span> <span data-ttu-id="a5eba-154">当你单击**关闭**、 **WCF 服务主机**对话框关闭，但会继续承载服务。</span><span class="sxs-lookup"><span data-stu-id="a5eba-154">When you click **Close**, the **WCF Service Host** dialog box closes, but the services continue to be hosted.</span></span> <span data-ttu-id="a5eba-155">当你单击**退出**，WCF 服务主机也将关闭。</span><span class="sxs-lookup"><span data-stu-id="a5eba-155">When you click **Exit**, WCF Service Host is also shut down.</span></span> <span data-ttu-id="a5eba-156">这还将停止所有承载的服务。</span><span class="sxs-lookup"><span data-stu-id="a5eba-156">This also stops all hosted services.</span></span>  
  
-   <span data-ttu-id="a5eba-157">**帮助**： 包含**有关**包含版本信息的命令。</span><span class="sxs-lookup"><span data-stu-id="a5eba-157">**Help**: Contains the **About** command that contains version information.</span></span> <span data-ttu-id="a5eba-158">它还包含**帮助**可以打开的帮助文件的命令。</span><span class="sxs-lookup"><span data-stu-id="a5eba-158">It also contains the **Help** command that can open a help file.</span></span>  
  
 <span data-ttu-id="a5eba-159">主**WCF 服务主机**窗口包含两个区域：</span><span class="sxs-lookup"><span data-stu-id="a5eba-159">The main **WCF Service Host** window contains two areas:</span></span>  
  
-   <span data-ttu-id="a5eba-160">第一个领域是**服务**。</span><span class="sxs-lookup"><span data-stu-id="a5eba-160">The first area is **Service**.</span></span> <span data-ttu-id="a5eba-161">该区域包含一个显示所有服务基本信息的列表。</span><span class="sxs-lookup"><span data-stu-id="a5eba-161">It contains a list that displays basic information of all services.</span></span> <span data-ttu-id="a5eba-162">这些信息包括：</span><span class="sxs-lookup"><span data-stu-id="a5eba-162">The information includes:</span></span>  
  
    -   <span data-ttu-id="a5eba-163">**服务**： 列出所有的服务。</span><span class="sxs-lookup"><span data-stu-id="a5eba-163">**Service**: Lists all the services.</span></span>  
  
    -   <span data-ttu-id="a5eba-164">**状态**： 列出服务的状态。</span><span class="sxs-lookup"><span data-stu-id="a5eba-164">**Status**: Lists the status of the service.</span></span> <span data-ttu-id="a5eba-165">有效值为"已启动"、"Stopped"和"错误"。</span><span class="sxs-lookup"><span data-stu-id="a5eba-165">Valid values are "Started", "Stopped," and "Error".</span></span>  
  
    -   <span data-ttu-id="a5eba-166">**元数据地址**： 显示服务的元数据地址。</span><span class="sxs-lookup"><span data-stu-id="a5eba-166">**Metadata Address**: Displays the metadata address of the services.</span></span>  
  
-   <span data-ttu-id="a5eba-167">第二个区域是**的其他信息**。</span><span class="sxs-lookup"><span data-stu-id="a5eba-167">The second area is **Additional Information**.</span></span> <span data-ttu-id="a5eba-168">它显示服务状态的详细的说明，在中选择特定的服务行**服务**区域。</span><span class="sxs-lookup"><span data-stu-id="a5eba-168">It displays a detailed explanation of the service status when the specific service line is selected in the **Service** area.</span></span> <span data-ttu-id="a5eba-169">如果状态为“错误”，则可以在屏幕上查看完整的错误消息。</span><span class="sxs-lookup"><span data-stu-id="a5eba-169">If the status is Error, you can view the full error message on the screen.</span></span>  
  
## <a name="stopping-wcf-service-host"></a><span data-ttu-id="a5eba-170">停止 WCF 服务主机</span><span class="sxs-lookup"><span data-stu-id="a5eba-170">Stopping WCF Service Host</span></span>  
 <span data-ttu-id="a5eba-171">可以通过以下四种方法来关闭 WCF 服务主机：</span><span class="sxs-lookup"><span data-stu-id="a5eba-171">You can shut down WCF Service Host in the following four ways:</span></span>  
  
-   <span data-ttu-id="a5eba-172">停止在 Visual Studio 中的调试会话。</span><span class="sxs-lookup"><span data-stu-id="a5eba-172">Stop the debugging session in Visual Studio.</span></span>  
  
-   <span data-ttu-id="a5eba-173">选择**退出**从**文件**菜单中的**WCF 服务主机**窗口。</span><span class="sxs-lookup"><span data-stu-id="a5eba-173">Select **Exit** from the **File** menu in the **WCF Service Host** window.</span></span>  
  
-   <span data-ttu-id="a5eba-174">选择**退出**的系统通知区域中的 WCF 服务主机任务栏图标的上下文菜单中。</span><span class="sxs-lookup"><span data-stu-id="a5eba-174">Select **Exit** from context menu of WCF Service Host tray icon in the system notification area.</span></span>  
  
-   <span data-ttu-id="a5eba-175">如果正在使用它，请退出 WCF 测试客户端。</span><span class="sxs-lookup"><span data-stu-id="a5eba-175">Exit WCF Test Client if it is being used.</span></span>  
  
## <a name="using-service-host-without-administrator-privilege"></a><span data-ttu-id="a5eba-176">在无管理员权限的情况下使用服务主机</span><span class="sxs-lookup"><span data-stu-id="a5eba-176">Using Service Host without Administrator privilege</span></span>  
 <span data-ttu-id="a5eba-177">若要使没有管理员权限的用户能够开发 WCF 服务，ACL （访问控制列表） 为创建命名空间"http://+:8731/Design_Time_Addresses"在 Visual Studio 的安装过程。</span><span class="sxs-lookup"><span data-stu-id="a5eba-177">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="a5eba-178">该 ACL 被设置为“(UI)”，这将包括登录到此计算机的所有交互用户。</span><span class="sxs-lookup"><span data-stu-id="a5eba-178">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="a5eba-179">管理员可以添加或删除此 ACL 中的用户或打开其他端口。此 ACL 使用户可以使用 WCF 服务自动主机 (wcfSvcHost.exe)，而无需向他们授予管理员权限。</span><span class="sxs-lookup"><span data-stu-id="a5eba-179">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="a5eba-180">可以使用提升的管理员帐户在 [!INCLUDE[wv](../../../includes/wv-md.md)] 中通过 netsh.exe 工具来修改访问权限。</span><span class="sxs-lookup"><span data-stu-id="a5eba-180">You can modify access using the netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="a5eba-181">下面是使用 netsh.exe 的示例。</span><span class="sxs-lookup"><span data-stu-id="a5eba-181">The following is an example of using netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="a5eba-182">Netsh.exe 的详细信息，请参阅"[如何使用 Netsh.exe 工具和命令行开关](http://go.microsoft.com/fwlink/?LinkId=97877)"。</span><span class="sxs-lookup"><span data-stu-id="a5eba-182">For more information on netsh.exe, see "[How to Use the Netsh.exe Tool and Command-Line Switches](http://go.microsoft.com/fwlink/?LinkId=97877)".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5eba-183">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5eba-183">See Also</span></span>  
 [<span data-ttu-id="a5eba-184">WCF 测试客户端 (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="a5eba-184">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
