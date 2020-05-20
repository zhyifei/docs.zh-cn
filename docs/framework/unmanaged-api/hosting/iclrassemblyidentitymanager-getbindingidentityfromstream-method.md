---
title: ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 方法
ms.date: 03/30/2017
api_name:
- ICLRAssemblyIdentityManager.GetBindingIdentityFromStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream
helpviewer_keywords:
- GetBindingIdentityFromStream method [.NET Framework hosting]
- ICLRAssemblyIdentityManager::GetBindingIdentityFromStream method [.NET Framework hosting]
ms.assetid: 40123b30-a589-46b3-95d3-af7b2b0baa05
topic_type:
- apiref
ms.openlocfilehash: abba19600616cad8ba3377ae2ebb23459449d2a0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615977"
---
# <a name="iclrassemblyidentitymanagergetbindingidentityfromstream-method"></a><span data-ttu-id="61069-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream 方法</span><span class="sxs-lookup"><span data-stu-id="61069-102">ICLRAssemblyIdentityManager::GetBindingIdentityFromStream Method</span></span>
<span data-ttu-id="61069-103">获取指定流中的程序集的规范程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="61069-103">Gets the canonical assembly identity data for the assembly in the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61069-104">语法</span><span class="sxs-lookup"><span data-stu-id="61069-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBindingIdentityFromStream (  
    [in] IStream    *pStream,  
    [in] DWORD       dwFlags,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61069-105">参数</span><span class="sxs-lookup"><span data-stu-id="61069-105">Parameters</span></span>  
 `pStream`  
 <span data-ttu-id="61069-106">中要计算的程序集流。</span><span class="sxs-lookup"><span data-stu-id="61069-106">[in] The assembly stream to be evaluated.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="61069-107">中提供用于将来的扩展性。</span><span class="sxs-lookup"><span data-stu-id="61069-107">[in] Provided for future extensibility.</span></span> <span data-ttu-id="61069-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT 是当前版本的公共语言运行时（CLR）支持的唯一值。</span><span class="sxs-lookup"><span data-stu-id="61069-108">CLR_ASSEMBLY_IDENTITY_FLAGS_DEFAULT is the only value that the current version of the common language runtime (CLR) supports.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="61069-109">弄包含不透明程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="61069-109">[out] A buffer containing the opaque assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="61069-110">[in，out]的大小 `pwzBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="61069-110">[in, out] The size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61069-111">返回值</span><span class="sxs-lookup"><span data-stu-id="61069-111">Return Value</span></span>  
  
|<span data-ttu-id="61069-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="61069-112">HRESULT</span></span>|<span data-ttu-id="61069-113">说明</span><span class="sxs-lookup"><span data-stu-id="61069-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="61069-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="61069-114">S_OK</span></span>|<span data-ttu-id="61069-115">该方法已成功返回。</span><span class="sxs-lookup"><span data-stu-id="61069-115">The method returned successfully.</span></span>|  
|<span data-ttu-id="61069-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="61069-116">E_INVALIDARG</span></span>|<span data-ttu-id="61069-117">提供的 `pStream` 为 null。</span><span class="sxs-lookup"><span data-stu-id="61069-117">The supplied `pStream` is null.</span></span>|  
|<span data-ttu-id="61069-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="61069-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="61069-119">的大小 `pwzBuffer` 太小。</span><span class="sxs-lookup"><span data-stu-id="61069-119">The size of `pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="61069-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="61069-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="61069-121">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="61069-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="61069-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="61069-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="61069-123">调用超时。</span><span class="sxs-lookup"><span data-stu-id="61069-123">The call timed out.</span></span>|  
|<span data-ttu-id="61069-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="61069-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="61069-125">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="61069-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="61069-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="61069-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="61069-127">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="61069-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="61069-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="61069-128">E_FAIL</span></span>|<span data-ttu-id="61069-129">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="61069-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="61069-130">如果方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="61069-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="61069-131">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="61069-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61069-132">要求</span><span class="sxs-lookup"><span data-stu-id="61069-132">Requirements</span></span>  
 <span data-ttu-id="61069-133">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61069-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61069-134">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="61069-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61069-135">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="61069-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61069-136">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61069-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61069-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61069-137">See also</span></span>

- [<span data-ttu-id="61069-138">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="61069-138">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="61069-139">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="61069-139">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
