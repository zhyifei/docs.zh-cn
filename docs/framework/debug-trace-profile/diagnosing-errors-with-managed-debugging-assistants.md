---
title: "使用托管调试助手诊断错误"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: EHMDA
helpviewer_keywords:
- run-time error debugging
- managed code, run-time debugging
- resource debugging
- registry, MDAs
- common language runtime, debugging
- MDAs (managed debugging assistants)
- configuration files [.NET Framework], debugging runtime events
- messages, managed debugging assistants
- application configuration files, managed debugging assistants
- debugging [.NET Framework], managed debugging assistants
- environment variables, MDAs
- access violation debugging [.NET Framework]
- diagnostics, managed debugging assistants
- unmanaged code, run-time debugging
- default debug output stream
- memory, debugging
- app.config files, managed debugging assistants
- managed debugging assistants (MDAs)
- debugging [.NET Framework], run-time errors
- trapping events
- runtime, error debugging
- disabling MDAs
- output, managed debugging assistants
- errors [.NET Framework], managed debugging assistants
ms.assetid: 76994ee6-9fa9-4059-b813-26578d24427c
caps.latest.revision: "63"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e23de3ea6e9693c05aa81da056ac7763bced8e9a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="diagnosing-errors-with-managed-debugging-assistants"></a><span data-ttu-id="62665-102">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="62665-102">Diagnosing Errors with Managed Debugging Assistants</span></span>
<span data-ttu-id="62665-103">托管调试助手 (MDA) 是调试辅助程序，它与公共语言运行时 (CLR) 一起工作以提供关于运行时状态的信息。</span><span class="sxs-lookup"><span data-stu-id="62665-103">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to provide information on runtime state.</span></span> <span data-ttu-id="62665-104">这些助手可生成关于你无法通过其他方式捕获的运行时事件的信息性消息。</span><span class="sxs-lookup"><span data-stu-id="62665-104">The assistants generate informational messages about runtime events that you cannot otherwise trap.</span></span> <span data-ttu-id="62665-105">可以使用 MDA 隔离在托管代码和非托管代码之间转换时发生的、难以发现的应用程序 Bug。</span><span class="sxs-lookup"><span data-stu-id="62665-105">You can use MDAs to isolate hard-to-find application bugs that occur when transitioning between managed and unmanaged code.</span></span> <span data-ttu-id="62665-106">可通过向 Windows 注册表添加注册表项或设置环境变量，启用或禁用所有的 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-106">You can enable or disable all MDAs by adding a key to the Windows registry or by setting an environment variable.</span></span> <span data-ttu-id="62665-107">可使用应用程序配置设置来启用特定的 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-107">You can enable specific MDAs by using application configuration settings.</span></span> <span data-ttu-id="62665-108">可以在应用程序的配置文件中为某些单独的 MDA 设置其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="62665-108">You can set additional configuration settings for some individual MDAs in the application's configuration file.</span></span> <span data-ttu-id="62665-109">由于将在加载运行时后分析这些配置文件，因此必须在托管应用程序启动之前启用 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-109">Because these configuration files are parsed when the runtime is loaded, you must enable the MDA before the managed application starts.</span></span> <span data-ttu-id="62665-110">不能为已经启动的应用程序启用 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-110">You cannot enable it for applications that have already started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62665-111">启用 MDA 后，即使不在调试器下执行代码，MDA 也会处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="62665-111">When an MDA is enabled, it is active even when your code is not executing under a debugger.</span></span> <span data-ttu-id="62665-112">如果在调试器不存在时引发 MDA 事件，尽管这不是未经处理的异常，事件消息也会出现在未经处理的异常对话框中。</span><span class="sxs-lookup"><span data-stu-id="62665-112">If an MDA event is raised when a debugger is not present, the event message is presented in an unhandled exception dialog box, although it is not an unhandled exception.</span></span> <span data-ttu-id="62665-113">若要避免出现该对话框，请在代码未在调试环境中执行时，移除 MDA 启用设置。</span><span class="sxs-lookup"><span data-stu-id="62665-113">To avoid the dialog box, remove the MDA-enabling settings when your code is not executing in a debugging environment.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="62665-114">在 Visual Studio 集成开发环境 (IDE) 中执行代码时，可以避免针对特定 MDA 事件出现的异常对话框。</span><span class="sxs-lookup"><span data-stu-id="62665-114">When your code is executing in the Visual Studio integrated development environment (IDE), you can avoid the exception dialog box that appears for specific MDA events.</span></span> <span data-ttu-id="62665-115">为此，请在“调试”菜单上，单击“异常”。</span><span class="sxs-lookup"><span data-stu-id="62665-115">To do that, on the **Debug** menu, click **Exceptions**.</span></span> <span data-ttu-id="62665-116">（如果“调试”菜单不包含“异常”命令，请单击“工具”菜单上的“自定义”添加该命令。）在“异常”对话框中，展开“托管调试助手”列表，然后清除单个 MDA 的“引发”复选框。</span><span class="sxs-lookup"><span data-stu-id="62665-116">(If the **Debug** menu does not contain an **Exceptions** command, click **Customize** on the **Tools** menu to add it.) In the **Exceptions** dialog box, expand the **Managed Debugging Assistants** list, and then clear the **Thrown** check box for the individual MDA.</span></span> <span data-ttu-id="62665-117">例如，要避免出现 [contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md) 的异常对话框，请在“托管调试助手”列表中清除其名称旁边的“引发”复选框。</span><span class="sxs-lookup"><span data-stu-id="62665-117">For example, to avoid the exception dialog box for a [contextSwitchDeadlock](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md) clear the **Thrown** check box next to its name in the **Managed Debugging Assistants** list.</span></span> <span data-ttu-id="62665-118">也可以使用此对话框启用 MDA 异常对话框的显示。</span><span class="sxs-lookup"><span data-stu-id="62665-118">You can also use this dialog box to enable the display of MDA exception dialog boxes.</span></span>  
  
 <span data-ttu-id="62665-119">下表列出了 .NET Framework 附带的 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-119">The following table lists the MDAs that ship with the .NET Framework.</span></span>  
  
|||  
|-|-|  
|[<span data-ttu-id="62665-120">asynchronousThreadAbort</span><span class="sxs-lookup"><span data-stu-id="62665-120">asynchronousThreadAbort</span></span>](../../../docs/framework/debug-trace-profile/asynchronousthreadabort-mda.md)|[<span data-ttu-id="62665-121">bindingFailure</span><span class="sxs-lookup"><span data-stu-id="62665-121">bindingFailure</span></span>](../../../docs/framework/debug-trace-profile/bindingfailure-mda.md)|  
|[<span data-ttu-id="62665-122">callbackOnCollectedDelegate</span><span class="sxs-lookup"><span data-stu-id="62665-122">callbackOnCollectedDelegate</span></span>](../../../docs/framework/debug-trace-profile/callbackoncollecteddelegate-mda.md)|[<span data-ttu-id="62665-123">contextSwitchDeadlock</span><span class="sxs-lookup"><span data-stu-id="62665-123">contextSwitchDeadlock</span></span>](../../../docs/framework/debug-trace-profile/contextswitchdeadlock-mda.md)|  
|[<span data-ttu-id="62665-124">dangerousThreadingAPI</span><span class="sxs-lookup"><span data-stu-id="62665-124">dangerousThreadingAPI</span></span>](../../../docs/framework/debug-trace-profile/dangerousthreadingapi-mda.md)|[<span data-ttu-id="62665-125">dateTimeInvalidLocalFormat</span><span class="sxs-lookup"><span data-stu-id="62665-125">dateTimeInvalidLocalFormat</span></span>](../../../docs/framework/debug-trace-profile/datetimeinvalidlocalformat-mda.md)|  
|[<span data-ttu-id="62665-126">dirtyCastAndCallOnInterface</span><span class="sxs-lookup"><span data-stu-id="62665-126">dirtyCastAndCallOnInterface</span></span>](../../../docs/framework/debug-trace-profile/dirtycastandcalloninterface-mda.md)|[<span data-ttu-id="62665-127">disconnectedContext</span><span class="sxs-lookup"><span data-stu-id="62665-127">disconnectedContext</span></span>](../../../docs/framework/debug-trace-profile/disconnectedcontext-mda.md)|  
|[<span data-ttu-id="62665-128">dllMainReturnsFalse</span><span class="sxs-lookup"><span data-stu-id="62665-128">dllMainReturnsFalse</span></span>](../../../docs/framework/debug-trace-profile/dllmainreturnsfalse-mda.md)|[<span data-ttu-id="62665-129">exceptionSwallowedOnCallFromCom</span><span class="sxs-lookup"><span data-stu-id="62665-129">exceptionSwallowedOnCallFromCom</span></span>](../../../docs/framework/debug-trace-profile/exceptionswallowedoncallfromcom-mda.md)|  
|[<span data-ttu-id="62665-130">failedQI</span><span class="sxs-lookup"><span data-stu-id="62665-130">failedQI</span></span>](../../../docs/framework/debug-trace-profile/failedqi-mda.md)|[<span data-ttu-id="62665-131">fatalExecutionEngineError</span><span class="sxs-lookup"><span data-stu-id="62665-131">fatalExecutionEngineError</span></span>](../../../docs/framework/debug-trace-profile/fatalexecutionengineerror-mda.md)|  
|[<span data-ttu-id="62665-132">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="62665-132">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)|[<span data-ttu-id="62665-133">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="62665-133">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)|  
|[<span data-ttu-id="62665-134">illegalPrepareConstrainedRegion</span><span class="sxs-lookup"><span data-stu-id="62665-134">illegalPrepareConstrainedRegion</span></span>](../../../docs/framework/debug-trace-profile/illegalprepareconstrainedregion-mda.md)|[<span data-ttu-id="62665-135">invalidApartmentStateChange</span><span class="sxs-lookup"><span data-stu-id="62665-135">invalidApartmentStateChange</span></span>](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)|  
|[<span data-ttu-id="62665-136">invalidCERCall</span><span class="sxs-lookup"><span data-stu-id="62665-136">invalidCERCall</span></span>](../../../docs/framework/debug-trace-profile/invalidcercall-mda.md)|[<span data-ttu-id="62665-137">invalidFunctionPointerInDelegate</span><span class="sxs-lookup"><span data-stu-id="62665-137">invalidFunctionPointerInDelegate</span></span>](../../../docs/framework/debug-trace-profile/invalidfunctionpointerindelegate-mda.md)|  
|[<span data-ttu-id="62665-138">invalidGCHandleCookie</span><span class="sxs-lookup"><span data-stu-id="62665-138">invalidGCHandleCookie</span></span>](../../../docs/framework/debug-trace-profile/invalidgchandlecookie-mda.md)|[<span data-ttu-id="62665-139">invalidIUnknown</span><span class="sxs-lookup"><span data-stu-id="62665-139">invalidIUnknown</span></span>](../../../docs/framework/debug-trace-profile/invalidiunknown-mda.md)|  
|[<span data-ttu-id="62665-140">invalidMemberDeclaration</span><span class="sxs-lookup"><span data-stu-id="62665-140">invalidMemberDeclaration</span></span>](../../../docs/framework/debug-trace-profile/invalidmemberdeclaration-mda.md)|[<span data-ttu-id="62665-141">invalidOverlappedToPinvoke</span><span class="sxs-lookup"><span data-stu-id="62665-141">invalidOverlappedToPinvoke</span></span>](../../../docs/framework/debug-trace-profile/invalidoverlappedtopinvoke-mda.md)|  
|[<span data-ttu-id="62665-142">invalidVariant</span><span class="sxs-lookup"><span data-stu-id="62665-142">invalidVariant</span></span>](../../../docs/framework/debug-trace-profile/invalidvariant-mda.md)|[<span data-ttu-id="62665-143">jitCompilationStart</span><span class="sxs-lookup"><span data-stu-id="62665-143">jitCompilationStart</span></span>](../../../docs/framework/debug-trace-profile/jitcompilationstart-mda.md)|  
|[<span data-ttu-id="62665-144">loaderLock</span><span class="sxs-lookup"><span data-stu-id="62665-144">loaderLock</span></span>](../../../docs/framework/debug-trace-profile/loaderlock-mda.md)|[<span data-ttu-id="62665-145">loadFromContext</span><span class="sxs-lookup"><span data-stu-id="62665-145">loadFromContext</span></span>](../../../docs/framework/debug-trace-profile/loadfromcontext-mda.md)|  
|[<span data-ttu-id="62665-146">marshalCleanupError</span><span class="sxs-lookup"><span data-stu-id="62665-146">marshalCleanupError</span></span>](../../../docs/framework/debug-trace-profile/marshalcleanuperror-mda.md)|[<span data-ttu-id="62665-147">marshaling</span><span class="sxs-lookup"><span data-stu-id="62665-147">marshaling</span></span>](../../../docs/framework/debug-trace-profile/marshaling-mda.md)|  
|[<span data-ttu-id="62665-148">memberInfoCacheCreation</span><span class="sxs-lookup"><span data-stu-id="62665-148">memberInfoCacheCreation</span></span>](../../../docs/framework/debug-trace-profile/memberinfocachecreation-mda.md)|[<span data-ttu-id="62665-149">moduloObjectHashcode</span><span class="sxs-lookup"><span data-stu-id="62665-149">moduloObjectHashcode</span></span>](../../../docs/framework/debug-trace-profile/moduloobjecthashcode-mda.md)|  
|[<span data-ttu-id="62665-150">nonComVisibleBaseClass</span><span class="sxs-lookup"><span data-stu-id="62665-150">nonComVisibleBaseClass</span></span>](../../../docs/framework/debug-trace-profile/noncomvisiblebaseclass-mda.md)|[<span data-ttu-id="62665-151">notMarshalable</span><span class="sxs-lookup"><span data-stu-id="62665-151">notMarshalable</span></span>](../../../docs/framework/debug-trace-profile/notmarshalable-mda.md)|  
|[<span data-ttu-id="62665-152">openGenericCERCall</span><span class="sxs-lookup"><span data-stu-id="62665-152">openGenericCERCall</span></span>](../../../docs/framework/debug-trace-profile/opengenericcercall-mda.md)|[<span data-ttu-id="62665-153">overlappedFreeError</span><span class="sxs-lookup"><span data-stu-id="62665-153">overlappedFreeError</span></span>](../../../docs/framework/debug-trace-profile/overlappedfreeerror-mda.md)|  
|[<span data-ttu-id="62665-154">pInvokeLog</span><span class="sxs-lookup"><span data-stu-id="62665-154">pInvokeLog</span></span>](../../../docs/framework/debug-trace-profile/pinvokelog-mda.md)|[<span data-ttu-id="62665-155">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="62665-155">pInvokeStackImbalance</span></span>](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)|  
|[<span data-ttu-id="62665-156">raceOnRCWCleanup</span><span class="sxs-lookup"><span data-stu-id="62665-156">raceOnRCWCleanup</span></span>](../../../docs/framework/debug-trace-profile/raceonrcwcleanup-mda.md)|[<span data-ttu-id="62665-157">reentrancy</span><span class="sxs-lookup"><span data-stu-id="62665-157">reentrancy</span></span>](../../../docs/framework/debug-trace-profile/reentrancy-mda.md)|  
|[<span data-ttu-id="62665-158">releaseHandleFailed</span><span class="sxs-lookup"><span data-stu-id="62665-158">releaseHandleFailed</span></span>](../../../docs/framework/debug-trace-profile/releasehandlefailed-mda.md)|[<span data-ttu-id="62665-159">reportAvOnComRelease</span><span class="sxs-lookup"><span data-stu-id="62665-159">reportAvOnComRelease</span></span>](../../../docs/framework/debug-trace-profile/reportavoncomrelease-mda.md)|  
|[<span data-ttu-id="62665-160">streamWriterBufferedDataLost</span><span class="sxs-lookup"><span data-stu-id="62665-160">streamWriterBufferedDataLost</span></span>](../../../docs/framework/debug-trace-profile/streamwriterbuffereddatalost-mda.md)|[<span data-ttu-id="62665-161">virtualCERCall</span><span class="sxs-lookup"><span data-stu-id="62665-161">virtualCERCall</span></span>](../../../docs/framework/debug-trace-profile/virtualcercall-mda.md)|  
  
 <span data-ttu-id="62665-162">默认情况下，.NET Framework 会为所有托管调试器激活 MDA 的子集。</span><span class="sxs-lookup"><span data-stu-id="62665-162">By default, the .NET Framework activates a subset of MDAs for all managed debuggers.</span></span> <span data-ttu-id="62665-163">通过单击“调试”菜单上的“异常”并展开“托管调试助手”列表，可以查看 Visual Studio 中的默认集。</span><span class="sxs-lookup"><span data-stu-id="62665-163">You can view the default set in Visual Studio by clicking **Exceptions** on the **Debug** menu and expanding the **Managed Debugging Assistants** list.</span></span>  
  
## <a name="enabling-and-disabling-mdas"></a><span data-ttu-id="62665-164">启用和禁用 MDA</span><span class="sxs-lookup"><span data-stu-id="62665-164">Enabling and Disabling MDAs</span></span>  
 <span data-ttu-id="62665-165">可使用注册表项、环境变量和应用程序配置设置，启用和禁用 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-165">You can enable and disable MDAs by using a registry key, an environment variable, and application configuration settings.</span></span> <span data-ttu-id="62665-166">若要使用应用程序配置设置，必须启用注册表项或环境变量。</span><span class="sxs-lookup"><span data-stu-id="62665-166">You must enable either the registry key or the environment variable to use the application configuration settings.</span></span>  
  
 <span data-ttu-id="62665-167">在 Visual Studio 2005 和更高版本中，启用宿主进程后，不能禁用默认集合中的 MDA 或启用不在默认集合中的 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-167">In Visual Studio 2005 and later versions, when the hosting process is enabled, you cannot disable MDAs that are in the default set or enable MDAs that are not in the default set.</span></span> <span data-ttu-id="62665-168">默认情况下，宿主进程处于启用状态，因此必须将其显式禁用。</span><span class="sxs-lookup"><span data-stu-id="62665-168">The hosting process is enabled by default, so it must be explicitly disabled.</span></span>  
  
 <span data-ttu-id="62665-169">若要在 Visual Studio 中禁用托管进程，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="62665-169">To disable the hosting process in Visual Studio, do the following:</span></span>  
  
1.  <span data-ttu-id="62665-170">在“解决方案资源管理器”中，选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="62665-170">In **Solution Explorer**, select a project.</span></span>  
  
2.  <span data-ttu-id="62665-171">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="62665-171">On the **Project** menu, click **Properties**.</span></span>  
  
     <span data-ttu-id="62665-172">此时将显示“项目设计器”窗口。</span><span class="sxs-lookup"><span data-stu-id="62665-172">The **Project Designer** window appears.</span></span>  
  
3.  <span data-ttu-id="62665-173">单击“调试”选项卡。</span><span class="sxs-lookup"><span data-stu-id="62665-173">Click the **Debug** tab.</span></span>  
  
4.  <span data-ttu-id="62665-174">在“启用调试器”部分中，清除“启用 Visual Studio 托管进程”复选框。</span><span class="sxs-lookup"><span data-stu-id="62665-174">In the **Enable Debuggers** section, clear the **Enable the Visual Studio hosting process** check box.</span></span>  
  
 <span data-ttu-id="62665-175">但是，禁用托管进程会影响性能。</span><span class="sxs-lookup"><span data-stu-id="62665-175">However, disabling the hosting process can affect performance.</span></span> <span data-ttu-id="62665-176">通过阻止 Visual Studio 在每次收到 MDA 通知时显示 MDA 对话框，可以避免需要禁用 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-176">You can avoid the need to disable MDAs by preventing Visual Studio from displaying the MDA dialog box whenever an MDA notification is received.</span></span> <span data-ttu-id="62665-177">为此，请单击“调试”菜单上的“异常”，展开“托管调试助手”列表，然后为单个 MDA 选中或清除“引发”复选框。</span><span class="sxs-lookup"><span data-stu-id="62665-177">To do that, click **Exceptions** on the **Debug** menu, expand the **Managed Debugging Assistants** list, and then select or clear the **Thrown** check box for the individual MDA.</span></span>  
  
### <a name="enabling-and-disabling-mdas-by-using-a-registry-key"></a><span data-ttu-id="62665-178">使用注册表项启用和禁用 MDA</span><span class="sxs-lookup"><span data-stu-id="62665-178">Enabling and Disabling MDAs by Using a Registry Key</span></span>  
 <span data-ttu-id="62665-179">可通过在 Windows 注册表中添加 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA 子项（类型为 REG_SZ，值为 1）启用 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-179">You can enable MDAs by adding the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\MDA subkey (type REG_SZ, value 1) in the Windows registry.</span></span> <span data-ttu-id="62665-180">将以下示例复制到名为 MDAEnable.reg 的文本文件中。打开 Windows 注册表编辑器 (RegEdit.exe)，从“文件”菜单选择“导入”。</span><span class="sxs-lookup"><span data-stu-id="62665-180">Copy the following example into a text file named MDAEnable.reg. Open the Windows Registry Editor (RegEdit.exe) and from the **File** menu choose **Import**.</span></span> <span data-ttu-id="62665-181">选择 MDAEnable.reg 文件以在该计算机上启用 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-181">Select the MDAEnable.reg  file to enable MDAs on that computer.</span></span> <span data-ttu-id="62665-182">将子项设置为字符串值 1（不是 DWORD 值 1）能够从 ApplicationName.suffix.mda.config 文件读取 MDA 设置。</span><span class="sxs-lookup"><span data-stu-id="62665-182">Setting the subkey to string value of 1 (not DWORD value of 1) enables the reading of MDA settings from the *ApplicationName.suffix*.mda.config file.</span></span> <span data-ttu-id="62665-183">（例如，Notepad 的 MDA 配置文件将被命名为 notepad.exe.mda.config）</span><span class="sxs-lookup"><span data-stu-id="62665-183">(For example the MDA configuration file for Notepad would be named notepad.exe.mda.config)</span></span>  
  
```  
Windows Registry Editor Version 5.00  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework]  
"MDA"="1"  
```  
  
 <span data-ttu-id="62665-184">如果计算机在 64 位操作系统上运行 32 位应用程序，应按下方所示设置 MDA 密钥：</span><span class="sxs-lookup"><span data-stu-id="62665-184">If the computer is running a 32-bit application on a 64-bit operating system, then the MDA key should be set like the following:</span></span>  
  
```  
      Windows Registry Editor Version 5.00   
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework]  
"MDA"="1"  
```  
  
 <span data-ttu-id="62665-185">有关详细信息，请参阅[使用特定于应用程序的配置设置启用和禁用 MDA](#appConfig)。</span><span class="sxs-lookup"><span data-stu-id="62665-185">See [Enabling and Disabling MDAs by Using Application-Specific Configuration Settings](#appConfig) for more information.</span></span> <span data-ttu-id="62665-186">可以使用 COMPLUS_MDA 环境变量重写注册表设置。</span><span class="sxs-lookup"><span data-stu-id="62665-186">The registry setting can be overridden by the COMPLUS_MDA environment variable.</span></span> <span data-ttu-id="62665-187">有关详细信息，请参阅[使用环境变量启用和禁用 MDA](#envVariable)。</span><span class="sxs-lookup"><span data-stu-id="62665-187">See [Enabling and Disabling MDAs by Using an Environment Variable](#envVariable) for more information.</span></span>  
  
 <span data-ttu-id="62665-188">若要禁用 MDA，请使用 Windows 注册表编辑器将 MDA 子项设置为 0（零）。</span><span class="sxs-lookup"><span data-stu-id="62665-188">To disable MDAs, set the MDA subkey to 0 (zero) using the Windows Registry Editor.</span></span>  
  
 <span data-ttu-id="62665-189">默认情况下，即使未添加该注册表项，有些 MDA 也会在运行附加到调试器的应用程序时启用。</span><span class="sxs-lookup"><span data-stu-id="62665-189">By default, some MDAs are enabled when you run an application that is attached to a debugger, even without adding the registry key.</span></span> <span data-ttu-id="62665-190">此类助手的示例包括 [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) 和 [invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md)。</span><span class="sxs-lookup"><span data-stu-id="62665-190">Examples of such assistants are [pInvokeStackImbalance](../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) and [invalidApartmentStateChange](../../../docs/framework/debug-trace-profile/invalidapartmentstatechange-mda.md).</span></span> <span data-ttu-id="62665-191">可以按本节前面所述，运行 MDADisable.reg 文件来禁用这些助手。</span><span class="sxs-lookup"><span data-stu-id="62665-191">You can disable these assistants by running the MDADisable.reg file as described earlier in this section.</span></span>  
  
<a name="envVariable"></a>   
### <a name="enabling-and-disabling-mdas-by-using-an-environment-variable"></a><span data-ttu-id="62665-192">使用环境变量启用和禁用 MDA</span><span class="sxs-lookup"><span data-stu-id="62665-192">Enabling and Disabling MDAs by Using an Environment Variable</span></span>  
 <span data-ttu-id="62665-193">还可以通过环境变量 COMPLUS_MDA 控制 MDA 激活，此变量可重写注册表项。</span><span class="sxs-lookup"><span data-stu-id="62665-193">MDA activation can also controlled by the environment variable COMPLUS_MDA, which overrides the registry key.</span></span> <span data-ttu-id="62665-194">COMPLUS_MDA 字符串是一个区分大小写、以分号分隔的 MDA 名称列表或其他特殊控制字符串。</span><span class="sxs-lookup"><span data-stu-id="62665-194">The COMPLUS_MDA string is a case-insensitive, semicolon-delimited list of MDA names or other special control strings.</span></span> <span data-ttu-id="62665-195">在托管或非托管调试器下启动将默认启用一组 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-195">Starting under a managed or unmanaged debugger enables a set of MDAs by default.</span></span> <span data-ttu-id="62665-196">这是通过在环境变量或注册表项的值前面，隐式附加默认在调试器下启用的、以分号分隔的 MDA 的列表来实现的。</span><span class="sxs-lookup"><span data-stu-id="62665-196">This is done by implicitly prepending the semicolon-delimited list of MDAs enabled by default under debuggers to the value of the environment variable or registry key.</span></span> <span data-ttu-id="62665-197">特殊控制字符串如下所示：</span><span class="sxs-lookup"><span data-stu-id="62665-197">The special control strings are the following:</span></span>  
  
-   <span data-ttu-id="62665-198">`0` - 停用所有 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-198">`0` - Deactivates all MDAs.</span></span>  
  
-   <span data-ttu-id="62665-199">`1` - 从 ApplicationName.mda.configg 读取 MDA 设置。</span><span class="sxs-lookup"><span data-stu-id="62665-199">`1` - Reads MDA settings from *ApplicationName*.mda.config.</span></span>  
  
-   <span data-ttu-id="62665-200">`managedDebugger` - 显式激活在调试器下启动托管可执行文件时隐式激活的所有 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-200">`managedDebugger` - Explicitly activates all MDAs that are implicitly activated when a managed executable is started under a debugger.</span></span>  
  
-   <span data-ttu-id="62665-201">`unmanagedDebugger` - 显式激活在调试器下启动非托管可执行文件时隐式激活的所有 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-201">`unmanagedDebugger` - Explicitly activates all MDAs that are implicitly activated when an unmanaged executable is started under a debugger.</span></span>  
  
 <span data-ttu-id="62665-202">如果存在冲突的设置，则最新的设置将重写先前的设置：</span><span class="sxs-lookup"><span data-stu-id="62665-202">If there are conflicting settings, the most recent settings override previous settings:</span></span>  
  
-   <span data-ttu-id="62665-203">`COMPLUS_MDA=0` 禁用所有 MDA，包括那些在调试器下隐式启用的 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-203">`COMPLUS_MDA=0` disables all MDAs, including those implicitly enabled under a debugger.</span></span>  
  
-   <span data-ttu-id="62665-204">除了调试器下隐式启用的所有 MDA，`COMPLUS_MDA=gcUnmanagedToManaged` 还启用 `gcUnmanagedToManaged`。</span><span class="sxs-lookup"><span data-stu-id="62665-204">`COMPLUS_MDA=gcUnmanagedToManaged` enables `gcUnmanagedToManaged` in addition to any MDAs that are implicitly enabled under a debugger.</span></span>  
  
-   <span data-ttu-id="62665-205">`COMPLUS_MDA=0;gcUnmanagedToManaged` 启用 `gcUnmanagedToManaged`，但是禁用将在调试器下隐式启用的 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-205">`COMPLUS_MDA=0;gcUnmanagedToManaged` enables `gcUnmanagedToManaged` but disables MDAs that would otherwise be implicitly enabled under a debugger.</span></span>  
  
<a name="appConfig"></a>   
### <a name="enabling-and-disabling-mdas-by-using-application-specific-configuration-settings"></a><span data-ttu-id="62665-206">使用特定于应用程序的配置设置启用和禁用 MDA</span><span class="sxs-lookup"><span data-stu-id="62665-206">Enabling and Disabling MDAs by Using Application-Specific Configuration Settings</span></span>  
 <span data-ttu-id="62665-207">可以在应用程序的 MDA 配置文件中单独地启用、禁用和配置某些助手。</span><span class="sxs-lookup"><span data-stu-id="62665-207">You can enable, disable, and configure some assistants individually in the MDA configuration file for the application.</span></span> <span data-ttu-id="62665-208">若要使用用于配置 MDA 的应用程序配置文件，必须设置 MDA 注册表项或 COMPLUS_MDA 环境变量。</span><span class="sxs-lookup"><span data-stu-id="62665-208">To enable the use of an application configuration file for configuring MDAs, either the MDA registry key or the COMPLUS_MDA environment variable must be set.</span></span> <span data-ttu-id="62665-209">应用程序配置文件通常与应用程序的可执行文件 (.exe) 位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="62665-209">The application configuration file is typically located in the same directory as the application's executable (.exe) file.</span></span> <span data-ttu-id="62665-210">文件名采用“ApplicationName.mda.config”形式；例如，notepad.exe.mda.config。在应用程序配置文件中启用的助手可能包含专门设计用于控制该助手的行为的特性或元素。</span><span class="sxs-lookup"><span data-stu-id="62665-210">The file name takes the form *ApplicationName*.mda.config; for example, notepad.exe.mda.config. Assistants that are enabled in the application configuration file may have attributes or elements specifically designed to control that assistant's behavior.</span></span> <span data-ttu-id="62665-211">下面的示例演示如何启用和配置 [marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md)。</span><span class="sxs-lookup"><span data-stu-id="62665-211">The following example shows how to enable and configure the [marshaling](../../../docs/framework/debug-trace-profile/marshaling-mda.md).</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="*"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="*"/>  
      </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
 <span data-ttu-id="62665-212">对于应用程序中每个托管到非托管的转换，`Marshaling` MDA 会发出有关正封送到非托管类型的托管类型信息。</span><span class="sxs-lookup"><span data-stu-id="62665-212">The `Marshaling` MDA emits information about the managed type that is being marshaled to an unmanaged type for each managed-to-unmanaged transition in the application.</span></span> <span data-ttu-id="62665-213">`Marshaling` MDA 还能够分别筛选 `<methodFilter>` 和 `<fieldFilter>` 子元素中提供的方法和结构字段的名称。</span><span class="sxs-lookup"><span data-stu-id="62665-213">The `Marshaling` MDA can also filter the names of the method and structure fields supplied in the `<methodFilter>` and `<fieldFilter>` child elements, respectively.</span></span>  
  
 <span data-ttu-id="62665-214">下面的示例演示如何使用其默认设置来启用多个 MDA。</span><span class="sxs-lookup"><span data-stu-id="62665-214">The following example shows how to enable multiple MDAs by using their default settings.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <illegalPrepareConstrainedRegion />  
    <invalidCERCall />  
    <openGenericCERCall />  
    <virtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="62665-215">若在配置文件中指定了多个助手，则必须按字母顺序列出这些助手。</span><span class="sxs-lookup"><span data-stu-id="62665-215">When you specify more than one assistant in a configuration file, you must list them in alphabetical order.</span></span> <span data-ttu-id="62665-216">例如，若要同时启用 `virtualCERCall` 和 `invalidCERCall` MDA，则必须先添加 `<invalidCERCall />` 项，再添加 `<virtualCERCall />` 项。</span><span class="sxs-lookup"><span data-stu-id="62665-216">For example, if you want to enable both the `virtualCERCall` and the `invalidCERCall` MDAs, you must add the `<invalidCERCall />` entry before the `<virtualCERCall />` entry.</span></span> <span data-ttu-id="62665-217">如果这些项未按字母顺序排列，将显示未处理的无效配置文件异常消息。</span><span class="sxs-lookup"><span data-stu-id="62665-217">If the entries are not in alphabetical order, an unhandled invalid configuration file exception message is displayed.</span></span>  
  
### <a name="mda-output"></a><span data-ttu-id="62665-218">MDA 输出</span><span class="sxs-lookup"><span data-stu-id="62665-218">MDA Output</span></span>  
 <span data-ttu-id="62665-219">MDA 输出类似于下面的示例，此示例显示了来自 `pInvokeStackImbalance` MDA 的输出。</span><span class="sxs-lookup"><span data-stu-id="62665-219">MDA output is similar to the following example, which shows the output from the `pInvokeStackImbalance` MDA.</span></span>  
  
 `A call to PInvoke function 'MDATest!MDATest.Program::StdCall' has unbalanced the stack. This is likely because the managed PInvoke signature does not match the unmanaged target signature. Check that the calling convention and parameters of the PInvoke signature match the target unmanaged signature.`  
  
## <a name="see-also"></a><span data-ttu-id="62665-220">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62665-220">See Also</span></span>  
 [<span data-ttu-id="62665-221">调试、跟踪和分析</span><span class="sxs-lookup"><span data-stu-id="62665-221">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)
