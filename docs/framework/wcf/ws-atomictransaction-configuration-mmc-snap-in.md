---
title: WS-AtomicTransaction 配置 MMC 管理单元
ms.date: 03/30/2017
ms.assetid: 23592973-1d51-44cc-b887-bf8b0d801e9e
ms.openlocfilehash: 9b6c7ecf112309b6c10414bfe506559e153911c2
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900729"
---
# <a name="ws-atomictransaction-configuration-mmc-snap-in"></a><span data-ttu-id="69e82-102">Ws-atomictransaction 配置 MMC 管理单元</span><span class="sxs-lookup"><span data-stu-id="69e82-102">WS-AtomicTransaction Configuration MMC snap-in</span></span>

<span data-ttu-id="69e82-103">WS-ATOMICTRANSACTION 配置 MMC 管理单元用于配置本地计算机和远程计算机上的 WS-ATOMICTRANSACTION 设置部分。</span><span class="sxs-lookup"><span data-stu-id="69e82-103">The WS-AtomicTransaction Configuration MMC snap-in is used to configure a portion of the WS-AtomicTransaction settings on both local and remote machines.</span></span>

## <a name="remarks"></a><span data-ttu-id="69e82-104">备注</span><span class="sxs-lookup"><span data-stu-id="69e82-104">Remarks</span></span>

<span data-ttu-id="69e82-105">如果运行 [!INCLUDE[wxp](../../../includes/wxp-md.md)] 或 Windows Server 2003，则可以通过导航到 **"控制面板"/"管理工具"/"组件服务**"，右键单击 "**我的电脑**"，然后选择 "**属性**" 来找到 MMC 管理单元。</span><span class="sxs-lookup"><span data-stu-id="69e82-105">If you are running [!INCLUDE[wxp](../../../includes/wxp-md.md)] or Windows Server 2003, the MMC snap-in can be found by navigating to **Control Panel/Administrative Tools/Component Services/**, right-clicking **My Computer**, and selecting **Properties**.</span></span> <span data-ttu-id="69e82-106">这与可在其中配置 MSDTC 的位置相同。</span><span class="sxs-lookup"><span data-stu-id="69e82-106">This is the same location where you can configure the MSDTC.</span></span> <span data-ttu-id="69e82-107">可用于配置的选项分组在 " **ws-at** " 选项卡下。</span><span class="sxs-lookup"><span data-stu-id="69e82-107">Options available for configuration are grouped under the **WS-AT** tab.</span></span>

 <span data-ttu-id="69e82-108">如果运行的是 Windows Vista 或 Windows Server 2008，则可以通过单击 "**开始**" 按钮，并在 "**搜索**" 框中键入 `dcomcnfg.exe` 来找到 MMC 管理单元。</span><span class="sxs-lookup"><span data-stu-id="69e82-108">If you are running Windows Vista or Windows Server 2008, MMC snap-in can be found by clicking the **Start** button, and typing in `dcomcnfg.exe` in the **Search** box.</span></span> <span data-ttu-id="69e82-109">打开 MMC 时，导航到 "我的**Computer\Distributed Transaction 处理协调器 DTC** " 节点，右键单击并选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="69e82-109">When the MMC is opened, navigate to the **My Computer\Distributed Transaction Coordinator\Local DTC** node, right click and select **Properties**.</span></span> <span data-ttu-id="69e82-110">可用于配置的选项分组在 " **ws-at** " 选项卡下。</span><span class="sxs-lookup"><span data-stu-id="69e82-110">Options available for configuration are grouped under the **WS-AT** tab.</span></span>

 <span data-ttu-id="69e82-111">使用前面的步骤来启动用于配置本地计算机的管理单元。</span><span class="sxs-lookup"><span data-stu-id="69e82-111">The previous steps are used to launch the snap-in for configuring a local machine.</span></span> <span data-ttu-id="69e82-112">如果要配置远程计算机，则应在 **"控制面板"/"管理工具"/"组件服务/** " 中找到远程计算机的名称，然后在运行 [!INCLUDE[wxp](../../../includes/wxp-md.md)] 或 Windows Server 2003 时执行类似的步骤。</span><span class="sxs-lookup"><span data-stu-id="69e82-112">If you want to configure a remote machine, you should locate the remote machine's name in **Control Panel/Administrative Tools/Component Services/**, and perform similar steps if you are running [!INCLUDE[wxp](../../../includes/wxp-md.md)] or Windows Server 2003.</span></span> <span data-ttu-id="69e82-113">如果你运行的是 Windows Vista 或 Windows Server 2008，请针对 Vista 和 Windows Server 2008 执行前面的步骤，但使用远程计算机的节点下的**Distributed Transaction 处理协调器 DTC**节点。</span><span class="sxs-lookup"><span data-stu-id="69e82-113">If you are running Windows Vista or Windows Server 2008, follow the previous steps for Vista and Windows Server 2008, but use the **Distributed Transaction Coordinator\Local DTC** node under the remote computer's node.</span></span>

 <span data-ttu-id="69e82-114">若要使用工具提供的用户界面，您必须注册 WsatUI.dll 文件，该文件位于以下路径中：</span><span class="sxs-lookup"><span data-stu-id="69e82-114">To use the user interface provided by the tool, you have to register the WsatUI.dll file, which is located at the following path,</span></span>

 <span data-ttu-id="69e82-115">**%PROGRAMFILES%\Microsoft SDKs\Windows\v6.0\Bin\WsatUI.dll**</span><span class="sxs-lookup"><span data-stu-id="69e82-115">**%PROGRAMFILES%\Microsoft SDKs\Windows\v6.0\Bin\WsatUI.dll**</span></span>

 <span data-ttu-id="69e82-116">可通过以下命令完成注册。</span><span class="sxs-lookup"><span data-stu-id="69e82-116">The registration can be done by the following command.</span></span>

```console
regasm.exe /codebase WsatUI.dll
```

 <span data-ttu-id="69e82-117">您可以使用此工具来修改基本 WS-AtomicTransaction 设置。</span><span class="sxs-lookup"><span data-stu-id="69e82-117">You can use this tool to modify the basic WS-AtomicTransaction settings.</span></span> <span data-ttu-id="69e82-118">例如，您可以启用和禁用 WS-AtomicTransaction 协议支持、为 WS-AT 配置 HTTP 端口、将 SSL 证书绑定到 HTTP 端口、通过指定证书主题名称来配置证书、选择跟踪模式以及设置默认和最大超时。</span><span class="sxs-lookup"><span data-stu-id="69e82-118">For example, you can enable and disable the WS-AtomicTransaction protocol support, configure the HTTP ports for WS-AT, bind an SSL Certificate to the HTTP port, configure certificates by specifying certificate subject names, select the Tracing mode and set default and maximum timeouts.</span></span>

 <span data-ttu-id="69e82-119">如果只能在本地计算机上配置 WS-ATOMICTRANSACTION 支持，则可以使用此工具的命令行版本。</span><span class="sxs-lookup"><span data-stu-id="69e82-119">If you must configure WS-AtomicTransaction support on the local machine only, you can use the command-line version of this tool.</span></span> <span data-ttu-id="69e82-120">有关命令行工具的详细信息，请参阅[Ws-atomictransaction 配置实用工具（wsatconfig.exe）](ws-atomictransaction-configuration-utility-wsatconfig-exe.md)主题。</span><span class="sxs-lookup"><span data-stu-id="69e82-120">For more information about the command-line tool, see the [WS-AtomicTransaction Configuration Utility (wsatConfig.exe)](ws-atomictransaction-configuration-utility-wsatconfig-exe.md) topic.</span></span>

 <span data-ttu-id="69e82-121">应该注意，MMC 管理单元和命令行工具都不支持配置所有 WS-AT 设置。</span><span class="sxs-lookup"><span data-stu-id="69e82-121">You should be aware that both the MMC Snap-in and the command-line tool do not support configuring all WS-AT settings.</span></span> <span data-ttu-id="69e82-122">只能通过直接修改注册表来编辑这些设置。</span><span class="sxs-lookup"><span data-stu-id="69e82-122">These settings can be edited only by modifying the registry directly.</span></span> <span data-ttu-id="69e82-123">有关这些注册表设置的详细信息，请参阅[配置 WS 原子事务支持](./feature-details/configuring-ws-atomic-transaction-support.md)。</span><span class="sxs-lookup"><span data-stu-id="69e82-123">For more information about these registry settings, see [Configuring WS-Atomic Transaction Support](./feature-details/configuring-ws-atomic-transaction-support.md).</span></span>

### <a name="user-interface-description"></a><span data-ttu-id="69e82-124">用户界面说明</span><span class="sxs-lookup"><span data-stu-id="69e82-124">User Interface Description</span></span>

<span data-ttu-id="69e82-125">**启用 WS 原子事务网络支持**：</span><span class="sxs-lookup"><span data-stu-id="69e82-125">**Enable WS-Atomic Transaction Network Support**:</span></span>

 <span data-ttu-id="69e82-126">切换选择此复选框将启用或禁用此管理单元的所有 GUI 组件。</span><span class="sxs-lookup"><span data-stu-id="69e82-126">Toggling this checkbox enables or disables all the GUI components of this snap-in.</span></span>

 <span data-ttu-id="69e82-127">在选中此框之前，应确保为入站和/或出站通信启用了“网络 DTC 访问”。</span><span class="sxs-lookup"><span data-stu-id="69e82-127">Before you check this box, you should make sure that Network DTC Access is enabled with inbound or outbound communication, or both.</span></span> <span data-ttu-id="69e82-128">可以在 MSDTC 管理单元的 "**安全性**" 选项卡中验证此值。</span><span class="sxs-lookup"><span data-stu-id="69e82-128">This value can be verified in the **Security** Tab of the MSDTC snap-in.</span></span>

#### <a name="network-group-box"></a><span data-ttu-id="69e82-129">“网络”分组框</span><span class="sxs-lookup"><span data-stu-id="69e82-129">Network Group Box</span></span>

<span data-ttu-id="69e82-130">您可以在“网络”组中指定 HTTPS 端口和其他安全设置（比如 SSL 加密）。</span><span class="sxs-lookup"><span data-stu-id="69e82-130">You can specify the HTTPS port and additional security settings such as SSL encryption in the Network group.</span></span> <span data-ttu-id="69e82-131">如果未启用 DTC 网络事务处理，则此组处于禁用状态（显示为灰色）。</span><span class="sxs-lookup"><span data-stu-id="69e82-131">This group is disabled (grayed out) if DTC Network Transactions are not enabled.</span></span>

 <span data-ttu-id="69e82-132">**HTTPS 端口**</span><span class="sxs-lookup"><span data-stu-id="69e82-132">**HTTPS Port**</span></span>

 <span data-ttu-id="69e82-133">这是用于 WS-AT 的 HTTPS 端口的值。</span><span class="sxs-lookup"><span data-stu-id="69e82-133">This is the value of the HTTPS port used for WS-AT.</span></span> <span data-ttu-id="69e82-134">该值必须是 1-65535 范围内的数字（以便表示有效的端口）。</span><span class="sxs-lookup"><span data-stu-id="69e82-134">The value must be a number in the range 1-65535 (as to represent a valid port).</span></span> <span data-ttu-id="69e82-135">如果更改 HTTP 端口，将会修改 HTTP 服务配置，这意味着将会释放以前使用的 WS-AT 服务地址，并基于新端口注册一个新的 WS-AT 服务地址。</span><span class="sxs-lookup"><span data-stu-id="69e82-135">Changing the HTTP Port modifies the HTTP Service Configuration, which means that the previously used WS-AT Service Address is released, and a new WS-AT Service Address is registered based on the new port.</span></span> <span data-ttu-id="69e82-136">此外，将使用当前为 SSL 加密选择的证书对新选择的端口进行加密。</span><span class="sxs-lookup"><span data-stu-id="69e82-136">In addition, the newly selected port is encrypted with the currently selected certificate for SSL Encryption.</span></span>

> [!NOTE]
> <span data-ttu-id="69e82-137">如果在运行此工具之前已启用了防火墙，则会在例外列表中自动注册该端口。</span><span class="sxs-lookup"><span data-stu-id="69e82-137">If you have already enabled the firewall before running this tool, the port is automatically registered in the exception list.</span></span> <span data-ttu-id="69e82-138">如果在运行此工具之前防火墙处于禁用状态，将不会对防火墙进行任何其他配置。</span><span class="sxs-lookup"><span data-stu-id="69e82-138">If the firewall is disabled before running this tool, nothing additional is configured regarding the firewall.</span></span>

 <span data-ttu-id="69e82-139">如果在配置 WS-AT 之后启用防火墙，您必须再次运行此工具并使用此参数提供端口号。</span><span class="sxs-lookup"><span data-stu-id="69e82-139">If you enable the firewall after configuring WS-AT, you must run this tool again and supply the port number using this parameter.</span></span> <span data-ttu-id="69e82-140">如果在配置之后禁用防火墙，WS-AT 将继续工作，而无需附加输入。</span><span class="sxs-lookup"><span data-stu-id="69e82-140">If you disable the firewall after configuring, WS-AT continues to work without additional input.</span></span>

 <span data-ttu-id="69e82-141">**终结点证书**</span><span class="sxs-lookup"><span data-stu-id="69e82-141">**Endpoint Certificate**</span></span>

 <span data-ttu-id="69e82-142">单击 "**选择**" 按钮将显示本地计算机上当前可用证书的列表，使用户可以选择可用于 SSL 加密的证书。</span><span class="sxs-lookup"><span data-stu-id="69e82-142">Clicking the **Select** button displays a list with the currently available certificates on the Local Machine, allowing the user to select the certificate that can be used for SSL encryption.</span></span> <span data-ttu-id="69e82-143">证书必须具有私钥。</span><span class="sxs-lookup"><span data-stu-id="69e82-143">The certificates must have a private key.</span></span> <span data-ttu-id="69e82-144">否则会收到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="69e82-144">Otherwise, you receive an error message.</span></span>

> [!NOTE]
> <span data-ttu-id="69e82-145">为选定端口设置 SSL 证书时，将覆盖与该端口关联的原始 SSL 证书（如果有）。</span><span class="sxs-lookup"><span data-stu-id="69e82-145">When you set an SSL certificate for a selected port, you overwrite the original SSL certificate associated with that port if one exists.</span></span>

 <span data-ttu-id="69e82-146">**授权帐户**</span><span class="sxs-lookup"><span data-stu-id="69e82-146">**Authorized Accounts**</span></span>

 <span data-ttu-id="69e82-147">单击 "**选择**" 按钮调用 Windows 访问控制列表编辑器，您可以在其中通过选中 "**参与**" 权限组中的 "**允许**" 或 "**拒绝**" 框，指定可参与 WS 原子事务的用户或组。</span><span class="sxs-lookup"><span data-stu-id="69e82-147">Clicking the **Select** button invokes the Windows Access Control List editor, where you can specify the user or group that can participate in WS-Atomic transactions by checking the **Allow** or **Deny** box in the **Participate** permission group.</span></span>

 <span data-ttu-id="69e82-148">**授权的证书**</span><span class="sxs-lookup"><span data-stu-id="69e82-148">**Authorized Certificates**</span></span>

 <span data-ttu-id="69e82-149">单击 "**选择**" 按钮将显示 LocalMachine 上当前可用证书的列表。</span><span class="sxs-lookup"><span data-stu-id="69e82-149">Clicking the **Select** button displays a list of currently available certificates on the LocalMachine.</span></span> <span data-ttu-id="69e82-150">然后，你可以选择允许哪些证书标识参与 WS-Atomic 事务处理。</span><span class="sxs-lookup"><span data-stu-id="69e82-150">You can then select which certificate identities are allowed to participate in WS-Atomic transactions.</span></span>

#### <a name="timeout-group-box"></a><span data-ttu-id="69e82-151">“超时”分组框</span><span class="sxs-lookup"><span data-stu-id="69e82-151">Timeout Group Box</span></span>

<span data-ttu-id="69e82-152">使用 "**超时**组" 框可以指定 WS 原子事务的默认和最大超时值。</span><span class="sxs-lookup"><span data-stu-id="69e82-152">The **Timeout** group box allows you to specify the default and maximum timeout for a WS-Atomic transaction.</span></span> <span data-ttu-id="69e82-153">传出超时的有效值介于 1 和 3600 之间。</span><span class="sxs-lookup"><span data-stu-id="69e82-153">A valid value for outgoing timeout is between 1 and 3600.</span></span> <span data-ttu-id="69e82-154">传入超时的有效值介于 0 和 3600 之间。</span><span class="sxs-lookup"><span data-stu-id="69e82-154">A valid value for incoming timeout is between 0 and 3600.</span></span>

#### <a name="tracing-and-logging-group-box"></a><span data-ttu-id="69e82-155">“跟踪和日志记录”分组框</span><span class="sxs-lookup"><span data-stu-id="69e82-155">Tracing and Logging Group Box</span></span>

<span data-ttu-id="69e82-156">"**跟踪和日志记录**组" 框可用于配置所需的跟踪和日志记录级别。</span><span class="sxs-lookup"><span data-stu-id="69e82-156">The **Tracing and Logging** group box allows you to configure the desired tracing and logging level.</span></span>

 <span data-ttu-id="69e82-157">单击 "**选项**" 按钮将调用一个页面，您可以在其中指定其他设置。</span><span class="sxs-lookup"><span data-stu-id="69e82-157">Clicking the **Options** button invokes a page where you can specify additional settings.</span></span>

 <span data-ttu-id="69e82-158">"**跟踪级别**" 组合框允许您从 <xref:System.Diagnostics.TraceLevel> 枚举的任何有效值中进行选择。</span><span class="sxs-lookup"><span data-stu-id="69e82-158">The **Trace Level** combination box allows you to choose from any valid value of the <xref:System.Diagnostics.TraceLevel> enumeration.</span></span> <span data-ttu-id="69e82-159">您也可以使用这些复选框来指定是否要执行活动跟踪、活动传播或收集个人身份信息。</span><span class="sxs-lookup"><span data-stu-id="69e82-159">You can also use the checkboxes to specify if you want to perform activity tracing, activity propagation or collect personal identifiable information.</span></span>

 <span data-ttu-id="69e82-160">你还可以在 "**日志记录会话**" 组框中指定日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="69e82-160">You can also specify logging sessions in the **Logging Session** group box.</span></span>

> [!NOTE]
> <span data-ttu-id="69e82-161">如果另一个跟踪使用者正在使用 WS-AT 跟踪提供程序，则您无法为跟踪事件创建新的日志记录会话。</span><span class="sxs-lookup"><span data-stu-id="69e82-161">When another trace consumer is using the WS-AT trace provider, you cannot create a new logging session for trace events.</span></span> <span data-ttu-id="69e82-162">任何试图在此时配置日志记录的操作都会导致错误消息“无法启用提供程序。</span><span class="sxs-lookup"><span data-stu-id="69e82-162">Any attempt to configure logging during this time results in the error message "Failed to enable provider.</span></span> <span data-ttu-id="69e82-163">错误代码: 1”。</span><span class="sxs-lookup"><span data-stu-id="69e82-163">Error code: 1".</span></span>

 <span data-ttu-id="69e82-164">有关跟踪和日志记录的详细信息，请参阅[管理和诊断](./diagnostics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="69e82-164">For more information about tracing and logging, see [Administration and Diagnostics](./diagnostics/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="69e82-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69e82-165">See also</span></span>

- [<span data-ttu-id="69e82-166">配置 WS-Atomic 事务支持</span><span class="sxs-lookup"><span data-stu-id="69e82-166">Configuring WS-Atomic Transaction Support</span></span>](./feature-details/configuring-ws-atomic-transaction-support.md)
- [<span data-ttu-id="69e82-167">WS-AtomicTransaction 配置实用工具 (wsatConfig.exe)</span><span class="sxs-lookup"><span data-stu-id="69e82-167">WS-AtomicTransaction Configuration Utility (wsatConfig.exe)</span></span>](ws-atomictransaction-configuration-utility-wsatconfig-exe.md)
- [<span data-ttu-id="69e82-168">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="69e82-168">Administration and Diagnostics</span></span>](./diagnostics/index.md)
