---
title: ICLRReferenceAssemblyEnum::Get 方法
ms.date: 03/30/2017
api_name:
- ICLRReferenceAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRReferenceAssemblyEnum::Get
helpviewer_keywords:
- ICLRReferenceAssemblyEnum::Get method [.NET Framework hosting]
- Get method, ICLRReferenceAssemblyEnum interface [.NET Framework hosting]
ms.assetid: f21c1612-9c5d-4abc-a337-577086d29c17
topic_type:
- apiref
ms.openlocfilehash: 8f479443e168c3fc7c627c3227e59f1e8b54f0e0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120507"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="d614d-102">ICLRReferenceAssemblyEnum::Get 方法</span><span class="sxs-lookup"><span data-stu-id="d614d-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="d614d-103">获取所提供索引处的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="d614d-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d614d-104">语法</span><span class="sxs-lookup"><span data-stu-id="d614d-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d614d-105">参数</span><span class="sxs-lookup"><span data-stu-id="d614d-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="d614d-106">中要返回的程序集标识的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="d614d-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="d614d-107">弄包含程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="d614d-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="d614d-108">[in，out]`pwzBuffer` 缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="d614d-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d614d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="d614d-109">Return Value</span></span>  
  
|<span data-ttu-id="d614d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d614d-110">HRESULT</span></span>|<span data-ttu-id="d614d-111">描述</span><span class="sxs-lookup"><span data-stu-id="d614d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d614d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d614d-112">S_OK</span></span>|<span data-ttu-id="d614d-113">`Get` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="d614d-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="d614d-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d614d-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="d614d-115">`pwzBuffer` 太小。</span><span class="sxs-lookup"><span data-stu-id="d614d-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="d614d-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="d614d-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="d614d-117">枚举中没有更多的项。</span><span class="sxs-lookup"><span data-stu-id="d614d-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="d614d-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d614d-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d614d-119">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="d614d-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d614d-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d614d-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d614d-121">调用超时。</span><span class="sxs-lookup"><span data-stu-id="d614d-121">The call timed out.</span></span>|  
|<span data-ttu-id="d614d-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d614d-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d614d-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="d614d-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d614d-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d614d-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d614d-125">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="d614d-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d614d-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d614d-126">E_FAIL</span></span>|<span data-ttu-id="d614d-127">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="d614d-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d614d-128">如果某个方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="d614d-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d614d-129">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="d614d-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d614d-130">备注</span><span class="sxs-lookup"><span data-stu-id="d614d-130">Remarks</span></span>  
 <span data-ttu-id="d614d-131">`Get` 通常称为两次。</span><span class="sxs-lookup"><span data-stu-id="d614d-131">`Get` is typically called twice.</span></span> <span data-ttu-id="d614d-132">第一次调用为 `pwzBuffer`提供 null 值，并将 `pcchBufferSize` 设置为适用于 `pwzBuffer`的大小。</span><span class="sxs-lookup"><span data-stu-id="d614d-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="d614d-133">第二个调用提供适当大小的 `pwzBuffer`，并在完成时包含规范程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="d614d-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d614d-134">要求</span><span class="sxs-lookup"><span data-stu-id="d614d-134">Requirements</span></span>  
 <span data-ttu-id="d614d-135">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d614d-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d614d-136">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="d614d-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d614d-137">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="d614d-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d614d-138">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d614d-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d614d-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="d614d-139">See also</span></span>

- [<span data-ttu-id="d614d-140">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="d614d-140">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="d614d-141">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="d614d-141">ICLRReferenceAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrreferenceassemblyenum-interface.md)
