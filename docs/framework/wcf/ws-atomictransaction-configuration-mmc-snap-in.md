---
title: WS-AtomicTransaction 配置 MMC 管理单元
ms.date: 03/30/2017
ms.assetid: 23592973-1d51-44cc-b887-bf8b0d801e9e
ms.openlocfilehash: 1fa0548e2d63562ddcb85fc6392bf5c99d67d6c7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916808"
---
# <a name="ws-atomictransaction-configuration-mmc-snap-in"></a><span data-ttu-id="21d1e-102">WS-AtomicTransaction 配置 MMC 管理单元</span><span class="sxs-lookup"><span data-stu-id="21d1e-102">WS-AtomicTransaction Configuration MMC Snap-in</span></span>
<span data-ttu-id="21d1e-103">WS-AtomicTransaction 配置 MMC 管理单元用于在本地计算机和远程计算机上配置一部分 WS-AtomicTransaction 设置。</span><span class="sxs-lookup"><span data-stu-id="21d1e-103">The WS-AtomicTransaction Configuration MMC Snap-in is used to configure a portion of the WS-AtomicTransaction settings on both local and remote machines.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21d1e-104">备注</span><span class="sxs-lookup"><span data-stu-id="21d1e-104">Remarks</span></span>  
 <span data-ttu-id="21d1e-105">如果你[!INCLUDE[wxp](../../../includes/wxp-md.md)]运行的是[!INCLUDE[ws2003](../../../includes/ws2003-md.md)]或, 则可以通过导航到 **"控制面板"/"管理工具"/"组件服务**", 右键单击**我的电脑**, 然后选择 "**属性**" 来找到 MMC 管理单元。</span><span class="sxs-lookup"><span data-stu-id="21d1e-105">If you are running [!INCLUDE[wxp](../../../includes/wxp-md.md)] or [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], the MMC snap-in can be found by navigating to **Control Panel/Administrative Tools/Component Services/**, right-clicking **My Computer**, and selecting **Properties**.</span></span> <span data-ttu-id="21d1e-106">这与可在其中配置 MSDTC 的位置相同。</span><span class="sxs-lookup"><span data-stu-id="21d1e-106">This is the same location where you can configure the MSDTC.</span></span> <span data-ttu-id="21d1e-107">可用于配置的选项分组在 " **ws-at** " 选项卡下。</span><span class="sxs-lookup"><span data-stu-id="21d1e-107">Options available for configuration are grouped under the **WS-AT** tab.</span></span>  
  
 <span data-ttu-id="21d1e-108">如果你运行的是 Windows Vista [!INCLUDE[lserver](../../../includes/lserver-md.md)]或, 则可以通过单击 "**开始**" 按钮`dcomcnfg.exe` , 然后在**搜索**框中键入来找到 MMC 管理单元。</span><span class="sxs-lookup"><span data-stu-id="21d1e-108">If you are running Windows Vista or [!INCLUDE[lserver](../../../includes/lserver-md.md)], MMC snap-in can be found by clicking the **Start** button, and typing in `dcomcnfg.exe` in the **Search** box.</span></span> <span data-ttu-id="21d1e-109">打开 MMC 时, 导航到 "我的**Computer\Distributed Transaction 处理协调器 DTC** " 节点, 右键单击并选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="21d1e-109">When the MMC is opened, navigate to the **My Computer\Distributed Transaction Coordinator\Local DTC** node, right click and select **Properties**.</span></span> <span data-ttu-id="21d1e-110">可用于配置的选项分组在 " **ws-at** " 选项卡下。</span><span class="sxs-lookup"><span data-stu-id="21d1e-110">Options available for configuration are grouped under the **WS-AT** tab.</span></span>  
  
 <span data-ttu-id="21d1e-111">使用前面的步骤来启动用于配置本地计算机的管理单元。</span><span class="sxs-lookup"><span data-stu-id="21d1e-111">The previous steps are used to launch the snap-in for configuring a local machine.</span></span> <span data-ttu-id="21d1e-112">如果要配置远程计算机, 则应在 **"控制面板"/"管理工具"/"组件服务/** " 中找到远程计算机的名称, 并在运行[!INCLUDE[wxp](../../../includes/wxp-md.md)]或[!INCLUDE[ws2003](../../../includes/ws2003-md.md)]的情况下执行类似的步骤。</span><span class="sxs-lookup"><span data-stu-id="21d1e-112">If you want to configure a remote machine, you should locate the remote machine's name in **Control Panel/Administrative Tools/Component Services/**, and perform similar steps if you are running [!INCLUDE[wxp](../../../includes/wxp-md.md)] or [!INCLUDE[ws2003](../../../includes/ws2003-md.md)].</span></span> <span data-ttu-id="21d1e-113">如果你运行的是 Windows vista [!INCLUDE[lserver](../../../includes/lserver-md.md)]或, 请对 Vista 和[!INCLUDE[lserver](../../../includes/lserver-md.md)]执行前面的步骤, 但使用远程计算机的节点下的**Distributed Transaction 处理协调器 DTC**节点。</span><span class="sxs-lookup"><span data-stu-id="21d1e-113">If you are running Windows Vista or [!INCLUDE[lserver](../../../includes/lserver-md.md)], follow the previous steps for Vista and [!INCLUDE[lserver](../../../includes/lserver-md.md)], but use the **Distributed Transaction Coordinator\Local DTC** node under the remote computer's node.</span></span>  
  
 <span data-ttu-id="21d1e-114">若要使用工具提供的用户界面，您必须注册 WsatUI.dll 文件，该文件位于以下路径中：</span><span class="sxs-lookup"><span data-stu-id="21d1e-114">To use the user interface provided by the tool, you have to register the WsatUI.dll file, which is located at the following path,</span></span>  
  
 <span data-ttu-id="21d1e-115">**%PROGRAMFILES%\Microsoft SDKs\Windows\v6.0\Bin\WsatUI.dll**</span><span class="sxs-lookup"><span data-stu-id="21d1e-115">**%PROGRAMFILES%\Microsoft SDKs\Windows\v6.0\Bin\WsatUI.dll**</span></span>  
  
 <span data-ttu-id="21d1e-116">可通过以下命令完成注册。</span><span class="sxs-lookup"><span data-stu-id="21d1e-116">The registration can be done by the following command.</span></span>  
  
```Output  
regasm.exe /codebase WsatUI.dll  
```  
  
 <span data-ttu-id="21d1e-117">您可以使用此工具来修改基本 WS-AtomicTransaction 设置。</span><span class="sxs-lookup"><span data-stu-id="21d1e-117">You can use this tool to modify the basic WS-AtomicTransaction settings.</span></span> <span data-ttu-id="21d1e-118">例如，您可以启用和禁用 WS-AtomicTransaction 协议支持、为 WS-AT 配置 HTTP 端口、将 SSL 证书绑定到 HTTP 端口、通过指定证书主题名称来配置证书、选择跟踪模式以及设置默认和最大超时。</span><span class="sxs-lookup"><span data-stu-id="21d1e-118">For example, you can enable and disable the WS-AtomicTransaction protocol support, configure the HTTP ports for WS-AT, bind an SSL Certificate to the HTTP port, configure certificates by specifying certificate subject names, select the Tracing mode and set default and maximum timeouts.</span></span>  
  
 <span data-ttu-id="21d1e-119">如果只必须在本地计算机上配置 WS-AtomicTransaction 支持，您可以使用此工具的命令行版本。</span><span class="sxs-lookup"><span data-stu-id="21d1e-119">If you must configure WS-AtomicTransaction support on the local machine only, you can use the command line version of this tool.</span></span> <span data-ttu-id="21d1e-120">有关命令行工具的详细信息, 请参阅[Ws-atomictransaction 配置实用工具 (wsatconfig.exe)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)主题。</span><span class="sxs-lookup"><span data-stu-id="21d1e-120">For more information about the command line tool, see the [WS-AtomicTransaction Configuration Utility (wsatConfig.exe)](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md) topic.</span></span>  
  
 <span data-ttu-id="21d1e-121">应该注意，MMC 管理单元和命令行工具都不支持配置所有 WS-AT 设置。</span><span class="sxs-lookup"><span data-stu-id="21d1e-121">You should be aware that both the MMC Snap-in and the command-line tool do not support configuring all WS-AT settings.</span></span> <span data-ttu-id="21d1e-122">只能通过直接修改注册表来编辑这些设置。</span><span class="sxs-lookup"><span data-stu-id="21d1e-122">These settings can be edited only by modifying the registry directly.</span></span> <span data-ttu-id="21d1e-123">有关这些注册表设置的详细信息, 请参阅[配置 WS 原子事务支持](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)。</span><span class="sxs-lookup"><span data-stu-id="21d1e-123">For more information about these registry settings, see [Configuring WS-Atomic Transaction Support](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md).</span></span>  
  
### <a name="user-interface-description"></a><span data-ttu-id="21d1e-124">用户界面说明</span><span class="sxs-lookup"><span data-stu-id="21d1e-124">User Interface Description</span></span>  
 <span data-ttu-id="21d1e-125">**启用 WS 原子事务网络支持**:</span><span class="sxs-lookup"><span data-stu-id="21d1e-125">**Enable WS-Atomic Transaction Network Support**:</span></span>  
  
 <span data-ttu-id="21d1e-126">切换选择此复选框将启用或禁用此管理单元的所有 GUI 组件。</span><span class="sxs-lookup"><span data-stu-id="21d1e-126">Toggling this checkbox enables or disables all the GUI components of this snap-in.</span></span>  
  
 <span data-ttu-id="21d1e-127">在选中此框之前，应确保为入站和/或出站通信启用了“网络 DTC 访问”。</span><span class="sxs-lookup"><span data-stu-id="21d1e-127">Before you check this box, you should make sure that Network DTC Access is enabled with inbound or outbound communication, or both.</span></span> <span data-ttu-id="21d1e-128">可以在 MSDTC 管理单元的 "**安全性**" 选项卡中验证此值。</span><span class="sxs-lookup"><span data-stu-id="21d1e-128">This value can be verified in the **Security** Tab of the MSDTC snap-in.</span></span>  
  
#### <a name="network-group-box"></a><span data-ttu-id="21d1e-129">“网络”分组框</span><span class="sxs-lookup"><span data-stu-id="21d1e-129">Network Group Box</span></span>  
 <span data-ttu-id="21d1e-130">您可以在“网络”组中指定 HTTPS 端口和其他安全设置（比如 SSL 加密）。</span><span class="sxs-lookup"><span data-stu-id="21d1e-130">You can specify the HTTPS port and additional security settings such as SSL encryption in the Network group.</span></span> <span data-ttu-id="21d1e-131">如果未启用 DTC 网络事务处理，则此组处于禁用状态（显示为灰色）。</span><span class="sxs-lookup"><span data-stu-id="21d1e-131">This group is disabled (grayed out) if DTC Network Transactions are not enabled.</span></span>  
  
 <span data-ttu-id="21d1e-132">**HTTPS 端口**</span><span class="sxs-lookup"><span data-stu-id="21d1e-132">**HTTPS Port**</span></span>  
  
 <span data-ttu-id="21d1e-133">这是用于 WS-AT 的 HTTPS 端口的值。</span><span class="sxs-lookup"><span data-stu-id="21d1e-133">This is the value of the HTTPS port used for WS-AT.</span></span> <span data-ttu-id="21d1e-134">该值必须是 1-65535 范围内的数字（以便表示有效的端口）。</span><span class="sxs-lookup"><span data-stu-id="21d1e-134">The value must be a number in the range 1-65535 (as to represent a valid port).</span></span> <span data-ttu-id="21d1e-135">如果更改 HTTP 端口，将会修改 HTTP 服务配置，这意味着将会释放以前使用的 WS-AT 服务地址，并基于新端口注册一个新的 WS-AT 服务地址。</span><span class="sxs-lookup"><span data-stu-id="21d1e-135">Changing the HTTP Port modifies the HTTP Service Configuration, which means that the previously used WS-AT Service Address is released, and a new WS-AT Service Address is registered based on the new port.</span></span> <span data-ttu-id="21d1e-136">此外，将使用当前为 SSL 加密选择的证书对新选择的端口进行加密。</span><span class="sxs-lookup"><span data-stu-id="21d1e-136">In addition, the newly selected port is encrypted with the currently selected certificate for SSL Encryption.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21d1e-137">如果在运行此工具之前已启用了防火墙，则会在例外列表中自动注册该端口。</span><span class="sxs-lookup"><span data-stu-id="21d1e-137">If you have already enabled the firewall before running this tool, the port is automatically registered in the exception list.</span></span> <span data-ttu-id="21d1e-138">如果在运行此工具之前防火墙处于禁用状态，将不会对防火墙进行任何其他配置。</span><span class="sxs-lookup"><span data-stu-id="21d1e-138">If the firewall is disabled before running this tool, nothing additional is configured regarding the firewall.</span></span>  
  
 <span data-ttu-id="21d1e-139">如果在配置 WS-AT 之后启用防火墙，您必须再次运行此工具并使用此参数提供端口号。</span><span class="sxs-lookup"><span data-stu-id="21d1e-139">If you enable the firewall after configuring WS-AT, you must run this tool again and supply the port number using this parameter.</span></span> <span data-ttu-id="21d1e-140">如果在配置之后禁用防火墙，WS-AT 将继续工作，而无需附加输入。</span><span class="sxs-lookup"><span data-stu-id="21d1e-140">If you disable the firewall after configuring, WS-AT continues to work without additional input.</span></span>  
  
 <span data-ttu-id="21d1e-141">**终结点证书**</span><span class="sxs-lookup"><span data-stu-id="21d1e-141">**Endpoint Certificate**</span></span>  
  
 <span data-ttu-id="21d1e-142">单击 "**选择**" 按钮将显示本地计算机上当前可用证书的列表, 使用户可以选择可用于 SSL 加密的证书。</span><span class="sxs-lookup"><span data-stu-id="21d1e-142">Clicking the **Select** button displays a list with the currently available certificates on the Local Machine, allowing the user to select the certificate that can be used for SSL encryption.</span></span> <span data-ttu-id="21d1e-143">证书必须具有私钥。</span><span class="sxs-lookup"><span data-stu-id="21d1e-143">The certificates must have a private key.</span></span> <span data-ttu-id="21d1e-144">否则会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="21d1e-144">Otherwise, you receive an error message.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21d1e-145">为选定端口设置 SSL 证书时，将覆盖与该端口关联的原始 SSL 证书（如果有）。</span><span class="sxs-lookup"><span data-stu-id="21d1e-145">When you set an SSL certificate for a selected port, you overwrite the original SSL certificate associated with that port if one exists.</span></span>  
  
 <span data-ttu-id="21d1e-146">**授权帐户**</span><span class="sxs-lookup"><span data-stu-id="21d1e-146">**Authorized Accounts**</span></span>  
  
 <span data-ttu-id="21d1e-147">单击 "**选择**" 按钮调用 Windows 访问控制列表编辑器, 您可以在其中指定可参与 WS 原子事务的用户或组, 方法是选中 " **参与**" 或 "**拒绝**" 框。权限组。</span><span class="sxs-lookup"><span data-stu-id="21d1e-147">Clicking the **Select** button invokes the Windows Access Control List editor, where you can specify the user or group that can participate in WS-Atomic transactions by checking the **Allow** or **Deny** box in the **Participate** permission group.</span></span>  
  
 <span data-ttu-id="21d1e-148">**授权的证书**</span><span class="sxs-lookup"><span data-stu-id="21d1e-148">**Authorized Certificates**</span></span>  
  
 <span data-ttu-id="21d1e-149">单击 "**选择**" 按钮将显示 LocalMachine 上当前可用证书的列表。</span><span class="sxs-lookup"><span data-stu-id="21d1e-149">Clicking the **Select** button displays a list of currently available certificates on the LocalMachine.</span></span> <span data-ttu-id="21d1e-150">然后，你可以选择允许哪些证书标识参与 WS-Atomic 事务处理。</span><span class="sxs-lookup"><span data-stu-id="21d1e-150">You can then select which certificate identities are allowed to participate in WS-Atomic transactions.</span></span>  
  
#### <a name="timeout-group-box"></a><span data-ttu-id="21d1e-151">“超时”分组框</span><span class="sxs-lookup"><span data-stu-id="21d1e-151">Timeout Group Box</span></span>  
 <span data-ttu-id="21d1e-152">使用 "**超时**组" 框可以指定 WS 原子事务的默认和最大超时值。</span><span class="sxs-lookup"><span data-stu-id="21d1e-152">The **Timeout** group box allows you to specify the default and maximum timeout for a WS-Atomic transaction.</span></span> <span data-ttu-id="21d1e-153">传出超时的有效值介于 1 和 3600 之间。</span><span class="sxs-lookup"><span data-stu-id="21d1e-153">A valid value for outgoing timeout is between 1 and 3600.</span></span> <span data-ttu-id="21d1e-154">传入超时的有效值介于 0 和 3600 之间。</span><span class="sxs-lookup"><span data-stu-id="21d1e-154">A valid value for incoming timeout is between 0 and 3600.</span></span>  
  
#### <a name="tracing-and-logging-group-box"></a><span data-ttu-id="21d1e-155">“跟踪和日志记录”分组框</span><span class="sxs-lookup"><span data-stu-id="21d1e-155">Tracing and Logging Group Box</span></span>  
 <span data-ttu-id="21d1e-156">"**跟踪和日志记录**组" 框可用于配置所需的跟踪和日志记录级别。</span><span class="sxs-lookup"><span data-stu-id="21d1e-156">The **Tracing and Logging** group Box allows you to configure the desired tracing and logging level.</span></span>  
  
 <span data-ttu-id="21d1e-157">单击 "**选项**" 按钮将调用一个页面, 您可以在其中指定其他设置。</span><span class="sxs-lookup"><span data-stu-id="21d1e-157">Clicking the **Options** button invokes a page where you can specify additional settings.</span></span>  
  
 <span data-ttu-id="21d1e-158">您可以通过 "**跟踪级别**" 组合框选择任何有效的<xref:System.Diagnostics.TraceLevel>枚举值。</span><span class="sxs-lookup"><span data-stu-id="21d1e-158">The **Trace Level** combination box allows you to choose from any valid value of the <xref:System.Diagnostics.TraceLevel> enumeration.</span></span> <span data-ttu-id="21d1e-159">您也可以使用这些复选框来指定是否要执行活动跟踪、活动传播或收集个人身份信息。</span><span class="sxs-lookup"><span data-stu-id="21d1e-159">You can also use the checkboxes to specify if you want to perform activity tracing, activity propagation or collect personal identifiable information.</span></span>  
  
 <span data-ttu-id="21d1e-160">你还可以在 "**日志记录会话**" 组框中指定日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="21d1e-160">You can also specify logging sessions in the **Logging Session** group box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21d1e-161">如果另一个跟踪使用者正在使用 WS-AT 跟踪提供程序，则您无法为跟踪事件创建新的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="21d1e-161">When another trace consumer is using the WS-AT trace provider, you cannot create a new logging session for trace events.</span></span> <span data-ttu-id="21d1e-162">任何试图在此时配置日志记录的操作都会导致错误消息“无法启用提供程序。</span><span class="sxs-lookup"><span data-stu-id="21d1e-162">Any attempt to configure logging during this time results in the error message "Failed to enable provider.</span></span> <span data-ttu-id="21d1e-163">错误代码:1".</span><span class="sxs-lookup"><span data-stu-id="21d1e-163">Error code: 1".</span></span>  
  
 <span data-ttu-id="21d1e-164">有关跟踪和日志记录的详细信息, 请参阅[管理和诊断](../../../docs/framework/wcf/diagnostics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="21d1e-164">For more information about tracing and logging, see [Administration and Diagnostics](../../../docs/framework/wcf/diagnostics/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21d1e-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="21d1e-165">See also</span></span>

- [<span data-ttu-id="21d1e-166">配置 WS-Atomic 事务支持</span><span class="sxs-lookup"><span data-stu-id="21d1e-166">Configuring WS-Atomic Transaction Support</span></span>](../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
- [<span data-ttu-id="21d1e-167">WS-AtomicTransaction 配置实用工具 (wsatConfig.exe)</span><span class="sxs-lookup"><span data-stu-id="21d1e-167">WS-AtomicTransaction Configuration Utility (wsatConfig.exe)</span></span>](../../../docs/framework/wcf/ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
- [<span data-ttu-id="21d1e-168">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="21d1e-168">Administration and Diagnostics</span></span>](../../../docs/framework/wcf/diagnostics/index.md)
