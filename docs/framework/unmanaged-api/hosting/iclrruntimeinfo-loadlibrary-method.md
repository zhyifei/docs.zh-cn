---
title: ICLRRuntimeInfo::LoadLibrary 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
ms.openlocfilehash: 8c72f58bb65bd862b0625bfa0398b26bad0197e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192083"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="c3641-102">ICLRRuntimeInfo::LoadLibrary 方法</span><span class="sxs-lookup"><span data-stu-id="c3641-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="c3641-103">从[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口表示的公共语言运行时（CLR）加载 .NET Framework 库。</span><span class="sxs-lookup"><span data-stu-id="c3641-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="c3641-104">此方法取代了[LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="c3641-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3641-105">语法</span><span class="sxs-lookup"><span data-stu-id="c3641-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3641-106">参数</span><span class="sxs-lookup"><span data-stu-id="c3641-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="c3641-107">中要加载的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="c3641-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="c3641-108">弄已加载的程序集的句柄。</span><span class="sxs-lookup"><span data-stu-id="c3641-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3641-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c3641-109">Return Value</span></span>  
 <span data-ttu-id="c3641-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="c3641-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c3641-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c3641-111">HRESULT</span></span>|<span data-ttu-id="c3641-112">描述</span><span class="sxs-lookup"><span data-stu-id="c3641-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c3641-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3641-113">S_OK</span></span>|<span data-ttu-id="c3641-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="c3641-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="c3641-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c3641-115">E_POINTER</span></span>|<span data-ttu-id="c3641-116">`pwzDllName` 或 `phndModule` 为 null。</span><span class="sxs-lookup"><span data-stu-id="c3641-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="c3641-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c3641-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c3641-118">没有足够的内存可用来处理请求。</span><span class="sxs-lookup"><span data-stu-id="c3641-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c3641-119">备注</span><span class="sxs-lookup"><span data-stu-id="c3641-119">Remarks</span></span>  
 <span data-ttu-id="c3641-120">此方法仅加载 .NET Framework 可再发行组件包中包含的 Dll。</span><span class="sxs-lookup"><span data-stu-id="c3641-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="c3641-121">它无法加载用户生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="c3641-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3641-122">要求</span><span class="sxs-lookup"><span data-stu-id="c3641-122">Requirements</span></span>  
 <span data-ttu-id="c3641-123">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c3641-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3641-124">**标头：** MetaHost</span><span class="sxs-lookup"><span data-stu-id="c3641-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c3641-125">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c3641-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3641-126">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3641-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3641-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3641-127">See also</span></span>

- [<span data-ttu-id="c3641-128">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="c3641-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="c3641-129">承载接口</span><span class="sxs-lookup"><span data-stu-id="c3641-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="c3641-130">承载</span><span class="sxs-lookup"><span data-stu-id="c3641-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
