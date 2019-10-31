---
title: ICLRProbingAssemblyEnum::Get 方法
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum.Get
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum::Get
helpviewer_keywords:
- Get method, ICLRProbingAssemblyEnum interface [.NET Framework hosting]
- ICLRProbingAssemblyEnum::Get method [.NET Framework hosting]
ms.assetid: fdb67a77-782f-44cf-a8a1-b75999b0f3c8
topic_type:
- apiref
ms.openlocfilehash: 2ff1f9428a92d091a51a4cca12d69d98da0ecba2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120535"
---
# <a name="iclrprobingassemblyenumget-method"></a><span data-ttu-id="2a9cb-102">ICLRProbingAssemblyEnum::Get 方法</span><span class="sxs-lookup"><span data-stu-id="2a9cb-102">ICLRProbingAssemblyEnum::Get Method</span></span>
<span data-ttu-id="2a9cb-103">获取指定索引处的程序集标识。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-103">Gets the assembly identity at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a9cb-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a9cb-104">Syntax</span></span>  
  
```cpp  
HRESULT Get (  
    [in] DWORD dwIndex,  
    [out, size_is(*pcchBufferSize)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a9cb-105">参数</span><span class="sxs-lookup"><span data-stu-id="2a9cb-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="2a9cb-106">中要返回的程序集标识的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-106">[in] The zero-based index of the assembly identity to return.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="2a9cb-107">弄包含程序集标识数据的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-107">[out] A buffer containing the assembly identity data.</span></span>  
  
 `pcchBufferSize`  
 <span data-ttu-id="2a9cb-108">[in，out]`pwzBuffer` 缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-108">[in, out] The size of the `pwzBuffer` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a9cb-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2a9cb-109">Return Value</span></span>  
  
|<span data-ttu-id="2a9cb-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a9cb-110">HRESULT</span></span>|<span data-ttu-id="2a9cb-111">描述</span><span class="sxs-lookup"><span data-stu-id="2a9cb-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a9cb-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a9cb-112">S_OK</span></span>|<span data-ttu-id="2a9cb-113">`Get` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-113">`Get` returned successfully.</span></span>|  
|<span data-ttu-id="2a9cb-114">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="2a9cb-114">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="2a9cb-115">`pwzBuffer` 太小。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-115">`pwzBuffer` is too small.</span></span>|  
|<span data-ttu-id="2a9cb-116">ERROR_NO_MORE_ITEMS</span><span class="sxs-lookup"><span data-stu-id="2a9cb-116">ERROR_NO_MORE_ITEMS</span></span>|<span data-ttu-id="2a9cb-117">枚举中没有更多的项。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-117">The enumeration contains no more items.</span></span>|  
|<span data-ttu-id="2a9cb-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2a9cb-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2a9cb-119">公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-119">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2a9cb-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2a9cb-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2a9cb-121">调用超时。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-121">The call timed out.</span></span>|  
|<span data-ttu-id="2a9cb-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2a9cb-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2a9cb-123">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2a9cb-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2a9cb-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2a9cb-125">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2a9cb-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2a9cb-126">E_FAIL</span></span>|<span data-ttu-id="2a9cb-127">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2a9cb-128">如果某个方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-128">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2a9cb-129">对任何宿主方法的后续调用都将返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-129">Subsequent calls to any hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a9cb-130">备注</span><span class="sxs-lookup"><span data-stu-id="2a9cb-130">Remarks</span></span>  
 <span data-ttu-id="2a9cb-131">索引0处的标识是特定于处理器体系结构的标识。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-131">The identity at index 0 is the identity specific to the processor architecture.</span></span> <span data-ttu-id="2a9cb-132">位于索引1处的标识是适用于 Microsoft 中间语言（MSIL）的体系结构非特定程序集。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-132">The identity at index 1 is the architecture-neutral assembly for Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="2a9cb-133">索引2处的标识不包含体系结构信息。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-133">The identity at index 2 contains no architecture information.</span></span>  
  
 <span data-ttu-id="2a9cb-134">`Get` 通常称为两次。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-134">`Get` is typically called twice.</span></span> <span data-ttu-id="2a9cb-135">第一次调用为 `pwzBuffer`提供 null 值，并将 `pcchBufferSize` 设置为适用于 `pwzBuffer`的大小。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-135">The first call supplies a null value for `pwzBuffer`, and sets `pcchBufferSize` to the size appropriate for `pwzBuffer`.</span></span> <span data-ttu-id="2a9cb-136">第二个调用提供适当大小的 `pwzBuffer`，并在完成时包含规范程序集标识数据。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-136">The second call supplies an appropriately sized `pwzBuffer`, and contains the canonical assembly identity data upon completion.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a9cb-137">要求</span><span class="sxs-lookup"><span data-stu-id="2a9cb-137">Requirements</span></span>  
 <span data-ttu-id="2a9cb-138">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2a9cb-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a9cb-139">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2a9cb-139">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a9cb-140">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="2a9cb-140">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a9cb-141">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a9cb-141">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a9cb-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a9cb-142">See also</span></span>

- [<span data-ttu-id="2a9cb-143">ICLRProbingAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="2a9cb-143">ICLRProbingAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-interface.md)
- [<span data-ttu-id="2a9cb-144">ICLRAssemblyIdentityManager 接口</span><span class="sxs-lookup"><span data-stu-id="2a9cb-144">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
