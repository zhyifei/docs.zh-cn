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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 878d68dd690a8764ef26f5f180fabd6c22841a25
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466826"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="c55df-102">ICLRRuntimeInfo::LoadLibrary 方法</span><span class="sxs-lookup"><span data-stu-id="c55df-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="c55df-103">从公共语言运行时 (CLR) 表示加载的.NET Framework 库[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="c55df-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="c55df-104">此方法取代[LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="c55df-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c55df-105">语法</span><span class="sxs-lookup"><span data-stu-id="c55df-105">Syntax</span></span>  
  
```  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c55df-106">参数</span><span class="sxs-lookup"><span data-stu-id="c55df-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="c55df-107">[in]要加载的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="c55df-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="c55df-108">[out]句柄加载的程序集。</span><span class="sxs-lookup"><span data-stu-id="c55df-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c55df-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c55df-109">Return Value</span></span>  
 <span data-ttu-id="c55df-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="c55df-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c55df-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c55df-111">HRESULT</span></span>|<span data-ttu-id="c55df-112">描述</span><span class="sxs-lookup"><span data-stu-id="c55df-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c55df-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c55df-113">S_OK</span></span>|<span data-ttu-id="c55df-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="c55df-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="c55df-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c55df-115">E_POINTER</span></span>|<span data-ttu-id="c55df-116">`pwzDllName` 或`phndModule`为 null。</span><span class="sxs-lookup"><span data-stu-id="c55df-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="c55df-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c55df-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c55df-118">没有足够的内存是可用来处理该请求。</span><span class="sxs-lookup"><span data-stu-id="c55df-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c55df-119">备注</span><span class="sxs-lookup"><span data-stu-id="c55df-119">Remarks</span></span>  
 <span data-ttu-id="c55df-120">此方法仅加载 Dll 包含在.NET Framework 可再发行组件包。</span><span class="sxs-lookup"><span data-stu-id="c55df-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="c55df-121">它可以加载用户生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="c55df-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c55df-122">要求</span><span class="sxs-lookup"><span data-stu-id="c55df-122">Requirements</span></span>  
 <span data-ttu-id="c55df-123">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c55df-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c55df-124">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c55df-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c55df-125">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c55df-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c55df-126">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c55df-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c55df-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="c55df-127">See also</span></span>
- [<span data-ttu-id="c55df-128">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="c55df-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="c55df-129">承载接口</span><span class="sxs-lookup"><span data-stu-id="c55df-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="c55df-130">承载</span><span class="sxs-lookup"><span data-stu-id="c55df-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
