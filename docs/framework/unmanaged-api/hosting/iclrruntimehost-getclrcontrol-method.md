---
title: ICLRRuntimeHost::GetCLRControl 方法
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type:
- apiref
ms.openlocfilehash: 478e07f18d40043de4e800c36647ac4a32499635
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120433"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="c9367-102">ICLRRuntimeHost::GetCLRControl 方法</span><span class="sxs-lookup"><span data-stu-id="c9367-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="c9367-103">获取[ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)类型的接口指针，宿主可使用该接口自定义公共语言运行时（CLR）的各个方面。</span><span class="sxs-lookup"><span data-stu-id="c9367-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9367-104">语法</span><span class="sxs-lookup"><span data-stu-id="c9367-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9367-105">参数</span><span class="sxs-lookup"><span data-stu-id="c9367-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="c9367-106">弄类型为[ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)的接口指针，该接口允许主机配置 CLR 的其他方面。</span><span class="sxs-lookup"><span data-stu-id="c9367-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9367-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c9367-107">Return Value</span></span>  
  
|<span data-ttu-id="c9367-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9367-108">HRESULT</span></span>|<span data-ttu-id="c9367-109">描述</span><span class="sxs-lookup"><span data-stu-id="c9367-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9367-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9367-110">S_OK</span></span>|<span data-ttu-id="c9367-111">`GetCLRControl` 成功返回。</span><span class="sxs-lookup"><span data-stu-id="c9367-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="c9367-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c9367-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c9367-113">CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="c9367-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c9367-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c9367-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c9367-115">调用超时。</span><span class="sxs-lookup"><span data-stu-id="c9367-115">The call timed out.</span></span>|  
|<span data-ttu-id="c9367-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c9367-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c9367-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="c9367-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c9367-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c9367-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c9367-119">已阻止的线程或纤程正在等待某个事件时，该事件被取消。</span><span class="sxs-lookup"><span data-stu-id="c9367-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c9367-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c9367-120">E_FAIL</span></span>|<span data-ttu-id="c9367-121">发生未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="c9367-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c9367-122">如果某个方法返回 E_FAIL，则 CLR 在该进程内将不再可用。</span><span class="sxs-lookup"><span data-stu-id="c9367-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c9367-123">对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="c9367-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c9367-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="c9367-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="c9367-125">CLR 已经开始。</span><span class="sxs-lookup"><span data-stu-id="c9367-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9367-126">备注</span><span class="sxs-lookup"><span data-stu-id="c9367-126">Remarks</span></span>  
 <span data-ttu-id="c9367-127">`ICLRControl` 提供[GetCLRManager 方法](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)，该方法使宿主可以获取指向某个管理器类型的接口指针。</span><span class="sxs-lookup"><span data-stu-id="c9367-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9367-128">要求</span><span class="sxs-lookup"><span data-stu-id="c9367-128">Requirements</span></span>  
 <span data-ttu-id="c9367-129">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c9367-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9367-130">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c9367-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9367-131">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c9367-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9367-132">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9367-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9367-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9367-133">See also</span></span>

- [<span data-ttu-id="c9367-134">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="c9367-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="c9367-135">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="c9367-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
