---
title: 弃用的 CLR 承载函数
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dde711f2d626d88fd80009fa83f1198dd9d47810
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490492"
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="45d1a-102">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="45d1a-103">本部分介绍早期版本的承载 API 使用的非托管全局静态函数。</span><span class="sxs-lookup"><span data-stu-id="45d1a-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="45d1a-104">除了基础结构函数 (`_Cor*`函数)，仅供.NET Framework，.NET Framework 4 中已弃用这些函数。</span><span class="sxs-lookup"><span data-stu-id="45d1a-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="45d1a-105">激活函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-105">Activation functions</span></span>  
 [<span data-ttu-id="45d1a-106">ClrCreateManagedInstance 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-106">ClrCreateManagedInstance Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="45d1a-107">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-107">Deprecated.</span></span> <span data-ttu-id="45d1a-108">创建指定的托管类型的实例。</span><span class="sxs-lookup"><span data-stu-id="45d1a-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="45d1a-109">CoInitializeCor 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-109">CoInitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 <span data-ttu-id="45d1a-110">已过时。</span><span class="sxs-lookup"><span data-stu-id="45d1a-110">Obsolete.</span></span> <span data-ttu-id="45d1a-111">若要初始化公共语言运行时 (CLR)，使用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或[CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)。</span><span class="sxs-lookup"><span data-stu-id="45d1a-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="45d1a-112">CoInitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-112">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 <span data-ttu-id="45d1a-113">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-113">Deprecated.</span></span> <span data-ttu-id="45d1a-114">确保 CLR 执行引擎已加载到进程。</span><span class="sxs-lookup"><span data-stu-id="45d1a-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="45d1a-115">使用[iclrruntimehost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="45d1a-115">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="45d1a-116">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-116">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 <span data-ttu-id="45d1a-117">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-117">Deprecated.</span></span> <span data-ttu-id="45d1a-118">通过使用版本信息的 XML 文件中存储公共语言运行时 (CLR) 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="45d1a-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="45d1a-119">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-119">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 <span data-ttu-id="45d1a-120">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-120">Deprecated.</span></span> <span data-ttu-id="45d1a-121">使非托管的宿主能够将 CLR 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="45d1a-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="45d1a-122">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-122">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="45d1a-123">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-123">Deprecated.</span></span> <span data-ttu-id="45d1a-124">通过使用从 XML 文件中读取的版本信息将 CLR 加载到进程中。</span><span class="sxs-lookup"><span data-stu-id="45d1a-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="45d1a-125">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-125">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 <span data-ttu-id="45d1a-126">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-126">Deprecated.</span></span> <span data-ttu-id="45d1a-127">启用非托管的宿主能够将 CLR 加载到进程中，并允许您设置标志以指定 CLR 的行为。</span><span class="sxs-lookup"><span data-stu-id="45d1a-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="45d1a-128">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 <span data-ttu-id="45d1a-129">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-129">Deprecated.</span></span> <span data-ttu-id="45d1a-130">使主机能够加载到进程的指定的版本的 CLR。</span><span class="sxs-lookup"><span data-stu-id="45d1a-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="45d1a-131">GetCORRequiredVersion 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-131">GetCORRequiredVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 <span data-ttu-id="45d1a-132">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-132">Deprecated.</span></span> <span data-ttu-id="45d1a-133">获取所需的 CLR 版本号。</span><span class="sxs-lookup"><span data-stu-id="45d1a-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="45d1a-134">GetCORSystemDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-134">GetCORSystemDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 <span data-ttu-id="45d1a-135">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-135">Deprecated.</span></span> <span data-ttu-id="45d1a-136">返回加载到进程中 CLR 的安装目录。</span><span class="sxs-lookup"><span data-stu-id="45d1a-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="45d1a-137">GetRealProcAddress 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-137">GetRealProcAddress Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 <span data-ttu-id="45d1a-138">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-138">Deprecated.</span></span> <span data-ttu-id="45d1a-139">获取指定从最新的已安装的 CLR 版本导出的函数的地址。</span><span class="sxs-lookup"><span data-stu-id="45d1a-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="45d1a-140">GetRequestedRuntimeInfo 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-140">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="45d1a-141">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-141">Deprecated.</span></span> <span data-ttu-id="45d1a-142">获取有关应用程序请求的 CLR 版本和目录信息。</span><span class="sxs-lookup"><span data-stu-id="45d1a-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="45d1a-143">CLR 转换函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-143">CLR version functions</span></span>  
 <span data-ttu-id="45d1a-144">在本部分中的函数返回 CLR 版本;它们不激活 CLR。</span><span class="sxs-lookup"><span data-stu-id="45d1a-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="45d1a-145">GetCORVersion 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-145">GetCORVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 <span data-ttu-id="45d1a-146">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-146">Deprecated.</span></span> <span data-ttu-id="45d1a-147">返回在当前进程中运行 CLR 的版本号。</span><span class="sxs-lookup"><span data-stu-id="45d1a-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="45d1a-148">GetFileVersion 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-148">GetFileVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 <span data-ttu-id="45d1a-149">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-149">Deprecated.</span></span> <span data-ttu-id="45d1a-150">获取指定的文件，使用指定的缓冲区的 CLR 版本信息。</span><span class="sxs-lookup"><span data-stu-id="45d1a-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="45d1a-151">GetRequestedRuntimeVersion 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-151">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 <span data-ttu-id="45d1a-152">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-152">Deprecated.</span></span> <span data-ttu-id="45d1a-153">获取由指定的应用程序请求的 CLR 的版本号。</span><span class="sxs-lookup"><span data-stu-id="45d1a-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="45d1a-154">如果未安装该版本，获取所请求的版本之前已安装的最新版本。</span><span class="sxs-lookup"><span data-stu-id="45d1a-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="45d1a-155">GetRequestedRuntimeVersionForCLSID 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="45d1a-156">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-156">Deprecated.</span></span> <span data-ttu-id="45d1a-157">获取具有指定 CLSID 的类的适当 CLR 版本信息。</span><span class="sxs-lookup"><span data-stu-id="45d1a-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="45d1a-158">GetVersionFromProcess 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-158">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 <span data-ttu-id="45d1a-159">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-159">Deprecated.</span></span> <span data-ttu-id="45d1a-160">获取与指定的进程句柄关联的 CLR 的版本号。</span><span class="sxs-lookup"><span data-stu-id="45d1a-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="45d1a-161">LockClrVersion 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-161">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 <span data-ttu-id="45d1a-162">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-162">Deprecated.</span></span> <span data-ttu-id="45d1a-163">允许宿主确定在进行显式初始化 CLR 之前将在进程中使用 CLR 的版本。</span><span class="sxs-lookup"><span data-stu-id="45d1a-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="45d1a-164">承载函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-164">Hosting functions</span></span>  
 [<span data-ttu-id="45d1a-165">CallFunctionShim 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-165">CallFunctionShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 <span data-ttu-id="45d1a-166">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-166">Deprecated.</span></span> <span data-ttu-id="45d1a-167">将指定的库中具有指定的名称和参数的函数调用。</span><span class="sxs-lookup"><span data-stu-id="45d1a-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="45d1a-168">CoEEShutDownCOM 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-168">CoEEShutDownCOM Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 <span data-ttu-id="45d1a-169">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-169">Deprecated.</span></span> <span data-ttu-id="45d1a-170">卸载过程中的 COM 程序集。</span><span class="sxs-lookup"><span data-stu-id="45d1a-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="45d1a-171">CorExitProcess 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-171">CorExitProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 <span data-ttu-id="45d1a-172">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-172">Deprecated.</span></span> <span data-ttu-id="45d1a-173">关闭当前的非托管进程。</span><span class="sxs-lookup"><span data-stu-id="45d1a-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="45d1a-174">CorLaunchApplication 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-174">CorLaunchApplication Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 <span data-ttu-id="45d1a-175">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-175">Deprecated.</span></span> <span data-ttu-id="45d1a-176">启动指定的网络路径，使用指定的清单和其他应用程序数据的应用程序。</span><span class="sxs-lookup"><span data-stu-id="45d1a-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="45d1a-177">CorMarkThreadInThreadPool 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-177">CorMarkThreadInThreadPool Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="45d1a-178">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-178">Deprecated.</span></span> <span data-ttu-id="45d1a-179">将标记为托管代码的执行当前正在执行的线程池线程。</span><span class="sxs-lookup"><span data-stu-id="45d1a-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="45d1a-180">从.NET Framework 2.0 版开始，此函数没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="45d1a-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="45d1a-181">它不是必需的并可以从你的代码。</span><span class="sxs-lookup"><span data-stu-id="45d1a-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="45d1a-182">CoUninitializeCor 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-182">CoUninitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 <span data-ttu-id="45d1a-183">已过时。</span><span class="sxs-lookup"><span data-stu-id="45d1a-183">Obsolete.</span></span> <span data-ttu-id="45d1a-184">CLR 不能从进程中卸载。</span><span class="sxs-lookup"><span data-stu-id="45d1a-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="45d1a-185">CoUninitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-185">CoUninitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 <span data-ttu-id="45d1a-186">已过时。</span><span class="sxs-lookup"><span data-stu-id="45d1a-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="45d1a-187">CreateDebuggingInterfaceFromVersion 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-187">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="45d1a-188">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-188">Deprecated.</span></span> <span data-ttu-id="45d1a-189">创建[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)对象根据指定的版本信息。</span><span class="sxs-lookup"><span data-stu-id="45d1a-189">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="45d1a-190">CreateICeeFileGen 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-190">CreateICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 <span data-ttu-id="45d1a-191">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-191">Deprecated.</span></span> <span data-ttu-id="45d1a-192">创建[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)对象。</span><span class="sxs-lookup"><span data-stu-id="45d1a-192">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="45d1a-193">DestroyICeeFileGen 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-193">DestroyICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 <span data-ttu-id="45d1a-194">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-194">Deprecated.</span></span> <span data-ttu-id="45d1a-195">销毁[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)对象。</span><span class="sxs-lookup"><span data-stu-id="45d1a-195">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="45d1a-196">FExecuteInAppDomainCallback 函数指针</span><span class="sxs-lookup"><span data-stu-id="45d1a-196">FExecuteInAppDomainCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="45d1a-197">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-197">Deprecated.</span></span> <span data-ttu-id="45d1a-198">指向 CLR 调用以执行托管的代码的函数。</span><span class="sxs-lookup"><span data-stu-id="45d1a-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="45d1a-199">FLockClrVersionCallback 函数指针</span><span class="sxs-lookup"><span data-stu-id="45d1a-199">FLockClrVersionCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="45d1a-200">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-200">Deprecated.</span></span> <span data-ttu-id="45d1a-201">指向 CLR 调用以通知宿主的函数的初始化已开始或完成。</span><span class="sxs-lookup"><span data-stu-id="45d1a-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="45d1a-202">GetCLRIdentityManager 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-202">GetCLRIdentityManager Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 <span data-ttu-id="45d1a-203">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-203">Deprecated.</span></span> <span data-ttu-id="45d1a-204">获取一个指针指向允许 CLR 管理标识的接口。</span><span class="sxs-lookup"><span data-stu-id="45d1a-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="45d1a-205">LoadLibraryShim 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-205">LoadLibraryShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 <span data-ttu-id="45d1a-206">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-206">Deprecated.</span></span> <span data-ttu-id="45d1a-207">加载指定的版本的.NET Framework DLL。</span><span class="sxs-lookup"><span data-stu-id="45d1a-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="45d1a-208">LoadStringRC 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-208">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 <span data-ttu-id="45d1a-209">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-209">Deprecated.</span></span> <span data-ttu-id="45d1a-210">通过使用当前线程的默认区域性将 HRESULT 值转换成一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="45d1a-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="45d1a-211">LoadStringRCEx 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-211">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 <span data-ttu-id="45d1a-212">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-212">Deprecated.</span></span> <span data-ttu-id="45d1a-213">将转换为相应的错误消息为指定的区域性的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="45d1a-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="45d1a-214">LPOVERLAPPED_COMPLETION_ROUTINE 函数指针</span><span class="sxs-lookup"><span data-stu-id="45d1a-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="45d1a-215">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-215">Deprecated.</span></span> <span data-ttu-id="45d1a-216">指向通知主机时的重叠的函数 (即异步) 到设备的 I/O 已完成。</span><span class="sxs-lookup"><span data-stu-id="45d1a-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="45d1a-217">LPTHREAD_START_ROUTINE 函数指针</span><span class="sxs-lookup"><span data-stu-id="45d1a-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="45d1a-218">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-218">Deprecated.</span></span> <span data-ttu-id="45d1a-219">指向通知宿主某个线程已开始执行的函数。</span><span class="sxs-lookup"><span data-stu-id="45d1a-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="45d1a-220">RunDll32ShimW 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-220">RunDll32ShimW Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 <span data-ttu-id="45d1a-221">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-221">Deprecated.</span></span> <span data-ttu-id="45d1a-222">执行指定的命令。</span><span class="sxs-lookup"><span data-stu-id="45d1a-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="45d1a-223">WAITORTIMERCALLBACK 函数指针</span><span class="sxs-lookup"><span data-stu-id="45d1a-223">WAITORTIMERCALLBACK Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 <span data-ttu-id="45d1a-224">已否决。</span><span class="sxs-lookup"><span data-stu-id="45d1a-224">Deprecated.</span></span> <span data-ttu-id="45d1a-225">指向函数通知宿主，等待句柄已收到信号或操作已超时。</span><span class="sxs-lookup"><span data-stu-id="45d1a-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="45d1a-226">基础结构函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-226">Infrastructure functions</span></span>  
 <span data-ttu-id="45d1a-227">在本部分中的函数是用于仅在.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="45d1a-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="45d1a-228">_CorDllMain 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-228">_CorDllMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 <span data-ttu-id="45d1a-229">初始化 CLR，查找托管的入口点 DLL 程序集 CLR 头中，并开始执行。</span><span class="sxs-lookup"><span data-stu-id="45d1a-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="45d1a-230">_CorExeMain 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-230">_CorExeMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 <span data-ttu-id="45d1a-231">初始化 CLR，查找托管的入口点的可执行程序集 CLR 头中，并开始执行。</span><span class="sxs-lookup"><span data-stu-id="45d1a-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="45d1a-232">_CorExeMain2 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-232">_CorExeMain2 Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 <span data-ttu-id="45d1a-233">在指定的内存映射代码中执行的入口点。</span><span class="sxs-lookup"><span data-stu-id="45d1a-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="45d1a-234">由操作系统加载程序调用此函数。</span><span class="sxs-lookup"><span data-stu-id="45d1a-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="45d1a-235">_CorImageUnloading 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-235">_CorImageUnloading Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 <span data-ttu-id="45d1a-236">卸载托管的模块映像时通知加载程序。</span><span class="sxs-lookup"><span data-stu-id="45d1a-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="45d1a-237">_CorValidateImage 函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-237">_CorValidateImage Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 <span data-ttu-id="45d1a-238">验证托管的模块映像，并已加载后通知操作系统加载程序。</span><span class="sxs-lookup"><span data-stu-id="45d1a-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d1a-239">请参阅</span><span class="sxs-lookup"><span data-stu-id="45d1a-239">See also</span></span>

- [<span data-ttu-id="45d1a-240">.NET Framework 4 承载全局静态函数</span><span class="sxs-lookup"><span data-stu-id="45d1a-240">.NET Framework 4 Hosting Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md)
