---
title: 弃用的 CLR 承载函数
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 62773ce526b1f21c57ab85a106708589fcf92f6f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138272"
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="79f69-102">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="79f69-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="79f69-103">本部分介绍了早期版本的托管 API 使用的非托管全局静态函数。</span><span class="sxs-lookup"><span data-stu-id="79f69-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="79f69-104">除了仅供 .NET Framework 使用的基础结构函数（`_Cor*` 函数）以外，.NET Framework 4 中已弃用这些函数。</span><span class="sxs-lookup"><span data-stu-id="79f69-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="79f69-105">激活函数</span><span class="sxs-lookup"><span data-stu-id="79f69-105">Activation functions</span></span>  
 [<span data-ttu-id="79f69-106">ClrCreateManagedInstance 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-106">ClrCreateManagedInstance Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="79f69-107">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-107">Deprecated.</span></span> <span data-ttu-id="79f69-108">创建指定托管类型的实例。</span><span class="sxs-lookup"><span data-stu-id="79f69-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="79f69-109">CoInitializeCor 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-109">CoInitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 <span data-ttu-id="79f69-110">已过时。</span><span class="sxs-lookup"><span data-stu-id="79f69-110">Obsolete.</span></span> <span data-ttu-id="79f69-111">若要初始化公共语言运行时（CLR），请使用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或[CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)。</span><span class="sxs-lookup"><span data-stu-id="79f69-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="79f69-112">CoInitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-112">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 <span data-ttu-id="79f69-113">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-113">Deprecated.</span></span> <span data-ttu-id="79f69-114">确保 CLR 执行引擎已加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="79f69-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="79f69-115">改为使用[ICLRRuntimeHost：： Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="79f69-115">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="79f69-116">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-116">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 <span data-ttu-id="79f69-117">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-117">Deprecated.</span></span> <span data-ttu-id="79f69-118">使用存储在 XML 文件中的版本信息将公共语言运行时（CLR）加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="79f69-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="79f69-119">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-119">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 <span data-ttu-id="79f69-120">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-120">Deprecated.</span></span> <span data-ttu-id="79f69-121">使非托管宿主能够将 CLR 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="79f69-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="79f69-122">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-122">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="79f69-123">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-123">Deprecated.</span></span> <span data-ttu-id="79f69-124">使用从 XML 文件读取的版本信息将 CLR 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="79f69-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="79f69-125">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-125">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 <span data-ttu-id="79f69-126">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-126">Deprecated.</span></span> <span data-ttu-id="79f69-127">使非托管宿主能够将 CLR 加载到进程中，并允许您设置标志来指定 CLR 的行为。</span><span class="sxs-lookup"><span data-stu-id="79f69-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="79f69-128">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 <span data-ttu-id="79f69-129">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-129">Deprecated.</span></span> <span data-ttu-id="79f69-130">使宿主可以将指定版本的 CLR 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="79f69-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="79f69-131">GetCORRequiredVersion 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-131">GetCORRequiredVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 <span data-ttu-id="79f69-132">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-132">Deprecated.</span></span> <span data-ttu-id="79f69-133">获取所需的 CLR 版本号。</span><span class="sxs-lookup"><span data-stu-id="79f69-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="79f69-134">GetCORSystemDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-134">GetCORSystemDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 <span data-ttu-id="79f69-135">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-135">Deprecated.</span></span> <span data-ttu-id="79f69-136">返回加载到进程中的 CLR 的安装目录。</span><span class="sxs-lookup"><span data-stu-id="79f69-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="79f69-137">GetRealProcAddress 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-137">GetRealProcAddress Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 <span data-ttu-id="79f69-138">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-138">Deprecated.</span></span> <span data-ttu-id="79f69-139">获取从安装的最新版本的 CLR 导出的指定函数的地址。</span><span class="sxs-lookup"><span data-stu-id="79f69-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="79f69-140">GetRequestedRuntimeInfo 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-140">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="79f69-141">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-141">Deprecated.</span></span> <span data-ttu-id="79f69-142">获取有关应用程序请求的 CLR 的版本和目录信息。</span><span class="sxs-lookup"><span data-stu-id="79f69-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="79f69-143">CLR 版本函数</span><span class="sxs-lookup"><span data-stu-id="79f69-143">CLR version functions</span></span>  
 <span data-ttu-id="79f69-144">本节中的函数返回 CLR 版本;它们不激活 CLR。</span><span class="sxs-lookup"><span data-stu-id="79f69-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="79f69-145">GetCORVersion 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-145">GetCORVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 <span data-ttu-id="79f69-146">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-146">Deprecated.</span></span> <span data-ttu-id="79f69-147">返回当前进程中正在运行的 CLR 的版本号。</span><span class="sxs-lookup"><span data-stu-id="79f69-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="79f69-148">GetFileVersion 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-148">GetFileVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 <span data-ttu-id="79f69-149">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-149">Deprecated.</span></span> <span data-ttu-id="79f69-150">使用指定的缓冲区获取指定文件的 CLR 版本信息。</span><span class="sxs-lookup"><span data-stu-id="79f69-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="79f69-151">GetRequestedRuntimeVersion 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-151">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 <span data-ttu-id="79f69-152">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-152">Deprecated.</span></span> <span data-ttu-id="79f69-153">获取指定应用程序请求的 CLR 的版本号。</span><span class="sxs-lookup"><span data-stu-id="79f69-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="79f69-154">如果未安装该版本，则获取在请求版本之前安装的最新版本。</span><span class="sxs-lookup"><span data-stu-id="79f69-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="79f69-155">GetRequestedRuntimeVersionForCLSID 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="79f69-156">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-156">Deprecated.</span></span> <span data-ttu-id="79f69-157">获取具有指定 CLSID 的类的相应 CLR 版本信息。</span><span class="sxs-lookup"><span data-stu-id="79f69-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="79f69-158">GetVersionFromProcess 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-158">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 <span data-ttu-id="79f69-159">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-159">Deprecated.</span></span> <span data-ttu-id="79f69-160">获取与指定的进程句柄关联的 CLR 的版本号。</span><span class="sxs-lookup"><span data-stu-id="79f69-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="79f69-161">LockClrVersion 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-161">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 <span data-ttu-id="79f69-162">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-162">Deprecated.</span></span> <span data-ttu-id="79f69-163">允许主机在显式初始化 CLR 之前确定将在进程内使用的 CLR 版本。</span><span class="sxs-lookup"><span data-stu-id="79f69-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="79f69-164">承载函数</span><span class="sxs-lookup"><span data-stu-id="79f69-164">Hosting functions</span></span>  
 [<span data-ttu-id="79f69-165">CallFunctionShim 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-165">CallFunctionShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 <span data-ttu-id="79f69-166">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-166">Deprecated.</span></span> <span data-ttu-id="79f69-167">对指定库中具有指定名称和参数的函数进行调用。</span><span class="sxs-lookup"><span data-stu-id="79f69-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="79f69-168">CoEEShutDownCOM 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-168">CoEEShutDownCOM Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 <span data-ttu-id="79f69-169">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-169">Deprecated.</span></span> <span data-ttu-id="79f69-170">从进程中卸载 COM 程序集。</span><span class="sxs-lookup"><span data-stu-id="79f69-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="79f69-171">CorExitProcess 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-171">CorExitProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 <span data-ttu-id="79f69-172">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-172">Deprecated.</span></span> <span data-ttu-id="79f69-173">关闭当前的非托管进程。</span><span class="sxs-lookup"><span data-stu-id="79f69-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="79f69-174">CorLaunchApplication 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-174">CorLaunchApplication Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 <span data-ttu-id="79f69-175">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-175">Deprecated.</span></span> <span data-ttu-id="79f69-176">使用指定的清单和其他应用程序数据，在指定的网络路径下启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="79f69-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="79f69-177">CorMarkThreadInThreadPool 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-177">CorMarkThreadInThreadPool Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="79f69-178">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-178">Deprecated.</span></span> <span data-ttu-id="79f69-179">标记当前正在执行的线程池线程以执行托管代码。</span><span class="sxs-lookup"><span data-stu-id="79f69-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="79f69-180">从 .NET Framework 版本2.0 开始，此函数不起作用。</span><span class="sxs-lookup"><span data-stu-id="79f69-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="79f69-181">这不是必需的，并且可以从代码中删除。</span><span class="sxs-lookup"><span data-stu-id="79f69-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="79f69-182">CoUninitializeCor 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-182">CoUninitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 <span data-ttu-id="79f69-183">已过时。</span><span class="sxs-lookup"><span data-stu-id="79f69-183">Obsolete.</span></span> <span data-ttu-id="79f69-184">CLR 无法从进程中卸载。</span><span class="sxs-lookup"><span data-stu-id="79f69-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="79f69-185">CoUninitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-185">CoUninitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 <span data-ttu-id="79f69-186">已过时。</span><span class="sxs-lookup"><span data-stu-id="79f69-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="79f69-187">CreateDebuggingInterfaceFromVersion 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-187">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="79f69-188">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-188">Deprecated.</span></span> <span data-ttu-id="79f69-189">基于指定的版本信息创建[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="79f69-189">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="79f69-190">CreateICeeFileGen 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-190">CreateICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 <span data-ttu-id="79f69-191">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-191">Deprecated.</span></span> <span data-ttu-id="79f69-192">创建[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)对象。</span><span class="sxs-lookup"><span data-stu-id="79f69-192">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="79f69-193">DestroyICeeFileGen 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-193">DestroyICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 <span data-ttu-id="79f69-194">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-194">Deprecated.</span></span> <span data-ttu-id="79f69-195">销毁[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)对象。</span><span class="sxs-lookup"><span data-stu-id="79f69-195">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="79f69-196">FExecuteInAppDomainCallback 函数指针</span><span class="sxs-lookup"><span data-stu-id="79f69-196">FExecuteInAppDomainCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="79f69-197">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-197">Deprecated.</span></span> <span data-ttu-id="79f69-198">指向 CLR 调用以执行托管代码的函数。</span><span class="sxs-lookup"><span data-stu-id="79f69-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="79f69-199">FLockClrVersionCallback 函数指针</span><span class="sxs-lookup"><span data-stu-id="79f69-199">FLockClrVersionCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="79f69-200">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-200">Deprecated.</span></span> <span data-ttu-id="79f69-201">指向一个函数，CLR 将调用该函数以通知宿主初始化已启动或已完成。</span><span class="sxs-lookup"><span data-stu-id="79f69-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="79f69-202">GetCLRIdentityManager 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-202">GetCLRIdentityManager Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 <span data-ttu-id="79f69-203">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-203">Deprecated.</span></span> <span data-ttu-id="79f69-204">获取一个指向接口的指针，该接口允许 CLR 管理标识。</span><span class="sxs-lookup"><span data-stu-id="79f69-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="79f69-205">LoadLibraryShim 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-205">LoadLibraryShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 <span data-ttu-id="79f69-206">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-206">Deprecated.</span></span> <span data-ttu-id="79f69-207">加载 .NET Framework DLL 的指定版本。</span><span class="sxs-lookup"><span data-stu-id="79f69-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="79f69-208">LoadStringRC 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-208">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 <span data-ttu-id="79f69-209">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-209">Deprecated.</span></span> <span data-ttu-id="79f69-210">使用当前线程的默认区域性将 HRESULT 值转换为错误消息。</span><span class="sxs-lookup"><span data-stu-id="79f69-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="79f69-211">LoadStringRCEx 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-211">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 <span data-ttu-id="79f69-212">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-212">Deprecated.</span></span> <span data-ttu-id="79f69-213">将 HRESULT 值转换为指定区域性的适当错误消息。</span><span class="sxs-lookup"><span data-stu-id="79f69-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="79f69-214">LPOVERLAPPED_COMPLETION_ROUTINE 函数指针</span><span class="sxs-lookup"><span data-stu-id="79f69-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="79f69-215">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-215">Deprecated.</span></span> <span data-ttu-id="79f69-216">指向一个函数，该函数在设备的重叠（即异步） i/o 完成时通知宿主。</span><span class="sxs-lookup"><span data-stu-id="79f69-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="79f69-217">LPTHREAD_START_ROUTINE 函数指针</span><span class="sxs-lookup"><span data-stu-id="79f69-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="79f69-218">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-218">Deprecated.</span></span> <span data-ttu-id="79f69-219">指向一个函数，该函数通知宿主线程已开始执行。</span><span class="sxs-lookup"><span data-stu-id="79f69-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="79f69-220">RunDll32ShimW 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-220">RunDll32ShimW Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 <span data-ttu-id="79f69-221">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-221">Deprecated.</span></span> <span data-ttu-id="79f69-222">执行指定的命令。</span><span class="sxs-lookup"><span data-stu-id="79f69-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="79f69-223">WAITORTIMERCALLBACK 函数指针</span><span class="sxs-lookup"><span data-stu-id="79f69-223">WAITORTIMERCALLBACK Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 <span data-ttu-id="79f69-224">已否决。</span><span class="sxs-lookup"><span data-stu-id="79f69-224">Deprecated.</span></span> <span data-ttu-id="79f69-225">指向一个函数，该函数通知宿主等待句柄已终止或超时。</span><span class="sxs-lookup"><span data-stu-id="79f69-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="79f69-226">基础结构函数</span><span class="sxs-lookup"><span data-stu-id="79f69-226">Infrastructure functions</span></span>  
 <span data-ttu-id="79f69-227">本节中的函数仅供 .NET Framework 使用。</span><span class="sxs-lookup"><span data-stu-id="79f69-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="79f69-228">_CorDllMain 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-228">_CorDllMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 <span data-ttu-id="79f69-229">初始化 CLR，查找 DLL 程序集的 CLR 头中的托管入口点，然后开始执行。</span><span class="sxs-lookup"><span data-stu-id="79f69-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="79f69-230">_CorExeMain 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-230">_CorExeMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 <span data-ttu-id="79f69-231">初始化 CLR，查找可执行程序集的 CLR 头中的托管入口点，然后开始执行。</span><span class="sxs-lookup"><span data-stu-id="79f69-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="79f69-232">_CorExeMain2 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-232">_CorExeMain2 Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 <span data-ttu-id="79f69-233">执行指定的内存映射代码中的入口点。</span><span class="sxs-lookup"><span data-stu-id="79f69-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="79f69-234">此函数由操作系统加载程序调用。</span><span class="sxs-lookup"><span data-stu-id="79f69-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="79f69-235">_CorImageUnloading 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-235">_CorImageUnloading Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 <span data-ttu-id="79f69-236">卸载托管模块映像时通知加载程序。</span><span class="sxs-lookup"><span data-stu-id="79f69-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="79f69-237">_CorValidateImage 函数</span><span class="sxs-lookup"><span data-stu-id="79f69-237">_CorValidateImage Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 <span data-ttu-id="79f69-238">验证托管模块映像，并在加载后通知操作系统加载程序。</span><span class="sxs-lookup"><span data-stu-id="79f69-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79f69-239">请参阅</span><span class="sxs-lookup"><span data-stu-id="79f69-239">See also</span></span>

- [<span data-ttu-id="79f69-240">.NET Framework 4 承载全局静态函数</span><span class="sxs-lookup"><span data-stu-id="79f69-240">.NET Framework 4 Hosting Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md)
