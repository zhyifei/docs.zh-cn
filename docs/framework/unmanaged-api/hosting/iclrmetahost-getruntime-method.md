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
ms.openlocfilehash: a0d6496e014b767b2bdaf68cdc62017813e1e57f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703633"
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="94160-102">ICLRMetaHost::GetRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="94160-102">ICLRMetaHost::GetRuntime Method</span></span>
<span data-ttu-id="94160-103">获取与特定版本的公共语言运行时（CLR）相对应的[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="94160-103">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="94160-104">此方法取代了与[STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md)标志一起使用的[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="94160-104">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94160-105">语法</span><span class="sxs-lookup"><span data-stu-id="94160-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94160-106">参数</span><span class="sxs-lookup"><span data-stu-id="94160-106">Parameters</span></span>  
 `pwzVersion`  
 <span data-ttu-id="94160-107">中存储在元数据中的 .NET Framework 编译版本，格式为 "v*A*"。*B.*[。*X*] "。</span><span class="sxs-lookup"><span data-stu-id="94160-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="94160-108">*A*、 *B*和*X*是与主版本、次版本和生成号对应的十进制数字。</span><span class="sxs-lookup"><span data-stu-id="94160-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94160-109">此参数必须匹配 .NET Framework 版本的目录名称，因为它显示在 C:\Windows\Microsoft.NET\Framework 或 C:\Windows\Microsoft.NET\Framework64。</span><span class="sxs-lookup"><span data-stu-id="94160-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="94160-110">示例值为 "v1.0.3705"、"v 1.1.4322"、"v 2.0.50727" 和 "v4.0"。*X*"，其中*X*依赖于安装的生成号。</span><span class="sxs-lookup"><span data-stu-id="94160-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="94160-111">"V" 前缀是必需的。</span><span class="sxs-lookup"><span data-stu-id="94160-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="94160-112">中所需接口的标识符。</span><span class="sxs-lookup"><span data-stu-id="94160-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="94160-113">目前，此参数的唯一有效值是 IID_ICLRRuntimeInfo。</span><span class="sxs-lookup"><span data-stu-id="94160-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="94160-114">弄指向[ICLRRuntimeInfo](iclrruntimeinfo-interface.md)接口的指针，该接口对应于所请求的运行时。</span><span class="sxs-lookup"><span data-stu-id="94160-114">[out] A pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94160-115">返回值</span><span class="sxs-lookup"><span data-stu-id="94160-115">Return Value</span></span>  
 <span data-ttu-id="94160-116">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="94160-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="94160-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94160-117">HRESULT</span></span>|<span data-ttu-id="94160-118">说明</span><span class="sxs-lookup"><span data-stu-id="94160-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94160-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="94160-119">S_OK</span></span>|<span data-ttu-id="94160-120">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="94160-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="94160-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="94160-121">E_POINTER</span></span>|<span data-ttu-id="94160-122">`pwzVersion` 或 `ppRuntime` 为 null。</span><span class="sxs-lookup"><span data-stu-id="94160-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94160-123">备注</span><span class="sxs-lookup"><span data-stu-id="94160-123">Remarks</span></span>  
 <span data-ttu-id="94160-124">此方法与旧接口（如[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)接口）和旧功能（如已弃用的函数）一致地进行交互 `CorBindTo*` （请参阅 .NET FRAMEWORK 2.0 托管 API 中[弃用的 CLR 承载函数](deprecated-clr-hosting-functions.md)）。</span><span class="sxs-lookup"><span data-stu-id="94160-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="94160-125">也就是说，用旧版 API 加载的运行时对新 API 可见，而与新 API 一起加载的运行时对旧 API 可见。</span><span class="sxs-lookup"><span data-stu-id="94160-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94160-126">要求</span><span class="sxs-lookup"><span data-stu-id="94160-126">Requirements</span></span>  
 <span data-ttu-id="94160-127">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="94160-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94160-128">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="94160-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="94160-129">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="94160-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94160-130">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94160-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94160-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94160-131">See also</span></span>

- [<span data-ttu-id="94160-132">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="94160-132">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="94160-133">弃用的 CLR 承载接口和 Coclass</span><span class="sxs-lookup"><span data-stu-id="94160-133">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)
- [<span data-ttu-id="94160-134">CLR 承载接口</span><span class="sxs-lookup"><span data-stu-id="94160-134">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="94160-135">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="94160-135">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
- [<span data-ttu-id="94160-136">承载</span><span class="sxs-lookup"><span data-stu-id="94160-136">Hosting</span></span>](index.md)
