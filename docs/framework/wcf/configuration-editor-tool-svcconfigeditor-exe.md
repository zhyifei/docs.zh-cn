---
title: 配置编辑器工具 (SvcConfigEditor.exe)
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files, creating
- configuration files
- Configuration file
- configuration file schema
ms.assetid: 2db21a57-5f64-426f-89df-fb0dc2d2def5
ms.openlocfilehash: 75657786135fd13222c6c7edd5acfa122cc72e52
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="configuration-editor-tool-svcconfigeditorexe"></a><span data-ttu-id="ceb31-102">配置编辑器工具 (SvcConfigEditor.exe)</span><span class="sxs-lookup"><span data-stu-id="ceb31-102">Configuration Editor Tool (SvcConfigEditor.exe)</span></span>
<span data-ttu-id="ceb31-103">通过 Windows Communication Foundation (WCF) 服务配置编辑器 (SvcConfigEditor.exe)，管理员和开发人员可以使用图形用户界面来创建和修改 WCF 服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-103">The Windows Communication Foundation (WCF) Service Configuration Editor (SvcConfigEditor.exe) allows administrators and developers to create and modify configuration settings for WCF services using a graphical user interface.</span></span> <span data-ttu-id="ceb31-104">利用此工具，您不必直接编辑 XML 配置文件就可管理 WCF 绑定、行为、服务和诊断的设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-104">With this tool, you can manage settings for WCF bindings, behaviors, services, and diagnostics without having to directly edit XML configuration files.</span></span>  
  
 <span data-ttu-id="ceb31-105">在 C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin 文件夹中可以找到服务配置编辑器。</span><span class="sxs-lookup"><span data-stu-id="ceb31-105">Service Configuration Editor can be found in the C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin folder.</span></span>  
  
## <a name="the-wcf-configuration-editor"></a><span data-ttu-id="ceb31-106">WCF 配置编辑器</span><span class="sxs-lookup"><span data-stu-id="ceb31-106">The WCF Configuration Editor</span></span>  
 <span data-ttu-id="ceb31-107">服务配置编辑器附带了一个向导，该向导可引导您完成配置 WCF 服务或客户端的所有步骤。</span><span class="sxs-lookup"><span data-stu-id="ceb31-107">Service Configuration Editor comes with a wizard that guides you through all the steps in configuring a WCF service or client.</span></span> <span data-ttu-id="ceb31-108">强烈建议您使用向导，而不是直接使用编辑器。</span><span class="sxs-lookup"><span data-stu-id="ceb31-108">You are strongly advised to use the wizard instead of the editor directly.</span></span>  
  
 <span data-ttu-id="ceb31-109">如果已经有一些符合标准 System.Configuration 架构的配置文件，可通过用户界面管理绑定、行为、服务和诊断的特定设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-109">If you already have some configuration files that comply with the standard System.Configuration schema, you can manage specific settings for bindings, behavior, services, and diagnostics with the user interface.</span></span> <span data-ttu-id="ceb31-110">使用服务配置编辑器，可以管理现有 WCF 配置文件及可执行文件、COM+ 服务和 Web 承载的服务的设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-110">The Service Configuration Editor enables you to manage the settings for existing WCF configuration files as well as executable files, COM+ services, and Web-hosted services.</span></span> <span data-ttu-id="ceb31-111">用服务配置编辑器打开 Web 承载的服务时，会同时显示服务自己的配置节和从上级节点继承的配置节。</span><span class="sxs-lookup"><span data-stu-id="ceb31-111">When opening a Web-hosted service with Service Configuration Editor, both the service’s own configuration and inherited configurations sections of upper level nodes are shown.</span></span>  
  
 <span data-ttu-id="ceb31-112">由于 WCF 配置设置位于配置文件的 `<system.serviceModel>` 节中，编辑器只会对此元素的内容进行操作，而不会访问同一文件中的其他元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-112">Because WCF configuration settings are located in the `<system.serviceModel>` section of the configuration file, the editor operates exclusively on the content of this element and does not access other elements in the same file.</span></span> <span data-ttu-id="ceb31-113">可以直接定位到现有配置文件，也可以选择包含服务、虚拟目录或 COM+ 服务的程序集。</span><span class="sxs-lookup"><span data-stu-id="ceb31-113">You can navigate to existing configuration files directly or you can select an assembly that contains a service, virtual directory, or COM+ service.</span></span> <span data-ttu-id="ceb31-114">编辑器将为该特定服务加载配置文件，并允许用户添加新元素或编辑嵌套在配置文件的 `<system.serviceModel>` 节中的现有元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-114">The editor loads the configuration file for that particular service and allows the user to either add new elements or edit existing elements nested in the `<system.serviceModel>` section of the configuration file.</span></span>  
  
 <span data-ttu-id="ceb31-115">编辑器支持 IntelliSense，并强制遵从架构要求。</span><span class="sxs-lookup"><span data-stu-id="ceb31-115">The editor supports IntelliSense and enforces schema compliance.</span></span> <span data-ttu-id="ceb31-116">可以保证生成的输出符合配置文件的架构，并具有在语法上正确的数据值。</span><span class="sxs-lookup"><span data-stu-id="ceb31-116">The resulting output is guaranteed to comply with the schema of the configuration file and to have syntactically correct data values.</span></span> <span data-ttu-id="ceb31-117">但是，编辑器不保证配置文件在语义上是有效的。</span><span class="sxs-lookup"><span data-stu-id="ceb31-117">However, the editor does not guarantee that the configuration file is semantically valid.</span></span> <span data-ttu-id="ceb31-118">换句话说，编辑器不保证配置文件可与它配置的服务协同工作。</span><span class="sxs-lookup"><span data-stu-id="ceb31-118">In other words, the editor does not guarantee that the configuration file can work with the service it configures.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ceb31-119">一旦您修改了某个配置元素后，编辑器将无法从配置文件中清除该元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-119">The editor cannot purge a configuration element from the configuration file once you have modified the element.</span></span> <span data-ttu-id="ceb31-120">例如，如果使用编辑器将终结点名称设置为非空字符串并加以保存，则配置文件会具有以下内容，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="ceb31-120">For example, if you use the editor to set the endpoint name to a non-empty string and save it, the configuration file has the following content, as shown in the following example.</span></span>  
>   
>  `<endpoint binding="basicHttpBinding" name="somename" />`  
>   
>  <span data-ttu-id="ceb31-121">如果尝试通过将名称设置为空字符串来移除名称并保存文件，则配置文件仍会包含 `name` 特性，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="ceb31-121">If you attempt to remove the name by setting it to an empty string and save the file, the configuration file still contains the `name` attribute, as shown in the following example.</span></span>  
>   
>  `<endpoint binding="basicHttpBinding" name="" />`  
>   
>  <span data-ttu-id="ceb31-122">若要清除该属性，您必须使用另一个文本编辑器手动编辑该元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-122">To purge the attribute, you must manually edit the element using another text editor.</span></span>  
>   
>  <span data-ttu-id="ceb31-123">在使用 `issueToken` 终结点行为的 `clientCredential` 元素时，应要特别小心此问题。</span><span class="sxs-lookup"><span data-stu-id="ceb31-123">You should be especially careful with this issue when you use the `issueToken` element of the `clientCredential` Endpoint behavior.</span></span> <span data-ttu-id="ceb31-124">特别是，其 `address` 子元素的 `localIssuer` 特性一定不能为空字符串。</span><span class="sxs-lookup"><span data-stu-id="ceb31-124">Specifically, the `address` attribute of its `localIssuer` sub-element must not be an empty string.</span></span> <span data-ttu-id="ceb31-125">如果使用配置编辑器修改了 `address` 特性并且想要完全移除该特性，您应使用除该编辑器之外的其他工具来进行操作。</span><span class="sxs-lookup"><span data-stu-id="ceb31-125">If you have modified the `address` attribute using the Configuration Editor and want to remove it completely, you should do so using a tool other than the Editor.</span></span> <span data-ttu-id="ceb31-126">否则，该特性会包含空字符串，并且应用程序会引发异常。</span><span class="sxs-lookup"><span data-stu-id="ceb31-126">Otherwise, the attribute contains an empty string and your application throws an exception.</span></span>  
  
## <a name="using-the-configuration-editor"></a><span data-ttu-id="ceb31-127">使用配置编辑器</span><span class="sxs-lookup"><span data-stu-id="ceb31-127">Using the Configuration Editor</span></span>  
 <span data-ttu-id="ceb31-128">可在以下 Windows SDK 安装位置中找到服务配置编辑器：</span><span class="sxs-lookup"><span data-stu-id="ceb31-128">The Service Configuration Editor can be found at the following Windows SDK installation location:</span></span>  
  
 <span data-ttu-id="ceb31-129">C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe</span><span class="sxs-lookup"><span data-stu-id="ceb31-129">C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin\SvcConfigEditor.exe</span></span>  
  
 <span data-ttu-id="ceb31-130">启动服务配置编辑器后，你可以使用**文件 / 打开**菜单浏览服务或你想要管理的程序集。</span><span class="sxs-lookup"><span data-stu-id="ceb31-130">After you launch the Service Configuration Editor, you can use the **File/Open** menu to browse for the service or assembly you want to manage.</span></span> <span data-ttu-id="ceb31-131">可以直接打开配置文件、浏览 WCF /COM+ 服务，以及打开 Web 承载的服务的配置文件。</span><span class="sxs-lookup"><span data-stu-id="ceb31-131">You can open configuration files directly, browse for WCF /COM+ services, and open configuration files for Web-hosted services.</span></span>  
  
 <span data-ttu-id="ceb31-132">服务配置编辑器的用户界面分成以下几个区域：</span><span class="sxs-lookup"><span data-stu-id="ceb31-132">The Service Configuration Editor's user interface is divided into the following areas:</span></span>  
  
-   <span data-ttu-id="ceb31-133">树视图窗格，在左侧以树状结构显示配置元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-133">Tree View Pane, which displays configuration elements in a tree structure on the left.</span></span> <span data-ttu-id="ceb31-134">右击节点可在树中执行操作。</span><span class="sxs-lookup"><span data-stu-id="ceb31-134">You can perform operations in the tree by right-clicking the nodes.</span></span>  
  
-   <span data-ttu-id="ceb31-135">任务窗格，在窗口的左下方显示了当前元素的常见任务</span><span class="sxs-lookup"><span data-stu-id="ceb31-135">Task Pane, which displays common tasks for current elements on the lower-left of the window</span></span>  
  
-   <span data-ttu-id="ceb31-136">详细信息窗格，在右侧显示了树视图中所选配置节点的详细设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-136">Detail Pane, which displays detailed settings of the configuration node selected in the Tree View on the right.</span></span>  
  
### <a name="opening-a-configuration-file"></a><span data-ttu-id="ceb31-137">打开配置文件</span><span class="sxs-lookup"><span data-stu-id="ceb31-137">Opening a Configuration File</span></span>  
  
1.  <span data-ttu-id="ceb31-138">通过使用命令窗口导航到你 WCF 的安装位置，，然后键入启动服务配置编辑器`SvcConfigEditor.exe`。</span><span class="sxs-lookup"><span data-stu-id="ceb31-138">Start Service Configuration Editor by using a command window to navigate to your WCF installation location, and then type `SvcConfigEditor.exe`.</span></span>  
  
2.  <span data-ttu-id="ceb31-139">从**文件**菜单上，选择**打开**单击你想要管理的文件的类型。</span><span class="sxs-lookup"><span data-stu-id="ceb31-139">From the **File** menu, select **Open** and click the type of file you want to manage.</span></span>  
  
3.  <span data-ttu-id="ceb31-140">在**打开**对话框框中，导航到你想要管理并双击它的特定文件。</span><span class="sxs-lookup"><span data-stu-id="ceb31-140">In the **Open** dialog box, navigate to the specific file you want to manage and double-click it.</span></span>  
  
 <span data-ttu-id="ceb31-141">查看器自动跟随配置合并路径，并创建合并配置的视图。</span><span class="sxs-lookup"><span data-stu-id="ceb31-141">The viewer automatically follows the configuration merge path and creates a view of the merged configuration.</span></span> <span data-ttu-id="ceb31-142">例如，非宿主服务的实际配置是 Machine.config 和 App.config 的组合。任何更改都将应用于 SvcConfigEditor 中当前打开的文件。</span><span class="sxs-lookup"><span data-stu-id="ceb31-142">For example, the actual configuration of a non-hosted service is a combination of Machine.config and App.config. Any changes are applied to the active file in the SvcConfigEditor.</span></span> <span data-ttu-id="ceb31-143">如果要编辑配置合并路径中的特定文件，应直接将其打开。</span><span class="sxs-lookup"><span data-stu-id="ceb31-143">If you want to edit a specific file in the configuration merge path, you should open it directly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ceb31-144">如果在编辑器外部修改了后者，配置编辑器将重新加载当前打开的配置文件。</span><span class="sxs-lookup"><span data-stu-id="ceb31-144">Configuration Editor reloads the currently opened configuration file when the latter has been modified outside the Editor.</span></span> <span data-ttu-id="ceb31-145">发生这种情况时，未在编辑器内永久保存的所有更改都将丢失。</span><span class="sxs-lookup"><span data-stu-id="ceb31-145">When this happens, all the changes that are not durably saved inside the Editor are lost.</span></span> <span data-ttu-id="ceb31-146">如果一直发生重新加载情况，最可能的原因是某项服务（例如，在后台运行的防病毒软件）在不断地访问配置文件。</span><span class="sxs-lookup"><span data-stu-id="ceb31-146">If reloading happens consistently, the most likely cause is a service that constantly accesses the configuration file, for example, an antivirus software running in the background.</span></span> <span data-ttu-id="ceb31-147">若要解决此问题，请确保配置编辑器是在文件打开时唯一能够访问该文件的进程。</span><span class="sxs-lookup"><span data-stu-id="ceb31-147">To resolve this, ensure that Configuration Editor is the only process that can access the file when it is opened.</span></span>  
  
### <a name="services"></a><span data-ttu-id="ceb31-148">服务</span><span class="sxs-lookup"><span data-stu-id="ceb31-148">Services</span></span>  
 <span data-ttu-id="ceb31-149">**服务**节点显示所有当前分配的配置文件中的服务。</span><span class="sxs-lookup"><span data-stu-id="ceb31-149">The **Services** node displays all of the services currently assigned in the configuration file.</span></span> <span data-ttu-id="ceb31-150">每个树中的子节点对应的子元素 <`services`> 配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-150">Each sub-node in the tree corresponds to a sub-element of the <`services`> element in the configuration file.</span></span>  
  
 <span data-ttu-id="ceb31-151">当你单击**服务**节点，你可以查看或执行任务在服务上的摘要页中**详细信息**窗格。</span><span class="sxs-lookup"><span data-stu-id="ceb31-151">When you click the **Services** node, you can view or perform tasks on the service Summary Page in the **Detail** Pane.</span></span>  
  
#### <a name="creating-a-new-service-configuration"></a><span data-ttu-id="ceb31-152">创建新的服务配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-152">Creating a new Service Configuration</span></span>  
 <span data-ttu-id="ceb31-153">可按下列方法创建新的服务配置：</span><span class="sxs-lookup"><span data-stu-id="ceb31-153">You can create a new service configuration in the following ways:</span></span>  
  
-   <span data-ttu-id="ceb31-154">使用向导： 单击链接**创建新的服务...**</span><span class="sxs-lookup"><span data-stu-id="ceb31-154">Using a Wizard: Click the link **Create a New Service…**</span></span> <span data-ttu-id="ceb31-155">上的任务窗格或摘要页以启动向导。</span><span class="sxs-lookup"><span data-stu-id="ceb31-155">on the Task Pane or Summary Page to launch the wizard.</span></span> <span data-ttu-id="ceb31-156">你还可以执行在**文件**菜单->**添加新项**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-156">You can also do so in the **File** menu -> **Add New Item**.</span></span>  
  
-   <span data-ttu-id="ceb31-157">手动创建： 可右击**服务**节点，然后选择**新服务**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-157">Create manually: You can right-click the **Services** node and choose **New Service**.</span></span>  
  
#### <a name="creating-a-new-service-endpoint-configuration"></a><span data-ttu-id="ceb31-158">创建新的服务终结点配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-158">Creating a new Service Endpoint Configuration</span></span>  
 <span data-ttu-id="ceb31-159">可按下列方法创建新的服务终结点配置：</span><span class="sxs-lookup"><span data-stu-id="ceb31-159">You can create a new service endpoint configuration in the following ways:</span></span>  
  
-   <span data-ttu-id="ceb31-160">使用向导创建： 单击链接**创建新的服务终结点...**</span><span class="sxs-lookup"><span data-stu-id="ceb31-160">Create using a Wizard: click the link **Create a New Service Endpoint…**</span></span> <span data-ttu-id="ceb31-161">上的任务窗格或摘要页以启动向导。</span><span class="sxs-lookup"><span data-stu-id="ceb31-161">on the Task Pane or Summary Page to launch the wizard.</span></span> <span data-ttu-id="ceb31-162">你还可以执行在**文件**菜单->**添加新项**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-162">You can also do so in the **File** menu -> **Add New Item**.</span></span>  
  
-   <span data-ttu-id="ceb31-163">手动创建： 一旦创建了服务，你可以右键单击**终结点**节点，然后选择"**新建服务终结点**"。</span><span class="sxs-lookup"><span data-stu-id="ceb31-163">Create manually: Once you created a Service, you can right-click the **Endpoints** node and choose "**New Service Endpoint**".</span></span>  
  
#### <a name="editing-a-service-configuration"></a><span data-ttu-id="ceb31-164">编辑服务配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-164">Editing a Service Configuration</span></span>  
  
1.  <span data-ttu-id="ceb31-165">单击**服务**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-165">Click a **Service** node.</span></span>  
  
2.  <span data-ttu-id="ceb31-166">在属性网格中编辑设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-166">Edit the settings in the property grids.</span></span>  
  
#### <a name="editing-a-service-endpoint-configuration"></a><span data-ttu-id="ceb31-167">编辑服务终结点配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-167">Editing a Service Endpoint Configuration</span></span>  
  
1.  <span data-ttu-id="ceb31-168">单击**服务终结点**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-168">Click a **Service Endpoint** node.</span></span>  
  
2.  <span data-ttu-id="ceb31-169">在属性网格中编辑设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-169">Edit the settings in the property grids.</span></span>  
  
#### <a name="adding-a-base-address"></a><span data-ttu-id="ceb31-170">添加基址</span><span class="sxs-lookup"><span data-stu-id="ceb31-170">Adding a Base Address</span></span>  
  
1.  <span data-ttu-id="ceb31-171">单击**主机**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-171">Click the **Host** node.</span></span>  
  
2.  <span data-ttu-id="ceb31-172">单击**新...**</span><span class="sxs-lookup"><span data-stu-id="ceb31-172">Click the **New…**</span></span> <span data-ttu-id="ceb31-173">按钮**基址**部分。</span><span class="sxs-lookup"><span data-stu-id="ceb31-173">button in the **Base Addresses** section.</span></span>  
  
3.  <span data-ttu-id="ceb31-174">在对话框中键入基址 URI。</span><span class="sxs-lookup"><span data-stu-id="ceb31-174">Type in the base address URI in the dialog box.</span></span>  
  
4.  <span data-ttu-id="ceb31-175">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-175">Click **OK**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ceb31-176">不能编辑的值[ \<Baseaddressprefixfilter >](../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md)内此工具。</span><span class="sxs-lookup"><span data-stu-id="ceb31-176">You cannot edit the value of [\<baseAddressPrefixFilters>](../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md) inside this tool.</span></span> <span data-ttu-id="ceb31-177">若要添加或修改此元素，应使用文本编辑器或 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="ceb31-177">To add or modify this element, you should use a text editor or Visual Studio.</span></span>  
  
### <a name="client"></a><span data-ttu-id="ceb31-178">客户端</span><span class="sxs-lookup"><span data-stu-id="ceb31-178">Client</span></span>  
 <span data-ttu-id="ceb31-179">**客户端**节点显示所有客户端终结点的配置文件中。</span><span class="sxs-lookup"><span data-stu-id="ceb31-179">The **Client** node displays all of the client endpoints in the configuration file.</span></span> <span data-ttu-id="ceb31-180">在树中的每个子节点对应的子元素 <`client`> 配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-180">Every sub-node in the tree corresponds to a sub-element of the <`client`> element in the configuration file.</span></span>  
  
 <span data-ttu-id="ceb31-181">当你单击**客户端**节点，你可以查看或客户端上执行任务**摘要页**中**详细信息窗格**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-181">When you click the **Client** node, you can view or perform tasks on the client **Summary Page** in the **Detail Pane**.</span></span>  
  
#### <a name="creating-a-new-client-endpoint-configuration"></a><span data-ttu-id="ceb31-182">创建新的客户端终结点配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-182">Creating a new Client Endpoint Configuration</span></span>  
 <span data-ttu-id="ceb31-183">可按下列方法创建新的客户端终结点配置：</span><span class="sxs-lookup"><span data-stu-id="ceb31-183">You can create a new client endpoint configuration in the following ways:</span></span>  
  
-   <span data-ttu-id="ceb31-184">向导创建： 单击链接**创建新的客户端...**</span><span class="sxs-lookup"><span data-stu-id="ceb31-184">Create by Wizard: Click the link **Create a New Client…**</span></span> <span data-ttu-id="ceb31-185">上**任务窗格**窗口的左下方或**摘要页**以启动向导。</span><span class="sxs-lookup"><span data-stu-id="ceb31-185">on the **Task Pane** on the lower-left of the window, or **Summary Page** to launch the wizard.</span></span> <span data-ttu-id="ceb31-186">你还可以执行在**文件**菜单->**添加新项**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-186">You can also do so in the **File** menu -> **Add New Item**.</span></span> <span data-ttu-id="ceb31-187">该向导会提示您指向从中生成客户端配置的服务配置的位置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-187">The wizard prompts you to point to the location of the service configuration, from which the client configuration is generated.</span></span> <span data-ttu-id="ceb31-188">然后，您可以选择要连接的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-188">You can then choose the service endpoint to connect to.</span></span>  
  
-   <span data-ttu-id="ceb31-189">手动创建： 右击**终结点**节点下的**客户端**，然后选择**新客户端终结点**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-189">Create manually: Right-click the **Endpoints** node under **Client**, and choose **New Client Endpoint**.</span></span>  
  
#### <a name="editing-a-client-endpoint-configuration"></a><span data-ttu-id="ceb31-190">编辑客户端终结点配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-190">Editing a Client Endpoint Configuration</span></span>  
  
1.  <span data-ttu-id="ceb31-191">单击**客户端终结点**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-191">Click a **Client Endpoint** node.</span></span>  
  
2.  <span data-ttu-id="ceb31-192">在属性网格中编辑设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-192">Edit the settings in the property grids.</span></span>  
  
### <a name="standard-endpoint"></a><span data-ttu-id="ceb31-193">标准终结点</span><span class="sxs-lookup"><span data-stu-id="ceb31-193">Standard Endpoint</span></span>  
 <span data-ttu-id="ceb31-194">标准终结点是一种专门的终结点，其地址、协定和绑定中的一个或多个方面已设置为默认值。</span><span class="sxs-lookup"><span data-stu-id="ceb31-194">Standard endpoints are specialized endpoints that have one or more aspects of the address, contract and binding set to default values.</span></span>  
  
 <span data-ttu-id="ceb31-195">此类配置设置存储在**标准终结点**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-195">Such configuration settings are stored in the **Standard Endpoint** node.</span></span> <span data-ttu-id="ceb31-196">**标准终结点**节点可显示在配置文件中的所有标准终结点设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-196">The **Standard Endpoint** node displays all of the standard endpoint settings in the configuration file.</span></span> <span data-ttu-id="ceb31-197">在树中的每个子节点对应于中的子元素`<standardEndpoints>`配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-197">Every sub-node in the tree corresponds to a sub-element in the `<standardEndpoints>` element in the configuration file.</span></span>  
  
 <span data-ttu-id="ceb31-198">当你单击**标准终结点**节点，您可以查看或执行任务的标准终结点上**摘要页**中**详细信息窗格**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-198">When you click the **Standard Endpoint** node, you can view or perform tasks on the standard endpoint **Summary Page** in the **Detail Pane**.</span></span>  
  
#### <a name="creating-a-new-standard-endpoint-configuration"></a><span data-ttu-id="ceb31-199">创建新的标准终结点配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-199">Creating a New Standard Endpoint Configuration</span></span>  
 <span data-ttu-id="ceb31-200">可按下列方法创建新的标准终结点配置：</span><span class="sxs-lookup"><span data-stu-id="ceb31-200">You can create a new standard endpoint configuration in the following ways:</span></span>  
  
-   <span data-ttu-id="ceb31-201">右键单击**标准终结点**节点，然后选择**新建标准终结点配置...**</span><span class="sxs-lookup"><span data-stu-id="ceb31-201">Right-click the **Standard Endpoint** node and select **New Standard Endpoint Configuration…**</span></span> <span data-ttu-id="ceb31-202">在对话框中选择绑定类型，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-202">Select the binding type in the dialog box and click **OK**.</span></span>  
  
-   <span data-ttu-id="ceb31-203">选择**标准终结点**节点，然后单击**新建标准终结点配置...**</span><span class="sxs-lookup"><span data-stu-id="ceb31-203">Select the **Standard Endpoint** node and click **New Standard Endpoint Configuration…**</span></span> <span data-ttu-id="ceb31-204">在**任务窗格**窗口的左下方。</span><span class="sxs-lookup"><span data-stu-id="ceb31-204">in the **Task Pane** on the lower-left of the window.</span></span>  
  
 <span data-ttu-id="ceb31-205">**创建新的标准终结点**对话框中显示，并列出所有已注册的标准终结点类型。</span><span class="sxs-lookup"><span data-stu-id="ceb31-205">The **Creating a New Standard Endpoint** dialog box displays and lists all registered standard endpoint types.</span></span>  
  
#### <a name="viewing-and-editing-a-standard-endpoint-configuration"></a><span data-ttu-id="ceb31-206">查看和编辑标准终结点配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-206">Viewing and Editing a Standard Endpoint Configuration</span></span>  
 <span data-ttu-id="ceb31-207">可按下列方法打开标准终结点配置以供查看和编辑：</span><span class="sxs-lookup"><span data-stu-id="ceb31-207">You can open a standard endpoint configuration for viewing and editing in the following ways:</span></span>  
  
-   <span data-ttu-id="ceb31-208">单击以展开**标准终结点**节点并单击相应的终结点子节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-208">Click to expand the **Standard Endpoint** node and click the respective endpoint sub-node.</span></span>  
  
-   <span data-ttu-id="ceb31-209">单击**标准终结点**节点，然后单击详细信息窗格上的相应终结点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-209">Click the **Standard Endpoint** node and click the respective endpoint on the Detail pane.</span></span>  
  
 <span data-ttu-id="ceb31-210">终结点的特性将显示在右侧窗格中以供编辑。</span><span class="sxs-lookup"><span data-stu-id="ceb31-210">Attributes for the endpoint are shown in the right pane for editing.</span></span>  
  
#### <a name="deleting-a-standard-endpoint-configuration"></a><span data-ttu-id="ceb31-211">删除标准终结点配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-211">Deleting a Standard Endpoint Configuration</span></span>  
 <span data-ttu-id="ceb31-212">可按下列方法删除标准终结点配置：</span><span class="sxs-lookup"><span data-stu-id="ceb31-212">You can delete a standard endpoint configuration in the following ways:</span></span>  
  
-   <span data-ttu-id="ceb31-213">单击以展开**标准终结点**节点并右击相应的终结点子节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-213">Click to expand the **Standard Endpoint** node and right-click the respective endpoint sub-node.</span></span> <span data-ttu-id="ceb31-214">使用上下文命令**删除标准终结点配置**要删除终结点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-214">Use the context command **Delete Standard Endpoint Configuration** to delete the endpoint.</span></span>  
  
-   <span data-ttu-id="ceb31-215">单击**标准终结点**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-215">Click the **Standard Endpoint** node.</span></span> <span data-ttu-id="ceb31-216">在**任务**窗格中，单击**删除标准终结点配置**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-216">In the **Task** pane, click **Delete Standard Endpoint Configuration**.</span></span>  
  
 <span data-ttu-id="ceb31-217">如果标准终结点正被使用，则在尝试删除时将显示一条警报消息：**“该标准终结点正被使用。如果现在删除，请确保删除其他配置部分中(例如，从服务终结点或客户端终结点中)对该标准终结点的所有引用。否则，配置将无效，并且下次将无法打开。是否确实要删除的标准终结点？"**</span><span class="sxs-lookup"><span data-stu-id="ceb31-217">If the standard endpoint is in used, a warning message is displayed when you attempt to delete it: **The standard endpoint is in use. If you delete it now, please be sure to delete all of its references in other parts of the configuration (for example, in the service endpoint or client endpoint). Otherwise, the configuration will be invalid and cannot be opened next time. Are you sure you want to delete the standard endpoint?"**</span></span>  
  
### <a name="binding"></a><span data-ttu-id="ceb31-218">绑定</span><span class="sxs-lookup"><span data-stu-id="ceb31-218">Binding</span></span>  
 <span data-ttu-id="ceb31-219">绑定配置用于配置终结点上的绑定。</span><span class="sxs-lookup"><span data-stu-id="ceb31-219">Binding configurations are used to configure bindings on endpoints.</span></span> <span data-ttu-id="ceb31-220">此类配置设置存储在**绑定**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-220">Such configuration settings are stored in the **Binding** node.</span></span> <span data-ttu-id="ceb31-221">终结点按名称引用绑定配置，并且多个终结点可引用同一个绑定配置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-221">Endpoints reference binding configurations by name and multiple endpoints can reference a single binding configuration.</span></span>  
  
 <span data-ttu-id="ceb31-222">**绑定**节点可显示的所有绑定设置中配置文件。</span><span class="sxs-lookup"><span data-stu-id="ceb31-222">The **Bindings** node displays all of the binding settings in the configuration file.</span></span> <span data-ttu-id="ceb31-223">在树中的每个子节点对应于中的子元素 <`bindings`> 配置文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-223">Every sub-node in the tree corresponds to a sub-element in the <`bindings`> element in the configuration file.</span></span>  
  
 <span data-ttu-id="ceb31-224">当你单击**绑定**节点，您可以查看或执行任务，在绑定上**摘要页**中**详细信息窗格**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-224">When you click the **Bindings** node, you can view or perform tasks on the binding **Summary Page** in the **Detail Pane**.</span></span>  
  
#### <a name="creating-a-new-binding-configuration"></a><span data-ttu-id="ceb31-225">创建新的绑定配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-225">Creating a New Binding Configuration</span></span>  
 <span data-ttu-id="ceb31-226">可按下列方法创建新的绑定配置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-226">You can create a new binding configuration in the following ways.</span></span>  
  
-   <span data-ttu-id="ceb31-227">右键单击**绑定**节点，然后选择**新建绑定配置**...</span><span class="sxs-lookup"><span data-stu-id="ceb31-227">Right-click the **Bindings** node and select **New Binding Configuration**…</span></span> <span data-ttu-id="ceb31-228">在对话框中选择绑定类型，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-228">Select the binding type in the dialog box and click **OK**.</span></span>  
  
-   <span data-ttu-id="ceb31-229">选择**绑定**节点，然后单击**新建绑定配置**...</span><span class="sxs-lookup"><span data-stu-id="ceb31-229">Select the **Bindings** node and click **New Binding Configuration**…</span></span> <span data-ttu-id="ceb31-230">在**任务窗格**窗口的左下方。</span><span class="sxs-lookup"><span data-stu-id="ceb31-230">in the **Task Pane** on the lower-left of the window.</span></span>  
  
-   <span data-ttu-id="ceb31-231">在服务或客户端摘要页中，单击**单击此处进行创建**中**绑定配置**字段创建相应的终结点的绑定配置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-231">In the service or client summary page, click **Click to Create** in the **Binding Configuration** field to create a binding configuration for the corresponding endpoint.</span></span>  
  
#### <a name="adding-binding-element-extensions-to-a-custom-binding"></a><span data-ttu-id="ceb31-232">向自定义绑定添加绑定元素扩展</span><span class="sxs-lookup"><span data-stu-id="ceb31-232">Adding Binding Element Extensions to a Custom Binding</span></span>  
  
1.  <span data-ttu-id="ceb31-233">选择要向其添加扩展元素的绑定。</span><span class="sxs-lookup"><span data-stu-id="ceb31-233">Select the binding you want to add an extension element to.</span></span>  
  
2.  <span data-ttu-id="ceb31-234">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-234">Click **Add**.</span></span>  
  
3.  <span data-ttu-id="ceb31-235">从可用扩展列表中，选择要添加的绑定元素扩展。</span><span class="sxs-lookup"><span data-stu-id="ceb31-235">From the list of available extensions, select the binding element extension you want to add.</span></span> <span data-ttu-id="ceb31-236">按住 Ctrl 键的同时进行选择可选择多项。</span><span class="sxs-lookup"><span data-stu-id="ceb31-236">To select multiple items, press the CTRL key simultaneously.</span></span>  
  
4.  <span data-ttu-id="ceb31-237">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-237">Click **Add**.</span></span>  
  
#### <a name="adjusting-the-extension-position-in-a-custom-binding"></a><span data-ttu-id="ceb31-238">调整自定义绑定中的扩展位置</span><span class="sxs-lookup"><span data-stu-id="ceb31-238">Adjusting the Extension Position in a Custom Binding</span></span>  
 <span data-ttu-id="ceb31-239">自定义绑定是形成堆栈的一系列绑定元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-239">A custom binding is a collection of binding elements that form a stack.</span></span> <span data-ttu-id="ceb31-240">堆栈中的每个绑定元素都有其自己的配置设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-240">Each binding element on the stack has its own configuration settings.</span></span> <span data-ttu-id="ceb31-241">绑定元素扩展在自定义绑定中的顺序指示它们在堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-241">The order of the binding element extensions in a custom binding indicates their positions in the stack.</span></span> <span data-ttu-id="ceb31-242">堆栈顶部的元素首先得到应用。</span><span class="sxs-lookup"><span data-stu-id="ceb31-242">Elements at the top of the stack are applied first.</span></span> <span data-ttu-id="ceb31-243">若要更改顺序：</span><span class="sxs-lookup"><span data-stu-id="ceb31-243">To change the ordering:</span></span>  
  
1.  <span data-ttu-id="ceb31-244">选择自定义绑定节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-244">Select the custom binding node.</span></span>  
  
2.  <span data-ttu-id="ceb31-245">选择中的一个绑定扩展元素**绑定元素扩展位置**部分。</span><span class="sxs-lookup"><span data-stu-id="ceb31-245">Select one binding extension element in the **Binding Element Extension Position** section.</span></span>  
  
3.  <span data-ttu-id="ceb31-246">使用**向上**或**下**要更改所选元素的位置的列表左侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="ceb31-246">Use the **Up** or **Down** button on the left side of the list to change the position of the selected element.</span></span>  
  
#### <a name="editing-the-configuration-of-binding-element-extensions-in-a-custom-binding"></a><span data-ttu-id="ceb31-247">编辑自定义绑定中的绑定元素扩展的配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-247">Editing the Configuration of Binding Element Extensions in a Custom Binding</span></span>  
  
1.  <span data-ttu-id="ceb31-248">选择树中的绑定节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-248">Select the binding node in the tree.</span></span>  
  
2.  <span data-ttu-id="ceb31-249">选择包含要编辑的元素的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="ceb31-249">Select the custom binding that contains the element you want to edit.</span></span>  
  
3.  <span data-ttu-id="ceb31-250">选择要编辑的绑定元素扩展。</span><span class="sxs-lookup"><span data-stu-id="ceb31-250">Select the binding element extension you want to edit.</span></span> <span data-ttu-id="ceb31-251">该元素的设置将出现在右窗格中，可在其中编辑这些设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-251">The settings of the element appear in the right pane, where they can be edited.</span></span>  
  
### <a name="diagnostics"></a><span data-ttu-id="ceb31-252">诊断</span><span class="sxs-lookup"><span data-stu-id="ceb31-252">Diagnostics</span></span>  
 <span data-ttu-id="ceb31-253">**诊断**节点可显示在配置文件中的所有诊断设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-253">The **Diagnostics** node displays all of the diagnostic settings in the configuration file.</span></span> <span data-ttu-id="ceb31-254">这样可以打开或关闭性能计数器、 启用或禁用 Windows Management Instrumentation (WMI)、 配置 WCF 跟踪和配置 WCF 消息日志记录。</span><span class="sxs-lookup"><span data-stu-id="ceb31-254">It enables you to turn performance counters on or off, enable or disable Windows Management Instrumentation (WMI), configure WCF tracing, and configure WCF message logging.</span></span> <span data-ttu-id="ceb31-255">中的设置**诊断**节点对应于 <`system.diagnostics`> 部分中，和`<diagnostics>`主题中`<system.serviceModel>`配置文件中。</span><span class="sxs-lookup"><span data-stu-id="ceb31-255">The settings in the **Diagnostics** node correspond to the <`system.diagnostics`> section, and `<diagnostics>` section in `<system.serviceModel>` in the configuration file.</span></span>  
  
 <span data-ttu-id="ceb31-256">当你单击**诊断**节点，您可以查看或执行诊断任务**摘要页**中**详细信息窗格**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-256">When you click the **Diagnostics** node, you can view or perform tasks on the diagnostics **Summary Page** in the **Detail Pane**.</span></span>  
  
#### <a name="configuring-performance-counters-and-wmi"></a><span data-ttu-id="ceb31-257">配置性能计数器和 WMI</span><span class="sxs-lookup"><span data-stu-id="ceb31-257">Configuring performance counters and WMI</span></span>  
  
1.  <span data-ttu-id="ceb31-258">单击**诊断**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-258">Click the **Diagnostics** node.</span></span>  
  
2.  <span data-ttu-id="ceb31-259">单击**切换性能计数器**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-259">Click **Toggle Performance Counters**.</span></span> <span data-ttu-id="ceb31-260">性能计数器有三种状态：Off（默认）、ServiceOnly 和 All。</span><span class="sxs-lookup"><span data-stu-id="ceb31-260">The performance counter has three states: Off (default), ServiceOnly, and All.</span></span> <span data-ttu-id="ceb31-261">单击链接可在这三种状态之间切换设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-261">Clicking the link toggles the setting among these three states.</span></span>  
  
#### <a name="configuring-wmi-provider"></a><span data-ttu-id="ceb31-262">配置 WMI 提供程序</span><span class="sxs-lookup"><span data-stu-id="ceb31-262">Configuring WMI Provider</span></span>  
  
1.  <span data-ttu-id="ceb31-263">单击**诊断**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-263">Click the **Diagnostics** node.</span></span>  
  
2.  <span data-ttu-id="ceb31-264">若要启用 WMI 提供程序，请单击**启用 WMI 提供程序**链接。</span><span class="sxs-lookup"><span data-stu-id="ceb31-264">To enable WMI provider, click the **Enable WMI Provider** link.</span></span>  
  
#### <a name="enabling-wcf-tracing"></a><span data-ttu-id="ceb31-265">启用 WCF 跟踪</span><span class="sxs-lookup"><span data-stu-id="ceb31-265">Enabling WCF Tracing</span></span>  
 <span data-ttu-id="ceb31-266">可创建具有标准属性的 WCF 跟踪文件，或者设置自定义的跟踪文件。</span><span class="sxs-lookup"><span data-stu-id="ceb31-266">You can create a WCF trace file with standard properties or set up a custom trace file.</span></span>  
  
1.  <span data-ttu-id="ceb31-267">单击**诊断**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-267">Click the **Diagnostics** node.</span></span>  
  
2.  <span data-ttu-id="ceb31-268">单击**启用跟踪**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-268">Click **Enable Tracing**.</span></span>  
  
3.  <span data-ttu-id="ceb31-269">单击**跟踪级别**链接调整跟踪级别。</span><span class="sxs-lookup"><span data-stu-id="ceb31-269">Click the **Trace Level** link to adjust the trace level.</span></span> <span data-ttu-id="ceb31-270">有六种跟踪级别：“禁用”、“严重”、“错误”、“警告”、“信息”和“详细”。</span><span class="sxs-lookup"><span data-stu-id="ceb31-270">There are six trace levels: Off, Critical, Error, Warning, Information, and Verbose.</span></span> <span data-ttu-id="ceb31-271">**活动跟踪**和**传播活动**选项使您能使用 WCF 活动跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="ceb31-271">The **Activity Tracing** and **Propagate Activity** option enable you to use the WCF activity tracing feature.</span></span>  
  
4.  <span data-ttu-id="ceb31-272">单击跟踪侦听器名称指定跟踪文件和选项。</span><span class="sxs-lookup"><span data-stu-id="ceb31-272">Click the trace listener name to specify the trace file and options.</span></span>  
  
#### <a name="enabling-wcf-logging"></a><span data-ttu-id="ceb31-273">启用 WCF 日志记录</span><span class="sxs-lookup"><span data-stu-id="ceb31-273">Enabling WCF Logging</span></span>  
 <span data-ttu-id="ceb31-274">可创建具有标准属性的 WCF 跟踪文件，或者设置自定义的跟踪文件。</span><span class="sxs-lookup"><span data-stu-id="ceb31-274">You can create a WCF trace file with standard properties or set up a custom trace file.</span></span>  
  
1.  <span data-ttu-id="ceb31-275">单击**诊断**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-275">Click the **Diagnostics** node.</span></span>  
  
2.  <span data-ttu-id="ceb31-276">单击**启用消息日志记录**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-276">Click **Enable Message Logging**.</span></span>  
  
3.  <span data-ttu-id="ceb31-277">单击**日志级别**链接调整日志级别。</span><span class="sxs-lookup"><span data-stu-id="ceb31-277">Click the **Log Level** link to adjust the log level.</span></span> <span data-ttu-id="ceb31-278">有 3 种日志级别：“格式错误”、“服务”和“传输”。</span><span class="sxs-lookup"><span data-stu-id="ceb31-278">There are three log levels: Malformed, Service, and Transport.</span></span>  
  
4.  <span data-ttu-id="ceb31-279">单击侦听器名称指定日志文件和选项。</span><span class="sxs-lookup"><span data-stu-id="ceb31-279">Click the listener name to specify the log file and options.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ceb31-280">如果你想要关闭你的应用程序时自动刷新，启用的跟踪和消息日志**自动刷新**选项。</span><span class="sxs-lookup"><span data-stu-id="ceb31-280">If you want the trace and message logs to be flushed automatically when your application is closed, enable the **Auto Flush** option.</span></span>  
  
 <span data-ttu-id="ceb31-281">**诊断****摘要页**使您能够完成配置诊断中的最常见任务。</span><span class="sxs-lookup"><span data-stu-id="ceb31-281">The **Diagnostics** **Summary Page** enables you to accomplish the most common tasks in configuring diagnostics.</span></span> <span data-ttu-id="ceb31-282">但是，如果你想要手动编辑侦听器和源设置，你必须展开**诊断**中的节点，然后编辑设置**消息日志记录**，**侦听器**和**源**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-282">However, if you want to manually edit the Listeners and Sources settings, you must expand the **Diagnostics** node and edit settings in **Message Logging**, **Listeners** and **Sources** node.</span></span>  
  
#### <a name="enabling-wcf-custom-tracing-or-message-logging"></a><span data-ttu-id="ceb31-283">启用 WCF 自定义跟踪或消息日志记录</span><span class="sxs-lookup"><span data-stu-id="ceb31-283">Enabling WCF Custom Tracing or Message Logging</span></span>  
  
1.  <span data-ttu-id="ceb31-284">单击**诊断**节点，并将其展开。</span><span class="sxs-lookup"><span data-stu-id="ceb31-284">Click the **Diagnostics** node, and expand it.</span></span>  
  
2.  <span data-ttu-id="ceb31-285">右键单击**侦听器**节点，然后选择**新侦听器**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-285">Right-click the **Listeners** node and select **New Listener**.</span></span>  
  
3.  <span data-ttu-id="ceb31-286">中的跟踪文件名称中的类型**InitData**字段。</span><span class="sxs-lookup"><span data-stu-id="ceb31-286">Type in the trace file name in the **InitData** field.</span></span> <span data-ttu-id="ceb31-287">你可以单击"..."按钮以浏览到的路径。</span><span class="sxs-lookup"><span data-stu-id="ceb31-287">You can click the "…" button to browse to a path.</span></span>  
  
4.  <span data-ttu-id="ceb31-288">单击**TypeName**行显示一个"..."按钮。</span><span class="sxs-lookup"><span data-stu-id="ceb31-288">Clicking the **TypeName** line displays a "…" button.</span></span> <span data-ttu-id="ceb31-289">单击此按钮可打开**跟踪侦听器类型浏览器**，可以用于查找已安装的预先配置的跟踪侦听器。</span><span class="sxs-lookup"><span data-stu-id="ceb31-289">Click this button to open the **Trace Listener Type Browser**, which you can use to find pre-configured trace listeners that are already installed.</span></span>  
  
5.  <span data-ttu-id="ceb31-290">请注意**源**部分。</span><span class="sxs-lookup"><span data-stu-id="ceb31-290">Note the **Source** section.</span></span> <span data-ttu-id="ceb31-291">单击**添加**中此部分以带有下拉列表菜单中打开一个对话框，其中列出了可用的跟踪源。</span><span class="sxs-lookup"><span data-stu-id="ceb31-291">Click **Add** in this section to open a dialog box with a drop-down menu, which lists available tracing sources.</span></span> <span data-ttu-id="ceb31-292">选择一个跟踪源，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-292">Select a tracing source and click **OK**.</span></span>  
  
6.  <span data-ttu-id="ceb31-293">若要编辑消息日志记录设置，请单击**消息日志记录**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-293">To edit Message Logging settings, click the **Message Logging** node.</span></span> <span data-ttu-id="ceb31-294">可在属性网格中编辑这些设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-294">You can edit the settings in the property grid.</span></span>  
  
### <a name="advanced"></a><span data-ttu-id="ceb31-295">高级</span><span class="sxs-lookup"><span data-stu-id="ceb31-295">Advanced</span></span>  
  
#### <a name="behaviors"></a><span data-ttu-id="ceb31-296">行为</span><span class="sxs-lookup"><span data-stu-id="ceb31-296">Behaviors</span></span>  
 <span data-ttu-id="ceb31-297">**行为**节点显示当前配置文件中定义的行为。</span><span class="sxs-lookup"><span data-stu-id="ceb31-297">The **Behaviors** node displays the behaviors that are currently defined in the configuration file.</span></span>  
  
 <span data-ttu-id="ceb31-298">行为配置用于配置终结点和服务的行为。</span><span class="sxs-lookup"><span data-stu-id="ceb31-298">Behavior configurations are used to configure behaviors of endpoints and services.</span></span> <span data-ttu-id="ceb31-299">此类配置设置存储在**高级**节点下的**服务行为**和**终结点行为**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-299">Such configuration settings are stored in the **Advanced** node under **Service Behaviors** and **Endpoint Behaviors**.</span></span> <span data-ttu-id="ceb31-300">服务行为由服务使用；而终结点行为则由终结点使用。</span><span class="sxs-lookup"><span data-stu-id="ceb31-300">Service behaviors are used by services; whereas endpoint behaviors by endpoints.</span></span>  
  
 <span data-ttu-id="ceb31-301">行为是形成堆栈的一系列扩展元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-301">Behaviors are a collection of extension elements that for a stack.</span></span> <span data-ttu-id="ceb31-302">堆栈顶部的元素首先得到应用。</span><span class="sxs-lookup"><span data-stu-id="ceb31-302">The element at the top of the stack is applied first.</span></span> <span data-ttu-id="ceb31-303">每个扩展元素可有其自己的配置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-303">Each extension element can have its own configuration.</span></span>  
  
##### <a name="creating-a-new-behavior-configuration"></a><span data-ttu-id="ceb31-304">创建新的行为配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-304">Creating a new Behavior Configuration</span></span>  
 <span data-ttu-id="ceb31-305">可通过以下两种方法创建新的行为配置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-305">You can create a new behavior configuration in two ways.</span></span>  
  
-   <span data-ttu-id="ceb31-306">右键单击其中一个行为节点，然后选择"**新建行为配置...**</span><span class="sxs-lookup"><span data-stu-id="ceb31-306">Right-click one of the behavior nodes and select "**New Behavior Configuration…**</span></span>  
  
-   <span data-ttu-id="ceb31-307">选择一个行为节点，然后单击**新建行为配置**...</span><span class="sxs-lookup"><span data-stu-id="ceb31-307">Select one of the behavior nodes and click the **New Behavior Configuration**…</span></span> <span data-ttu-id="ceb31-308">在**任务窗格**窗口的左下方。</span><span class="sxs-lookup"><span data-stu-id="ceb31-308">in the **Task Pane** on the lower-left of the window.</span></span>  
  
##### <a name="adding-behavior-element-extensions-to-a-behavior"></a><span data-ttu-id="ceb31-309">向行为中添加行为元素扩展</span><span class="sxs-lookup"><span data-stu-id="ceb31-309">Adding Behavior Element Extensions to a Behavior</span></span>  
  
1.  <span data-ttu-id="ceb31-310">选择一个行为节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-310">Select one of the behavior nodes.</span></span>  
  
2.  <span data-ttu-id="ceb31-311">选择要编辑的行为。</span><span class="sxs-lookup"><span data-stu-id="ceb31-311">Select the behavior you want edit.</span></span>  
  
3.  <span data-ttu-id="ceb31-312">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-312">Click **Add**.</span></span>  
  
4.  <span data-ttu-id="ceb31-313">从可用扩展列表中，选择要添加的行为元素扩展。</span><span class="sxs-lookup"><span data-stu-id="ceb31-313">From the list of available extensions, select the behavior element extension you want to add.</span></span>  
  
5.  <span data-ttu-id="ceb31-314">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-314">Click **Add**.</span></span>  
  
##### <a name="adjusting-the-extension-position-in-a-behavior"></a><span data-ttu-id="ceb31-315">调整行为中的扩展位置</span><span class="sxs-lookup"><span data-stu-id="ceb31-315">Adjusting the Extension Position in a Behavior</span></span>  
 <span data-ttu-id="ceb31-316">行为是形成堆栈的元素集合。</span><span class="sxs-lookup"><span data-stu-id="ceb31-316">Behaviors are collections of elements that form a stack.</span></span> <span data-ttu-id="ceb31-317">堆栈中的每个元素都有其自己的配置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-317">Each element on the stack has its own configuration.</span></span> <span data-ttu-id="ceb31-318">行为元素扩展在行为中的顺序指示它们在堆栈中的位置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-318">The order of the behavior element extensions in a behavior indicates their positions in the stack.</span></span> <span data-ttu-id="ceb31-319">堆栈顶部的元素首先得到应用。</span><span class="sxs-lookup"><span data-stu-id="ceb31-319">Elements at the top of the stack are applied first.</span></span> <span data-ttu-id="ceb31-320">若要更改顺序：</span><span class="sxs-lookup"><span data-stu-id="ceb31-320">To change the ordering:</span></span>  
  
1.  <span data-ttu-id="ceb31-321">选择一个行为节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-321">Select one of the behavior nodes.</span></span>  
  
2.  <span data-ttu-id="ceb31-322">选择要编辑的行为。</span><span class="sxs-lookup"><span data-stu-id="ceb31-322">Select the behavior you want edit.</span></span>  
  
3.  <span data-ttu-id="ceb31-323">选择中的行为扩展元素**行为元素扩展位置**部分。</span><span class="sxs-lookup"><span data-stu-id="ceb31-323">Select a behavior extension element in the **Behavior Element Extension Position** section.</span></span>  
  
4.  <span data-ttu-id="ceb31-324">使用**向上**或**下**要更改所选元素的位置的列表左侧的按钮。</span><span class="sxs-lookup"><span data-stu-id="ceb31-324">Use the **Up** or **Down** button on the left side of the list to change the position of the selected element.</span></span>  
  
##### <a name="editing-the-configuration-of-behavior-element-extensions"></a><span data-ttu-id="ceb31-325">编辑行为元素扩展的配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-325">Editing the Configuration of Behavior Element Extensions</span></span>  
  
1.  <span data-ttu-id="ceb31-326">选择树中的一个行为节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-326">Select one of the behavior nodes in the tree.</span></span>  
  
2.  <span data-ttu-id="ceb31-327">选择包含要编辑的元素的行为。</span><span class="sxs-lookup"><span data-stu-id="ceb31-327">Select the behavior that contains the element you want to edit.</span></span>  
  
3.  <span data-ttu-id="ceb31-328">选择要编辑的行为元素扩展。</span><span class="sxs-lookup"><span data-stu-id="ceb31-328">Select the behavior element extension you want to edit.</span></span> <span data-ttu-id="ceb31-329">该元素的设置将出现在右窗格中，可在其中编辑这些设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-329">The settings of the element appear in the right pane where they can be edited.</span></span>  
  
#### <a name="protocolmapping"></a><span data-ttu-id="ceb31-330">ProtocolMapping</span><span class="sxs-lookup"><span data-stu-id="ceb31-330">ProtocolMapping</span></span>  
 <span data-ttu-id="ceb31-331">使用本节，可以通过协议地址方案和可能的绑定之间已定义的映射，来设置不同协议（如 http、tcp、MSMQ 或 net.pipe）的默认绑定类型。</span><span class="sxs-lookup"><span data-stu-id="ceb31-331">This section allows you to set default binding types for different protocols such as http, tcp, MSMQ or net.pipe through defined mapping between protocol address schemes and the possible bindings.</span></span> <span data-ttu-id="ceb31-332">还可以添加对其他协议的新映射。</span><span class="sxs-lookup"><span data-stu-id="ceb31-332">You can also add new mappings to other protocols.</span></span>  
  
#### <a name="extensions"></a><span data-ttu-id="ceb31-333">扩展</span><span class="sxs-lookup"><span data-stu-id="ceb31-333">Extensions</span></span>  
 <span data-ttu-id="ceb31-334">在 WCF 配置中使用，可以注册新的绑定扩展、 绑定元素扩展、 标准终结点扩展和行为扩展。</span><span class="sxs-lookup"><span data-stu-id="ceb31-334">New binding extensions, binding element extensions, standard endpoint extensions and behavior extensions can be registered for use in WCF configuration.</span></span> <span data-ttu-id="ceb31-335">扩展是名称/类型对。</span><span class="sxs-lookup"><span data-stu-id="ceb31-335">Extensions are name/type pairs.</span></span> <span data-ttu-id="ceb31-336">名称定义扩展在配置中的名称，而类型则实现该扩展。</span><span class="sxs-lookup"><span data-stu-id="ceb31-336">The name defines the name of the extension in configuration, whereas the type implements the extension.</span></span> <span data-ttu-id="ceb31-337">有四种类型的扩展：</span><span class="sxs-lookup"><span data-stu-id="ceb31-337">There are four types of extensions:</span></span>  
  
-   <span data-ttu-id="ceb31-338">绑定扩展定义整个绑定类型。</span><span class="sxs-lookup"><span data-stu-id="ceb31-338">Binding extensions define an entire binding type.</span></span> <span data-ttu-id="ceb31-339">示例：`basicHttpBinding`。</span><span class="sxs-lookup"><span data-stu-id="ceb31-339">Example: `basicHttpBinding`.</span></span>  
  
-   <span data-ttu-id="ceb31-340">绑定元素扩展定义绑定的元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-340">Binding element extensions define an element of a binding.</span></span> <span data-ttu-id="ceb31-341">示例：`textMessageEncoding`。</span><span class="sxs-lookup"><span data-stu-id="ceb31-341">Example: `textMessageEncoding`.</span></span>  
  
-   <span data-ttu-id="ceb31-342">标准终结点扩展定义整个标准终结点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-342">Standard endpoint extensions define an entire standard endpoint.</span></span> <span data-ttu-id="ceb31-343">示例：`discoveryEndpoint`。</span><span class="sxs-lookup"><span data-stu-id="ceb31-343">Example: `discoveryEndpoint`.</span></span>  
  
-   <span data-ttu-id="ceb31-344">行为元素扩展定义行为的元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-344">Behavior element extensions define an element of a behavior.</span></span> <span data-ttu-id="ceb31-345">示例：`clientVia`。</span><span class="sxs-lookup"><span data-stu-id="ceb31-345">Example: `clientVia`.</span></span>  
  
 <span data-ttu-id="ceb31-346">可像使用同类型的任何其他 WCF 组件一样使用已在配置中注册的扩展。</span><span class="sxs-lookup"><span data-stu-id="ceb31-346">Extensions that have been registered in configuration can be used like any other WCF component of the same type.</span></span>  
  
##### <a name="adding-a-new-extension"></a><span data-ttu-id="ceb31-347">添加新扩展</span><span class="sxs-lookup"><span data-stu-id="ceb31-347">Adding a new extension</span></span>  
 <span data-ttu-id="ceb31-348">选择高级节点中的某个扩展节点：</span><span class="sxs-lookup"><span data-stu-id="ceb31-348">Select one of the extension nodes in the advanced nodes:</span></span>  
  
1.  <span data-ttu-id="ceb31-349">单击“新建” 。</span><span class="sxs-lookup"><span data-stu-id="ceb31-349">Click **New**.</span></span>  
  
2.  <span data-ttu-id="ceb31-350">输入名称和类型。</span><span class="sxs-lookup"><span data-stu-id="ceb31-350">Enter a name and type.</span></span>  
  
3.  <span data-ttu-id="ceb31-351">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-351">Click **OK**.</span></span>  
  
4.  <span data-ttu-id="ceb31-352">扩展现在出现在编辑器中的适当位置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-352">The extension now appears in the appropriate place in the Editor.</span></span> <span data-ttu-id="ceb31-353">例如，如果添加了行为元素扩展，它将出现在可用扩展的列表中。</span><span class="sxs-lookup"><span data-stu-id="ceb31-353">For example, if you add a behavior element extension, it appears in the list of available extensions.</span></span>  
  
#### <a name="hosting-environment"></a><span data-ttu-id="ceb31-354">宿主环境</span><span class="sxs-lookup"><span data-stu-id="ceb31-354">Hosting Environment</span></span>  
 <span data-ttu-id="ceb31-355">本节介绍如何为服务主机环境定义实例化设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-355">This section allows you to define instantiation settings for the service hosting environment.</span></span>  
  
### <a name="creating-a-configuration-file-using-the-wizard"></a><span data-ttu-id="ceb31-356">使用向导创建配置文件</span><span class="sxs-lookup"><span data-stu-id="ceb31-356">Creating a Configuration File Using the Wizard</span></span>  
 <span data-ttu-id="ceb31-357">创建新配置文件的一种方法是使用“新建服务元素向导”。</span><span class="sxs-lookup"><span data-stu-id="ceb31-357">One way to create a new configuration file is to use the New Service Element Wizard.</span></span> <span data-ttu-id="ceb31-358">该向导查找已安装的服务类型和其他元素符合的计算机上，包括 COM + 和 Web 承载的虚拟目录，WCF，并加载它们以方便创建更简化的配置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-358">The wizard finds the installed service types and other elements compatible with WCF on the computer, including COM+ and Web-hosted virtual directories, and loads them to make creating the configuration much more streamlined.</span></span>  
  
#### <a name="creating-a-configuration-file"></a><span data-ttu-id="ceb31-359">创建配置文件</span><span class="sxs-lookup"><span data-stu-id="ceb31-359">Creating a Configuration File</span></span>  
  
1.  <span data-ttu-id="ceb31-360">通过使用命令窗口导航到你 WCF 的安装位置，，然后键入启动服务配置编辑器`SvcConfigEditor.exe`。</span><span class="sxs-lookup"><span data-stu-id="ceb31-360">Start Service Configuration Editor by using a command window to navigate to your WCF installation location, and then type `SvcConfigEditor.exe`.</span></span>  
  
2.  <span data-ttu-id="ceb31-361">从**文件**菜单上，选择**打开**单击**可执行文件**， **COM + 服务**，或**WebHosted 服务**，具体取决于你想要创建的配置文件的类型。</span><span class="sxs-lookup"><span data-stu-id="ceb31-361">From the **File** menu, select **Open** and click **Executable**, **COM+ Service**, or **WebHosted Service**, depending on the type of configuration file you want to create.</span></span>  
  
3.  <span data-ttu-id="ceb31-362">在**打开**对话框框中，导航到你想要创建的配置文件，并双击它的特定文件。</span><span class="sxs-lookup"><span data-stu-id="ceb31-362">In the **Open** dialog box, navigate to the specific file you want to create a configuration file for and double-click it.</span></span>  
  
4.  <span data-ttu-id="ceb31-363">在**文件**菜单上，指向**添加新项**单击**服务**。</span><span class="sxs-lookup"><span data-stu-id="ceb31-363">In the **File** menu, point to **Add New Item** and click **Service**.</span></span> <span data-ttu-id="ceb31-364">“新建服务元素向导”随即打开。</span><span class="sxs-lookup"><span data-stu-id="ceb31-364">The New Service Element Wizard opens.</span></span>  
  
5.  <span data-ttu-id="ceb31-365">按照向导中的步骤创建新服务。</span><span class="sxs-lookup"><span data-stu-id="ceb31-365">Follow the steps in the wizard to create the new service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ceb31-366">如果想要从向导生成的配置文件中使用 NetPeerTcpBinding，您必须手动添加一个绑定配置元素，并将其 `mode` 元素的 `security` 特性设置为“None”。</span><span class="sxs-lookup"><span data-stu-id="ceb31-366">If you want to use the NetPeerTcpBinding from the configuration file generated by the Wizard, you have to manually add a binding configuration element and modify the `mode` attribute of its `security` element to "None".</span></span>  
  
## <a name="configuring-com"></a><span data-ttu-id="ceb31-367">配置 COM+</span><span class="sxs-lookup"><span data-stu-id="ceb31-367">Configuring COM+</span></span>  
 <span data-ttu-id="ceb31-368">使用服务配置编辑器可以为现有 COM+ 应用程序创建新的配置文件，或者编辑现有的 COM+ 配置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-368">The Service Configuration Editor enables you to create a new configuration file for an existing COM+ application, or edit an existing COM+ configuration.</span></span> <span data-ttu-id="ceb31-369">**COM 协定**节点才可见 <`comContract`> 部分中的配置文件存在。</span><span class="sxs-lookup"><span data-stu-id="ceb31-369">The **COM Contract** node is only visible when the <`comContract`> section exists in the configuration file.</span></span>  
  
### <a name="creating-a-new-com-configuration"></a><span data-ttu-id="ceb31-370">创建新的 COM+ 配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-370">Creating a New COM+ Configuration</span></span>  
 <span data-ttu-id="ceb31-371">创建新的 COM+ 配置之前，请确保您的 COM+ 应用程序已安装在 Component Services 中，并已在全局程序集缓存 (GAC) 中注册。</span><span class="sxs-lookup"><span data-stu-id="ceb31-371">Before creating a new COM+ configuration, make sure that your COM+ application is installed in Component Services, and registered in the Global Assembly Cache (GAC).</span></span>  
  
1.  <span data-ttu-id="ceb31-372">选择**文件**菜单->**集成** -> **COM + 应用程序。**</span><span class="sxs-lookup"><span data-stu-id="ceb31-372">Select **File** menu -> **Integrate** -> **COM+ Application.**</span></span> <span data-ttu-id="ceb31-373">此操作将关闭当前打开的文件。</span><span class="sxs-lookup"><span data-stu-id="ceb31-373">This operation closes the current opened file.</span></span> <span data-ttu-id="ceb31-374">如果当前文件中有未保存的数据，将显示“保存”对话框。</span><span class="sxs-lookup"><span data-stu-id="ceb31-374">If there is unsaved data in the current file, a Save dialog appears.</span></span> <span data-ttu-id="ceb31-375">**COM + 集成向导**随即启动。</span><span class="sxs-lookup"><span data-stu-id="ceb31-375">The **COM+ Integration Wizard** is then launched.</span></span>  
  
2.  <span data-ttu-id="ceb31-376">在第一页中，从树中选择 COM+ 应用程序。</span><span class="sxs-lookup"><span data-stu-id="ceb31-376">In the first page, select the COM+ application from the tree.</span></span> <span data-ttu-id="ceb31-377">如果在树中找不到你的 COM+ 应用程序，请验证它是否已安装在组件服务中，并已在全局程序集缓存 (GAC) 中注册。</span><span class="sxs-lookup"><span data-stu-id="ceb31-377">If you cannot find your COM+ application in the tree, verify that it is installed in the Component Services and registered in the Global Assembly Cache (GAC).</span></span>  
  
3.  <span data-ttu-id="ceb31-378">在下一页中，选择将要哪个（哪些）方法公开为 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="ceb31-378">In the next page, select which method(s) you want to expose as WCF services.</span></span> <span data-ttu-id="ceb31-379">默认情况下，COM+ 应用程序中支持的所有方法都将显示并被选中。</span><span class="sxs-lookup"><span data-stu-id="ceb31-379">All the supported methods in the COM+ application are displayed and selected by default.</span></span>  
  
4.  <span data-ttu-id="ceb31-380">选择宿主方法。</span><span class="sxs-lookup"><span data-stu-id="ceb31-380">Choose a hosting method.</span></span>  
  
5.  <span data-ttu-id="ceb31-381">根据向导中的指导配置其他设置。</span><span class="sxs-lookup"><span data-stu-id="ceb31-381">Configure other settings according to the guides in the wizard.</span></span>  
  
6.  <span data-ttu-id="ceb31-382">服务配置编辑器在后台利用 ComSvcConfig.exe 来生成配置文件。</span><span class="sxs-lookup"><span data-stu-id="ceb31-382">Service Configuration Editor utilizes ComSvcConfig.exe in the background to generate configuration file.</span></span> <span data-ttu-id="ceb31-383">此操作完成后，可查看摘要，然后退出向导。</span><span class="sxs-lookup"><span data-stu-id="ceb31-383">After this is completed, you can view a summary and exit the wizard.</span></span> <span data-ttu-id="ceb31-384">生成的配置文件将打开，您可以直接进行编辑。</span><span class="sxs-lookup"><span data-stu-id="ceb31-384">The generated configuration file is opened so that you can edit it directly.</span></span>  
  
### <a name="editing-an-existing-com-configuration"></a><span data-ttu-id="ceb31-385">编辑现有 COM+ 配置</span><span class="sxs-lookup"><span data-stu-id="ceb31-385">Editing an Existing COM+ Configuration</span></span>  
  
1.  <span data-ttu-id="ceb31-386">选择**文件**菜单->**打开** -> **COM + 服务**...</span><span class="sxs-lookup"><span data-stu-id="ceb31-386">Select **File** menu -> **Open** -> **COM+ Service**…</span></span>  
  
2.  <span data-ttu-id="ceb31-387">从列表中选择要编辑的 COM+ 服务。</span><span class="sxs-lookup"><span data-stu-id="ceb31-387">Select the COM+ Service you want to edit from the list.</span></span>  
  
3.  <span data-ttu-id="ceb31-388">编辑中的配置设置**COM 协定**节点。</span><span class="sxs-lookup"><span data-stu-id="ceb31-388">Edit configuration settings in the **COM Contracts** node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ceb31-389">也可以直接打开并编辑包含 COM 约定的配置文件。</span><span class="sxs-lookup"><span data-stu-id="ceb31-389">You can also directly open and edit a configuration file that contains COM contracts.</span></span>  
  
## <a name="security"></a><span data-ttu-id="ceb31-390">安全性</span><span class="sxs-lookup"><span data-stu-id="ceb31-390">Security</span></span>  
 <span data-ttu-id="ceb31-391">不能保证配置编辑器生成的服务配置文件是安全的。</span><span class="sxs-lookup"><span data-stu-id="ceb31-391">A service configuration file generated by the Configuration Editor is not guaranteed to be secure.</span></span> <span data-ttu-id="ceb31-392">请参阅[安全](../../../docs/framework/wcf/feature-details/security.md)文档以了解如何保护您的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="ceb31-392">Please refer to the [Security](../../../docs/framework/wcf/feature-details/security.md) documentation to find out how to secure your WCF services.</span></span>  
  
 <span data-ttu-id="ceb31-393">此外，只能使用配置编辑器来读取和写入有效的 WCF 配置元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-393">In addition, the Configuration Editor can only be used to read and write valid WCF configuration elements.</span></span> <span data-ttu-id="ceb31-394">工具将忽略符合架构的用户定义元素。</span><span class="sxs-lookup"><span data-stu-id="ceb31-394">The tool ignores schema-compliant, user-defined elements.</span></span> <span data-ttu-id="ceb31-395">工具不会尝试从配置文件中移除这些元素，或确定它们对已知 WCF 元素的影响。</span><span class="sxs-lookup"><span data-stu-id="ceb31-395">It also does not attempt remove these elements from the configuration file or determine their effects on the known WCF elements.</span></span> <span data-ttu-id="ceb31-396">用户需要负责确定这些元素是否会对应用程序或系统构成威胁。</span><span class="sxs-lookup"><span data-stu-id="ceb31-396">It is the user’s responsibility to determine whether these elements pose a threat to the application or the system.</span></span>
