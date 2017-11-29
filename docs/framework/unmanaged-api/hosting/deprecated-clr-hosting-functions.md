---
title: "弃用的 CLR 承载函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9530fecb4f2ca6f59d165e49c282320966fd2fa8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="deprecated-clr-hosting-functions"></a><span data-ttu-id="5e5ee-102">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-102">Deprecated CLR Hosting Functions</span></span>
<span data-ttu-id="5e5ee-103">本部分介绍的托管 API 的早期版本使用的非托管全局静态函数。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-103">This section describes the unmanaged global static functions that earlier versions of the hosting API used.</span></span>  
  
 <span data-ttu-id="5e5ee-104">除了基础结构函数 (`_Cor*`函数)，用于仅由.NET Framework，这些函数中已弃用[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-104">With the exception of the infrastructure functions (`_Cor*` functions), which are used only by the .NET Framework, these functions have been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="activation-functions"></a><span data-ttu-id="5e5ee-105">激活函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-105">Activation functions</span></span>  
 [<span data-ttu-id="5e5ee-106">ClrCreateManagedInstance 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-106">ClrCreateManagedInstance Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrcreatemanagedinstance-function.md)  
 <span data-ttu-id="5e5ee-107">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-107">Deprecated.</span></span> <span data-ttu-id="5e5ee-108">创建指定的托管类型的实例。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-108">Creates an instance of the specified managed type.</span></span>  
  
 [<span data-ttu-id="5e5ee-109">CoInitializeCor 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-109">CoInitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializecor-function.md)  
 <span data-ttu-id="5e5ee-110">已过时。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-110">Obsolete.</span></span> <span data-ttu-id="5e5ee-111">若要初始化公共语言运行时 (CLR)，使用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或[CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-111">To initialize the common language runtime (CLR), use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
 [<span data-ttu-id="5e5ee-112">CoInitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-112">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)  
 <span data-ttu-id="5e5ee-113">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-113">Deprecated.</span></span> <span data-ttu-id="5e5ee-114">确保 CLR 执行引擎已加载到进程。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-114">Ensures that the CLR execution engine is loaded into a process.</span></span> <span data-ttu-id="5e5ee-115">使用[iclrruntimehost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-115">Use the [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method instead.</span></span>  
  
 [<span data-ttu-id="5e5ee-116">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-116">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 <span data-ttu-id="5e5ee-117">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-117">Deprecated.</span></span> <span data-ttu-id="5e5ee-118">通过使用版本信息存储在 XML 文件中，到的进程中加载公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-118">Loads the common language runtime (CLR) into a process by using version information stored in an XML file.</span></span>  
  
 [<span data-ttu-id="5e5ee-119">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-119">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 <span data-ttu-id="5e5ee-120">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-120">Deprecated.</span></span> <span data-ttu-id="5e5ee-121">使非托管的宿主能够将 CLR 加载到过程中。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-121">Enables unmanaged hosts to load the CLR into a process.</span></span>  
  
 [<span data-ttu-id="5e5ee-122">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-122">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 <span data-ttu-id="5e5ee-123">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-123">Deprecated.</span></span> <span data-ttu-id="5e5ee-124">通过使用从 XML 文件中读取的版本信息加载到进程的 CLR。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-124">Loads the CLR into a process by using version information that is read from an XML file.</span></span>  
  
 [<span data-ttu-id="5e5ee-125">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-125">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 <span data-ttu-id="5e5ee-126">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-126">Deprecated.</span></span> <span data-ttu-id="5e5ee-127">提供非托管的宿主能够将 CLR 加载到进程中，并允许你设置标志以指定的 CLR 的行为。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-127">Enables unmanaged hosts to load the CLR into a process, and allows you to set flags to specify the behavior of the CLR.</span></span>  
  
 [<span data-ttu-id="5e5ee-128">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 <span data-ttu-id="5e5ee-129">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-129">Deprecated.</span></span> <span data-ttu-id="5e5ee-130">使主机可以加载到进程的 CLR 的指定的版本。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-130">Enables hosts to load a specified version of the CLR into a process.</span></span>  
  
 [<span data-ttu-id="5e5ee-131">GetCORRequiredVersion 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-131">GetCORRequiredVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorrequiredversion-function.md)  
 <span data-ttu-id="5e5ee-132">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-132">Deprecated.</span></span> <span data-ttu-id="5e5ee-133">获取所需的 CLR 版本数量。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-133">Gets the required CLR version number.</span></span>  
  
 [<span data-ttu-id="5e5ee-134">GetCORSystemDirectory 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-134">GetCORSystemDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md)  
 <span data-ttu-id="5e5ee-135">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-135">Deprecated.</span></span> <span data-ttu-id="5e5ee-136">返回加载到进程的 CLR 的安装目录。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-136">Returns the installation directory of the CLR that is loaded into the process.</span></span>  
  
 [<span data-ttu-id="5e5ee-137">GetRealProcAddress 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-137">GetRealProcAddress Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md)  
 <span data-ttu-id="5e5ee-138">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-138">Deprecated.</span></span> <span data-ttu-id="5e5ee-139">获取指定从最新的已安装的 CLR 版本导出的函数的地址。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-139">Gets the address of the specified function that is exported from the latest installed version of the CLR.</span></span>  
  
 [<span data-ttu-id="5e5ee-140">GetRequestedRuntimeInfo 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-140">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 <span data-ttu-id="5e5ee-141">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-141">Deprecated.</span></span> <span data-ttu-id="5e5ee-142">获取有关应用程序请求的 CLR 版本和目录信息。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-142">Gets version and directory information about the CLR requested by an application.</span></span>  
  
## <a name="clr-version-functions"></a><span data-ttu-id="5e5ee-143">CLR 版本函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-143">CLR version functions</span></span>  
 <span data-ttu-id="5e5ee-144">本部分中的函数返回的 CLR 版本;它们不激活 CLR。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-144">The functions in this section return a CLR version; they do not activate the CLR.</span></span>  
  
 [<span data-ttu-id="5e5ee-145">GetCORVersion 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-145">GetCORVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getcorversion-function.md)  
 <span data-ttu-id="5e5ee-146">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-146">Deprecated.</span></span> <span data-ttu-id="5e5ee-147">返回在当前进程中运行 CLR 的版本号。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-147">Returns the version number of the CLR that is running in the current process.</span></span>  
  
 [<span data-ttu-id="5e5ee-148">GetFileVersion 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-148">GetFileVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md)  
 <span data-ttu-id="5e5ee-149">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-149">Deprecated.</span></span> <span data-ttu-id="5e5ee-150">获取指定的文件，使用指定的缓冲区的 CLR 版本信息。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-150">Gets the CLR version information of the specified file, using the specified buffer.</span></span>  
  
 [<span data-ttu-id="5e5ee-151">GetRequestedRuntimeVersion 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-151">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 <span data-ttu-id="5e5ee-152">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-152">Deprecated.</span></span> <span data-ttu-id="5e5ee-153">获取由指定的应用程序请求的 CLR 的版本号。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-153">Gets the version number of the CLR requested by the specified application.</span></span> <span data-ttu-id="5e5ee-154">如果未安装该版本，获取在请求的版本之前安装了最新版本。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-154">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 [<span data-ttu-id="5e5ee-155">GetRequestedRuntimeVersionForCLSID 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-155">GetRequestedRuntimeVersionForCLSID Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversionforclsid-function.md)  
 <span data-ttu-id="5e5ee-156">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-156">Deprecated.</span></span> <span data-ttu-id="5e5ee-157">获取具有指定的 CLSID 的类的相应 CLR 版本信息。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-157">Gets the appropriate CLR version information for the class with the specified CLSID.</span></span>  
  
 [<span data-ttu-id="5e5ee-158">GetVersionFromProcess 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-158">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 <span data-ttu-id="5e5ee-159">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-159">Deprecated.</span></span> <span data-ttu-id="5e5ee-160">获取与指定的进程句柄关联的 CLR 的版本号。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-160">Gets the version number of the CLR that is associated with the specified process handle.</span></span>  
  
 [<span data-ttu-id="5e5ee-161">LockClrVersion 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-161">LockClrVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md)  
 <span data-ttu-id="5e5ee-162">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-162">Deprecated.</span></span> <span data-ttu-id="5e5ee-163">允许宿主确定在进行显式初始化 CLR 之前将在过程内使用 CLR 的版本。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-163">Allows the host to determine which version of the CLR will be used within the process before explicitly initializing the CLR.</span></span>  
  
## <a name="hosting-functions"></a><span data-ttu-id="5e5ee-164">承载函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-164">Hosting functions</span></span>  
 [<span data-ttu-id="5e5ee-165">CallFunctionShim 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-165">CallFunctionShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/callfunctionshim-function.md)  
 <span data-ttu-id="5e5ee-166">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-166">Deprecated.</span></span> <span data-ttu-id="5e5ee-167">将指定的库中具有指定的名称和参数的函数调用。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-167">Makes a call to the function that has the specified name and parameters in the specified library.</span></span>  
  
 [<span data-ttu-id="5e5ee-168">CoEEShutDownCOM 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-168">CoEEShutDownCOM Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coeeshutdowncom-function.md)  
 <span data-ttu-id="5e5ee-169">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-169">Deprecated.</span></span> <span data-ttu-id="5e5ee-170">卸载过程中的 COM 程序集。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-170">Unloads a COM assembly from the process.</span></span>  
  
 [<span data-ttu-id="5e5ee-171">CorExitProcess 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-171">CorExitProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)  
 <span data-ttu-id="5e5ee-172">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-172">Deprecated.</span></span> <span data-ttu-id="5e5ee-173">关闭当前的非托管进程。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-173">Shuts down the current unmanaged process.</span></span>  
  
 [<span data-ttu-id="5e5ee-174">CorLaunchApplication 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-174">CorLaunchApplication Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corlaunchapplication-function.md)  
 <span data-ttu-id="5e5ee-175">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-175">Deprecated.</span></span> <span data-ttu-id="5e5ee-176">启动位于指定的网络路径，使用指定的清单和其他应用程序数据的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-176">Starts the application at the specified network path, using the specified manifests and other application data.</span></span>  
  
 [<span data-ttu-id="5e5ee-177">CorMarkThreadInThreadPool 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-177">CorMarkThreadInThreadPool Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cormarkthreadinthreadpool-function.md)  
 <span data-ttu-id="5e5ee-178">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-178">Deprecated.</span></span> <span data-ttu-id="5e5ee-179">将标记为托管代码的执行当前正在执行的线程池线程。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-179">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="5e5ee-180">从.NET Framework 2.0 版开始，此函数不起作用。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-180">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="5e5ee-181">它不是必需的并且可以在代码中删除。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-181">It is not required, and can be removed from your code.</span></span>  
  
 [<span data-ttu-id="5e5ee-182">CoUninitializeCor 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-182">CoUninitializeCor Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)  
 <span data-ttu-id="5e5ee-183">已过时。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-183">Obsolete.</span></span> <span data-ttu-id="5e5ee-184">CLR 不能为从进程中卸载。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-184">The CLR cannot be unloaded from a process.</span></span>  
  
 [<span data-ttu-id="5e5ee-185">CoUninitializeEE 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-185">CoUninitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md)  
 <span data-ttu-id="5e5ee-186">已过时。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-186">Obsolete.</span></span>  
  
 [<span data-ttu-id="5e5ee-187">CreateDebuggingInterfaceFromVersion 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-187">CreateDebuggingInterfaceFromVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md)  
 <span data-ttu-id="5e5ee-188">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-188">Deprecated.</span></span> <span data-ttu-id="5e5ee-189">创建[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)对象根据指定的版本信息。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-189">Creates an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) object based on the specified version information.</span></span>  
  
 [<span data-ttu-id="5e5ee-190">CreateICeeFileGen 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-190">CreateICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md)  
 <span data-ttu-id="5e5ee-191">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-191">Deprecated.</span></span> <span data-ttu-id="5e5ee-192">创建[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)对象。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-192">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="5e5ee-193">DestroyICeeFileGen 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-193">DestroyICeeFileGen Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md)  
 <span data-ttu-id="5e5ee-194">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-194">Deprecated.</span></span> <span data-ttu-id="5e5ee-195">销毁[ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md)对象。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-195">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 [<span data-ttu-id="5e5ee-196">FExecuteInAppDomainCallback 函数指针</span><span class="sxs-lookup"><span data-stu-id="5e5ee-196">FExecuteInAppDomainCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/fexecuteinappdomaincallback-function-pointer.md)  
 <span data-ttu-id="5e5ee-197">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-197">Deprecated.</span></span> <span data-ttu-id="5e5ee-198">指向 CLR 调用以执行托管的代码的函数。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-198">Points to a function that the CLR calls to execute managed code.</span></span>  
  
 [<span data-ttu-id="5e5ee-199">FLockClrVersionCallback 函数指针</span><span class="sxs-lookup"><span data-stu-id="5e5ee-199">FLockClrVersionCallback Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)  
 <span data-ttu-id="5e5ee-200">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-200">Deprecated.</span></span> <span data-ttu-id="5e5ee-201">指向 CLR 调用用于通知宿主的函数初始化已开始或完成。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-201">Points to a function that the CLR calls to notify the host that initialization has either started or completed.</span></span>  
  
 [<span data-ttu-id="5e5ee-202">GetCLRIdentityManager 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-202">GetCLRIdentityManager Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getclridentitymanager-function.md)  
 <span data-ttu-id="5e5ee-203">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-203">Deprecated.</span></span> <span data-ttu-id="5e5ee-204">获取一个指针指向使 CLR 管理标识的接口。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-204">Gets a pointer to an interface that allows the CLR to manage identities.</span></span>  
  
 [<span data-ttu-id="5e5ee-205">LoadLibraryShim 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-205">LoadLibraryShim Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)  
 <span data-ttu-id="5e5ee-206">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-206">Deprecated.</span></span> <span data-ttu-id="5e5ee-207">加载.NET Framework DLL 的指定的版本。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-207">Loads a specified version of a .NET Framework DLL.</span></span>  
  
 [<span data-ttu-id="5e5ee-208">LoadStringRC 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-208">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 <span data-ttu-id="5e5ee-209">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-209">Deprecated.</span></span> <span data-ttu-id="5e5ee-210">将 HRESULT 值转换为一条错误消息中，通过使用当前线程的默认区域性。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-210">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 [<span data-ttu-id="5e5ee-211">LoadStringRCEx 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-211">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
 <span data-ttu-id="5e5ee-212">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-212">Deprecated.</span></span> <span data-ttu-id="5e5ee-213">将转换为相应的错误消息为指定的区域性的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-213">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 [<span data-ttu-id="5e5ee-214">LPOVERLAPPED_COMPLETION_ROUTINE 函数指针</span><span class="sxs-lookup"><span data-stu-id="5e5ee-214">LPOVERLAPPED_COMPLETION_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpoverlapped-completion-routine-function-pointer.md)  
 <span data-ttu-id="5e5ee-215">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-215">Deprecated.</span></span> <span data-ttu-id="5e5ee-216">指向通知时的重叠的宿主的函数 (即异步) 对设备 i/o 操作已完成。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-216">Points to a function that notifies the host when an overlapped (that is, asynchronous) I/O to a device has completed.</span></span>  
  
 [<span data-ttu-id="5e5ee-217">LPTHREAD_START_ROUTINE 函数指针</span><span class="sxs-lookup"><span data-stu-id="5e5ee-217">LPTHREAD_START_ROUTINE Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/lpthread-start-routine-function-pointer.md)  
 <span data-ttu-id="5e5ee-218">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-218">Deprecated.</span></span> <span data-ttu-id="5e5ee-219">指向通知线程已开始执行的主机的函数。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-219">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 [<span data-ttu-id="5e5ee-220">RunDll32ShimW 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-220">RunDll32ShimW Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/rundll32shimw-function.md)  
 <span data-ttu-id="5e5ee-221">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-221">Deprecated.</span></span> <span data-ttu-id="5e5ee-222">执行指定的命令。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-222">Executes the specified command.</span></span>  
  
 [<span data-ttu-id="5e5ee-223">WAITORTIMERCALLBACK 函数指针</span><span class="sxs-lookup"><span data-stu-id="5e5ee-223">WAITORTIMERCALLBACK Function Pointer</span></span>](../../../../docs/framework/unmanaged-api/hosting/waitortimercallback-function-pointer.md)  
 <span data-ttu-id="5e5ee-224">已否决。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-224">Deprecated.</span></span> <span data-ttu-id="5e5ee-225">指向以通知主机，等待句柄已发出信号或超时的函数。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-225">Points to a function that notifies the host that a wait handle has either been signaled or timed out.</span></span>  
  
## <a name="infrastructure-functions"></a><span data-ttu-id="5e5ee-226">基础结构函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-226">Infrastructure functions</span></span>  
 <span data-ttu-id="5e5ee-227">本部分中的函数可由.NET Framework 仅使用。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-227">The functions in this section are for use by the .NET Framework only.</span></span>  
  
 [<span data-ttu-id="5e5ee-228">_CorDllMain 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-228">_CorDllMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)  
 <span data-ttu-id="5e5ee-229">初始化 CLR、 查找托管的入口点 DLL 程序集的 CLR 头中，并开始执行。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-229">Initializes the CLR, locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="5e5ee-230">_CorExeMain 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-230">_CorExeMain Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)  
 <span data-ttu-id="5e5ee-231">初始化 CLR，查找可执行程序集的 CLR 标头中的托管的入口点并开始执行。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-231">Initializes the CLR, locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
 [<span data-ttu-id="5e5ee-232">_CorExeMain2 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-232">_CorExeMain2 Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corexemain2-function.md)  
 <span data-ttu-id="5e5ee-233">在指定的内存映射代码中执行的入口点。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-233">Executes the entry point in the specified memory-mapped code.</span></span> <span data-ttu-id="5e5ee-234">操作系统加载程序通过调用此函数。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-234">This function is called by the operating system loader.</span></span>  
  
 [<span data-ttu-id="5e5ee-235">_CorImageUnloading 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-235">_CorImageUnloading Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)  
 <span data-ttu-id="5e5ee-236">卸载托管的模块映像时通知加载程序。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-236">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 [<span data-ttu-id="5e5ee-237">_CorValidateImage 函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-237">_CorValidateImage Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md)  
 <span data-ttu-id="5e5ee-238">验证托管的模块映像，并通知操作系统加载程序后将其加载。</span><span class="sxs-lookup"><span data-stu-id="5e5ee-238">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e5ee-239">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e5ee-239">See Also</span></span>  
 [<span data-ttu-id="5e5ee-240">.NET framework 4 承载全局静态函数</span><span class="sxs-lookup"><span data-stu-id="5e5ee-240">.NET Framework 4 Hosting Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/net-framework-4-hosting-global-static-functions.md) 
