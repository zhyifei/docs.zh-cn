---
title: ICLRMetaHost 接口
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
ms.openlocfilehash: 391adc6f9fe55ad7ca527ea416956ab013a27b15
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703726"
---
# <a name="iclrmetahost-interface"></a><span data-ttu-id="e4890-102">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="e4890-102">ICLRMetaHost Interface</span></span>
<span data-ttu-id="e4890-103">提供一些方法，这些方法基于公共语言运行时（CLR）的版本号返回特定版本的公共语言运行时（CLR），列出所有已安装的 Clr，列出在指定进程中加载的所有运行时，发现编译程序集所用的 CLR 版本，退出使用干净运行时关闭的进程，以及查询旧 API 绑定。</span><span class="sxs-lookup"><span data-stu-id="e4890-103">Provides methods that return a specific version of the common language runtime (CLR) based on its version number, list all installed CLRs, list all runtimes that are loaded in a specified process, discover the CLR version used to compile an assembly, exit a process with a clean runtime shutdown, and query legacy API binding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e4890-104">方法</span><span class="sxs-lookup"><span data-stu-id="e4890-104">Methods</span></span>  
  
|<span data-ttu-id="e4890-105">方法</span><span class="sxs-lookup"><span data-stu-id="e4890-105">Method</span></span>|<span data-ttu-id="e4890-106">说明</span><span class="sxs-lookup"><span data-stu-id="e4890-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e4890-107">EnumerateInstalledRuntimes 方法</span><span class="sxs-lookup"><span data-stu-id="e4890-107">EnumerateInstalledRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateinstalledruntimes-method.md)|<span data-ttu-id="e4890-108">返回一个枚举，该枚举包含计算机上安装的每个 CLR 版本的有效[ICLRRuntimeInfo](iclrruntimeinfo-interface.md)接口指针。</span><span class="sxs-lookup"><span data-stu-id="e4890-108">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each CLR version that is installed on a computer.</span></span>|  
|[<span data-ttu-id="e4890-109">EnumerateLoadedRuntimes 方法</span><span class="sxs-lookup"><span data-stu-id="e4890-109">EnumerateLoadedRuntimes Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-enumerateloadedruntimes-method.md)|<span data-ttu-id="e4890-110">返回一个枚举，该枚举包含给定进程中加载的每个 CLR 的有效[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口指针。</span><span class="sxs-lookup"><span data-stu-id="e4890-110">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each CLR that is loaded in a given process.</span></span> <span data-ttu-id="e4890-111">此方法取代了[GetVersionFromProcess](getversionfromprocess-function.md)。</span><span class="sxs-lookup"><span data-stu-id="e4890-111">This method supersedes [GetVersionFromProcess](getversionfromprocess-function.md).</span></span>|  
|[<span data-ttu-id="e4890-112">ExitProcess 方法</span><span class="sxs-lookup"><span data-stu-id="e4890-112">ExitProcess Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-exitprocess-method.md)|<span data-ttu-id="e4890-113">尝试正常关闭所有加载的运行时，然后终止进程。</span><span class="sxs-lookup"><span data-stu-id="e4890-113">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="e4890-114">取代[CorExitProcess](corexitprocess-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="e4890-114">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>|  
|[<span data-ttu-id="e4890-115">GetRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="e4890-115">GetRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md)|<span data-ttu-id="e4890-116">获取与特定 CLR 版本相对应的[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="e4890-116">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular CLR version.</span></span> <span data-ttu-id="e4890-117">此方法取代了与[STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md)标志一起使用的[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="e4890-117">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) flag.</span></span>|  
|[<span data-ttu-id="e4890-118">GetVersionFromFile 方法</span><span class="sxs-lookup"><span data-stu-id="e4890-118">GetVersionFromFile Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getversionfromfile-method.md)|<span data-ttu-id="e4890-119">在给定程序集的文件路径的情况下，获取程序集的原始 .NET Framework 编译版本（存储在元数据中）。</span><span class="sxs-lookup"><span data-stu-id="e4890-119">Gets the assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="e4890-120">此方法取代了[GetFileVersion](getfileversion-function.md)。</span><span class="sxs-lookup"><span data-stu-id="e4890-120">This method supersedes [GetFileVersion](getfileversion-function.md).</span></span>|  
|[<span data-ttu-id="e4890-121">QueryLegacyV2RuntimeBinding 方法</span><span class="sxs-lookup"><span data-stu-id="e4890-121">QueryLegacyV2RuntimeBinding Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-querylegacyv2runtimebinding-method.md)|<span data-ttu-id="e4890-122">返回一个接口，该接口表示已绑定旧激活策略的运行时，例如，通过使用 `useLegacyV2RuntimeActivationPolicy` [ \< 启动> 元素](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)配置文件项上的特性，直接使用旧的激活 Api 或通过调用[ICLRRuntimeInfo：： BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e4890-122">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>|  
|[<span data-ttu-id="e4890-123">RequestRuntimeLoadedNotification 方法</span><span class="sxs-lookup"><span data-stu-id="e4890-123">RequestRuntimeLoadedNotification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-requestruntimeloadednotification-method.md)|<span data-ttu-id="e4890-124">当首次加载 CLR 版本但尚未启动时，保证对指定函数指针的回调。</span><span class="sxs-lookup"><span data-stu-id="e4890-124">Guarantees a callback to the specified function pointer when a CLR version is first loaded, but not yet started.</span></span> <span data-ttu-id="e4890-125">此方法取代[LockClrVersion](lockclrversion-function.md)</span><span class="sxs-lookup"><span data-stu-id="e4890-125">This method supersedes [LockClrVersion](lockclrversion-function.md)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4890-126">备注</span><span class="sxs-lookup"><span data-stu-id="e4890-126">Remarks</span></span>  
 <span data-ttu-id="e4890-127">获取此接口实例的唯一方法是调用[CLRCreateInstance](clrcreateinstance-function.md)函数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e4890-127">The only way to get an instance of this interface is by calling the [CLRCreateInstance](clrcreateinstance-function.md) function as follows:</span></span>  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e4890-128">要求</span><span class="sxs-lookup"><span data-stu-id="e4890-128">Requirements</span></span>  
 <span data-ttu-id="e4890-129">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4890-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4890-130">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="e4890-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e4890-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="e4890-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4890-132">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4890-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4890-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4890-133">See also</span></span>

- [<span data-ttu-id="e4890-134">承载接口</span><span class="sxs-lookup"><span data-stu-id="e4890-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="e4890-135">承载</span><span class="sxs-lookup"><span data-stu-id="e4890-135">Hosting</span></span>](index.md)
