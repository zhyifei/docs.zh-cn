---
title: ICLRMetaHost::EnumerateLoadedRuntimes 方法
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db10b5c67a098cc34292a2680bd832f9cef2861b
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48584099"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="70f23-102">ICLRMetaHost::EnumerateLoadedRuntimes 方法</span><span class="sxs-lookup"><span data-stu-id="70f23-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="70f23-103">返回一个枚举，包含一个有效[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)给定进程中加载公共语言运行时 (CLR) 的每个版本的接口指针。</span><span class="sxs-lookup"><span data-stu-id="70f23-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="70f23-104">此方法取代[GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="70f23-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70f23-105">语法</span><span class="sxs-lookup"><span data-stu-id="70f23-105">Syntax</span></span>  
  
```  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="70f23-106">参数</span><span class="sxs-lookup"><span data-stu-id="70f23-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="70f23-107">[in]要加载的运行时检查的进程的句柄。</span><span class="sxs-lookup"><span data-stu-id="70f23-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="70f23-108">[out]<xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>的枚举[ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)接口对应于每个由进程加载的 CLR。</span><span class="sxs-lookup"><span data-stu-id="70f23-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70f23-109">返回值</span><span class="sxs-lookup"><span data-stu-id="70f23-109">Return Value</span></span>  
 <span data-ttu-id="70f23-110">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="70f23-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="70f23-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="70f23-111">HRESULT</span></span>|<span data-ttu-id="70f23-112">描述</span><span class="sxs-lookup"><span data-stu-id="70f23-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="70f23-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="70f23-113">S_OK</span></span>|<span data-ttu-id="70f23-114">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="70f23-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="70f23-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="70f23-115">E_POINTER</span></span>|<span data-ttu-id="70f23-116">`ppEnumerator` 为 null。</span><span class="sxs-lookup"><span data-stu-id="70f23-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="70f23-117">备注</span><span class="sxs-lookup"><span data-stu-id="70f23-117">Remarks</span></span>  
 <span data-ttu-id="70f23-118">此方法是列出所有加载运行时，即使它们已如加载已弃用的函数[CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)。</span><span class="sxs-lookup"><span data-stu-id="70f23-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70f23-119">要求</span><span class="sxs-lookup"><span data-stu-id="70f23-119">Requirements</span></span>  
 <span data-ttu-id="70f23-120">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="70f23-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70f23-121">**标头：** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="70f23-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="70f23-122">**库：** 作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="70f23-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="70f23-123">**.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70f23-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f23-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="70f23-124">See Also</span></span>  
 [<span data-ttu-id="70f23-125">ICLRMetaHost 接口</span><span class="sxs-lookup"><span data-stu-id="70f23-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="70f23-126">承载</span><span class="sxs-lookup"><span data-stu-id="70f23-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
