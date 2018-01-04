---
title: "ICLRRuntimeInfo::LoadLibrary 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.LoadLibrary
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b688a4f2557c5ab2ef112e13b411e25ad47b8c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="c1f33-102">ICLRRuntimeInfo::LoadLibrary 方法</span><span class="sxs-lookup"><span data-stu-id="c1f33-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="c1f33-103">从公共语言运行时 (CLR) 由加载的.NET Framework 库[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="c1f33-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="c1f33-104">此方法取代[LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="c1f33-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1f33-105">语法</span><span class="sxs-lookup"><span data-stu-id="c1f33-105">Syntax</span></span>  
  
```  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c1f33-106">参数</span><span class="sxs-lookup"><span data-stu-id="c1f33-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="c1f33-107">[in]要加载的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="c1f33-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="c1f33-108">[out]加载的程序集句柄。</span><span class="sxs-lookup"><span data-stu-id="c1f33-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1f33-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c1f33-109">Return Value</span></span>  
 <span data-ttu-id="c1f33-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="c1f33-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c1f33-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c1f33-111">HRESULT</span></span>|<span data-ttu-id="c1f33-112">描述</span><span class="sxs-lookup"><span data-stu-id="c1f33-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c1f33-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c1f33-113">S_OK</span></span>|<span data-ttu-id="c1f33-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="c1f33-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="c1f33-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c1f33-115">E_POINTER</span></span>|<span data-ttu-id="c1f33-116">`pwzDllName` 或 `phndModule` 为 null。</span><span class="sxs-lookup"><span data-stu-id="c1f33-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="c1f33-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c1f33-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c1f33-118">没有足够的内存可用于处理该请求。</span><span class="sxs-lookup"><span data-stu-id="c1f33-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1f33-119">备注</span><span class="sxs-lookup"><span data-stu-id="c1f33-119">Remarks</span></span>  
 <span data-ttu-id="c1f33-120">此方法仅加载 Dll 包括在.NET Framework 可再发行组件包。</span><span class="sxs-lookup"><span data-stu-id="c1f33-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="c1f33-121">它无法加载用户生成的程序集。</span><span class="sxs-lookup"><span data-stu-id="c1f33-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1f33-122">惠?</span><span class="sxs-lookup"><span data-stu-id="c1f33-122">Requirements</span></span>  
 <span data-ttu-id="c1f33-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c1f33-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1f33-124">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c1f33-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c1f33-125">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c1f33-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1f33-126">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1f33-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1f33-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1f33-127">See Also</span></span>  
 [<span data-ttu-id="c1f33-128">ICLRRuntimeInfo 接口</span><span class="sxs-lookup"><span data-stu-id="c1f33-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="c1f33-129">承载接口</span><span class="sxs-lookup"><span data-stu-id="c1f33-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="c1f33-130">承载</span><span class="sxs-lookup"><span data-stu-id="c1f33-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
