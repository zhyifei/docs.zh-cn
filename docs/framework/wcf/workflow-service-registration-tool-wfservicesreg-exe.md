---
title: 工作流服务注册工具 (WFServicesReg.exe)
ms.date: 03/30/2017
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
ms.openlocfilehash: 182bef75bff1785905d77d3bc497e0701e297912
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346592"
---
# <a name="workflow-service-registration-tool-wfservicesregexe"></a><span data-ttu-id="69c9a-102">工作流服务注册工具 (WFServicesReg.exe)</span><span class="sxs-lookup"><span data-stu-id="69c9a-102">WorkFlow Service Registration Tool (WFServicesReg.exe)</span></span>
<span data-ttu-id="69c9a-103">工作流服务注册工具 (WFServicesReg.exe) 是一个独立的工具，可用于添加、移除或修复 Windows Workflow Foundation (WF) 服务的配置元素。</span><span class="sxs-lookup"><span data-stu-id="69c9a-103">Workflow Services Registration tool (WFServicesReg.exe) is a stand-alone tool that can be used to add, remove, or repair the configuration elements for Windows Workflow Foundation (WF) services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69c9a-104">语法</span><span class="sxs-lookup"><span data-stu-id="69c9a-104">Syntax</span></span>  
  
```console  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## <a name="remarks"></a><span data-ttu-id="69c9a-105">备注</span><span class="sxs-lookup"><span data-stu-id="69c9a-105">Remarks</span></span>  
 <span data-ttu-id="69c9a-106">此工具可在 .NET Framework 3.5 安装位置（具体来说就是%windir%\Microsoft.NET\Framework\v3.5）或64位计算机上的%windir%\Microsoft.NET\Framework64\v3.5 中找到。</span><span class="sxs-lookup"><span data-stu-id="69c9a-106">The tool can be found at the .NET Framework 3.5 installation location, specifically, %windir%\Microsoft.NET\Framework\v3.5, or at %windir%\Microsoft.NET\Framework64\v3.5 in 64-bit machines.</span></span>  
  
 <span data-ttu-id="69c9a-107">下表说明了可用于工作流服务注册工具 (WFServicesReg.exe) 的选项。</span><span class="sxs-lookup"><span data-stu-id="69c9a-107">The following tables describe the options that can be used with the Workflow Services Registration tool (WFServicesReg.exe).</span></span>  
  
|<span data-ttu-id="69c9a-108">选项</span><span class="sxs-lookup"><span data-stu-id="69c9a-108">Option</span></span>|<span data-ttu-id="69c9a-109">描述</span><span class="sxs-lookup"><span data-stu-id="69c9a-109">Description</span></span>|  
|------------|-----------------|  
|`/c`|<span data-ttu-id="69c9a-110">配置 Windows Workflow Services。</span><span class="sxs-lookup"><span data-stu-id="69c9a-110">Configures Windows Workflow Services.</span></span> <span data-ttu-id="69c9a-111">在安装和修复方案中使用。</span><span class="sxs-lookup"><span data-stu-id="69c9a-111">Used in install and repair scenarios.</span></span>|  
|`/r`|<span data-ttu-id="69c9a-112">移除 Windows Workflow Services 配置。</span><span class="sxs-lookup"><span data-stu-id="69c9a-112">Removes Windows Workflow Services Configuration.</span></span>|  
|`/v`|<span data-ttu-id="69c9a-113">打印详细信息（针对配置或移除）。</span><span class="sxs-lookup"><span data-stu-id="69c9a-113">Print verbose information (for either configuration or removal).</span></span>|  
|`/m`|<span data-ttu-id="69c9a-114">启用 MSI 日志记录格式。</span><span class="sxs-lookup"><span data-stu-id="69c9a-114">Enables MSI logging format.</span></span>|  
|`/i`|<span data-ttu-id="69c9a-115">应用程序运行时最小化窗口。</span><span class="sxs-lookup"><span data-stu-id="69c9a-115">Minimizes the window when the application runs.</span></span>|  
  
## <a name="registration"></a><span data-ttu-id="69c9a-116">注册</span><span class="sxs-lookup"><span data-stu-id="69c9a-116">Registration</span></span>  
 <span data-ttu-id="69c9a-117">该工具检查 Web.config 文件并注册以下内容：</span><span class="sxs-lookup"><span data-stu-id="69c9a-117">The tool inspects the Web.config file and registers the following:</span></span>  
  
- <span data-ttu-id="69c9a-118">.NET Framework 3.5 引用程序集。</span><span class="sxs-lookup"><span data-stu-id="69c9a-118">.NET Framework 3.5 reference assemblies.</span></span>  
  
- <span data-ttu-id="69c9a-119">用于 .xoml 文件的生成提供程序。</span><span class="sxs-lookup"><span data-stu-id="69c9a-119">A build provider for .xoml files.</span></span>  
  
- <span data-ttu-id="69c9a-120">用于 .xoml 和 .rules 文件的 HTTP 处理程序。</span><span class="sxs-lookup"><span data-stu-id="69c9a-120">HTTP handlers for .xoml and .rules files.</span></span>  
  
 <span data-ttu-id="69c9a-121">该工具检查 Machine.config 文件并注册以下扩展：</span><span class="sxs-lookup"><span data-stu-id="69c9a-121">The tool inspects the Machine.config file and registers the following extensions:</span></span>  
  
- <span data-ttu-id="69c9a-122">behaviorExtensions</span><span class="sxs-lookup"><span data-stu-id="69c9a-122">behaviorExtensions</span></span>  
  
- <span data-ttu-id="69c9a-123">bindingElementExtensions</span><span class="sxs-lookup"><span data-stu-id="69c9a-123">bindingElementExtensions</span></span>  
  
- <span data-ttu-id="69c9a-124">bindingExtensions</span><span class="sxs-lookup"><span data-stu-id="69c9a-124">bindingExtensions</span></span>  
  
 <span data-ttu-id="69c9a-125">该工具还注册以下客户端元数据导入程序：</span><span class="sxs-lookup"><span data-stu-id="69c9a-125">The tool also registers the following client metadata importers:</span></span>  
  
- <span data-ttu-id="69c9a-126">policyImporters</span><span class="sxs-lookup"><span data-stu-id="69c9a-126">policyImporters</span></span>  
  
- <span data-ttu-id="69c9a-127">wsdlImporters</span><span class="sxs-lookup"><span data-stu-id="69c9a-127">wsdlImporters</span></span>  
  
 <span data-ttu-id="69c9a-128">该工具还在 IIS 元数据库中注册 .xoml 和 .rules 脚本映射和处理程序。</span><span class="sxs-lookup"><span data-stu-id="69c9a-128">The tool also registers .xoml and .rules scriptmaps and handlers in the IIS metabase.</span></span>  
  
 <span data-ttu-id="69c9a-129">在 Windows Server 2003 和 [!INCLUDE[wxp](../../../includes/wxp-md.md)] 机（IIS 5.1 和 IIS 6.0）上，注册了一组 xoml 和. 规则脚本映射。</span><span class="sxs-lookup"><span data-stu-id="69c9a-129">On Windows Server 2003 and [!INCLUDE[wxp](../../../includes/wxp-md.md)] machines (IIS 5.1 and IIS 6.0), one set of .xoml and .rules scriptmaps are registered.</span></span>  
  
 <span data-ttu-id="69c9a-130">在 64 位计算机上，如果启用 `Enable32BitAppOnWin64` 开关，则该工具注册 WOW 模式脚本映射；如果禁用 `Enable32BitAppOnWin64` 开关，则该工具注册本机 64 位模式脚本映射。</span><span class="sxs-lookup"><span data-stu-id="69c9a-130">On 64-bit machines, the tool registers WOW mode scriptmaps if the `Enable32BitAppOnWin64` switch is enabled, or native 64-bit scriptmaps if the `Enable32BitAppOnWin64` switch is disabled.</span></span>  
  
 <span data-ttu-id="69c9a-131">在 Windows Vista 和 Windows Server 2008 （IIS 7.0 及更高版本）计算机上，注册了两组 xoml 和. 规则处理程序：一个用于集成模式，另一个用于经典模式。</span><span class="sxs-lookup"><span data-stu-id="69c9a-131">On Windows Vista and Windows Server 2008 (IIS 7.0 and above) machines, two sets of .xoml and .rules handlers are registered: one for Integrated mode and one for Classic mode.</span></span>  
  
 <span data-ttu-id="69c9a-132">在 64 位计算机上，注册三组处理程序（无论 `Enable32BitAppOnWin64` 开关处于什么状态）：一组用于集成模式，一组用于 WOW 经典模式，一组用于本机 64 位经典模式。</span><span class="sxs-lookup"><span data-stu-id="69c9a-132">On 64-bit machines, three sets of handlers are registered (regardless of the state of the `Enable32BitAppOnWin64` switch): one for Integrated mode, one for WOW Classic mode and one for native 64-bit Classic mode.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69c9a-133">与 ServiceModelreg.exe 不同，WFServicesReg.exe 不允许添加、移除和修复特定网站的脚本映射或处理程序。</span><span class="sxs-lookup"><span data-stu-id="69c9a-133">Unlike ServiceModelreg.exe, WFServicesReg.exe does not allow adding, removing, or repairing scriptmaps or handlers for a particular Web site.</span></span> <span data-ttu-id="69c9a-134">有关此问题的解决方法，请参见“修复脚本映射”一节。</span><span class="sxs-lookup"><span data-stu-id="69c9a-134">For a workaround to this issue, see the "Repairing the Scriptmaps" section.</span></span>  
  
## <a name="usage-scenarios"></a><span data-ttu-id="69c9a-135">使用方案</span><span class="sxs-lookup"><span data-stu-id="69c9a-135">Usage Scenarios</span></span>  
  
### <a name="installing-iis-after-net-framework-35-is-installed"></a><span data-ttu-id="69c9a-136">安装 .NET Framework 3.5 之后安装 IIS</span><span class="sxs-lookup"><span data-stu-id="69c9a-136">Installing IIS after .NET Framework 3.5 is installed</span></span>  
 <span data-ttu-id="69c9a-137">在 Windows Server 2003 计算机上，在安装 IIS 之前会安装 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="69c9a-137">On a Windows Server 2003 machine, .NET Framework 3.5 is installed prior to IIS installation.</span></span> <span data-ttu-id="69c9a-138">由于 IIS 元数据库不可用，.NET Framework 3.5 的安装成功，无需安装 xoml 和。</span><span class="sxs-lookup"><span data-stu-id="69c9a-138">Due to the unavailability of the IIS metabase, installation of .NET Framework 3.5 succeeds without installing .xoml and .rules scriptmaps.</span></span>  
  
 <span data-ttu-id="69c9a-139">安装 IIS 后，可以使用具有 `/c` 开关的 WFServicesReg.exe 工具来安装这些特定的脚本映射。</span><span class="sxs-lookup"><span data-stu-id="69c9a-139">After IIS is installed, you can use the WFServicesReg.exe tool with the `/c` switch to install these specific scriptmaps.</span></span>  
  
### <a name="repairing-the-scriptmaps"></a><span data-ttu-id="69c9a-140">修复脚本映射</span><span class="sxs-lookup"><span data-stu-id="69c9a-140">Repairing the Scriptmaps</span></span>  
  
#### <a name="scriptmap-deleted-under-web-sites-node"></a><span data-ttu-id="69c9a-141">删除了网站节点下的脚本映射</span><span class="sxs-lookup"><span data-stu-id="69c9a-141">Scriptmap deleted under Web Sites node</span></span>  
 <span data-ttu-id="69c9a-142">在 Windows Server 2003 计算机上，将从 "网站" 节点中意外删除 xoml 或。</span><span class="sxs-lookup"><span data-stu-id="69c9a-142">On a Windows Server 2003 machine, .xoml or .rules is accidentally deleted from the Web Sites node.</span></span> <span data-ttu-id="69c9a-143">通过运行具有 `/c` 开关的 WFServicesReg.exe 工具可以修复这个问题。</span><span class="sxs-lookup"><span data-stu-id="69c9a-143">This can be repaired by running the WFServicesReg.exe tool with the `/c` switch.</span></span>  
  
#### <a name="scriptmap-deleted-under-a-particular-web-site"></a><span data-ttu-id="69c9a-144">删除了特定网站下的脚本映射</span><span class="sxs-lookup"><span data-stu-id="69c9a-144">Scriptmap deleted under a particular Web site</span></span>  
 <span data-ttu-id="69c9a-145">在 Windows Server 2003 计算机上，. xoml 或。从特定网站（例如，默认网站）意外删除规则，而不是从 "网站" 节点中删除。</span><span class="sxs-lookup"><span data-stu-id="69c9a-145">On a Windows Server 2003 machine, .xoml or .rules is accidentally deleted from a particular Web site (for example, the Default Web Site) rather than from the Web Sites node.</span></span>  
  
 <span data-ttu-id="69c9a-146">若要修复特定网站的已删除处理程序，您应运行 "Wfservicesreg.exe/r" 以从所有网站中删除处理程序，然后运行 "Wfservicesreg.exe/c" 为所有网站创建适当的处理程序。</span><span class="sxs-lookup"><span data-stu-id="69c9a-146">To repair deleted handlers for a particular Web site, you should run "WFServicesReg.exe /r" to remove handlers from all Web sites, then run "WFServicesReg.exe /c" to create the appropriate handlers for all Web sites.</span></span>  
  
### <a name="configuring-handlers-after-switching-iis-mode"></a><span data-ttu-id="69c9a-147">切换 IIS 模式后配置处理程序</span><span class="sxs-lookup"><span data-stu-id="69c9a-147">Configuring handlers after switching IIS mode</span></span>  
 <span data-ttu-id="69c9a-148">如果 IIS 处于共享配置模式并且安装了 .NET Framework 3.5，则会在共享位置下配置 IIS 元数据库。</span><span class="sxs-lookup"><span data-stu-id="69c9a-148">When IIS is in shared configuration mode and .NET Framework 3.5 is installed, the IIS metabase is configured under a shared location.</span></span> <span data-ttu-id="69c9a-149">如果将 IIS 切换到非共享配置模式，则本地元数据库将不包含必需的处理程序。</span><span class="sxs-lookup"><span data-stu-id="69c9a-149">If you switch IIS to non-shared configuration mode, the local metabase will not contain the required handlers.</span></span> <span data-ttu-id="69c9a-150">若要正确配置本地元数据库，你可以将共享元数据库导入到本地，或运行 "Wfservicesreg.exe/c"，这将配置本地元数据库。</span><span class="sxs-lookup"><span data-stu-id="69c9a-150">To configure the local metabase properly, you can either import the shared metabase to local, or run "WFServicesReg.exe /c", which configures the local metabase.</span></span>
