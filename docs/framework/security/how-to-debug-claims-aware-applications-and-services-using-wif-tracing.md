---
title: 如何：使用 WIF 跟踪调试声明感知应用程序和服务
ms.date: 03/30/2017
ms.assetid: 3d51ba59-3adb-4ca4-bd33-5027531af687
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 69c7e30168686eeb7d530b167b1f87c567c63874
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463190"
---
# <a name="how-to-debug-claims-aware-applications-and-services-using-wif-tracing"></a><span data-ttu-id="7ee32-102">如何：使用 WIF 跟踪调试声明感知应用程序和服务</span><span class="sxs-lookup"><span data-stu-id="7ee32-102">How To: Debug Claims-Aware Applications And Services Using WIF Tracing</span></span>
## <a name="applies-to"></a><span data-ttu-id="7ee32-103">适用于</span><span class="sxs-lookup"><span data-stu-id="7ee32-103">Applies To</span></span>  
  
-   <span data-ttu-id="7ee32-104">Microsoft® Windows® Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="7ee32-104">Microsoft® Windows® Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="7ee32-105">服务跟踪查看器工具 (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="7ee32-105">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>  
  
-   <span data-ttu-id="7ee32-106">对 WIF 应用程序进行故障排除和调试</span><span class="sxs-lookup"><span data-stu-id="7ee32-106">Troubleshooting and Debugging WIF Applications</span></span>  
  
## <a name="summary"></a><span data-ttu-id="7ee32-107">摘要</span><span class="sxs-lookup"><span data-stu-id="7ee32-107">Summary</span></span>  
 <span data-ttu-id="7ee32-108">本操作说明介绍进行后述操作所需的步骤：配置 WIF 跟踪、收集跟踪日志以及使用“跟踪查看器”工具分析跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="7ee32-108">This How-To describes required steps for how to configure WIF tracing, collect trace logs, and how to analyze the trace logs using Trace Viewer tool.</span></span> <span data-ttu-id="7ee32-109">它为排除 WIF 相关问题所需的操作提供跟踪项的常规映射。</span><span class="sxs-lookup"><span data-stu-id="7ee32-109">It provides general mapping for trace entries to actions needed to troubleshoot issues related to WIF.</span></span>  
  
## <a name="contents"></a><span data-ttu-id="7ee32-110">内容</span><span class="sxs-lookup"><span data-stu-id="7ee32-110">Contents</span></span>  
  
-   <span data-ttu-id="7ee32-111">目标</span><span class="sxs-lookup"><span data-stu-id="7ee32-111">Objectives</span></span>  
  
-   <span data-ttu-id="7ee32-112">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="7ee32-112">Summary of Steps</span></span>  
  
-   <span data-ttu-id="7ee32-113">步骤 1 – 使用 Web.config 配置文件配置 WIF 跟踪</span><span class="sxs-lookup"><span data-stu-id="7ee32-113">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
-   <span data-ttu-id="7ee32-114">步骤 2 – 使用跟踪查看器工具分析 WIF 跟踪文件</span><span class="sxs-lookup"><span data-stu-id="7ee32-114">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
-   <span data-ttu-id="7ee32-115">步骤 3 – 确定解决方案以修复 WIF 相关问题</span><span class="sxs-lookup"><span data-stu-id="7ee32-115">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
-   <span data-ttu-id="7ee32-116">相关项</span><span class="sxs-lookup"><span data-stu-id="7ee32-116">Related Items</span></span>  
  
## <a name="objectives"></a><span data-ttu-id="7ee32-117">目标</span><span class="sxs-lookup"><span data-stu-id="7ee32-117">Objectives</span></span>  
  
-   <span data-ttu-id="7ee32-118">配置 WIF 跟踪。</span><span class="sxs-lookup"><span data-stu-id="7ee32-118">Configure WIF tracing.</span></span>  
  
-   <span data-ttu-id="7ee32-119">在跟踪查看器工具中查看跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="7ee32-119">View trace logs in the Trace Viewer tool.</span></span>  
  
-   <span data-ttu-id="7ee32-120">在跟踪日志中标识 WIF 相关问题。</span><span class="sxs-lookup"><span data-stu-id="7ee32-120">Identify WIF related issues in the trace logs.</span></span>  
  
-   <span data-ttu-id="7ee32-121">将纠正措施应用于在跟踪日志中发现的 WIF 相关问题。</span><span class="sxs-lookup"><span data-stu-id="7ee32-121">Apply corrective actions to WIF related issues found in the trace logs.</span></span>  
  
## <a name="summary-of-steps"></a><span data-ttu-id="7ee32-122">步骤摘要</span><span class="sxs-lookup"><span data-stu-id="7ee32-122">Summary of Steps</span></span>  
  
-   <span data-ttu-id="7ee32-123">步骤 1 – 使用 Web.config 配置文件配置 WIF 跟踪</span><span class="sxs-lookup"><span data-stu-id="7ee32-123">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
  
-   <span data-ttu-id="7ee32-124">步骤 2 – 使用跟踪查看器工具分析 WIF 跟踪文件</span><span class="sxs-lookup"><span data-stu-id="7ee32-124">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
  
-   <span data-ttu-id="7ee32-125">步骤 3 – 确定解决方案以修复 WIF 相关问题</span><span class="sxs-lookup"><span data-stu-id="7ee32-125">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
  
## <a name="step-1--configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="7ee32-126">步骤 1 – 使用 Web.config 配置文件配置 WIF 跟踪</span><span class="sxs-lookup"><span data-stu-id="7ee32-126">Step 1 – Configure WIF Tracing Using Web.config Configuration File</span></span>  
 <span data-ttu-id="7ee32-127">在此步骤中，将向 Web.config 文件中的配置节添加更改，该文件使 WIF 能够跟踪其事件并将这些事件存储在跟踪日志中。</span><span class="sxs-lookup"><span data-stu-id="7ee32-127">In this step, you will add changes to configuration sections in the *Web.config* file that enable WIF to trace its events and store them in a trace log.</span></span>  
  
#### <a name="to-configure-wif-tracing-using-webconfig-configuration-file"></a><span data-ttu-id="7ee32-128">使用 Web.config 配置文件配置 WIF 跟踪</span><span class="sxs-lookup"><span data-stu-id="7ee32-128">To configure WIF tracing using Web.config configuration file</span></span>  
  
1.  <span data-ttu-id="7ee32-129">在 Visual Studio 编辑器中打开“Web.config”或“App.config”根配置文件，方法是在解决方案资源管理器中双击文件。</span><span class="sxs-lookup"><span data-stu-id="7ee32-129">Open the root **Web.config** or **App.config** configuration file in the Visual Studio editor by double clicking on it in **Solution Explorer**.</span></span> <span data-ttu-id="7ee32-130">如果解决方案没有“Web.config”或“App.config”配置文件，可在“解决方案资源管理器”中右键单击解决方案，再单击“添加”，然后单击“新建项...”来添加该文件。</span><span class="sxs-lookup"><span data-stu-id="7ee32-130">If your solution does not have **Web.config** or **App.config** configuration file, add it by right clicking on the solution in the **Solution Explorer** and clicking **Add**, then clicking **New Item…**.</span></span> <span data-ttu-id="7ee32-131">在“新建项”对话框上，从列表中为“App.config”选择“应用程序配置文件”，或为“Web.config”选择“Web 配置文件”，然后单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="7ee32-131">On the **New Item** dialog, Select **Application Configuration File** for **App.config** or **Web Configuration File** for **Web.config** from the list and click **OK**.</span></span>  
  
2.  <span data-ttu-id="7ee32-132">在配置文件末尾将与下列条目相似的配置条目添加到“\<configuration>”节点内的配置文件中：</span><span class="sxs-lookup"><span data-stu-id="7ee32-132">Add the configuration entries similar to the following to the configuration file inside **\<configuration>** node at the end of the configuration file:</span></span>  
  
    ```xml  
    <system.diagnostics>  
        <sources>  
            <source name="System.IdentityModel" switchValue="Verbose">  
                <listeners>  
                    <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="WIFTrace.e2e"/>  
                </listeners>  
            </source>  
        </sources>  
        <trace autoflush="true"/>  
    </system.diagnostics>  
    ```  
  
3.  <span data-ttu-id="7ee32-133">以上配置指示 WIF 生成详细的跟踪事件并将其记录到 WIFTrace.e2e 文件中。</span><span class="sxs-lookup"><span data-stu-id="7ee32-133">The above configuration instructs WIF to generate verbose trace events and log them into *WIFTrace.e2e* file.</span></span> <span data-ttu-id="7ee32-134">有关 switchValue 开关的值的完整列表，请参阅以下主题中的跟踪级别表：[配置跟踪](../wcf/diagnostics/tracing/configuring-tracing.md)。</span><span class="sxs-lookup"><span data-stu-id="7ee32-134">For a complete list of values for the **switchValue** switch, refer to the Trace Level table found in the following topic: [Configuring Tracing](../wcf/diagnostics/tracing/configuring-tracing.md).</span></span>  
  
## <a name="step-2--analyze-wif-trace-files-using-trace-viewer-tool"></a><span data-ttu-id="7ee32-135">步骤 2 – 使用跟踪查看器工具分析 WIF 跟踪文件</span><span class="sxs-lookup"><span data-stu-id="7ee32-135">Step 2 – Analyze WIF Trace Files Using Trace Viewer Tool</span></span>  
 <span data-ttu-id="7ee32-136">在此步骤中，将使用跟踪查看器工具 (SvcTraceViewer.exe) 来分析 WIF 跟踪日志。</span><span class="sxs-lookup"><span data-stu-id="7ee32-136">In this step, you will use the Trace Viewer Tool (SvcTraceViewer.exe) to analyze WIF trace logs.</span></span>  
  
#### <a name="to-analyze-wif-trace-logs-using-trace-viewer-tool-svctraceviewerexe"></a><span data-ttu-id="7ee32-137">使用跟踪查看器工具 (SvcTraceViewer.exe) 分析 WIF 跟踪日志</span><span class="sxs-lookup"><span data-stu-id="7ee32-137">To analyze WIF trace logs using Trace Viewer tool (SvcTraceViewer.exe)</span></span>  
  
1.  <span data-ttu-id="7ee32-138">跟踪查看器工具 (SvcTraceViewer.exe) 作为 Windows SDK 的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="7ee32-138">Trace Viewer tool (SvcTraceViewer.exe) ships as part of the Windows SDK.</span></span> <span data-ttu-id="7ee32-139">如果尚未安装 Windows SDK，可在 [Windows SDK](https://www.microsoft.com/download/en/details.aspx?id=8279) 中下载。</span><span class="sxs-lookup"><span data-stu-id="7ee32-139">If you haven’t already installed the Windows SDK, you can download it here: [Windows SDK](https://www.microsoft.com/download/en/details.aspx?id=8279).</span></span>  
  
2.  <span data-ttu-id="7ee32-140">运行跟踪查看器工具 (SvcTraceViewer.exe)。</span><span class="sxs-lookup"><span data-stu-id="7ee32-140">Run the Trace Viewer tool (SvcTraceViewer.exe).</span></span> <span data-ttu-id="7ee32-141">通常可以在安装路径的 Bin 文件夹中找到。</span><span class="sxs-lookup"><span data-stu-id="7ee32-141">It is typically available in the **Bin** folder of the installation path.</span></span>  
  
3.  <span data-ttu-id="7ee32-142">打开 WIF 跟踪日志文件（如 WIFTrace.e2e），方法是在菜单中选择“文件”、“打开…”</span><span class="sxs-lookup"><span data-stu-id="7ee32-142">Open the WIF trace log file, for example, WIFTrace.e2e by selecting **File**, **Open…**</span></span> <span data-ttu-id="7ee32-143">选项或使用 Ctrl+O 快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7ee32-143">option in the menu or using the **Ctrl+O** shortcut.</span></span> <span data-ttu-id="7ee32-144">在跟踪查看器工具中打开跟踪日志文件。</span><span class="sxs-lookup"><span data-stu-id="7ee32-144">The trace log file opens in the Trace Viewer tool.</span></span>  
  
4.  <span data-ttu-id="7ee32-145">查看“活动”选项卡中的条目。每个项均应包含一个活动编号、记录的跟踪数、活动持续时间及其开始和结束时间戳。</span><span class="sxs-lookup"><span data-stu-id="7ee32-145">Review entries in the **Activity** tab. Each entry should contain an activity number, the number of traces that were logged, duration of the activity and its start and end timestamps.</span></span>  
  
5.  <span data-ttu-id="7ee32-146">单击“活动”选项卡。应可以在该工具的主区域中看到详细的跟踪项。</span><span class="sxs-lookup"><span data-stu-id="7ee32-146">Click on the **Activity** tab. You should see detailed trace entries in the main area of the tool.</span></span> <span data-ttu-id="7ee32-147">使用菜单中的“级别”下拉列表，筛选特定跟踪级别，比如“全部”、“警告”、“错误”、“信息”等。</span><span class="sxs-lookup"><span data-stu-id="7ee32-147">Use the **Level** dropdown list on the menu to filter specific level of traces, for example: **All**, **Warning**, **Errors**, **Information**, etc.</span></span>  
  
6.  <span data-ttu-id="7ee32-148">在工具的下部区域中单击特定跟踪项，查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ee32-148">Click on specific trace entries to review the details in the lower area of the tool.</span></span> <span data-ttu-id="7ee32-149">可通过选择相应的选项卡使用“格式化”和“XML”视图来查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ee32-149">The details can be viewed using **Formatted** and **XML** view by choosing corresponding tabs.</span></span>  
  
## <a name="step-3--identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="7ee32-150">步骤 3 – 确定解决方案以修复 WIF 相关问题</span><span class="sxs-lookup"><span data-stu-id="7ee32-150">Step 3 – Identify Solutions to Fix WIF Related Issues</span></span>  
 <span data-ttu-id="7ee32-151">在此步骤中，可以确定通过 WIF 跟踪日志和跟踪查看器工具标识的 WIF 相关问题的解决方案。</span><span class="sxs-lookup"><span data-stu-id="7ee32-151">In this step, you can identify solutions for WIF-related issues identified by using the WIF trace log and Trace Viewer tool.</span></span> <span data-ttu-id="7ee32-152">它概述了 WIF 相关异常对用于排除问题的潜在解决方案或所需操作的常规映射。</span><span class="sxs-lookup"><span data-stu-id="7ee32-152">It outlines general mapping of WIF related exceptions to potential solutions or required actions to troubleshoot the issue.</span></span>  
  
#### <a name="to-identify-solutions-to-fix-wif-related-issues"></a><span data-ttu-id="7ee32-153">确定解决方案以修复 WIF 相关问题</span><span class="sxs-lookup"><span data-stu-id="7ee32-153">To identify solutions to fix WIF related issues</span></span>  
  
1.  <span data-ttu-id="7ee32-154">查看以下 WIF 异常和解决问题所需操作表。</span><span class="sxs-lookup"><span data-stu-id="7ee32-154">Review the following table of WIF exceptions and the required actions to correct the issues.</span></span>  
  
|<span data-ttu-id="7ee32-155">**错误 ID**</span><span class="sxs-lookup"><span data-stu-id="7ee32-155">**Error ID**</span></span>|<span data-ttu-id="7ee32-156">**错误消息**</span><span class="sxs-lookup"><span data-stu-id="7ee32-156">**Error Message**</span></span>|<span data-ttu-id="7ee32-157">**修复错误所需操作**</span><span class="sxs-lookup"><span data-stu-id="7ee32-157">**Action needed to fix the error**</span></span>|  
|-|-|-|  
|<span data-ttu-id="7ee32-158">ID4175</span><span class="sxs-lookup"><span data-stu-id="7ee32-158">ID4175</span></span>|<span data-ttu-id="7ee32-159">IssuerNameRegistry 未识别的安全令牌的颁发者。</span><span class="sxs-lookup"><span data-stu-id="7ee32-159">The issuer of the security token was not recognized by the IssuerNameRegistry.</span></span>  <span data-ttu-id="7ee32-160">若要接受来自此颁发者的安全令牌，请将 IssuerNameRegistry 配置为返回此颁发者的有效名称。</span><span class="sxs-lookup"><span data-stu-id="7ee32-160">To accept security tokens from this issuer, configure the IssuerNameRegistry to return a valid name for this issuer.</span></span>|<span data-ttu-id="7ee32-161">从 MMC 管理单元复制指纹并将其粘贴到 Web.config 文件中可能会导致此错误。</span><span class="sxs-lookup"><span data-stu-id="7ee32-161">This error can be caused by copying a thumbprint from the MMC snap-in and pasting it into the *Web.config* file.</span></span> <span data-ttu-id="7ee32-162">具体而言，从证书属性窗口中复制时，可以获得文本字符串中额外的非打印字符。</span><span class="sxs-lookup"><span data-stu-id="7ee32-162">Specifically, you can get an extra non-printable character in the text string when copying from the certificate properties window.</span></span> <span data-ttu-id="7ee32-163">此额外的字符将导致指纹匹配失败。可在此处找到正确复制指纹的过程： [http://msdn.microsoft.com/library/ff359102.aspx](https://msdn.microsoft.com/library/ff359102.aspx)</span><span class="sxs-lookup"><span data-stu-id="7ee32-163">This extra character causes the thumbprint match to fail.The procedure for correctly copying the thumbprint can be found here: [http://msdn.microsoft.com/library/ff359102.aspx](https://msdn.microsoft.com/library/ff359102.aspx)</span></span>|  
  
## <a name="related-items"></a><span data-ttu-id="7ee32-164">相关项</span><span class="sxs-lookup"><span data-stu-id="7ee32-164">Related Items</span></span>  
  
-   [<span data-ttu-id="7ee32-165">使用服务跟踪查看器查看相关跟踪和进行故障排除</span><span class="sxs-lookup"><span data-stu-id="7ee32-165">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
