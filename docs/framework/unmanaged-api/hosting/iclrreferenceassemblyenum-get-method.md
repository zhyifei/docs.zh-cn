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
ms.openlocfilehash: 5afa7b37b804b6a11a894e0e6c7708c7787a20ae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703362"
---
# <a name="iclrreferenceassemblyenumget-method"></a><span data-ttu-id="0e3fc-102">ICLRReferenceAssemblyEnum::Get 方法</span><span class="sxs-lookup"><span data-stu-id="0e3fc-102">ICLRReferenceAssemblyEnum::Get Method</span></span>
<span data-ttu-id="0e3fc-103">获取所提供索引处的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-103">Gets the assembly identity at the supplied index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e3fc-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e3fc-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e3fc-105">参数</span><span class="sxs-lookup"><span data-stu-id="0e3fc-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="0e3fc-106">中要返回的程序集标识的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="0e3fc-107">弄包含程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="0e3fc-108">[in，out]缓冲区的大小 `pwzBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e3fc-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0e3fc-109">Return Value</span></span>  
  
|<span data-ttu-id="0e3fc-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e3fc-110">HRESULT</span></span>|<span data-ttu-id="0e3fc-111">说明</span><span class="sxs-lookup"><span data-stu-id="0e3fc-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0e3fc-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="0e3fc-112">S_OK</span></span>|<span data-ttu-id="0e3fc-113">`Get`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="0e3fc-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="0e3fc-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="0e3fc-115">`pwzBuffer` 太小。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="0e3fc-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="0e3fc-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="0e3fc-117">枚举中没有更多的项。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="0e3fc-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0e3fc-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0e3fc-119">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0e3fc-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0e3fc-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0e3fc-121">调用超时。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-121">The call timed out.</span></span>|  
|<span data-ttu-id="0e3fc-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0e3fc-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0e3fc-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0e3fc-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0e3fc-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0e3fc-125">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0e3fc-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0e3fc-126">E_FAIL</span></span>|<span data-ttu-id="0e3fc-127">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0e3fc-128">如果方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0e3fc-129">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e3fc-130">备注</span><span class="sxs-lookup"><span data-stu-id="0e3fc-130">Remarks</span></span>  
 <span data-ttu-id="0e3fc-131">`Get`通常称为两次。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-131">`Get` is typically called twice.</span></span> <span data-ttu-id="0e3fc-132">第一次调用为提供 null 值 `pwzBuffer` ，并将设置 `pcchBufferSize` 为适合的大小 `pwzBuffer` 。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-132">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="0e3fc-133">第二个调用提供适当大小的 `pwzBuffer` ，并在完成时包含规范程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-133">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e3fc-134">要求</span><span class="sxs-lookup"><span data-stu-id="0e3fc-134">Requirements</span></span>  
 <span data-ttu-id="0e3fc-135">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0e3fc-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e3fc-136">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="0e3fc-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0e3fc-137">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="0e3fc-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0e3fc-138">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e3fc-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e3fc-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e3fc-139">See also</span></span>

- [<span data-ttu-id="0e3fc-140">ICLRAssemblyReferenceList 接口</span><span class="sxs-lookup"><span data-stu-id="0e3fc-140">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="0e3fc-141">ICLRReferenceAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="0e3fc-141">ICLRReferenceAssemblyEnum Interface</span></span>](iclrreferenceassemblyenum-interface.md)
