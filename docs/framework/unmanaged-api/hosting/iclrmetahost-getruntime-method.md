---
title: ICLRMetaHost::GetRuntime 方法
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 55fd6e6eec0c5107398bd0a7dda0281f69eb471b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492512"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="6c971-102">ICLRMetaHost::GetRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="6c971-102">ICLRMetaHost::GetRuntime Method</span></span>
<span data-ttu-id="6c971-103">获取[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)对应于特定版本的公共语言运行时 (CLR) 的接口。</span><span class="sxs-lookup"><span data-stu-id="6c971-103">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="6c971-104">此方法取代[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数与一起使用[STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)标志。</span><span class="sxs-lookup"><span data-stu-id="6c971-104">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c971-105">语法</span><span class="sxs-lookup"><span data-stu-id="6c971-105">Syntax</span></span>  
  
```  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in, REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c971-106">参数</span><span class="sxs-lookup"><span data-stu-id="6c971-106">Parameters</span></span>  
 `pwzVersion`  
 <span data-ttu-id="6c971-107">[in]在格式中的元数据中存储的.NET Framework 编译版本"v*A*。*B*[。*X*]"。</span><span class="sxs-lookup"><span data-stu-id="6c971-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="6c971-108">*一个*， *B*，和*X*是对应于主版本、 次版本和生成号的十进制数字。</span><span class="sxs-lookup"><span data-stu-id="6c971-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c971-109">此参数必须与.NET Framework 版本的目录名称匹配，C:\Windows\Microsoft.NET\Framework 或 C:\Windows\Microsoft.NET\Framework64 下显示。</span><span class="sxs-lookup"><span data-stu-id="6c971-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="6c971-110">示例值为"v1.0.3705"、"v1.1.4322"、"v2.0.50727"和"v4.0。*X*"，其中*X*取决于安装的内部版本号。</span><span class="sxs-lookup"><span data-stu-id="6c971-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="6c971-111">"V"前缀是必需的。</span><span class="sxs-lookup"><span data-stu-id="6c971-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="6c971-112">[in]所需的接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="6c971-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="6c971-113">目前，唯一有效的值为此参数是 IID_ICLRRuntimeInfo。</span><span class="sxs-lookup"><span data-stu-id="6c971-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="6c971-114">[out]一个指向[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)对应于请求的运行时的接口。</span><span class="sxs-lookup"><span data-stu-id="6c971-114">[out] A pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c971-115">返回值</span><span class="sxs-lookup"><span data-stu-id="6c971-115">Return Value</span></span>  
 <span data-ttu-id="6c971-116">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="6c971-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6c971-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c971-117">HRESULT</span></span>|<span data-ttu-id="6c971-118">描述</span><span class="sxs-lookup"><span data-stu-id="6c971-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c971-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c971-119">S_OK</span></span>|<span data-ttu-id="6c971-120">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="6c971-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="6c971-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6c971-121">E_POINTER</span></span>|<span data-ttu-id="6c971-122">`pwzVersion` 或`ppRuntime`为 null。</span><span class="sxs-lookup"><span data-stu-id="6c971-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c971-123">备注</span><span class="sxs-lookup"><span data-stu-id="6c971-123">Remarks</span></span>  
 <span data-ttu-id="6c971-124">此方法始终与交互旧式界面如[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)如不推荐使用的接口和旧版函数`CorBindTo*`函数 (请参阅[不推荐使用 CLR 承载函数](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)托管 API 在.NET Framework 2.0 中)。</span><span class="sxs-lookup"><span data-stu-id="6c971-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="6c971-125">即，使用传统的 API 加载的运行时是可见新的 API，并使用新的 API 加载的运行时对传统的 API 可见。</span><span class="sxs-lookup"><span data-stu-id="6c971-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span> <span data-ttu-id="6c971-126">.</span><span class="sxs-lookup"><span data-stu-id="6c971-126">.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c971-127">要求</span><span class="sxs-lookup"><span data-stu-id="6c971-127">Requirements</span></span>  
 <span data-ttu-id="6c971-128">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6c971-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c971-129">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6c971-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6c971-130">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6c971-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c971-131">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c971-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c971-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c971-132">See also</span></span>
- [<span data-ttu-id="6c971-133">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="6c971-133">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="6c971-134">弃用的 CLR 承接接口和组件类</span><span class="sxs-lookup"><span data-stu-id="6c971-134">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)
- [<span data-ttu-id="6c971-135">CLR Hosting 接口</span><span class="sxs-lookup"><span data-stu-id="6c971-135">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="6c971-136">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="6c971-136">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="6c971-137">承载</span><span class="sxs-lookup"><span data-stu-id="6c971-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
