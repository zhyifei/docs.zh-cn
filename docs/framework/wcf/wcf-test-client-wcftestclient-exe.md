---
title: WCF 测试客户端 (WcfTestClient.exe)
ms.date: 03/30/2017
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
ms.openlocfilehash: edce9d2eb2d0bcd915beae0c75d3474d93d8fd51
ms.sourcegitcommit: c6f69b0cf149f6b54483a6d5c2ece222913f43ce
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2019
ms.locfileid: "55904002"
---
# <a name="wcf-test-client-wcftestclientexe"></a><span data-ttu-id="cc970-102">WCF 测试客户端 (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="cc970-102">WCF Test Client (WcfTestClient.exe)</span></span>
<span data-ttu-id="cc970-103">Windows Communication Foundation (WCF) 测试客户端 (WcfTestClient.exe) 是一个 GUI 工具，使用户能够输入测试参数、 将该输入到服务，提交并查看服务发回的响应。</span><span class="sxs-lookup"><span data-stu-id="cc970-103">Windows Communication Foundation (WCF) Test Client (WcfTestClient.exe) is a GUI tool that enables users to input test parameters, submit that input to the service, and view the response that the service sends back.</span></span> <span data-ttu-id="cc970-104">它提供了完美的服务测试体验与 WCF 服务主机结合使用时。</span><span class="sxs-lookup"><span data-stu-id="cc970-104">It provides a seamless service testing experience when combined with WCF Service Host.</span></span>  
  
 <span data-ttu-id="cc970-105">通常可以在以下位置找到 WCF 测试客户端 (WcfTestClient.exe): `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` -社区可能是其中一个"企业"，"Professional"或"Community"具体取决于哪一级别的 Visual Studio 安装。</span><span class="sxs-lookup"><span data-stu-id="cc970-105">You can typically find the WCF Test Client (WcfTestClient.exe) in the following location: `C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` - Community may be one of "Enterprise", "Professional" or "Community" depending on which level of Visual Studio is installed.</span></span>
  
## <a name="scenarios-for-using-test-client"></a><span data-ttu-id="cc970-106">使用测试客户端的方案</span><span class="sxs-lookup"><span data-stu-id="cc970-106">Scenarios for Using Test Client</span></span>  
 <span data-ttu-id="cc970-107">以下各节讨论在其中您可以使用 WCF 测试客户端来简化开发过程的最常见方案。</span><span class="sxs-lookup"><span data-stu-id="cc970-107">The following sections discuss the most common scenarios in which you can use WCF Test Client to streamline your development process.</span></span>  
  
### <a name="inside-visual-studio"></a><span data-ttu-id="cc970-108">Visual Studio 内部</span><span class="sxs-lookup"><span data-stu-id="cc970-108">Inside Visual Studio</span></span>  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a><span data-ttu-id="cc970-109">WCF 服务主机启动 WCF 测试客户端和一项服务</span><span class="sxs-lookup"><span data-stu-id="cc970-109">WCF Service Host Starts WCF Test Client with a Single Service</span></span>  
 <span data-ttu-id="cc970-110">创建新的 WCF 服务项目并按 F5 启动调试器后，WCF 服务主机开始将服务托管在你的项目。</span><span class="sxs-lookup"><span data-stu-id="cc970-110">After you create a new WCF service project and press F5 to start the debugger, the WCF Service Host begins to host the service in your project.</span></span> <span data-ttu-id="cc970-111">然后，WCF 测试客户端打开并显示配置文件中定义的服务终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="cc970-111">Then, WCF Test Client opens and displays a list of service endpoints defined in the configuration file.</span></span> <span data-ttu-id="cc970-112">可以测试参数和调用服务，并可以重复此过程以继续测试和验证服务。</span><span class="sxs-lookup"><span data-stu-id="cc970-112">You can test the parameters and invoke the service, and repeat this process to continuously test and validate your service.</span></span>  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a><span data-ttu-id="cc970-113">WCF 服务主机启动 WCF 测试客户端和多项服务</span><span class="sxs-lookup"><span data-stu-id="cc970-113">WCF Service Host Starts WCF Test Client with Multiple Services</span></span>  
 <span data-ttu-id="cc970-114">WCF 测试客户端还可用于帮助调试包含多个服务的服务项目。</span><span class="sxs-lookup"><span data-stu-id="cc970-114">You can also use WCF Test Client to help debug a service project that contains multiple services.</span></span> <span data-ttu-id="cc970-115">WCF 测试客户端打开后，它自动循环访问你的项目中的服务列表并将其打开进行测试。</span><span class="sxs-lookup"><span data-stu-id="cc970-115">When WCF Test Client opens, it automatically iterates the list of services in your project and opens them for testing.</span></span>  
  
### <a name="outside-visual-studio"></a><span data-ttu-id="cc970-116">Visual Studio 外部</span><span class="sxs-lookup"><span data-stu-id="cc970-116">Outside Visual Studio</span></span>  
 <span data-ttu-id="cc970-117">Visual Studio 来测试在 Internet 上的任意服务外，还可以调用 WCF 测试客户端 (WcfTestClient.exe)。</span><span class="sxs-lookup"><span data-stu-id="cc970-117">You can also invoke the WCF Test Client (WcfTestClient.exe) outside Visual Studio to test an arbitrary service on the Internet.</span></span> <span data-ttu-id="cc970-118">若要找到此工具，请转到以下位置：</span><span class="sxs-lookup"><span data-stu-id="cc970-118">To locate the tool, go to the following location:</span></span>  
  
 <span data-ttu-id="cc970-119">`C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` （社区可以是"企业"、"Professional"或"社区"，具体取决于在计算机安装的 Visual Studio 级别之一）</span><span class="sxs-lookup"><span data-stu-id="cc970-119">`C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE` (where community can be one of "Enterprise", "Professional" or "Community" depending on which level of Visual Studio is installed on the machine)</span></span>
  
 <span data-ttu-id="cc970-120">若要使用该工具，可以双击此文件名从该位置打开它，也可以从命令行启动它。</span><span class="sxs-lookup"><span data-stu-id="cc970-120">To use the tool, double-click the file name to open it from this location, or launch it from a command line.</span></span>  
  
 <span data-ttu-id="cc970-121">WCF 测试客户端将任意数目的 Uri 作为命令行参数。</span><span class="sxs-lookup"><span data-stu-id="cc970-121">WCF Test Client takes an arbitrary number of URIs as command line arguments.</span></span>  <span data-ttu-id="cc970-122">这些 URI 是可以测试的服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="cc970-122">These are the URIs of services that can be tested.</span></span>  
  
 `wcfTestClient.exe URI1 URI2 …`  
  
 <span data-ttu-id="cc970-123">WCF 测试客户端窗口打开后，单击**文件**->**添加服务**，并输入你想要打开的服务的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="cc970-123">After the WCF Test Client window is opened, click **File**->**Add Service**, and enter the endpoint address of the service you want to open.</span></span>  
  
## <a name="wcf-test-client-user-interface"></a><span data-ttu-id="cc970-124">WCF 测试客户端用户界面</span><span class="sxs-lookup"><span data-stu-id="cc970-124">WCF Test Client User Interface</span></span>  
 <span data-ttu-id="cc970-125">与单个服务或多个服务，可以使用 WCF 测试客户端。</span><span class="sxs-lookup"><span data-stu-id="cc970-125">You can use WCF Test Client with a single service or multiple services.</span></span>  
  
### <a name="service-operations"></a><span data-ttu-id="cc970-126">服务操作</span><span class="sxs-lookup"><span data-stu-id="cc970-126">Service Operations</span></span>  
 <span data-ttu-id="cc970-127">WCF 测试客户端主窗口的左的窗格列出了所有可用服务，以及它们各自的终结点和操作。</span><span class="sxs-lookup"><span data-stu-id="cc970-127">The left pane of the WCF Test Client main window lists all the available services, along with their respective endpoints and operations.</span></span>  
  
 <span data-ttu-id="cc970-128">双击某个操作后，可以在具有此操作名称的新选项卡内的右窗格中查看其内容。</span><span class="sxs-lookup"><span data-stu-id="cc970-128">When you double-click an operation, you can view its content in the right pane inside a new tab with the operation's name.</span></span>  
  
 <span data-ttu-id="cc970-129">左窗格还列出了客户端配置文件。</span><span class="sxs-lookup"><span data-stu-id="cc970-129">The left pane also lists client configuration files.</span></span> <span data-ttu-id="cc970-130">双击任何项可以在新选项卡式窗口内的右窗格中显示文件的内容。</span><span class="sxs-lookup"><span data-stu-id="cc970-130">Double-click any of the items to display the content of the file in a new tabbed window in the right pane.</span></span>  
  
### <a name="entering-test-parameters"></a><span data-ttu-id="cc970-131">输入测试参数</span><span class="sxs-lookup"><span data-stu-id="cc970-131">Entering Test Parameters</span></span>  
 <span data-ttu-id="cc970-132">若要查看测试参数，请双击某个操作以在右侧窗格中打开它。</span><span class="sxs-lookup"><span data-stu-id="cc970-132">To view the test parameters, double-click an operation to open it in the right pane.</span></span> <span data-ttu-id="cc970-133">参数显示在**格式化**视图默认情况下的，可以输入任意值以测试服务的参数。</span><span class="sxs-lookup"><span data-stu-id="cc970-133">The parameters are showed in **Formatted** view by default, and you can enter arbitrary values for the parameters to test the service.</span></span>  
  
 <span data-ttu-id="cc970-134">若要查看消息的 XML，请单击**XML**。</span><span class="sxs-lookup"><span data-stu-id="cc970-134">To view the message's XML, click **XML**.</span></span> <span data-ttu-id="cc970-135">若要将其发送到服务，请单击**Invoke**。</span><span class="sxs-lookup"><span data-stu-id="cc970-135">To send them to the service, click **Invoke**.</span></span>  
  
 <span data-ttu-id="cc970-136">数据集参数，请单击 **...**</span><span class="sxs-lookup"><span data-stu-id="cc970-136">For a DataSet parameter, click the **…**</span></span> <span data-ttu-id="cc970-137">按钮旁边**编辑...**</span><span class="sxs-lookup"><span data-stu-id="cc970-137">button next to **Edit…**</span></span> <span data-ttu-id="cc970-138">若要在新窗口中显示数据网格中编辑它。</span><span class="sxs-lookup"><span data-stu-id="cc970-138">to edit it in a new window showing the DataGrid.</span></span> <span data-ttu-id="cc970-139">请注意的外观**复制数据集**并**粘贴数据集**按钮。</span><span class="sxs-lookup"><span data-stu-id="cc970-139">Notice the appearance of the **Copy DataSet** and **Paste DataSet** buttons.</span></span> <span data-ttu-id="cc970-140">如果第一次编辑时 DataSet 对象的架构未知，则 DataGrid 为空。</span><span class="sxs-lookup"><span data-stu-id="cc970-140">If the schema of the DataSet object is unknown upon the first edit, the DataGrid is empty.</span></span> <span data-ttu-id="cc970-141">您必须将具有相同架构的 DataSet 对象粘贴到 DataGrid 中的当前对象。</span><span class="sxs-lookup"><span data-stu-id="cc970-141">You have to paste a DataSet object with the same schema into the current object in the DataGrid.</span></span> <span data-ttu-id="cc970-142">（请注意，在粘贴操作之前需要从其他位置复制架构。）此外可以通过单击复制 Dataset 对象以供将来使用情况**复制数据集**按钮。</span><span class="sxs-lookup"><span data-stu-id="cc970-142">(Notice that you need to copy the schema from somewhere else before the paste operation.) You can also copy a Dataset object for future usage by clicking the **Copy DataSet** button.</span></span>  
  
 <span data-ttu-id="cc970-143">服务响应将出现在测试参数下面。</span><span class="sxs-lookup"><span data-stu-id="cc970-143">The service's response appears below the test parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc970-144">如果预期的返回值是字符串，则结果将显示为带引号的字符串，即使提供的输入未包含在引号中，也是如此。</span><span class="sxs-lookup"><span data-stu-id="cc970-144">If the expected return value is a string, the result will be displayed as a quoted string even though the input provided was not in quotes.</span></span>  
  
 <span data-ttu-id="cc970-145">如果在创建服务约定时将特定操作指定为单向操作，则不会显示服务响应。</span><span class="sxs-lookup"><span data-stu-id="cc970-145">If you specified a particular operation as one-way when you created the contract for the service, no service response is displayed.</span></span> <span data-ttu-id="cc970-146">消息一旦处于排队等待发送状态，则会弹出一个对话框，通知您已成功发送消息。</span><span class="sxs-lookup"><span data-stu-id="cc970-146">As soon as the message is queued for delivery, a dialog box pops up to notify you that the message was successfully sent.</span></span>  
  
### <a name="session-support"></a><span data-ttu-id="cc970-147">会话支持</span><span class="sxs-lookup"><span data-stu-id="cc970-147">Session Support</span></span>  
 <span data-ttu-id="cc970-148">**启动新的代理**服务操作的选项卡中的复选框可用于切换会话支持。</span><span class="sxs-lookup"><span data-stu-id="cc970-148">The **Start a new proxy** check box in a service operation's tab enables you to toggle session support.</span></span> <span data-ttu-id="cc970-149">默认情况下清除此框。</span><span class="sxs-lookup"><span data-stu-id="cc970-149">This box is cleared by default.</span></span>  
  
 <span data-ttu-id="cc970-150">当为某个特定操作 （或同一服务终结点中的另一个操作） 中输入测试参数并单击**Invoke**多次清除此复选框，这些操作将共用一个代理，并且服务状态为保留多个操作。</span><span class="sxs-lookup"><span data-stu-id="cc970-150">When you enter test parameters for a specific operation (or another operation in the same service endpoint) and click **Invoke** multiple times with the check box cleared, these operations share one proxy and the service status is persisted across multiple operations.</span></span>  
  
 <span data-ttu-id="cc970-151">如果**启动新的代理**复选框后，新的代理启动每个**Invoke**、 上一个会话方案终止，并且会重置服务状态。</span><span class="sxs-lookup"><span data-stu-id="cc970-151">If the **Start a new proxy** check box is checked, a new proxy is started for each **Invoke**, the previous session scenario is ended, and the service status is reset.</span></span>  
  
### <a name="editing-client-configuration"></a><span data-ttu-id="cc970-152">编辑客户端配置</span><span class="sxs-lookup"><span data-stu-id="cc970-152">Editing Client Configuration</span></span>  
 <span data-ttu-id="cc970-153">WCF 测试客户端主窗口的左的窗格列出了客户端配置文件。</span><span class="sxs-lookup"><span data-stu-id="cc970-153">The left pane of the WCF Test Client main window lists client configuration files.</span></span> <span data-ttu-id="cc970-154">双击任何项可以在右窗格中显示文件的内容。</span><span class="sxs-lookup"><span data-stu-id="cc970-154">Double-click any of the items to display the contents of the file in the right pane.</span></span>  
  
#### <a name="edit-with-service-configuration-editor"></a><span data-ttu-id="cc970-155">使用服务配置编辑器进行编辑</span><span class="sxs-lookup"><span data-stu-id="cc970-155">Edit with Service Configuration Editor</span></span>  
 <span data-ttu-id="cc970-156">右键单击**配置文件**在左窗格中，选择上下文菜单**用 svcconfigeditor 进行编辑**。</span><span class="sxs-lookup"><span data-stu-id="cc970-156">Right-click **Config File** in the left pane and select the context menu **Edit with SvcConfigEditor**.</span></span> <span data-ttu-id="cc970-157">服务配置编辑器启动并显示客户端配置内容。</span><span class="sxs-lookup"><span data-stu-id="cc970-157">Service Configuration Editor is launched with the client configuration content.</span></span> <span data-ttu-id="cc970-158">可以编辑配置，然后将其保存在此工具中。</span><span class="sxs-lookup"><span data-stu-id="cc970-158">You can edit the configuration and save it within the tool.</span></span>  
  
 <span data-ttu-id="cc970-159">在服务配置编辑器中保存该文件之后, WCF 测试客户端显示一条警告消息，告知你该文件已外被修改，并询问是否想要重新加载它。</span><span class="sxs-lookup"><span data-stu-id="cc970-159">After saving the file in Service Configuration Editor, WCF Test Client displays a warning message to inform you that the file has been modified outside and asks whether you would like to reload it.</span></span>  
  
 <span data-ttu-id="cc970-160">如果选择**是**，"Client.dll.config"选项卡中的配置内容将反映在编辑器中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cc970-160">If you select **Yes**, the configuration content in the "Client.dll.config" tab reflects the changes you made in the editor.</span></span>  
  
 <span data-ttu-id="cc970-161">如果选择**否**，"Client.dll.config"选项卡中的配置内容保持不变，并且修改后的内容自动保存到源文件。</span><span class="sxs-lookup"><span data-stu-id="cc970-161">If you select **No**, the configuration content in the "Client.dll.config" tab remains unchanged and the modified content is automatically saved to the source file.</span></span>  
  
#### <a name="restore-to-default-configuration"></a><span data-ttu-id="cc970-162">还原到默认配置</span><span class="sxs-lookup"><span data-stu-id="cc970-162">Restore to Default Configuration</span></span>  
 <span data-ttu-id="cc970-163">如果你想要取消所有更改并还原到默认客户端配置中，右键单击**配置文件**在左窗格中，选择上下文菜单**还原到默认配置**。加载默认配置值和还原"Client.dll.config"选项卡中的内容。</span><span class="sxs-lookup"><span data-stu-id="cc970-163">If you want to cancel all the changes and restore to the default client configuration, right-click **Config File** in the left pane and select the context menu **Restore to Default Config**. The default configuration value is loaded and content in "Client.dll.config" tab is restored.</span></span>  
  
#### <a name="validate-changes"></a><span data-ttu-id="cc970-164">验证更改</span><span class="sxs-lookup"><span data-stu-id="cc970-164">Validate Changes</span></span>  
 <span data-ttu-id="cc970-165">WCF 测试客户端中正在加载已保存的更改，配置被检查针对 WCF 架构有效性。</span><span class="sxs-lookup"><span data-stu-id="cc970-165">When saved changes are being loaded in WCF Test Client, the configuration is checked for validity against WCF schema.</span></span> <span data-ttu-id="cc970-166">如果发现错误，将显示一个对话框来给出错误详细信息。</span><span class="sxs-lookup"><span data-stu-id="cc970-166">If errors are found, a dialog box is displayed to show error details.</span></span>  
  
 <span data-ttu-id="cc970-167">在代理生成、 二进制编译或服务调用，支持编辑 （即，"编辑..."、"还原..."等） 的菜单项被禁用。</span><span class="sxs-lookup"><span data-stu-id="cc970-167">During proxy generation, binary compiling, or service invoking, menu items that support editing (that is, "Edit …", "Restore …", and so on) are disabled.</span></span> <span data-ttu-id="cc970-168">加载更新到 WCF 测试客户端配置时，将同时禁用服务调用。</span><span class="sxs-lookup"><span data-stu-id="cc970-168">Service invocation is also disabled when loading updated configuration to WCF Test Client.</span></span>  
  
#### <a name="persist-client-configuration"></a><span data-ttu-id="cc970-169">使客户端配置保持不变</span><span class="sxs-lookup"><span data-stu-id="cc970-169">Persist Client Configuration</span></span>  
 <span data-ttu-id="cc970-170">**工具**->**选项**->**客户端配置**选项卡包含**始终重新生成配置时启动服务**选项，默认情况下启用。</span><span class="sxs-lookup"><span data-stu-id="cc970-170">The **Tools**->**Options**->**Client Configuration** tab contains an **Always Regenerate Config When Launching Services** option, which is enabled by default.</span></span> <span data-ttu-id="cc970-171">此选项指定每次 WCF 测试客户端加载服务时，它重新生成基于最新的服务协定和服务 App.config 文件配置文件。</span><span class="sxs-lookup"><span data-stu-id="cc970-171">This option specifies that every time WCF Test Client loads a service, it regenerates a configuration file based on the latest service contract and service App.config files.</span></span>  
  
 <span data-ttu-id="cc970-172">如果已编辑的客户端配置为 WCF 服务并想要始终使用此更新后的文件来调试你的服务，可以取消选中**重新生成**选项。</span><span class="sxs-lookup"><span data-stu-id="cc970-172">If you have edited the client configuration for your WCF service and want to always use this updated file to debug your service, you can uncheck the **Regenerate** option.</span></span> <span data-ttu-id="cc970-173">通过此操作，即使更新服务并重新打开 WCF 测试客户端，Client.dll.config 文件将是你先前更新而不是重新生成一个基于更新的服务的一个。</span><span class="sxs-lookup"><span data-stu-id="cc970-173">By doing so, even when you update the service and reopen WCF Test Client, the Client.dll.config file is the one you updated previously instead of a regenerated one based on the updated service.</span></span>  
  
 <span data-ttu-id="cc970-174">但是，您可能需要编辑此配置文件以使其与重新生成的代理一致。</span><span class="sxs-lookup"><span data-stu-id="cc970-174">However, you might need to edit the configuration file to make it consistent with the regenerated proxy.</span></span> <span data-ttu-id="cc970-175">如果由于更新了服务而导致重新生成的代理与配置文件不匹配，则调用该服务时将出错。</span><span class="sxs-lookup"><span data-stu-id="cc970-175">If the regenerated proxy and configuration file are mismatched due to an updated service, errors will occur when the service is invoked.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="cc970-176">如果您已修改了客户端配置文件并选择以后再使用它，则可以在以下位置找到此文件：</span><span class="sxs-lookup"><span data-stu-id="cc970-176">If you have modified the client configuration file and select to reuse it in the future, you can find the file in the following location:</span></span>  
>   
>  <span data-ttu-id="cc970-177">\Documents 和设置\\[User Account] \My Documents\Test 客户端项目。</span><span class="sxs-lookup"><span data-stu-id="cc970-177">\Documents and Settings\\[User Account]\My Documents\Test Client Projects.</span></span>  
>   
>  <span data-ttu-id="cc970-178">任何存储到客户端配置文件的已更新的凭据信息都是由此文件夹的访问控制列表 (ACL) 保护的。</span><span class="sxs-lookup"><span data-stu-id="cc970-178">Any updated credential information stored to the client configuration file is protected by the Access Control List (ACL) of this folder.</span></span>  
  
### <a name="adding-removing-and-refreshing-services"></a><span data-ttu-id="cc970-179">添加、删除和刷新服务</span><span class="sxs-lookup"><span data-stu-id="cc970-179">Adding, Removing and Refreshing Services</span></span>  
  
#### <a name="add-service"></a><span data-ttu-id="cc970-180">添加服务</span><span class="sxs-lookup"><span data-stu-id="cc970-180">Add Service</span></span>  
 <span data-ttu-id="cc970-181">单击**文件**->**添加服务**将服务添加到 WCF 测试客户端。</span><span class="sxs-lookup"><span data-stu-id="cc970-181">Click **File**->**Add Service** to add a service to WCF Test Client.</span></span> <span data-ttu-id="cc970-182">然后您需要键入要添加的服务的 URI（终结点地址）。</span><span class="sxs-lookup"><span data-stu-id="cc970-182">You are then required to type the URI (endpoint address) of the service to be added.</span></span> <span data-ttu-id="cc970-183">该服务的地址可以是 mex 地址，也可以是 WSDL 地址。</span><span class="sxs-lookup"><span data-stu-id="cc970-183">The service’s address can be a mex address or WSDL address.</span></span>  
  
 <span data-ttu-id="cc970-184">此外可以找到列表中 10 个最近添加了的服务的终结点**最新服务**子菜单。</span><span class="sxs-lookup"><span data-stu-id="cc970-184">You can also find a list of 10 recently added services' endpoints in the **Recent Services** submenu.</span></span> <span data-ttu-id="cc970-185">如果选择其中之一，指定的服务添加到 WCF 测试客户端。</span><span class="sxs-lookup"><span data-stu-id="cc970-185">If you select one of them, the specified service is added to WCF Test Client.</span></span>  
  
 <span data-ttu-id="cc970-186">此外可以右击服务树的根**我的服务项目**，然后选择**添加的服务**来实现相同的结果。</span><span class="sxs-lookup"><span data-stu-id="cc970-186">You can also right-click the root of service tree **My Service Projects**, and select **Add Service** to achieve the same result.</span></span>  
  
 <span data-ttu-id="cc970-187">在代理生成、二进制编译或服务调用期间，支持添加服务的菜单项被禁用。</span><span class="sxs-lookup"><span data-stu-id="cc970-187">During proxy generation, binary compiling, or service invocation, menu items that support adding a service are disabled.</span></span> <span data-ttu-id="cc970-188">服务调用也被禁用。</span><span class="sxs-lookup"><span data-stu-id="cc970-188">Service invocation is also disabled.</span></span>  
  
#### <a name="remove-service"></a><span data-ttu-id="cc970-189">移除服务</span><span class="sxs-lookup"><span data-stu-id="cc970-189">Remove Service</span></span>  
 <span data-ttu-id="cc970-190">右键单击要删除，并且选择的服务的服务根**删除服务**从 WCF 测试客户端中删除服务。</span><span class="sxs-lookup"><span data-stu-id="cc970-190">Right-click the service root of the service to be removed, and select **Remove Service** to remove a service from WCF Test Client.</span></span>  
  
 <span data-ttu-id="cc970-191">在代理生成、二进制编译或服务调用期间，支持删除服务的菜单项被禁用。</span><span class="sxs-lookup"><span data-stu-id="cc970-191">During proxy generation, binary compiling, or service invocation, menu items that support removing a service are disabled.</span></span> <span data-ttu-id="cc970-192">服务调用也被禁用。</span><span class="sxs-lookup"><span data-stu-id="cc970-192">Service invocation is also disabled.</span></span>  
  
#### <a name="refresh-service"></a><span data-ttu-id="cc970-193">刷新服务</span><span class="sxs-lookup"><span data-stu-id="cc970-193">Refresh Service</span></span>  
 <span data-ttu-id="cc970-194">如果运行 WCF 测试客户端和你想要确保该服务的 WCF 测试客户端实现是最新时，将向服务进行更改，右键单击该服务，然后选择的服务根**刷新服务**。</span><span class="sxs-lookup"><span data-stu-id="cc970-194">If a change is made to the service while WCF Test Client is running and you want to ensure that the WCF Test Client implementation for that service is up-to-date, right-click the service root of the service, and select **Refresh Service**.</span></span> <span data-ttu-id="cc970-195">请注意，刷新后服务状态将重置。</span><span class="sxs-lookup"><span data-stu-id="cc970-195">Note that after refreshing, the service status is reset.</span></span>  
  
 <span data-ttu-id="cc970-196">在代理生成、二进制编译或服务调用期间，支持刷新服务的菜单项被禁用。</span><span class="sxs-lookup"><span data-stu-id="cc970-196">During proxy generation, binary compiling, or service invocation, menu items that support refreshing a service are disabled.</span></span> <span data-ttu-id="cc970-197">服务调用也被禁用。</span><span class="sxs-lookup"><span data-stu-id="cc970-197">Service invocation is also disabled.</span></span>  
  
## <a name="location-of-files-generated-by-the-test-client"></a><span data-ttu-id="cc970-198">测试客户端生成的文件的位置</span><span class="sxs-lookup"><span data-stu-id="cc970-198">Location of Files Generated by the Test Client</span></span>  
 <span data-ttu-id="cc970-199">默认情况下，WCF 测试客户端存储在"%appdata%\Local\temp\Test Client Projects"文件夹中生成客户端代码和配置文件。</span><span class="sxs-lookup"><span data-stu-id="cc970-199">By default, WCF Test Client stores generated client code and configuration files in the "%appdata%\Local\temp\Test Client Projects" folder.</span></span> <span data-ttu-id="cc970-200">WCF 测试客户端退出后，将删除此文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc970-200">This folder is deleted after WCF Test Client exits.</span></span> <span data-ttu-id="cc970-201">如果在 WCF 测试客户端中修改配置文件和**始终重新生成启动服务时配置**选项处于禁用状态，修改后的文件复制到"My Documents\Test Client Projects"下的"Cached Config"文件夹使用映射 （元数据的地址-到--文件名） XML 文件的索引。</span><span class="sxs-lookup"><span data-stu-id="cc970-201">If a configuration file is modified in WCF Test Client and the **Always Regenerate Config When Launching Services** option is disabled, the modified file is copied to the "Cached Config" folder under "My Documents\Test Client Projects" with a mapping (metadata-address-to-file-name) XML file as an index.</span></span>  
  
 <span data-ttu-id="cc970-202">你还可以在命令行中，使用启动 WCF 测试客户端`/ProjectPath`开关来指定新的所需的路径用于存储生成的文件，或者使用`/RestoreProjectPath`开关还原默认位置。</span><span class="sxs-lookup"><span data-stu-id="cc970-202">You can also start WCF Test Client in a command line, use the `/ProjectPath` switch to specify a new desired path for storing generated files, or use the `/RestoreProjectPath` switch to restore the default location.</span></span> <span data-ttu-id="cc970-203">语法如下所示：</span><span class="sxs-lookup"><span data-stu-id="cc970-203">The syntax is as follows:</span></span>  
  
 `wcfTestClient.exe /ProjectPath [desired location]`  
  
 <span data-ttu-id="cc970-204">运行此命令不会打开 WCF 测试客户端。</span><span class="sxs-lookup"><span data-stu-id="cc970-204">Running this command does not open WCF Test Client.</span></span> <span data-ttu-id="cc970-205">而只会更改文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="cc970-205">Only the folder location is changed.</span></span> <span data-ttu-id="cc970-206">是否正在运行 WCF 测试客户端，可以运行此命令。</span><span class="sxs-lookup"><span data-stu-id="cc970-206">You can run this command whether WCF Test Client is running or not.</span></span> <span data-ttu-id="cc970-207">重新启动 WCF 测试客户端时，将应用新位置。</span><span class="sxs-lookup"><span data-stu-id="cc970-207">The new location is applied when WCF Test Client is restarted.</span></span> <span data-ttu-id="cc970-208">在注册表中，或在"%appdata%\Local\temp\Test Client Projects"文件夹的 WcfTestClient.exe.option 文件中，可以保存的位置信息。</span><span class="sxs-lookup"><span data-stu-id="cc970-208">The location information can be saved in registry, or in the WcfTestClient.exe.option file in the "%appdata%\Local\temp\Test Client Projects" folder.</span></span>  
  
## <a name="features-supported-by-wcf-test-client"></a><span data-ttu-id="cc970-209">WCF 测试客户端支持的功能</span><span class="sxs-lookup"><span data-stu-id="cc970-209">Features supported by WCF Test Client</span></span>  
 <span data-ttu-id="cc970-210">以下是 WCF 测试客户端支持的功能的列表：</span><span class="sxs-lookup"><span data-stu-id="cc970-210">The following is a list of features supported by WCF Test Client:</span></span>  
  
-   <span data-ttu-id="cc970-211">服务调用：请求/响应和单向消息。</span><span class="sxs-lookup"><span data-stu-id="cc970-211">Service Invocation: Request/Response and One-way message.</span></span>  
  
-   <span data-ttu-id="cc970-212">绑定：Svcutil.exe 支持的所有绑定。</span><span class="sxs-lookup"><span data-stu-id="cc970-212">Bindings: all bindings supported by Svcutil.exe.</span></span>  
  
-   <span data-ttu-id="cc970-213">控制会话。</span><span class="sxs-lookup"><span data-stu-id="cc970-213">Controlling Session.</span></span>  
  
-   <span data-ttu-id="cc970-214">消息协定。</span><span class="sxs-lookup"><span data-stu-id="cc970-214">Message Contract.</span></span>  
  
-   <span data-ttu-id="cc970-215">XML 序列化。</span><span class="sxs-lookup"><span data-stu-id="cc970-215">XML serialization.</span></span>  
  
 <span data-ttu-id="cc970-216">以下是 WCF 测试客户端不支持的功能的列表：</span><span class="sxs-lookup"><span data-stu-id="cc970-216">The following is a list of features not supported by WCF Test Client:</span></span>  
  
-   <span data-ttu-id="cc970-217">类型：<xref:System.IO.Stream>、<xref:System.ServiceModel.Channels.Message>、<xref:System.Xml.XmlElement>、<xref:System.Xml.XmlAttribute>、<xref:System.Xml.XmlNode>、实现 <xref:System.Xml.Serialization.IXmlSerializable> 接口的类型（包括相关 <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> 特性）、<xref:System.Xml.Linq.XDocument> 和 <xref:System.Xml.Linq.XElement> 类型以及 ADO.NET <xref:System.Data.DataTable> 类型。</span><span class="sxs-lookup"><span data-stu-id="cc970-217">Types: <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message>, <xref:System.Xml.XmlElement>, <xref:System.Xml.XmlAttribute>, <xref:System.Xml.XmlNode>, types that implement the <xref:System.Xml.Serialization.IXmlSerializable> interface, including the related <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> attribute, and the <xref:System.Xml.Linq.XDocument> and <xref:System.Xml.Linq.XElement> types and the ADO.NET <xref:System.Data.DataTable> type.</span></span>  
  
-   <span data-ttu-id="cc970-218">双工协定。</span><span class="sxs-lookup"><span data-stu-id="cc970-218">Duplex contract.</span></span>  
  
-   <span data-ttu-id="cc970-219">事务。</span><span class="sxs-lookup"><span data-stu-id="cc970-219">Transaction.</span></span>  
  
-   <span data-ttu-id="cc970-220">安全性：[!INCLUDE[infocard](../../../includes/infocard-md.md)]、证书和用户名/密码。</span><span class="sxs-lookup"><span data-stu-id="cc970-220">Security: [!INCLUDE[infocard](../../../includes/infocard-md.md)] , Certificate, and Username/Password.</span></span>  
  
-   <span data-ttu-id="cc970-221">绑定：WSFederationbinding、 任何上下文绑定和 Https 绑定、 WebHttpbinding （Json 响应消息支持）。</span><span class="sxs-lookup"><span data-stu-id="cc970-221">Bindings: WSFederationbinding, any Context bindings and Https binding, WebHttpbinding (Json response message support).</span></span>  
  
## <a name="closing-wcf-test-client"></a><span data-ttu-id="cc970-222">关闭 WCF 测试客户端</span><span class="sxs-lookup"><span data-stu-id="cc970-222">Closing WCF Test Client</span></span>  
 <span data-ttu-id="cc970-223">你可以按以下方式关闭 WCF 测试客户端：</span><span class="sxs-lookup"><span data-stu-id="cc970-223">You can close WCF Test Client in the following ways:</span></span>  
  
-   <span data-ttu-id="cc970-224">上**文件**菜单上，单击**退出**。</span><span class="sxs-lookup"><span data-stu-id="cc970-224">On the **File** menu, click **Exit**.</span></span> <span data-ttu-id="cc970-225">或者，在 WCF 测试客户端主窗口中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="cc970-225">Alternatively, in the WCF Test Client main window, click **Close**.</span></span> <span data-ttu-id="cc970-226">同时这些操作还关闭 WCF 服务自动主机并停止 Visual Studio 调试过程，如果通过 Visual Studio 启动 WCF 测试客户端。</span><span class="sxs-lookup"><span data-stu-id="cc970-226">Both of these actions also shut down WCF Service Auto Host and stop the Visual Studio debugging process if WCF Test Client was launched by Visual Studio.</span></span>  
  
-   <span data-ttu-id="cc970-227">右键单击**WCF 服务主机**在通知区域中，然后单击图标**退出。**</span><span class="sxs-lookup"><span data-stu-id="cc970-227">Right-click the **WCF Service Host** icon in the notification area, and then click **Exit.**</span></span> <span data-ttu-id="cc970-228">这会关闭 WCF 服务自动主机和 WCF 测试客户端并停止 Visual Studio 调试过程。</span><span class="sxs-lookup"><span data-stu-id="cc970-228">This shuts down both WCF Service Auto Host and WCF Test Client and stops the Visual Studio debugging process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc970-229">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc970-229">See also</span></span>
- [<span data-ttu-id="cc970-230">WCF 服务主机 (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="cc970-230">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
